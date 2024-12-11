# Struct

A struct is a type that you define that contains a group of data together.

## Define a Struct

Struct is define using the keyword struct, and in {} contains the data and type that you would like to go with that struct.

```
struct Person {
    name: String,
    age: int,
}
```

## Methods on Struct

Create methods on structs with the keyword impl

```
impl Person {
    fn new(name:&str, age:int) -> Self {
        Self {
            name: name,
            age: int,
        }
    }

    fn happy_birthday(&self) {
        println!("Happy Birthday {} you are {} years old.", self.name, self.age);
    }
}
```

The first method new is the constructor, which returns the instance created.

Create other methods as you wish.  The &self argument allows you to call self in the method.  You do not have to pass in the instance when you call it.
