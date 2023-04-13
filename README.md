# Stack
public class Stack {
    private Object[] items;
    private int top;

    public Stack(int capacity) {
        items = new Object[capacity];
        top = -1;
    }

    public boolean isEmpty() {
        return top == -1;
    }

    public boolean isFull() {
        return top == items.length - 1;
    }

    public void push(Object item) {
        if (isFull()) {
            throw new StackOverflowError();
        }
        items[++top] = item;
    }

    public Object pop() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return items[top--];
    }

    public Object peek() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return items[top];
    }
}
