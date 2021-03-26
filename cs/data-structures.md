# Data structures

## Linked list

### Strengths:

- Fast operations on the ends. Adding elements at either end of a linked list is O(1)O(1). Removing the first element is also O(1)O(1).
- Flexible size. There's no need to specify how many elements you're going to store ahead of time. You can keep adding elements as long as there's enough space on the machine.

### Weaknesses:

- Costly lookups. To access or edit an item in a linked list, you have to take O(i)O(i) time to walk from the head of the list to the iith item.

### Uses:

Stacks and queues only need fast operations on the ends, so linked lists are ideal.

### Compare with array

Most computers have caching systems that make reading from sequential addresses in memory faster than reading from scattered addresses.

Array items are always located right next to each other in computer memory, but linked list nodes can be scattered all over.

So iterating through a linked list is usually quite a bit slower than iterating through the items in an array, even though they're both theoretically O(n)O(n) time.

[source](https://www.interviewcake.com/concept/python/linked-list)

---

## Learning resources:

- [Learning Data Structures in JavaScript from Scratch on Udemy](https://www.udemy.com/course/learning-data-structures-in-javascript-from-scratch/)

[more in the CS curriculum](roadmap.md) and [Coding Cheat Sheets](https://github.com/aspittel/coding-cheat-sheets)

[Python dictionaries](../python/dict.md)
