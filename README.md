## Implement Stack using array
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
## Implement Queue using array
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
};

int main() {
    Queue myQueue(5); 

    myQueue.push(1);
    myQueue.push(2);
    myQueue.push(3);

    cout << "Front element: " << myQueue.peek() << endl; 
    cout << "Queue size: " << myQueue.size() << endl; 

    myQueue.pop();
    cout << "Front element after pop: " << myQueue.peek() << endl; 

    return 0;
}
```
