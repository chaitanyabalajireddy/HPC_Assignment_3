
# **Concurrent Binary Search Tree with Various Locks**
This project implements a concurrent binary search tree (ConBST) that utilizes logical ordering for synchronization and evaluates its performance using different locking mechanisms under varying thread counts.

## **Introduction**
The concurrent binary search tree aims to provide a thread-safe data structure that supports efficient insertion, deletion, and search operations in a concurrent environment. This project explores the performance of ConBST by employing various locking mechanisms commonly used in concurrent programming.

### **Implemented Locks**
The following locking mechanisms have been implemented and evaluated for their impact on ConBST's performance:

### **Test And Set Lock**
- A basic lock that uses atomic operations for mutual exclusion. Threads repeatedly try to acquire the lock until successful, leading to potential contention.

### **Test Test And Set Lock**
- Similar to the Test And Set Lock but with additional spinning on a local flag before attempting to acquire the lock, reducing contention in some scenarios.

### **Test Test And Set Lock with Backoff**
- Enhancement to the Test Test And Set Lock, introducing a backoff strategy where a thread yields its execution for a brief period when unable to acquire the lock immediately.

### **Array-Based Queue Lock**
- A lock implementation that uses an array-based queue for thread synchronization. It aims to minimize contention by allowing threads to wait in a queue.

### **CLH Queue Lock**
- A queue-based lock utilizing the Craig, Landin, and Hagersten (CLH) lock algorithm. It employs a linked list of nodes to manage thread contention.

### **MCS Queue Lock**
- Another queue-based lock implementing the Mellor-Crummey and Scott (MCS) lock algorithm. Threads maintain a queue structure to handle contention for access.

## Usage
To utilize the implemented locks with the ConBST, follow these steps:

- **Compilation**: Compile the project using a Java compiler (e.g., javac).<br />
- **Lock Selection**: Modify the ConBST_Test.java source code to select the desired lock for testing by uncommenting the respective lock.<br />
- **Running Tests**: Run the ConBST_Test program with varying thread counts (1, 2, 4, 6, 8, 10, 12, 14, and 16) to evaluate the lock's performance.<br />
- **Performance Testing**: The ConBST_Test program facilitates performance testing under different thread counts. Observe the throughput and efficiency of each lock under varying concurrent scenarios.

## Results
The test results provide insights into the behavior of each locking mechanism concerning scalability, contention, and overall performance. Analysis of these results can help identify the suitability of locks for different workload types and thread counts.

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/ca64964f-763f-41f7-ac9f-40e2d045252d)

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/c90a3436-6220-41c8-8de3-4f919bea195a)

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/14a65d3c-2e18-49a6-9dcb-2419a8d87d04)

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/74780b29-380c-4f71-8a02-9d4d9dc1bc23)

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/d2a85c0f-d9e6-4b31-96fd-7e59730f015a)

![image](https://github.com/chaitanyabalajireddy/HPC_Assignment_3/assets/91625648/46f19dfb-6220-434f-a766-cb299fb887fb)
