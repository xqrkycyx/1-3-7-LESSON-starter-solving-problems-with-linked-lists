# Starter: Solving problems with linked lists

_Sample problems and solutions for problem solving with linked lists_

## Getting Started

Clone this repository.

```bash
git clone https://github.com/Thinkful-Ed/starter-solving-problems-with-linked-lists.git
```

Navigate to the root of the repository and install dependencies.

```bash
npm i
```

To run the tests

```bash
npm test
```

## Solutions

To view the sample solutions checkout the **Solution** branch.

## Problems

- [Reverse a linked list](./src/reverse)
- [Third from end](./src/thirdfromend)
- [Swap Nodes](./src/swap)
- [The Josephus Problem](./src/josephus)

## Pseudocode

```
function reverseIterative(list)
   // accepts list - a linked list, potentially empty, to be reversed

   declare a variable named reversedList and initialize it to an empty LinkedList
   declare a variable node initialized to the head of the list
   while the node pointer is not null do
     insert the node value at the head of the reversedList
     move the node pointer along to the next node
  return the reversedList

// --------------------------------------------------
// Javascript implementation / translation
// --------------------------------------------------

function reverseIterative(list) {
  const reversedList = new LinkedList();
  let node = list.head;
  while (node) {
    reversedList.insertAtHead(node.value);
    node = node.next;
  }
  return reversedList;
}

```

```
function thirdFromEnd(list) {
  if the list is empty then return null

  declare a variable named pointer1 and initialize it to the head of the list
  declare a variable named i and initialize it to 0
  while i is less than 2 and the next pointer of pointer1 is not null do
    set pointer1 to its next pointer
    increment i
  if i is less than 2 then return null

  declare a variable named pointer2 and initialize it to the head of the list
  while the next pointer of pointer1 is not null do
    set pointer1 to its next pointer
    set pointer2 to its next pointer

  return pointer2

```

```
function swap
  // accepts list - a linked list
             x - a node in the linked list
             y - a node in the linked list

  if the list is empty then
    return  the list

  declare a variable x_next and initialize it to the next pointer of x
  declare a variable x_prev and initialize it to the previous node to x, null if x is the head
  declare a variable y_prev and initialize it to the previous node to y, null if y is the head

  set the next pointer of x to the next pointer of y
  set the next pointer of y to x_next

  if x is not the head  of the list then
    set next pointer of x_prev to y
  else
    set head to y

  if y is not the head  of the list then
    set next pointer of y_prev to x
  else
    set head to x

  return the list

```

```
function josephus
  // Accepts: list the LinkedList of names
              m the number to skip

  declare variable node and initialize it to the head
  declare variable tail and initialize it to the last node in the list
  assign the next pointer of the tail to the head of the list

  while there are more than one nodes left do:
    move node to node.next m times
    if the next pointer of the current node points to the head
      set the head to the next node after the head
    set node.next  to  node.next.next
    node = node.next;
  }
  return node.value;
}
```
