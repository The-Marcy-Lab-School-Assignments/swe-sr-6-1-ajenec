# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Arrays, Linked Lists and Doubly Linked Lists all allow programmers to organize data in a sequence. So, how would you choose to use one over the other?

In your response, make sure to compare the time complexities for insertion, removal, and random access (grabbing a particular known element by index/position) for each data structure as well as memory usage and ease of traversal.

### Response 1

When choosing between arrays, linked lists, and doubly linked lists, it depends on the specific use case and performance requirements. You need to choose based on their time complexities for insertion, removal, and random access _(grabbing a particular known element by index/position)_ for each data structure as well as memory usage and ease of traversal.

### Arrays

They store elements in **contiguous memory locations**, resulting in easily calculable addresses for the elements stored and this allows **faster access** to an element at a specific index.

- **Insertion:**
  - If you're adding an element at the end _(and space is available)_, the time complexity is `O(1)`.
  - If you're inserting an element at the beginning or middle the time complexity is `O(n)` because the elements need to be shifted to make space.
- **Removal:**
  - if you're removing an element from the end, the time complexity is `O(n)`.
  - If you're removing an element`O(1)`.
- **Random Access:** O(1)
- **Memory Usage:** Efficient Requires contiguous memory allocation
- **Traversal Ease:** Easy with indexing. Your able to iterate through an entire array.

## Prompt 2

Imagine you are developing a web browser's "back" button functionality. When a user clicks "back," the browser should navigate to the previously visited webpage.

Would you use a stack or a queue to implement this functionality?

In your response, explain what a Stack/Queue is and why it would be best for this use case. Make sure that your response includes the terms LIFO or FIFO.

### Response 2

## Prompt 3

What is an Abstract Data Type and why are they worth learning about?

### Response 3

## Prompt 4

A few classic problems involving a stack are the `isBalanced` and `isPalindrome` functions. Choose one of these functions and provide a solution to it along with a brief lesson explaining how it works.

### Response 4
