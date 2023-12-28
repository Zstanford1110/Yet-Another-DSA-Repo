Let's learn about Arrays, for real this time. This is in a traditional sense, btw.

Surprise: const a = []; is technically not an array. The truth hurts. So, what is it?

# Fundamentals: 
- An array is a FIXED SIZE, CONTIGOUS (unbreaking, connected) memory space that contains a certain number of bytes


# Understanding in a Traditional Sense
To a human, an array makes sense. It's like a list of values stored side-by-side in memory. Very abstracted.
To the computer, an array is a series of bytes. The computer is provided instructions on how to read those bytes
and draw actual values from memory. Generally, it knows the type of the values stored in the array, so that means it
knows the size of each element in the array. To access specific indices, it uses the size and offset from the beginning
of the array to reach our value. It knows where to start and stop reading bytes to extract a value from the contigous
memory.

The computer knows the size (ex: 8-bit number) and the offset (ex: index 2). Ex: Computer reads Offset x size (8 x 2) to reach
the beginning of the 3rd 8-bit number in the array, then reads 8 more bits and retrieves or modifies them.

# Growing/Shrinking an Array:
- We cannot simply grow or shrink an array at all. This would cause it to overflow into other data in our memory. When you insert 
a new value, you are really just changing an existing part of the array's memory. It doesn't actually grow in memory.
Same goes for deleting a value, you are really just setting the bytes in memory to represent null, 0, etc.
- There is no push, pop, insertAt, removeAt built into an array. Programming languages typically implement these behind
the scenes. Or you do!
- You're going to have to reallocate if you want to change your array's size.

# Time Complexities:
1. Retrieving from a specific index: O(1) - Using offset, data size, and contigous memory the computer can jump straight to
the bytes we need and provide them. It doesn't have to walk over every single value in memory.
2. Modifying Entries: O(1) - Same situation as before. The computer can jump straight to the memory address of the element and change its
bit values