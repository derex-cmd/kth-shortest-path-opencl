# 🚀 Top K Shortest Paths with MPI and OpenMP

## 📚 Project Overview

This project implements a parallel algorithm to find the top K shortest paths in a graph using **MPI (Message Passing Interface)** and **OpenMP (Open Multi-Processing)**. The project includes two versions of the code:

1. **Serial Code**: A basic implementation without optimization.
2. **Parallel Code**: An optimized implementation using parallelization techniques.

Both versions aim to efficiently process large graphs and provide accurate results. The project faced several challenges, including efficient graph parsing, memory management, and ensuring correct parallel execution. The detailed project report is included in the repository.

## 🛠️ Compilation and Execution Instructions

### 📋 Prerequisites

- Windows Subsystem for Linux (WSL) installed and configured
- Docker installed on WSL

### 🏃 Steps

#### 🔀 For Parallel Code

1. Open WSL.
2. Navigate to the project directory:

    ```bash
    cd alpine-mpich/cluster/project
    ```

3. Start the Docker container with MPI environment:

    ```bash
    docker run --rm -it -v $(pwd):/project nlknguyen/alpine-mpich
    ```

4. Compile your MPI C code using `mpicc`:

    ```bash
    mpicc -o parallel parallel.c
    ```

5. Run the MPI executable using `mpirun` specifying the number of processes:

    ```bash
    mpirun -n [num_processes] ./parallel [name_of_csv_file]
    ```

    Replace `[num_processes]` with the desired number of processes and `[name_of_csv_file]` with the name of the CSV file your program will operate on.

    **Example:**

    ```bash
    mpirun -n 4 ./parallel classic-who.csv
    ```

    **Notes:**
    - Ensure that your C source code file (`parallel.c`) contains the main function and necessary MPI initialization (`MPI_Init`, `MPI_Finalize`).
    - Verify that the input CSV file (`classic-who.csv`) is located in the same directory as your project files or provide the correct path.
    - Adjust the number of MPI processes (`-n`) based on your system’s capabilities and the size of the input graph.
    - After execution, the program will output the top K shortest paths based on the provided input graph.

#### 🔗 For Serial Code

1. Open WSL.
2. Navigate to the project directory:

    ```bash
    cd /path/to/serial/code
    ```

3. Compile your C code using gcc:

    ```bash
    gcc -o serial serial.c
    ```

4. Run the executable:

    ```bash
    ./serial [name_of_csv_file]
    ```

    Replace `[name_of_csv_file]` with the name of the CSV file your program will operate on.

    **Example:**

    ```bash
    ./serial classic-who.csv
    ```

    **Notes:**
    - Ensure that your C source code file (`serial.c`) contains the main function.
    - Verify that the input CSV file (`classic-who.csv`) is located in the same directory as your project files or provide the correct path.
    - After execution, the program will output the top K shortest paths based on the provided input graph.

## 📄 Report

For a detailed overview of the project, including challenges faced, optimizations applied, and experimental results, please refer to the [project report](report.pdf).

## 👥 Contributors

- **Muhammad Omer Nasir** (i212476@nu.edu.pk) 
- **Muhammad Yahya** (i212592@nu.edu.pk)


