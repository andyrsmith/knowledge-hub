# Borrowing

Borrowing is where you pass a pointer of a variable into a function in order for it to be used later.  This is for variables who's size is not determined at compile time to which the data is on the heap

## Types of borrowing 

&var and &mut var.  

&var lets you borrow and read the value. 

&mut lets you borrow and change the value

With mut borrow you are unable to keep it in scope and borrow it again.


component ECS system
