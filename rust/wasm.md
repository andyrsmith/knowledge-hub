# Wasm - How to build Rust program for web

This guide assumes that it is a program and not just a library

## What to install

Install the toolchain

```
rustup target add wasm32-unknown-unknown
```

Install the Bindgen

```
cargo install wasm-bindgen-cli
```

## Build and Compile

To compile the program for wasm

```
cargo build --target wasm32-unknown-unknown --release
```

To create a javascript link for your program to the web browser

```
wasm-bindgen target\wasm32-unknown-unknown\release\{name-of-wasm-binary} --out-dir .\{name-of-directory} --no-modules --no-typescript
```

## Basic HTML code

Basic HTML file to display the program

```
<html>
  <head>
    <meta content="text/html;charset=utf-8" http-equiv="Content-Type" />
  </head>
  <body>
    <p>Rust WASM Project</p>
    <canvas id="canvas" width="640" height="480"></canvas>
    <script src="./{js-output-file}"></script>
    <script>
      window.addEventListener("load", async () => {
        await wasm_bindgen("{wasm-binary}");
      });
    </script>
  </body>
</html>
```

## Tablet and mobile support

If your program depends on keypresses and would like it to work on a mobile device.  This solution will work by creating buttons on the web page that will send the proper keys to the wasm binary.

### Setup

In cargo.toml add wasm-bindgen as a dependencies

```
wasm-bindgen = "0.2"
```

### Methods to set, clear, and get key

Add this code with the trait wasm_bindgen.  That trait will allow your javascript to access those methods.

```
use wasm_bindgen::prelude::*;


// Store the current key state
static mut CURRENT_KEY: Option<String> = None;

#[wasm_bindgen]
pub fn get_current_key() -> Option<String> {
    unsafe { CURRENT_KEY.clone() }
}

#[wasm_bindgen]
pub fn set_current_key(key: String) {
    unsafe {
        CURRENT_KEY = Some(key);
    }
}

#[wasm_bindgen]
pub fn clear_current_key() {
    unsafe {
        CURRENT_KEY = None;
    }
}
```

In the rust code get the current key and do the action you need to.

```
        if let Some(key) = get_current_key(){
            match key.as_str() {
                "space" => {
                    clear_current_key();
                    if self.player.y >= 25 {
                        self.player.jumping = true; 
                    }

                    },
                _ => {}
            }
        }
```

May need to run the clear_current_key function so action will not keep preforming.

### HTML/Javascript

Create buttons and setup event listener on them to wait for the click and send set the key you need.

```
<html>
  <head>
    <meta content="text/html;charset=utf-8" http-equiv="Content-Type" />
  </head>
  <body>
    <p>Rust Program</p>
    <canvas id="canvas" width="640" height="480"></canvas>
    <button id="start">Start</button>
    <button id="jump">Jump</button>
    <script src="./dinosaur-game.js"></script>
    <script>

      async function run() {
          await wasm_bindgen("./dinosaur-game_bg.wasm").then(() => {
              const {get_current_key, set_current_key, clear_current_key } = wasm_bindgen;

              const startButton = document.getElementById("start");
              startButton.addEventListener('click', () => {
                set_current_key("p");
              });


              const jumpButton = document.getElementById("jump");

              jumpButton.addEventListener('click', () => {
                  set_current_key("space");
              });
          });
      };

      run();
    </script>
  </body>
</html>
```

## Other areas to explore

- wasm-pack
- wasm-bindgen --no-modules




