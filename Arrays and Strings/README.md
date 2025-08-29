# Mastery Guide: Arrays & Strings

Welcome to my deep-dive into Arrays and Strings. This document serves as a comprehensive guide to the core concepts, performance characteristics, and strategic problem-solving patterns for these foundational data structures. The focus here is on building optimal, interview-ready solutions with a clear understanding of time and space complexity trade-offs.

---
## 🧠 Core Concepts & Performance Analysis

A deep understanding of the fundamentals is non-negotiable for writing high-performance code.

### Arrays
* **The Core:** A fixed-size, contiguous block of memory holding elements of the same type.
* **Performance Profile:**
    * **Pro (Speed):** Constant-time `$O(1)` random access by index (`nums[i]`). This is its superpower. Due to contiguous memory, it also benefits from excellent **cache locality**, making iteration extremely fast.
    * **Con (Flexibility):** Fixed size and slow `$O(n)` insertion/deletion in the middle, as these operations require shifting subsequent elements.

### Strings
* **The Core:** A sequence of characters. In languages like Java, strings are **immutable**.
* **Performance Profile:**
    * **The Trap:** String immutability means any "modification" (like concatenation in a loop) creates a new string, leading to a disastrous `$O(n^2)` time complexity.
    * **The Professional Standard:** For any iterative string building, **`StringBuilder` is mandatory**. It uses a mutable internal buffer, achieving an optimal, amortized `$O(n)` complexity.

---
## 🛠️ The Strategic Toolkit: Interview Patterns

Solving array problems efficiently is about pattern recognition. This is the toolkit for deconstructing any array or string problem.

### 1. Pattern: The Two Pointers
* **The Interview Pitch:** "This problem can be optimized by using a Two Pointers approach. By using two pointers that traverse the array, I can process the data in a single pass, avoiding a brute-force nested loop and reducing the time complexity from `$O(n^2)` to `$O(n)`."
* **The Simple Idea:** Like two friends walking towards or with each other along a path to find something together. 🚶‍♂️...🚶‍♀️
* **The Signal (When to Use It):**
    * Problems on **sorted arrays** looking for a pair.
    * Problems involving **palindromes**.
    * Anytime you need to compare elements from opposite ends of an array.
* **Canonical Problems:**
    * `LC 167 - Two Sum II`: The classic "converging" pointers pattern.
    * `LC 11 - Container With Most Water`: A brilliant example of moving pointers based on a greedy condition.
    * `LC 125 - Valid Palindrome`: Pointers moving inwards from both ends.

### 2. Pattern: The Sliding Window
* **The Interview Pitch:** "Since this problem asks for an optimal value over a contiguous subarray, the Sliding Window pattern is the ideal approach. It allows me to maintain and update a dynamic window over the data in a single pass for an `$O(n)` solution."
* **The Simple Idea:** A resizable frame that slides across a list, keeping track of what's inside the frame. 
* **The Signal (When to Use It):**
    * "Longest/shortest **contiguous** subarray/substring..."
    * "Maximum/minimum sum of a **contiguous** subarray of size k..."
* **Canonical Problems:**
    * `LC 3 - Longest Substring Without Repeating Characters`: The quintessential dynamic window problem.
    * `LC 424 - Longest Repeating Character Replacement`: An advanced application requiring clever state management.
    * `LC 121 - Best Time to Buy and Sell Stock`: A simple but effective use of the pattern's logic.

### 3. Pattern: Hashing for Lookups
* **The Interview Pitch:** "A brute-force solution here would be `$O(n^2)` due to the nested search. I can optimize this by leveraging a HashMap for instant lookups. This is a classic space-for-time trade-off, reducing the time complexity to `$O(n)` at the cost of `$O(n)` space."
* **The Simple Idea:** Like having a magical dictionary where you can look up any word instantly. 📖
* **The Signal (When to Use It):**
    * Anytime you are repeatedly searching for elements.
    * Problems involving frequency counts (e.g., anagrams).
    * Checking for duplicates.
* **Canonical Problems:**
    * `LC 1 - Two Sum`: The most famous interview problem, perfectly solved with a HashMap.
    * `LC 49 - Group Anagrams`: Demonstrates using a canonical representation (a sorted string) as a key.

### 4. Pattern: Prefix Sum / Product
* **The Interview Pitch:** "This problem requires calculating sums of multiple subarrays. To avoid re-calculation, I'll use the Prefix Sum pattern. A one-time `$O(n)` pre-computation will allow all future subarray sum queries to be answered in `$O(1)` time."
* **The Simple Idea:** A "running total" list that lets you find the sum between any two points instantly.
* **The Signal (When to Use It):**
    * Repeated calculation of subarray sums.
    * When a value at index `i` depends on an aggregate of everything to its left and right.
* **Canonical Problems:**
    * `LC 560 - Subarray Sum Equals K`: A brilliant combination of the Prefix Sum and Hashing patterns.
    * `LC 238 - Product of Array Except Self`: A clever variation using both prefix and postfix products.

---
## ⚡ Quick Revision & Cheat Sheet

This table is for last-minute review before an interview.

| Pattern | The Signal (Keywords) | Key Use Case / Problem |
| :--- | :--- | :--- |
| **Two Pointers** | `sorted array`, `palindrome`, `find pair` | Find a pair that sums to a target. |
| **Sliding Window**| `longest/shortest`, `contiguous subarray`, `size k`| Find the longest substring with no repeating chars. |
| **Hashing** | `find duplicates`, `group by`, `anagrams` | Find two numbers that sum to a target (Two Sum). |
| **Prefix Sum** | `sum of subarray`, `running total` | Find how many subarrays sum to `k`. |
| **In-place Manip.**| `O(1) space`, `move zeroes`, `sort colors` | Move all zeroes to the end of an array. |
