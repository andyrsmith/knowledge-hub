# mod and pub use crate

Dividing the code into different modules will let you split the code into different files.

Any functions, variables, structs will need to have the pub keyword in front of them which will make the public.

## Using mod

When you use mod in main.rs rust looks for a file with that name mod in the current directory.

```
mod map;
```

For mod map rust will look if there is a file called map.rs, which in main than you are allowed to use what is public from that file.

## Pub use crate

Now after adding the mod map you are able to use code from the file map.rs by

```
crate::map::make_map();
```

Note in this example we have to add crate::map:: to any call in that file.  If we add the following then we don't have to add crate::map to any function call.

```
use crate::map::*;
```

Now we can just call the function like this
```
make_map();
```

The * will allow use to use anything that is public in that file, but we can be specific if we like.

## Prelude

To be able to use in multiple file without having to and use crate::map::* to each file just put it in a mod prelude

```
mod prelude {
    pub use crate::map::*;
}
```

Then in any file just use

```
use prelude::*;
```

And anything in the prelude block is accessible.
