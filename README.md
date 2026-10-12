# CIT300 Practical Assignment 2 — Merged Video Presentation Script & Viva Guide
### 3-Member Group Edition (Fully Aligned with Assignment Specification)

> **Submission Requirement**: One merged demonstration video  
> **Strict Maximum Duration**: Less than 15 minutes (Target: ~12.0 minutes, exactly ~4 minutes per member)  
> **Mandatory Rule**: **Every member's face must be clearly visible on camera throughout their individual presentation.** (Use OBS Studio, Zoom, or Google Meet with webcam overlay / Picture-in-Picture over screen share).

---

## 3-Member Group Timeline & Role Allocation

As specified in **Section 5 & 6 (Suggested Team Responsibilities)** of the assignment brief:
> *"If your group has fewer members, combine the suggested responsibilities among the available members and still implement all specified components... Regardless of the number of members: Every required component must be implemented."*

| Part | Speaker | Assigned Responsibilities | Allocated Time | Code Files to Show | Terminal Menu to Demo |
| :---: | :--- | :--- | :---: | :--- | :--- |
| **1** | **Member 1** (Lead) | System Architecture, Main Menu Integration & Array / Searching Implementation | **0:00 – 4:00** (~4.0 mins) | `Main.java`, `ArrayOperations.java`, `SearchingOperations.java` | Option 1 (Array), Option 5 (Searching) |
| **2** | **Member 2** | Stack, Circular Queue & Singly Linked List Data Structures (LIFO, FIFO & Pointers) | **4:00 – 8:00** (~4.0 mins) | `StackOperations.java`, `QueueOperations.java`, `LinkedListOperations.java` | Option 2 (Stack), Option 3 (Queue), Option 4 (Linked List) |
| **3** | **Member 3** | Graph Component (BFS / DFS Traversals) & Performance Benchmark Suite | **8:00 – 12:00** (~4.0 mins) | `Graph.java`, `PerformanceAnalyzer.java` | Option 6 (Graph), Option 8 (All State), Option 7 (Performance) |

---

## Video Recording Setup Checklist (Before Pressing Record)

1. **Webcam / Face Visibility**: Place your webcam overlay in the top-right corner. It **must remain visible continuously** while speaking.
2. **IDE Zoom**: In VS Code or IntelliJ, press `Ctrl + +` (zoom in) so code lines are easy to read on video.
3. **Terminal Zoom**: In PowerShell or Command Prompt, increase font size to 18pt or 20pt.
4. **Desktop Cleanup**: Close personal chat apps, tabs, and notifications.
5. **Pre-Flight Test**: Run `run.bat` or `javac -d bin src\datastructures\*.java` once to verify zero compilation errors.

---

## PART 1: System Architecture, Array Operations & Searching Algorithms

- **Presenter**: Member 1 (Lead Developer)
- **Allocated Time**: 0:00 – 4:00 (4 minutes)
- **Primary Source Files**: `Main.java`, `ArrayOperations.java`, `SearchingOperations.java`

---

### Step 1.1: Project & Team Introduction (0:00 – 0:40 | 40 seconds)

🎬 **Camera Action**: Look directly into webcam with face clearly visible.
🗣️ **What to Say**:
> *"Good day, lecturer and evaluators. My name is **A.M.Fathima Rifatha**, Student ID **23DA2-1029**.  
> I am the team leader for our 3-member group project in CIT300 Practical Assignment 2: the **Data Structure and Graph Performance Analyzer**.  
> In accordance with Section 5 and 6 of the assignment brief for a 3-member team, we combined the eight required components across our group without omitting any component.  
> My personal responsibility covered the **System Architecture and Interactive Console Framework** in `Main.java`, as well as the **Dynamic Array Operations** and **Searching Algorithms Comparison** in `ArrayOperations.java` and `SearchingOperations.java`."*

---

### Step 1.2: Code Walkthrough (0:40 – 1:50 | 70 seconds)

🎬 **Screen Action**: Switch to VS Code / IDE (webcam PiP visible).  
1. Open `Main.java`: Highlight `readInteger()` (lines 460–470) showing the `try-catch` input validation loop.
2. Open `ArrayOperations.java`: Highlight `insertAt()` (lines 45–60), `deleteAt()` (lines 79–95), and `resize()` (lines 148–152).
3. Open `SearchingOperations.java`: Highlight `linearSearch()` (lines 46–62) and `binarySearch()` (lines 71–95).

🗣️ **What to Say**:
> *"In `Main.java`, I designed the central 9-option interactive menu that unifies all data structures into one system. To ensure crash resilience, every user input passes through our `readInteger` validator. It catches `NumberFormatException` in a `try-catch` block, prompting the user again without crashing the application.  
> In `ArrayOperations.java`, I implemented a resizable array. When the array reaches capacity, the `resize()` method automatically doubles its size using `Arrays.copyOf`, providing amortized $O(1)$ insertions at the end. For arbitrary index insertions and deletions, elements are shifted with strict boundary validation.  
> In `SearchingOperations.java`, I implemented two distinct searching algorithms: sequential `linearSearch` and iterative `binarySearch`. Both methods record comparison step counts and execution time in nanoseconds. Linear search evaluates elements sequentially in $O(n)$ time, while Binary search operates in logarithmic $O(\log n)$ time by repeatedly halving the search space on sorted data."*

---

### Step 1.3: Live Console Demonstration (1:50 – 3:20 | 90 seconds)

🎬 **Screen Action**: Switch to running console terminal.

⌨️ **Keys to Press**:
1. At Main Menu: Type `1` (Array Operations).
2. Type `1` (Insert Element), enter `99`.
3. Type `6` (Display Array) $\rightarrow$ Point out `99` is appended.
4. Type `5` (Search Element), enter `99` $\rightarrow$ Point out step count and index.
5. Type `3` (Delete Element), enter `99` $\rightarrow$ Show deletion success.
6. Type `6` (Display Array) $\rightarrow$ Point out elements shifted to close the gap.
7. Type `8` (Return to Main Menu).
8. At Main Menu: Type `5` (Searching Operations).
9. Type `3` (Compare Linear vs Binary Search), enter `40`. Point out the comparison table on screen!
10. Type `4` (Return to Main Menu).

🗣️ **What to Say**:
> *"Now for the live demonstration:  
> Selecting Option 1 opens Array Operations. I insert 99, and displaying the array shows 99 added to our pre-loaded elements.  
> Searching for 99 demonstrates our step tracker, reporting the exact index and step count.  
> Deleting 99 shifts subsequent elements left to close the gap cleanly.  
> Returning to the main menu and choosing Option 5 opens Searching Operations. Choosing Option 3 compares Linear Search against Binary Search on the same dataset. Notice the comparison table: Binary Search finds the target with significantly fewer steps due to its logarithmic nature."*

---

### Step 1.4: Complexity Summary & Handover (3:20 – 4:00 | 40 seconds)

🎬 **Camera Action**: Look back at webcam.
🗣️ **What to Say**:
> *"To summarize: Array lookup by known index is $O(1)$, while search and arbitrary deletion are $O(n)$. Binary Search drastically outperforms Linear Search on large datasets because its steps grow logarithmically ($O(\log n)$) rather than linearly ($O(n)$).  
> I will now hand over to Member 2 to present the Stack, Circular Queue, and Singly Linked List data structures."*

---

## PART 2: Stack, Circular Queue & Singly Linked List Data Structures

- **Presenter**: Member 2
- **Allocated Time**: 4:00 – 8:00 (4 minutes)
- **Primary Source Files**: `StackOperations.java`, `QueueOperations.java`, `LinkedListOperations.java`

---

### Step 2.1: Face Introduction (4:00 – 4:30 | 30 seconds)

🎬 **Camera Action**: Look directly into webcam with face clearly visible.
🗣️ **What to Say**:
> *"Hello everyone and hello to our lecturer. My name is **M.S.F. Noaf**, Student ID **23DA2-0975**.  
> In our 3-member group, my assigned responsibility was implementing the core linear data structures: the **Stack**, the **Circular Queue**, and the **Singly Linked List** in `StackOperations.java`, `QueueOperations.java`, and `LinkedListOperations.java`."*

---

### Step 2.2: Code Walkthrough (4:30 – 5:50 | 80 seconds)

🎬 **Screen Action**: Open VS Code / IDE.
1. Open `StackOperations.java`: Highlight `push()` (lines 32–38), `pop()` underflow guard (lines 46–54), and vertical ASCII visualizer (lines 79–90).
2. Open `QueueOperations.java`: Highlight circular arithmetic `(rear + 1) % capacity` (lines 37–45), `dequeue()` underflow guard (lines 53–63), and `resize()` (lines 123–133).
3. Open `LinkedListOperations.java`: Highlight lines 13–21 (static `Node` inner class), `insertHead()` (lines 54–60), and `delete()` (lines 67–96).

🗣️ **What to Say**:
> *"In `StackOperations.java`, I implemented a Last-In, First-Out (LIFO) stack. The `top` pointer tracks the top element. As required by Section 2.B of the brief, we safely handle empty-stack conditions: if `isEmpty()` is true, `pop()` and `peek()` print an explicit underflow notice and return `null`, preventing application crashes.  
> In `QueueOperations.java`, I engineered a First-In, First-Out (FIFO) queue using a circular array. Modular arithmetic `(rear + 1) % capacity` wraps elements around to index 0 as items are dequeued, eliminating memory drift and shifting overhead. Underflow is guarded identically.  
> In `LinkedListOperations.java`, I built a pure custom Singly Linked List using an internal `Node` class containing an integer `data` and a `Node next` pointer reference, without relying on `java.util.LinkedList`. Inserting at the head is $O(1)$ by reassigning the head pointer, and `delete` handles empty lists, head deletion, and pointer bypass for middle/tail nodes."*

---

### Step 2.3: Live Console Demonstration (5:50 – 7:20 | 90 seconds)

🎬 **Screen Action**: Switch to running console terminal.

⌨️ **Keys to Press**:
1. At Main Menu: Type `2` (Stack Operations).
2. Type `4` (Display Stack) $\rightarrow$ Point out vertical ASCII rendering `[TOP]` to `[BASE]`.
3. Type `1` (Push), enter `500`.
4. Type `3` (Peek) $\rightarrow$ Shows `500`.
5. Type `2` (Pop) repeatedly until empty, then press `2` once more $\rightarrow$ **Point out `Error: Stack Underflow!`**.
6. Type `6` (Return to Main Menu).
7. At Main Menu: Type `3` (Queue Operations).
8. Type `4` (Display Queue) $\rightarrow$ Shows horizontal queue `[FRONT] -> ... -> [REAR]`.
9. Type `2` (Dequeue) $\rightarrow$ Removes the front element (FIFO).
10. Type `6` (Return to Main Menu).
11. At Main Menu: Type `4` (Linked List Operations).
12. Type `5` (Display) $\rightarrow$ Shows `[Head] -> [5] -> [15] -> [25] -> null`.
13. Type `2` (Insert Head), enter `1`.
14. Type `5` (Display) $\rightarrow$ Shows `1` at the head in $O(1)$ time.
15. Type `4` (Search Element), enter `15` $\rightarrow$ Shows index and node traversal steps!
16. Type `3` (Delete Element), enter `15`.
17. Type `5` (Display) $\rightarrow$ Shows `15` removed and pointers relinked: `[Head] -> [1] -> [5] -> [25] -> null`.
18. Type `6` (Return to Main Menu).

🗣️ **What to Say**:
> *"Now for the live demonstration:  
> Under Option 2, displaying the stack shows our vertical ASCII visualizer. Pushing 500 places it at the top, and peeking confirms it. Popping until empty and attempting one more pop cleanly triggers our `Stack Underflow` protection without throwing an uncaught exception.  
> Under Option 3, Queue Operations displays our horizontal FIFO structure. Dequeuing removes the front item first, confirming FIFO order.  
> Under Option 4, Linked List Operations displays our node pointer chain terminating in null. Inserting 1 at the head immediately updates the head pointer in $O(1)$ time. Searching for 15 traverses node-by-node, reporting both the index and step count. Finally, deleting 15 safely bypasses the node and relinks surrounding pointers."*

---

### Step 2.4: Complexity Summary & Handover (7:20 – 8:00 | 40 seconds)

🎬 **Camera Action**: Look back at webcam.
🗣️ **What to Say**:
> *"To summarize: Stack and Queue provide $O(1)$ constant time insertions and deletions. The Singly Linked List provides dynamic sizing without array resizing, with $O(1)$ head insertions and $O(n)$ search and traversal. Furthermore, the Queue powers BFS, and the Stack powers DFS.  
> I will now hand over to Member 3 to present our mandatory Graph component, traversals, and the integrated Performance Analyzer."*

---

## PART 3: Graph Traversals (BFS / DFS) & Performance Analyzer

- **Presenter**: Member 3
- **Allocated Time**: 8:00 – 12:00 (4 minutes)
- **Primary Source Files**: `Graph.java`, `PerformanceAnalyzer.java`

---

### Step 3.1: Face Introduction (8:00 – 8:30 | 30 seconds)

🎬 **Camera Action**: Look directly into webcam with face clearly visible.
🗣️ **What to Say**:
> *"Hello everyone and hello to our lecturer. My name is **M.R.F. Sara**, Student ID **23DA2-0679**.  
> For our 3-member team, I was responsible for the mandatory **Graph Component** and its traversal algorithms in `Graph.java`, as well as the **Performance Analyzer and Algorithmic Complexity Benchmarks** in `PerformanceAnalyzer.java`."*

---

### Step 3.2: Code Walkthrough (8:30 – 9:45 | 75 seconds)

🎬 **Screen Action**: Open VS Code / IDE.
1. Open `Graph.java`:
   - Highlight line 12 (`Map<Integer, List<Integer>> adjList`) and line 45 (`TreeMap`).
   - Highlight lines 124–156 (`bfs` using FIFO Queue).
   - Highlight lines 164–201 (`dfs` using explicit LIFO Stack).
   - Highlight lines 247–268 (`loadSampleGraph` benchmark graph).
2. Open `PerformanceAnalyzer.java`:
   - Highlight lines 16–52 (`runIntegratedComparison` Section 4 table).
   - Highlight lines 58–84 (`runLargeDatasetBenchmark` 50,000-element stress test).

🗣️ **What to Say**:
> *"In `Graph.java`, I implemented an **Adjacency List** using `Map<Integer, List<Integer>>` backed by a `TreeMap` to ensure vertices and neighbor lists remain naturally ordered for deterministic outputs.  
> For traversals:  
> - `bfs` uses a FIFO Queue to discover neighbors level-by-level, utilizing a `visited` set to avoid revisiting vertices.  
> - `dfs` uses an explicit LIFO Stack to explore deeply along each branch before backtracking.  
> Both methods return a `TraversalResult` recording the exact visit order, steps taken, and execution time in nanoseconds.  
> In `PerformanceAnalyzer.java`, I implemented the exact Performance Comparison table mandated by Section 4 of the assignment brief, as well as an empirical 50,000-element stress test to demonstrate asymptotic logarithmic speedup."*

---

### Step 3.3: Live Console Demonstration (9:45 – 11:15 | 90 seconds)

🎬 **Screen Action**: Switch to terminal.

⌨️ **Keys to Press**:
1. At Main Menu: Type `6` (Graph Operations).
2. Type `7` (Reset to Sample Assignment Benchmark Graph).
3. Type `3` (Display Graph) $\rightarrow$ Point out vertices 1 to 5 and connected neighbors.
4. Type `4` (BFS Traversal), enter start vertex `1` $\rightarrow$ Order: `[1, 2, 3, 4, 5]`.
5. Type `5` (DFS Traversal), enter start vertex `1` $\rightarrow$ Order: `[1, 2, 4, 5, 3]`.
6. Type `6` (Search Path / Reachability), enter start `1` and target `5` $\rightarrow$ Reachable!
7. Type `8` (Return to Main Menu).
8. At Main Menu: Type `8` (Display All Results) $\rightarrow$ Point out system-wide snapshot of all 5 data structures!
9. At Main Menu: Type `7` (Performance Comparison).
10. Type `1` (Run Integrated Comparison Table), enter target `30`.
    - **Highlight the exact Section 4 table displayed on screen!**
11. Type `2` (Run Stress Test Benchmark with 50,000 Elements).
    - **Highlight: Linear Search = 49,999 steps vs Binary Search = 16 steps (~3100x speedup)!**
12. Type `4` (Return to Main Menu), then type `9` (Exit).

🗣️ **What to Say**:
> *"Now for the live graph and performance demonstration:  
> Under Option 6, I reset the graph to the assignment benchmark graph with vertices 1 through 5. Displaying the graph clearly presents the adjacency list.  
> Running BFS from vertex 1 produces the level-by-level sequence: 1, 2, 3, 4, 5.  
> Running DFS from vertex 1 explores deep branches first, producing: 1, 2, 4, 5, 3.  
> Option 6 confirms vertex 5 is reachable from vertex 1.  
> Returning to the main menu, Option 8 displays a unified snapshot of all five data structures active in memory.  
> Now under Option 7, selecting Option 1 generates the assignment Section 4 Performance Comparison table: Linear Search took 3 steps, Binary Search took 1 step, and both BFS and DFS visited 5 vertices in 15 steps.  
> Finally, Option 2 executes our 50,000-element stress test: Linear Search took 49,999 steps, while Binary Search solved it in only 16 steps—demonstrating an empirical speedup of over 3,100 times!"*

---

### Step 3.4: Group Conclusion & Wrap-Up (11:15 – 12:00 | 45 seconds)

🎬 **Camera Action**: Look directly into webcam.
🗣️ **What to Say**:
> *"To conclude our 3-member group presentation:  
> Our project fully satisfies every requirement of CIT300 Practical Assignment 2:  
> - All linear and non-linear data structures, searching, and graph traversals are fully implemented without omitting any component.  
> - Underflow and overflow conditions are handled safely without exceptions.  
> - Performance metrics and step counters match Section 4 of the assignment specification.  
> - And our team collaboration history is maintained across 3 dedicated feature branches and merge pull requests on GitHub.  
> Thank you very much for your time and evaluation!"*

---

## Technical Viva Q&A Defense Guide (For All 3 Members)

| Potential Viva Question | Model Answer | Best Suited Member |
| :--- | :--- | :---: |
| **Why does Binary Search require a sorted array?** | Binary Search relies on the order invariant ($arr[mid] < target$ or $> target$) to eliminate half the array in each comparison. If unsorted, the target could lie in either half, rendering the division invalid. | Member 1 |
| **How does your circular queue prevent array memory waste?** | In a linear array queue, `front` shifts forward during dequeue, leaving unused space at the beginning. A circular array uses `(rear + 1) % capacity` to wrap back to index 0 when space is available. | Member 2 |
| **Why is deleting from an Array $O(n)$ while deleting from a Linked List head is $O(1)$?** | Array elements are stored contiguously; deleting an element requires shifting subsequent elements forward. In a Linked List, deleting the head only requires reassigning the `head` pointer reference to `head.next`. | Member 2 |
| **Why is BFS implemented with a Queue, but DFS with a Stack?** | BFS requires exploring nodes layer-by-layer (FIFO), which is natural for a Queue. DFS explores deepest descendants first before backtracking (LIFO), which requires a Stack (or recursion call stack). | Member 3 |
| **What is the time and space complexity of BFS and DFS on an adjacency list?** | Time complexity is $O(V + E)$ because each vertex is visited once, and each edge is inspected. Space complexity is $O(V)$ for the visited set and the queue/stack data structure. | Member 3 |
| **How did your 3-member team divide and combine responsibilities?** | As permitted by Section 6 of the brief, Member 1 handled Array, Searching & Main Console Integration; Member 2 handled Stack, Circular Queue & Linked List; and Member 3 handled Graph & Performance Analyzer. | Any Member |
