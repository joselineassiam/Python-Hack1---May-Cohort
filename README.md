# Data Structures and Algorithms Practice

This repository contains your solutions to three simple data structures and algorithms problems. Please follow the instructions below to complete the tasks and submit your work.

## Questions

### 1. Reverse a String Using a Stack
- **Task:** Implement a stack data structure to reverse a string.
- **Function:** reverse_string(s: str) -> str
- **Example:**
  - Input: "hello"
  - Output: "olleh"

  #### ANSWER

  def reverse_string(s: str) -> str:
    stack = []
    for char in s:
        stack.append(char)
    
    reversed_str = ''
    while stack:
        reversed_str += stack.pop()
    
    return reversed_str

# Example usage:
print(reverse_string("hello"))  # Output: "olleh"


### 2. Implement a Queue Using Two Stacks
- **Task:** Implement a queue using two stacks.
- **Class:** QueueWithStacks
- **Methods:**
  - enqueue(x: int): Adds an element to the queue.
  - dequeue() -> int: Removes and returns the front element of the queue.
- **Example:**
  
python
  q = QueueWithStacks()
  q.enqueue(1)
  q.enqueue(2)
  print(q.dequeue())  # Output: 1
  print(q.dequeue())  # Output: 2


  #### ANSWER

  class QueueWithStacks:
    def __init__(self):
        self.stack1 = []
        self.stack2 = []

    def enqueue(self, x: int):
        self.stack1.append(x)

    def dequeue(self) -> int:
        if not self.stack2:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
        return self.stack2.pop() if self.stack2 else None

# Example usage:
q = QueueWithStacks()
q.enqueue(1)
q.enqueue(2)
print(q.dequeue())  # Output: 1
print(q.dequeue())  # Output: 2



### 3. Find the Maximum Element in a List Using a Linked List
- **Task:** Implement a singly linked list and find the maximum element in the list.
- **Class:** LinkedList
- **Method:** find_max() -> int
- **Example**
python
  ll = LinkedList()
  ll.append(3)
  ll.append(1)
  ll.append(4)
  ll.append(2)
  print(ll.find_max())  # Output: 4


  #### ANSWERclass Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node

    def find_max(self) -> int:
        if not self.head:
            return None
        
        max_value = self.head.data
        current = self.head.next
        while current:
            if current.data > max_value:
                max_value = current.data
            current = current.next
        
        return max_value

# Example usage:
ll = LinkedList()
ll.append(3)
ll.append(1)
ll.append(4)
ll.append(2)
print(ll.find_max())  # Output: 4






### Submission Instructions
- Fork this repository.
- Clone the forked repository to your local machine.
- Create a separate branch for your solutions.
- Implement the solutions to the above questions in Python.
- Commit your changes with clear and descriptive messages.
- Push your changes to your forked repository.
- Create a pull request (PR) to the original repository with your solutions- Submit the URL of your GitHub repository as your final submission.

### Submission form 
https://forms.gle/VUTFyWTXKUPq4CMQ
