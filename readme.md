# C++ Library Management System: Technical Specification

## 1.0 Abstract

This document provides a technical overview of the C++ Library Management System, a command-line application designed for the systematic administration of a lending library's core operations. The system's architecture facilitates the management of a book inventory, the registration of borrowers, the processing of book loans and returns, and the archival of all transactional data. Data persistence is achieved through the utilization of local text-based files, thereby ensuring the preservation of the system's state across execution cycles.

## 2.0 System Capabilities

The application is endowed with the following functional capabilities:

* **Inventory Management**: The system permits the addition of new book records to the institutional inventory.
* **Patron Registration**: A mechanism is provided for the enrollment of new students as registered borrowers.
* **Circulation Control**: The software systematically manages the circulation of materials, encompassing both the issuance and the return of books.
* **Inventory Auditing**: A comprehensive report of the entire book collection can be generated, which enumerates each item's identification number, title, author, and current circulation status.
* **Transactional Ledger**: A complete and chronological ledger of all circulation activities is maintained and available for review.
* **Data Persistence**: All operational data, including inventory, patron records, and transaction histories, are serialized to external text files to ensure data retention.

## 3.0 Implementation and Execution

### 3.1 Prerequisites for Compilation

Successful compilation of the source code necessitates the presence of a standard C++ compiler. The GNU Compiler Collection's `g++` compiler is the recommended toolchain. The acquisition of the requisite compiler is dependent upon the operating system in use:

* **Windows**: The `g++` compiler may be acquired through the installation of the [MinGW-w64](https://www.mingw-w64.org/) project or via the Windows Subsystem for Linux (WSL).
* **macOS**: The Apple Command Line Tools, which include the Clang/LLVM compiler toolchain, can be installed by executing the command `xcode-select --install` within a terminal environment.
* **Linux**: For Debian-based distributions, the `build-essential` package, which contains the GCC, can be installed by executing `sudo apt-get install build-essential`.

### 3.2 Compilation Protocol

The generation of the executable file from the source code shall be performed in accordance with the following procedure:

1.  The source code must be contained within a file designated `main.cpp`.
2.  A command-line terminal must be initiated.
3.  The working directory of the terminal must be set to the location of the `main.cpp` file.
4.  The compilation shall be invoked via the subsequent command:

    ```sh
    g++ main.cpp -o library_system -std=c++11
    ```

    This operation will produce an executable file named `library_system` (or `library_system.exe` on the Windows platform).

### 3.3 Execution Procedure

Subsequent to a successful compilation, the application may be executed by issuing the appropriate command from the terminal:

* **For macOS/Linux Systems**:
    ```sh
    ./library_system
    ```

* **For Windows Systems**:
    ```sh
    .\library_system.exe
    ```

Upon initiation, the application's main menu will be displayed. The requisite data files for persistent storage will be created automatically if they are not already present in the execution directory.

## 4.0 Directory Contents

The project directory is comprised of the following file components:

* `main.cpp`: The C++ source file containing the complete implementation of the application logic.
* `README.md`: The present document, which furnishes a technical description and operational guidelines.
* `books.txt`: The designated data file for storing the book inventory records.
* `students.txt`: The designated data file for storing the registered patron records.
* `transactions.txt`: The designated data file serving as a log for all circulation transactions.
