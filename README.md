# GatorLibrary Management System

A Red-Black Tree and Binary Min-Heap based library management system developed for COP 5536 - Advanced Data Structures at the University of Florida.

## Overview

GatorLibrary is a command-line tool that allows management of books, patrons, and reservations in a fictional library system. It supports fast book lookups using a Red-Black Tree (RBT) and handles reservation queues via per-book Binary Min-Heaps prioritized by user-defined priority levels and reservation time.

## Core Data Structures

- **Red-Black Tree**: Used to store books, enabling fast insertions, deletions, and lookups based on `bookID`.
- **Binary Min-Heap**: Each book has a reservation heap to manage waitlists. Patron requests are ordered by priority and timestamp.

## Book Node Structure

Each Red-Black Tree node (book) includes:
- `bookID`
- `bookName`
- `authorName`
- `availabilityStatus` (`Yes` / `No`)
- `borrowedBy` (Patron ID)
- `reservationHeap` (Min-Heap of patrons waiting)

## Supported Operations

- `InsertBook(bookID, bookName, authorName, availabilityStatus)`
- `PrintBook(bookID)`
- `PrintBooks(bookID1, bookID2)`
- `BorrowBook(patronID, bookID, priority)`
- `ReturnBook(patronID, bookID)`
- `DeleteBook(bookID)`
- `FindClosestBook(targetID)`
- `ColorFlipCount()`
- `Quit()`

## Features

- Handles reservation priority and waitlist (Max 20 entries)
- Automatically assigns returned books to the next prioritized patron
- Tracks color flips in the Red-Black Tree for analytics
- Efficient searching, range queries, and neighbor lookups

## How to Run

### Requirements
- Python 3.x

### Execution
```bash
python3 gatorLibrary.py input_file.txt
```

- The program will produce an output file named: `input_file_output_file.txt`
- Each line in the input file corresponds to one of the supported operations.

### Example
Input (`test1.txt`):
```
InsertBook(1, "Book1", "Author1", "Yes")
BorrowBook(101, 1, 1)
ReturnBook(101, 1)
Quit()
```

Output (`test1_output_file.txt`):
```
Book 1 Borrowed by Patron 101
Book 1 Returned by Patron 101
Program Terminated!!
```

## File Structure

- `gatorLibrary.py`: Main source code
- `README.md`: Project overview and instructions

## Author

- **Aravind Namburi**
- Course: Advanced Data Structures

## 📝 Notes

- All data structures are implemented from scratch.
- No external libraries are used for trees or heaps.
- Reservation is based on `(priority, timestamp)` with FIFO for ties.
- Book IDs must be unique; each book has only one copy.

---

This project demonstrates mastery of custom data structure implementation, file-based I/O, and algorithmic problem solving in a real-world application.

