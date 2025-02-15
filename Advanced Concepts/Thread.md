# [Thread](#thread)
A thread is a lightweight unit of a process that can run independently. Multiple threads within the same process share resources like memory but execute separately. In C++, threading is a mechanism that allows multiple tasks (or functions) to run concurrently within the same program. On Linux, you can use the C++11 `<thread>` library or POSIX Threads (Pthreads) to manage threads.

## Creating and Managing Threads

### a) Creating a Thread
C++11 introduced the `<thread>` library, which simplifies working with threads. You can create a thread using the `std::thread` class.

```cpp
#include <iostream>
#include <thread>

void printMessage() {
    std::cout << "Hello from thread!" << std::endl;
}

int main() {
    std::thread t(printMessage); // Create a thread
    t.join(); // Wait for thread to complete
    return 0;
}
```

### b) Joining and Detaching Threads
- `join()`: The main thread waits for the created thread to finish before continuing execution.
- `detach()`: The thread runs independently, and the main thread does not wait for it.

```cpp
std::thread t(printMessage);
t.join();  // Ensures main thread waits for t to complete
```

OR

```cpp
std::thread t(printMessage);
t.detach();  // t runs independently; main thread continues execution
```

⚠️ **Warning**: `detach()` can lead to undefined behavior if the main function ends before the detached thread finishes.

## 3. Passing Arguments to Threads

You can pass parameters to threads using lambda functions or by reference.

### a) Passing by Value
```cpp
void printNumber(int x) {
    std::cout << "Number: " << x << std::endl;
}

int main() {
    std::thread t(printNumber, 10); // Pass value 10
    t.join();
    return 0;
}
```

### b) Passing by Reference
Use `std::ref()` to pass arguments by reference.

```cpp
void increment(int &x) {
    x++;
}

int main() {
    int num = 5;
    std::thread t(increment, std::ref(num));
    t.join();
    std::cout << "Updated Number: " << num << std::endl;
    return 0;
}
```

## 4. Using Mutex for Thread Synchronization
Multiple threads accessing shared data can lead to race conditions. Use `std::mutex` to prevent data corruption.

```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;

void printMessage(const std::string &msg) {
    mtx.lock();  // Lock mutex
    std::cout << msg << std::endl;
    mtx.unlock();  // Unlock mutex
}

int main() {
    std::thread t1(printMessage, "Thread 1");
    std::thread t2(printMessage, "Thread 2");

    t1.join();
    t2.join();
    return 0;
}
```

Alternatively, use `std::lock_guard` for automatic unlocking:

```cpp
void printMessage(const std::string &msg) {
    std::lock_guard<std::mutex> guard(mtx);
    std::cout << msg << std::endl;
}
```

