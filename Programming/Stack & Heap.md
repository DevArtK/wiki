#Stack and Heap

Both the Stack and Heap are parts of memory available to your code at runtime,
but they are structured in different ways.


## Stack

The **Stack** stores values in the order it get them and removes the values in
the opposite order.

- This is referred to as *last in, first out*
    Think of a stack of plates; when you add more plates, you put them on top of
    a pile, and when you need a plate, you take one off the top.

- Adding or removing plates from the middle or bottom wouldn't work as well.

- Adding data is called *pushing* onto the stack.

- Removing data is calling *popping off* the stack.

- All data stored on the stack must have a known, fixed size.

- **Data with an unknown size at compile time or a size that might change must be
  stored on the heap instead**.


## Heap

The heap is less organized; when you put data on the heap, you request a certain
amount of space.

The memory allocator finds and empty spot in the heap that is big enough, marks
it as being in use, and returns a *pointer*, which is the address of that
location.

- This process is called *allocating on the heap* and sometimes abbreviated as
  just *allocating*.

    Pushing values onto the stack is not considered allocating.

- Because the pointer to the heap is a known, fixed size, you can store the
  pointer on the stack, but when you want the actual data, you must follow
  the pointer.

    Think of being seated at a restaurant. When you enter, you state the number
    of people in your group, and the staff finds an empty table that fits
    everyone and leads you there.
    If someone in you group comes late, they can ask where you've been seated to
    find you.


## Heap vs Stack: Space and Time

**Pushing to the stack is faster than allocating on the heap because the
allocator never has to search for a place to store new data**

- That location is always at the top of the stack.

- Comparatively, allocating space on the heap requires more work, because the
  allocator must first find a big enough space to hold the data and then perform
  bookkeeping to prepare for the next allocation.

Accessing data in the heap is slower than accessing data on the stack because
you have to follow a pointer to get there.
- Contemporary processors are faster if they jump around less in memory


## Calling a Function

When your code calls a function, the values passed into the function (including,
potentially, pointers to data on the heap) and the function's local variables
get pushed onto the stack.

When the function is over, those values get popped off the stack
