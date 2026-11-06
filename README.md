# 🔎 Inverted Search – Hash Table Based Text Search Engine in C

A command-line application developed using **C Programming** that implements an inverted indexing mechanism to efficiently search words across multiple text files.

The project uses a **Hash Table and Singly Linked Lists** to organize unique words, maintain file references, and track the number of occurrences of each word.

Instead of searching through every file individually, the application builds an inverted database that makes word lookup and file identification easier.

---

## 📌 Project Overview

The Inverted Search Engine reads multiple `.txt` files, extracts words, and organizes them into a hash table containing 27 buckets:

- 26 buckets for English alphabet characters (`a`–`z`)
- 1 bucket for special characters and other starting characters

Each bucket maintains a linked list of unique words. Every word node maintains another linked list containing the file names and word frequencies.

This structure helps identify:
- Which files contain a particular word.
- How many files contain that word.
- How many times the word occurs in each file.

## ✨ Key Features

- **File Validation:** Checks whether input files have a valid `.txt` extension.
- **Empty File Detection:** Identifies and skips empty files.
- **Duplicate File Detection:** Prevents the same file from being processed multiple times.
- **Database Creation:** Reads words from validated files and builds the inverted database.
- **Hash-Based Indexing:** Uses a 27-bucket hash table to organize words.
- **Word Frequency Tracking:** Maintains the occurrence count of each word in individual files.
- **Database Display:** Displays the complete inverted database in a formatted table.
- **Word Search:** Searches for a word and displays the files containing it.
- **Database Update:** Restores an existing database from a previously saved text file.
- **Database Saving:** Saves the current database into a text file for future use.
- **Memory Management:** Uses dynamic memory allocation and deallocation.

## 🏗️ Data Structure Design

The project uses a combination of a Hash Table and Singly Linked Lists.

### 1. Hash Table

- Contains 27 buckets.
- Each bucket is associated with an alphabet character or a special-character category.
- Each bucket points to a linked list of main nodes.

### 2. Main Node

Stores information about each unique word.

| Member | Purpose |
|---|---|
| `word` | Stores the unique word |
| `file_count` | Number of files containing the word |
| `sub_link` | Points to the first sub node |
| `main_link` | Points to the next main node |

### 3. Sub Node

Stores file-related information for each word.

| Member | Purpose |
|---|---|
| `file_name` | Stores the file name |
| `word_count` | Number of occurrences in that file |
| `sub_link` | Points to the next sub node |

### 4. File Linked List

Maintains the list of validated input files before database creation.

## 🔄 Project Workflow

1. Accept multiple `.txt` files through command-line arguments.
2. Validate file extensions, check for empty files, and detect duplicates.
3. Store validated file names in a linked list.
4. Read words from each validated file.
5. Calculate the hash index using the first character of each word.
6. Create a main node for every unique word.
7. Create or update sub nodes to maintain file names and word frequencies.
8. Build the complete inverted database.
9. Perform search, display, update, and save operations through the menu.

## 🛠️ Technologies & Concepts Used

**Programming Language**
- C

**Data Structures**
- Hash Tables
- Singly Linked Lists
- Linked List Traversal

**C Programming Concepts**
- Pointers
- Structures
- Dynamic Memory Allocation (`malloc()` and `free()`)
- String Handling
- File Handling
- Modular Programming
- Functions and Header Files

**Development Tools**
- GCC Compiler
- Visual Studio Code
- Linux Terminal

## 📂 Project Structure

```text
Inverted_Search/
│
├── main.c
├── invert.h
├── invert.c
├── create_database.c
├── display_database.c
├── search_database.c
├── update
