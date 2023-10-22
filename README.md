Project-0x19. C - Stacks, Queues - LIFO, FIFO.

1. **Stack (LIFO - Last In, First Out):** A stack is a linear data structure where elements are added and removed from one end called the "top" of the stack. The last item pushed onto the stack is the first one to be popped off. Stacks are commonly used for tasks such as function call management (the call stack) or undo operations.

   In C, you can implement a stack using an array or a linked list. You would use functions like `push` to add an element to the top of the stack and `pop` to remove the top element.

   Example of stack implementation in C using an array:
   
   #define MAX_SIZE 100

   int stack[MAX_SIZE];
   int top = -1; // Initialize top to -1

   void push(int value) {
       if (top < MAX_SIZE - 1) {
           stack[++top] = value;
       } else {
           // Stack is full, can't push
       }
   }

   int pop() {
       if (top >= 0) {
           return stack[top--];
       } else {
           // Stack is empty, nothing to pop
           return -1;
       }
   }
   

2. **Queue (FIFO - First In, First Out):** A queue is another linear data structure where elements are added at the back and removed from the front. The first element added is the first one to be removed. Queues are commonly used for tasks like managing tasks in a print spooler or processing requests in a web server.

   In C, you can implement a queue using an array or a linked list. You would use functions like `enqueue` to add an element to the back of the queue and `dequeue` to remove an element from the front.

   Example of a queue implementation in C using an array:
   
   #define MAX_SIZE 100

   int queue[MAX_SIZE];
   int front = 0;
   int rear = -1;
   int itemCount = 0; // Initialize itemCount to 0

   void enqueue(int value) {
       if (itemCount < MAX_SIZE) {
           if (rear == MAX_SIZE - 1) {
               rear = -1; // Wrap around if necessary
           }
           queue[++rear] = value;
           itemCount++;
       } else {
           // Queue is full, can't enqueue
       }
   }

   int dequeue() {
       if (itemCount > 0) {
           int data = queue[front++];
           if (front == MAX_SIZE) {
               front = 0; // Wrap around if necessary
           }
           itemCount--;
           return data;
       } else {
           // Queue is empty, nothing to dequeue
           return -1;
       }
   }
   
