# HPC_Assignment_2 
Created a concurrent double-linked list (sorted list) using the following synchronization techniques:

- Coarse-grain Synchronization
- Fine-grain Synchronization
- Optimistic Synchronization
- Lazy Synchronization
- Non-blocking Synchronization

Verified the performance of the concurrent data structure for different problem sizes (2 × 1000, 2 × 10000, and 2 × 100000) by varying the number of threads (1, 2, 4, 6, 8, 10, 12, 14, and 16) and workloads (0C-0I-50D, 50C-25I-25D, and 100C-0I-0D).

### Coarse-grain Synchronization
Coarse-grained synchronization involves locking the entire data structure (in this case, the entire doubly linked list) to protect it from concurrent access. When one thread acquires the lock, it has exclusive access to the entire list, preventing other threads from accessing it until the lock is released.
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/100d9957-4d40-43f5-97c6-16dc69fc870b)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/f6cee3bb-5f18-4d21-a88f-9fbea8d6defb)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/027f41af-edd2-47da-9db8-6241aa9680a6)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/1d52d885-edbd-43d4-82a7-0f63294ff987)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/0e71400b-b440-461d-91c2-08253f55a12c)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/70705053-c74c-4324-ae4e-593b1aacfb9e)

### Fine-grained synchronization
Fine-grained synchronization divides the doubly linked list into smaller, independently locked sections. Each section (e.g., a node or a group of nodes) has its lock. Threads can operate concurrently on different sections, reducing contention.
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/1e6801dd-d765-44db-95b1-f22de45268ab)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/3f226c0d-656a-4e03-82c4-2f6086e55c5a)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/6843f46b-d690-4359-80ba-49918ada42a2)

### Optimistic Synchronization
Optimistic synchronization assumes that conflicts between threads are rare. Instead of locking data structures, each thread reads and makes modifications locally. Before applying changes, the thread validates that no other thread has modified the same data. If conflicts occur, the thread retries the operation.
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/2c6a86c3-833e-4b2c-a7ec-f3201fa46c3c)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/2588f08d-1ad1-4649-9ece-5604f140f100)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/37001a1a-23ca-4073-8c71-168a794df0bd)

### Lazy Synchronization
 Lazy synchronization aims to delay synchronization until absolutely necessary. Threads perform operations without initially acquiring locks. Only during critical sections or when conflicts are detected are locks acquired to ensure data consistency.
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/513dbf2a-bcbb-4ad5-ad4e-7d3ce38afd21)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/f5bde437-ddf9-4bc5-bc82-fa1cca6d3b16)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/d64ef44c-a6d7-4dc7-a910-d094481b2c1e)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/b57d5083-b50e-4c10-9507-a1f29c43f1a0)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/a6df36e0-fb2c-48b3-afb9-734ac2683439)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/04f82650-0612-4bff-972f-0900722f9bd9)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/3eb6b94f-c4ab-4a07-a75e-16cefc38d1dd)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/47e64bdc-a8ad-4963-a3e9-1311325140db)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/db460ff0-2999-41fd-ba05-df107cafc90d)

### Non-blocking Synchronization
Non-blocking synchronization techniques aim to eliminate the use of locks entirely. Instead, atomic operations, such as compare-and-swap (CAS), are used to modify data structures in a thread-safe manner. If a CAS operation fails due to a concurrent modification, the thread retries the operation.
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/defce5d5-604c-4a70-a8f8-235ab0debbc2)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/7c692bf8-e78b-440c-acc0-97247bb6676b)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/de40a71f-3ea3-4ccb-bd8d-5c9214d4d00a)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/42efeea4-b056-4ca6-a5cc-6ca31dd2083f)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/d855d244-95e6-408c-9356-5d948a3e05cc)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/45fb809c-a26d-4870-a190-d58f02a3a645)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/e037b611-8683-4979-8cfd-7afd3a16cebc)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/446eba82-2744-44ac-9650-cc14c506fa9b)
![image](https://github.com/harshakarnam57/HPC2/assets/64098766/d8b487bc-413b-49f1-945a-b9b7af12f73e)

NOTE: In some techniques for a problem siza 3 individual graphs are plotted due to different range of throughput for each workload.
