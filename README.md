# Database Systems

This is the homework for the NDHU CSIEB0170 Operating Systems (2023 Fall) course. 

## Matrix Multiplication Parallelization

### Overview
The primary objective of this assignment is to develop an optimized matrix multiplication program that significantly outperforms the baseline sequential implementation (`origin.c`). By utilizing the **POSIX Threads (Pthreads)** library, the system implements a multi-threaded architecture to handle 1000 matrix calculation tasks concurrently, aiming to minimize total execution time and maximize CPU utilization.

This project compares two approaches:
* **Sequential Version (`origin.c`)**: The original single-threaded baseline that processes files one by one.
* **Parallel Version (`main.c`)**: The optimized version designed to be faster by distributing the workload across multiple threads.

### How to Run

#### 1. Requirements
Before running the application, ensure you have a C compiler (such as `gcc`) installed and that your environment supports the Pthreads library:
```bash
# Verify gcc installation
gcc --version
```

#### 2. Requirements
The program is designed to batch-process 1000 matrix input files. If you need to generate multiple test files from existing ones, you can use the following command:
```bash
# Duplicate input files to reach 1000 files
for i in {4..1000}; do
  cp "in$((i-3)).txt" "in$i.txt"
done
```

#### 3. Compiling the Code
To compile both the optimized and original versions, execute the following commands in your terminal:
```bash
# Compile the Parallel version with pthread library
gcc main.c -lpthread -o main

# Compile the Sequential version
gcc origin.c -o origin
```

#### 4. Running the Program
To compile both the optimized and original versions, execute the following commands in your terminal:
```bash
# Run parallel multiplication (Optimized)
./main

# Run sequential multiplication (Original)
./origin
```