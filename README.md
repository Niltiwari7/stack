## Implement Stack using the array
## Code
```
#include <iostream>
using namespace std;

class Stack {
public:
    int size;
    int top = -1;
    int* arr;

    Stack(int n) {
        size = n;
        arr = new int[n];
    }

    void push(int val) {
        if (top >= size - 1) {
            cout << "Stack is full. Cannot push." << endl;
            return;
        }
        arr[++top] = val;
    }

    int peek() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
            return -1;
        }
        return arr[top];
    }

    int pop() {
        if (top == -1) {
            cout << "Stack is empty. Cannot pop." << endl;
            return -1; 
        }
        return arr[top--];
    }

    int stack_size() {
        return top + 1;
    }
};

int main() {
    Stack myStack(5);

    myStack.push(1);
    myStack.push(2);
    myStack.push(3);

    cout << "Top element: " << myStack.peek() << endl; 
    cout << "Stack size: " << myStack.stack_size() << endl; 

    myStack.pop();
    cout << "Top element after pop: " << myStack.peek() << endl; 

    return 0;
}
```
## Implement Queue using the array
## Code
```
#include<iostream>
using namespace std;

class Queue {
public:
    int front = -1;
    int rear = -1;
    int maxSize;
    int* arr;

    Queue(int n) {
        maxSize = n;
        arr = new int[n];
    }

    void push(int val) {
        if (rear == maxSize - 1) {
            cout << "Queue is full" << endl;
            return;
        }
        arr[++rear] = val;
    }

    int peek() {
        if (isEmpty()) {
            cout << "Queue is empty" << endl;
            return -1; 
        }
        return arr[front + 1];
    }

    int pop() {
        if (isEmpty()) {
            cout << "Queue is empty" << endl;
            return -1; 
        }
        int val = arr[++front];
        return val;
    }

    bool isEmpty() {
        return front == rear;
    }

    int size() {
        return rear - front;
    }

    void print() {
        for (int i = front + 1; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
};

int main() {
    Queue q(4);

    // print Queue elements
    q.print();

    // inserting elements in the queue
    q.push(20);
    q.push(30);
    q.push(40);
    q.push(50);

    // print Queue elements
    q.print();

    // insert element in the queue
    q.push(60);

    // print Queue elements
    q.print();

    q.pop();
    q.pop();

    cout << "\n\nafter two node deletion\n\n";

    // print Queue elements
    q.print();

    // print front of the queue
    cout << "Front of the queue: " << q.peek() << endl;

    return 0;
}
```
