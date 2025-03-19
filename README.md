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
  - If you're removing an element `O(1)`.
- **Random Access:** `O(1)` because of direct indexing.
- **Memory Usage:** Efficient but requires contiguous memory allocation, which can make resizing costly.
- **Traversal Ease:** Easy with indexing. You can iterate through an entire array in `O(n)` time.

```js
// Using an array to store games
let playStation = ["COD", "Fortnite"];
console.log(playStation[1]); // Fast access by index

playStation.push("Marvel Rivals"); // Adding a new game at the end
console.log(playStation); // Output: ['COD', 'Fortnite', 'Marvel Rivals']

playStation.pop(); // Removing the last game
console.log(playStation); // Output: ['COD', 'Fortnite']
```

### Singly Linked List

A linear data structure where each node contains a piece of _data_ and a **pointer** to the _next node_ in the sequence. The next of the last node is `null`, indicating the end of the list.

- **Insertion:**
  - `O(1)` if you're inserting at the head.
  - `O(n)` if you're inserting at a specific index (traversal required).
- **Removal:**
  - `O(1)` if removing from the head.
  - `O(n)` if removing from a specific index (traversal required).
- **Random Access:** You must traverse from the head.
- **Memory Usage:** Higher than arrays due to an extra pointer per node and requires one reference per node.
- **Traversal Ease:** Only forward traversal.

### Doubly Linked List

In a doubly linked list, the `head node` has a next reference pointing to the `next node` in the list. Usually, it doesn't have a previous reference because it is the first node. Each node after has data and references to the previous and next nodes.

- **Insertion:**
  - `O(1)` if you're inserting at the head or tail.
  - `O(n)` if you're inserting at a specific index (traversal required).
- **Removal:**
  - `O(1)` if removing from the head or tail.
  - `O(n)` if removing from a specific index.
- **Random Access:** You must traverse in both directions.
- **Memory Usage:** Higher than singly linked lists because it stores two pointers per node. Using more memory like this can impact the overall memory efficiency, especially for large lists.
- **Traversal Ease:** Allows for traversal in both directions.

### When to Use Each?

Use **arrays** when you need fast random access to elements, the number of elements is known in advance or doesn't change often, or if insertions or removals happen mostly at the end. For example:

- Game Leaderboards: Store top scores in an array since accessing the `n-th` highest score is quick.

Choose a **singly linked list** if you need to frequently insert or remove elements, especially at the head, without the need for fast random access. It’s ideal when you don’t know the exact number of elements in advance or don’t require contiguous memory. For example:

- Undo/Redo Functionality: In text editors (e.g., Microsoft Word, VS Code), each action is stored as a node in a singly linked list.

Use **doubly linked list** for fast insertions and deletions at both ends, when traversal in both directions is required, and memory overhead. For example:

- Browser Back/Forward Navigation: The history of visited pages is stored in a doubly linked list, allowing users to go back and forward easily.

## Prompt 2

Imagine you are developing a web browser's "back" button functionality. When a user clicks "back," the browser should navigate to the previously visited webpage.

Would you use a stack or a queue to implement this functionality?

In your response, explain what a Stack/Queue is and why it would be best for this use case. Make sure that your response includes the terms LIFO or FIFO.

### Response 2

To implement the "back" button in a web browser, you would use a stack.

### What is a Stack?

A `stack` is a **abstract data type** that uses the **LIFO** principle **(Last In, First Out)**. This means that the last item added is the first one to be removed. This has a collection of values with two operations:

- `push` = Inserts a new element to the "top" of the stack.
- `pop` = Removes the most recent element added to the stack.

### Why Use a Stack for the "Back" Button?

When you click the "back" button, the browser should go to the **most recent page** you visited. A stack works here because each time you visit a new page, you _push_ it into the stack. When you press "back," the browser _pops_ the most recent page off the stack, taking you back to the previous page. However, a **queue** follows the **FIFO** principle **(First In, First Out)**, meaning the first item added is the first one removed. This wouldn't be ideal for the "back" button since you'd be going back to the oldest page first, not the most recent one.

## Prompt 3

What is an Abstract Data Type and why are they worth learning about?

### Response 3

In abstract data type is a data structure that is a way of organizing and Storing Data in a computer so that it can be accessed, modified, and processed efficiently. Operations act as an interface where we focus on the what and not the how a method/operation is done. For Example:

```js
const myStack = new Stack();
myStack.add(5);
myStack.add(9);
myStack.remove();
```

Lets say you created a Stack class. That class has methods/operations such as `.add()`, `.remove()`, etc. is an interface of sorts but we don't exactly know how the method is executed under the hood. The internal details on how the operation works is hidden or `Abstracted` away.

## Prompt 4

A few classic problems involving a stack are the `isBalanced` and `isPalindrome` functions. Choose one of these functions and provide a solution to it along with a brief lesson explaining how it works.

### Response 4

Lets go over how the `isPalindrome` function can be solved with a stack. A palindrome is a word that is the same spelled backwards. An example is: tenet or racecar. Here is my Stack class:

```js
class Stack {
  #stack = [];
  constructor() {}

  push(data) {
    this.#stack.push(data);
  }

  pop() {
    let top = this.#stack.pop();
    return top;
  }

  peek() {
    return this.#stack[this.#stack.length - 1];
  }

  isEmpty() {
    return this.#stack.length === 0;
  }

  getSize() {
    return this.#stack.length;
  }
}
```

The function will take in an `inputString`. The first thing we want to do is have a variable for our stack lets call it `myStack`. We also want the length of the input and the middle of the input. As well as a for loop to add letters into our stack up until the middle index Shown below:

```js
const isPalindrome = ('tenet') =>{
const myStack = new Stack();
const length = inputString.length; // tenet.length: 5
const mid = Math.floor(length / 2); // index 2 = n

for(i = 0; i < mid; i++){
    myStack.push(inputString[i]) // [t,e]
}
}
```

I will make a new variable to show where to start the next for loop, lets call it `start`.

```js
let start = length % 2 === 0 ? mid : mid + 1; //5 is not divisible by 2 so the new value of mid will be 3 not 2
```

Our final for loop will start at our new variable and go up until the length of the input and we will have a conditional to determine whether we have a palindrome or not.

```js
for (let i = start /*3*/; i < length /*5*/; i++) {
  if (myStack.pop() !== inputString[i]) return false;
  return true;
  //[t, e]
  // if ([e] === e) true
  // if ([t] === t) true

  //This is a palindrome!
}
```
