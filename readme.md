# 🎬 redemption-arc

### *From "we'll keep your resume on file" to "when can you start?"*

> **Mission:** Deep-dive into algorithm patterns, SQL fundamentals, and ship a full-stack Spring Boot project to land a software engineering role by end of January. This is the training montage. The dramatic music is playing. The interviewer doesn't stand a chance.

**Start Date:** Week of December 9, 2024  
**MVP Deadline:** December 31, 2024 — Project on resume, deployed, ready to demo  
**Daily Commitment:** 3-4 hours focused work  
**Philosophy:** Depth over breadth. Ship fast. Iterate in January.  
**Vibe:** Rocky running up the steps, but the steps are LeetCode problems and the meat punching is Spring Boot controllers.  
**Language:** Java ☕ — Because we're going full enterprise-ready for this redemption arc.

---

## 📍 Quick Navigation

> *Jump around like your career depends on it (because it does)*

### Main Sections

- [📚 Resources](#-resources)
- [☕ Java Quick Reference](#-java-quick-reference) ← *Your new best friend*
- [🗓️ Daily Structure](#%EF%B8%8F-daily-structure)
- [📋 Weekly Overview](#-weekly-overview)

### The Training Arc

| Week | Topic | Link |
|------|-------|------|
| 1 | **Arrays & Hashing + Interview Prep Sprint** | [Week 1](#week-1-arrays--hashing--interview-prep-sprint) |
| 2 | Two Pointers & Project Setup | [Week 2](#week-2-two-pointers--project-setup) |
| 3 | Sliding Window & Binary Search | [Week 3](#week-3-sliding-window--binary-search) |
| 4 | Stacks, Linked Lists & React Setup | [Week 4](#week-4-stacks-linked-lists--react-setup) |
| 5 | Trees & **MVP SHIP** | [Week 5](#week-5-trees--mvp-ship-) |
| 6 | Trees (Advanced) & Graphs | [Week 6](#week-6-trees-advanced--graphs) |
| 7 | Backtracking & Heaps | [Week 7](#week-7-backtracking--heaps) |
| 8 | Dynamic Programming | [Week 8](#week-8-dynamic-programming) |

### The Finale

- [📊 Progress Tracker](#-progress-tracker)
- [🎬 The Climax](#-the-climax)
- [💡 Daily Reminders](#-daily-reminders)
- [🎬 Credits](#-credits)

---

## 📚 Resources

[↑ Back to Navigation](#-quick-navigation)

### Algorithms

- **CTCI 6th Edition** — Theory companion for each topic
- **NeetCode.io** — Video explanations when stuck
- **LeetCode** — All practice problems

### SQL

- **Learning SQL, 3rd Edition by Alan Beaulieu** — Chapters 2-9 (fundamentals focused)
- **PostgreSQL** — Your database of choice

### Spring Boot & Backend

- **Spring Initializr** — https://start.spring.io (Spring Web, JDBC, PostgreSQL Driver)
- **Spring Guides** — https://spring.io/guides/gs/relational-data-access/
- **Baeldung** — https://www.baeldung.com/spring-jdbc-jdbctemplate (JDBC patterns)

### React

- **React Docs** — https://react.dev/learn (Quick Start + Tutorial)
- **Vite** — https://vitejs.dev/guide/ (Project setup)

### Your Project

- **Ticket Support System** — Full-stack: Spring Boot + JDBC + PostgreSQL + React
- **MVP by Dec 31** — Deploy and put on resume
- **January** — Add features, polish, interview prep

---

## ☕ Java Quick Reference

[↑ Back to Navigation](#-quick-navigation)

> *Keep this open in another tab. You'll need it. Trust the redemption arc.*

### Essential Imports

```java
import java.util.*;  // List, Map, Set, Queue, PriorityQueue, etc.
import java.util.stream.*;  // For stream operations
```

### Data Structure Initialization

```java
// Arrays
int[] arr = new int[10];
int[] arr = {1, 2, 3, 4, 5};
int[][] matrix = new int[m][n];

// ArrayList
List<Integer> list = new ArrayList<>();
List<String> list = new ArrayList<>(Arrays.asList("a", "b", "c"));

// HashMap
Map<Integer, Integer> map = new HashMap<>();
Map<String, List<Integer>> map = new HashMap<>();
map.put(key, value);
map.get(key);
map.getOrDefault(key, defaultValue);
map.containsKey(key);
map.keySet();  // iterate keys
map.values();  // iterate values
map.entrySet();  // iterate key-value pairs

// HashSet
Set<Integer> set = new HashSet<>();
set.add(value);
set.contains(value);
set.remove(value);

// Queue (LinkedList or ArrayDeque)
Queue<Integer> queue = new LinkedList<>();
Queue<Integer> queue = new ArrayDeque<>();  // faster
queue.offer(value);  // add to back
queue.poll();  // remove from front
queue.peek();  // look at front

// Stack (use Deque)
Deque<Integer> stack = new ArrayDeque<>();
stack.push(value);  // add to top
stack.pop();  // remove from top
stack.peek();  // look at top

// PriorityQueue (min heap by default)
PriorityQueue<Integer> minHeap = new PriorityQueue<>();
PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
// Custom comparator
PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
pq.offer(value);
pq.poll();
pq.peek();
```

### Common Operations

```java
// Array sorting
Arrays.sort(arr);  // ascending
Arrays.sort(arr, Collections.reverseOrder());  // descending (Integer[] only)
Arrays.sort(arr, (a, b) -> b - a);  // descending with comparator

// List sorting
Collections.sort(list);
list.sort((a, b) -> a - b);
list.sort(Comparator.comparingInt(a -> a[0]));  // sort by first element

// String operations
String s = "hello";
char[] chars = s.toCharArray();
String reversed = new StringBuilder(s).reverse().toString();
s.substring(start, end);  // end is exclusive
s.charAt(index);
s.length();
String.valueOf(num);  // int to string
Integer.parseInt(str);  // string to int

// StringBuilder (for string manipulation)
StringBuilder sb = new StringBuilder();
sb.append("text");
sb.insert(index, "text");
sb.deleteCharAt(index);
sb.setCharAt(index, 'c');
sb.toString();

// Array to List
List<Integer> list = Arrays.stream(arr).boxed().collect(Collectors.toList());
// List to Array
int[] arr = list.stream().mapToInt(i -> i).toArray();

// Math
Math.max(a, b);
Math.min(a, b);
Math.abs(a);
Integer.MAX_VALUE;
Integer.MIN_VALUE;

// Character checks
Character.isLetterOrDigit(c);
Character.isLetter(c);
Character.isDigit(c);
Character.toLowerCase(c);
Character.toUpperCase(c);
```

### Iteration Patterns

```java
// Array
for (int i = 0; i < arr.length; i++) { }
for (int num : arr) { }

// List
for (int i = 0; i < list.size(); i++) { }
for (Integer num : list) { }

// Map
for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
    int key = entry.getKey();
    int value = entry.getValue();
}
for (Integer key : map.keySet()) { }

// 2D Array
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[0].length; j++) { }
}

// Four directions (grid problems)
int[][] directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
for (int[] dir : directions) {
    int newRow = row + dir[0];
    int newCol = col + dir[1];
}
```

### Common Gotchas

```java
// Integer comparison (use .equals() for Integer objects!)
Integer a = 128, b = 128;
a == b;  // FALSE! (reference comparison)
a.equals(b);  // TRUE (value comparison)

// Array copy
int[] copy = arr.clone();
int[] copy = Arrays.copyOf(arr, arr.length);

// List copy
List<Integer> copy = new ArrayList<>(original);

// Null checks
if (root == null) return;
if (list == null || list.isEmpty()) return;
```

---

## 🗓️ Daily Structure

[↑ Back to Navigation](#-quick-navigation)

*Every redemption arc needs a training montage. This is yours.*

| Time Block | Activity |
|------------|----------|
| **Morning (2 hrs)** | Algorithm problems (3-4 problems) |
| **Afternoon (1.5 hrs)** | Project work (Spring Boot / React) + SQL reading |
| **Evening (30 min)** | Review templates, job applications |

**Sundays:** Review week's templates from memory. Re-attempt any problems you struggled with. Stare dramatically out a window contemplating your journey.

---

## 📋 Weekly Overview

[↑ Back to Navigation](#-quick-navigation)

| Week | Algorithm Topics | Problems | CTCI Chapters | SQL Chapters | Project Milestone |
|------|------------------|----------|---------------|--------------|-------------------|
| 1 | **Arrays & Hashing + Interview Prep** | 10 ✓ | Ch 1 ✓ | Ch 2-4 | ACID, ETL, behavioral |
| 2 | Two Pointers + Remaining Arrays | 20 | Ch 1 (cont.) | Ch 5 | Schema + Spring Boot skeleton |
| 3 | Sliding Window, Binary Search | 20 | Ch 3, 10 | Ch 6-7 | JDBC repos + REST endpoints |
| 4 | Stacks, Linked Lists | 20 | Ch 2 | Ch 8-9 | React basics + API integration |
| 5 | Trees (Basics + Advanced) | 20 | Ch 4 | — | **MVP COMPLETE + DEPLOY** |
| 6 | Trees (cont.) & Graphs | 20 | Ch 4 (cont.) | — | Feature: Comments system |
| 7 | Backtracking & Heaps | 20 | Ch 8 | — | Feature: Dashboard metrics |
| 8 | Dynamic Programming | 20 | Ch 8 (cont.) | — | Polish + interview prep |

**Total: 150 algorithm problems + SQL fundamentals + deployed full-stack project**

---

# Week 1: Arrays & Hashing + Interview Prep Sprint

### *Act I: The Hero Completes Arrays, Then Gets Called to Adventure*

[↑ Back to Navigation](#-quick-navigation)

> **Context:** Started the week grinding LeetCode. Then BNBuilders called. Now pivoting to interview prep for Monday while keeping momentum.

## ✅ Already Completed (Early Week)

### CTCI Chapter 1: Arrays and Strings
- Hash table fundamentals
- String manipulation techniques
- Big O for array operations

### LeetCode Problems 1-10
1. **Two Sum** — Hash map lookup pattern ✓
2. **Contains Duplicate** — Set membership ✓
3. **Valid Anagram** — Frequency counter comparison ✓
4. **Two Sum II - Input Array Is Sorted** — Precursor to two pointers ✓
5. **Majority Element** — Boyer-Moore or hash map ✓
6. **Contains Duplicate II** — Hash map with index tracking ✓
7. **Missing Number** — Math or XOR approach ✓
8. **Find All Numbers Disappeared in Array** — In-place marking ✓
9. **Group Anagrams** — Hash map with sorted key ✓
10. **Top K Frequent Elements** — Hash map + heap or bucket sort ✓

---

## 🎯 Interview Prep Sprint (Weekend Focus)

> **Target:** BNBuilders Data Engineer interview. One hour, in-person, Seattle. This weekend is 100% focused on being ready for Monday.

## The Role

**Company:** BNBuilders (General Contractor)  
**Position:** Data Engineer  
**Salary:** $80,000 - $85,000  
**Tech Stack (from job posting):**
- Azure Data Factory (ETL/ELT)
- Power BI (data visualization)
- Data warehousing & data modeling
- Transactional database development
- 3rd party API integrations

**What they want:** Someone who can work with business units, gather requirements, build data solutions, and communicate findings to stakeholders at all levels.

## Thursday Night: Foundation

### ACID Properties (Know This Cold)

**A - Atomicity**
- All or nothing. A transaction either completes entirely or fails entirely.
- Example: Transferring money between accounts. Both the debit AND credit must succeed, or neither happens.

**C - Consistency**
- Database moves from one valid state to another valid state.
- All rules, constraints, and triggers are satisfied before and after the transaction.
- Example: If a foreign key constraint exists, you can't insert a ticket referencing a non-existent user.

**I - Isolation**
- Concurrent transactions don't interfere with each other.
- Each transaction appears to run in isolation, even if many are running simultaneously.
- Example: Two agents updating the same ticket simultaneously won't corrupt the data.

**D - Durability**
- Once a transaction is committed, it stays committed.
- Even if the system crashes, the data persists (written to disk, not just memory).
- Example: After a ticket is saved, a power outage won't lose it.

**Interview Tip:** If asked about ACID, explain it conversationally:
> "ACID ensures database reliability. Atomicity means transactions are all-or-nothing. Consistency keeps the database in a valid state. Isolation prevents concurrent transactions from interfering. Durability guarantees committed data survives crashes."

### Learning SQL

**Chapter 2: Creating and Populating a Database** — CREATE TABLE, INSERT, data types  
**Chapter 3: Query Primer** — SELECT basics, WHERE, ORDER BY, LIMIT  
**Chapter 4: Filtering** — WHERE conditions, AND/OR/NOT, BETWEEN, IN, LIKE

### Company Research

- [ ] Skim BNBuilders website
- [ ] Look at recent Seattle projects (life science, healthcare, higher ed, corporate tech)
- [ ] Understand: they're a construction company, not a tech company. Data supports project management.

## Friday: ETL Deep Dive

### What is ETL?

**E - Extract**
- Pull data from source systems
- Sources: databases, APIs, flat files (CSV, JSON), spreadsheets, web scraping
- Example: Pulling project data from a construction management system

**T - Transform**
- Clean, validate, reshape the data
- Operations: filtering, joining, aggregating, type conversion, handling nulls
- Example: Standardizing date formats, converting currencies, removing duplicates

**L - Load**
- Put the transformed data into a destination
- Destinations: data warehouse, database, data lake, BI tool
- Example: Loading cleaned project metrics into a Power BI dashboard

**ELT vs ETL:**
- ETL: Transform before loading (traditional)
- ELT: Load raw data first, transform in the warehouse (modern, cloud-native)
- Azure Data Factory supports both patterns

### Your Projects ARE ETL Pipelines

**Naive Bayes Sentiment Classifier:**
- **Extract:** Loaded movie review dataset
- **Transform:** Tokenization, stopword removal, Porter stemming, Laplace smoothing
- **Load:** Fed into classifier for predictions

**Markov Chain System Analysis:**
- **Extract:** Input system state data
- **Transform:** Matrix computations, probability calculations
- **Load:** Output steady-state distributions

**Frame it this way in the interview:**
> "While I haven't used Azure Data Factory specifically, I've built data pipelines in my coursework. For example, my NLP project involved extracting review data, transforming it through tokenization and stemming, and loading it into a Bayesian classifier. The concepts transfer—I'd just need to learn the specific tooling."

### SQL Practice

Focus on:
- JOINs (INNER, LEFT, RIGHT)
- GROUP BY with HAVING
- Subqueries
- Window functions (bonus, but good to know conceptually)

### ETL Hands-On Exercise (Optional)

If you have time, do a simple Python + PostgreSQL exercise:
1. Create a CSV with sample data
2. Write a Python script that reads the CSV (Extract)
3. Clean/transform the data (Transform)
4. Insert into PostgreSQL (Load)

## Saturday: Projects + Behavioral

### Project Deep Dive

For each project, be ready to explain:
1. **What problem did it solve?** (1 sentence)
2. **What was your approach?** (2-3 sentences)
3. **What was the hardest part?** (1-2 sentences)
4. **What did you learn?** (1 sentence)

**SHA3-SHAKE Cryptographic Library:**
- Implemented SHA-3 hash functions following FIPS 202 spec
- Built CLI for file hashing, MAC generation, encryption/decryption
- Hardest part: Understanding the Keccak permutation math
- Learned: Low-level bit manipulation, following technical specifications

**Naive Bayes Sentiment Classifier:**
- Built NLP pipeline to classify movie review sentiment
- Used NLTK for preprocessing, implemented Naive Bayes from scratch
- Hardest part: Handling edge cases with Laplace smoothing
- Learned: Statistical modeling, text preprocessing fundamentals

**j-- Compiler Extension:**
- Extended a Java compiler to support additional language features
- Added multi-line comments, operators, loops, exception handling
- Hardest part: Grammar rules and AST node generation
- Learned: How compilers parse and process code

### Behavioral Stories (STAR Format)

**Leadership Under Pressure (Navy):**
- **S:** Mount Captain for .50 cal gun crew during live FIAC intercept
- **T:** Direct target identification and engagement with 3-4 personnel
- **A:** Maintained clear communication, followed procedures under stress
- **R:** Zero mission failures, crew performed safely

**Teaching Complex Concepts (Mathnasium):**
- **S:** Student struggling with algebra concepts, getting frustrated
- **T:** Help them understand without making them feel dumb
- **A:** Found analogy that connected to their interests, broke it into smaller steps
- **R:** Student had "aha" moment, improved confidence and grades

**Stakeholder Communication (Mathnasium):**
- **S:** Presenting diagnostic assessment results to skeptical parent
- **T:** Explain learning gaps and recommend program without being salesy
- **A:** Used specific examples, showed data, connected to parent's goals for child
- **R:** Parent enrolled, student succeeded in program

### Questions to Ask Them

1. What does the current data infrastructure look like?
2. What kinds of problems would I be solving in the first few months?
3. How does the data team collaborate with project managers and field teams?
4. What's the biggest data challenge the company is facing right now?
5. What does success look like in this role at 6 months? 1 year?

## Sunday: Mock Interview + Rest

### Mock Interview Topics

Practice answering out loud:

1. **Tell me about yourself.** (2 minutes max)
   - Navy veteran, CS degree from UW Tacoma, teaching background
   - Technical skills: Java, Python, SQL, databases
   - Why you're excited about this role

2. **Walk me through a data project.**
   - Pick one (NLP classifier is probably best for this role)
   - Use the structure from Saturday's prep

3. **What is ACID?**
   - Explain conversationally, give examples

4. **What is ETL?**
   - Define each step, explain where you've done similar work

5. **Why BNBuilders?**
   - Construction is tangible—you can see the impact of your work
   - Diverse sectors (healthcare, higher ed, life science, tech) = variety
   - Data is increasingly critical in construction (schedules, budgets, resources)
   - You want to grow with a company, not just take a job

6. **Why should we hire you?**
   - Technical foundation + communication skills
   - Teaching experience = ability to explain complex things simply
   - Military discipline = reliability, attention to detail
   - Fast learner, coachable, eager to contribute

### Final Checklist

- [ ] ACID: Can explain all four properties with examples
- [ ] ETL: Can define and relate to your own projects
- [ ] SQL: Comfortable with SELECT, JOIN, GROUP BY, WHERE
- [ ] Projects: Can explain each in under 2 minutes
- [ ] Behavioral: Have 3 STAR stories ready
- [ ] Questions: Have 3-5 questions for them
- [ ] Logistics: Know where the office is, what to wear, arrive 10 min early

### Rest

Get good sleep. You're ready.

---

## Week 1 Tasks

### Already Completed (Early Week)
- [x] Read CTCI Chapter 1
- [x] Complete LeetCode problems 1-10 (Two Sum through Find All Numbers Disappeared)

### Interview Prep Sprint (Weekend Focus)
- [ ] Read Learning SQL Chapter 2
- [ ] Read Learning SQL Chapter 3
- [ ] Read Learning SQL Chapter 4
- [ ] Learn ACID properties (can explain from memory)
- [ ] Understand ETL concepts (can relate to your projects)
- [ ] Review your projects (can explain each in 2 min)
- [ ] Prepare behavioral STAR stories (3 ready)
- [ ] Research BNBuilders (website, recent projects)
- [ ] Prepare questions for interviewer (3-5)
- [ ] Mock interview practice (out loud)

---

# Week 2: Two Pointers & Project Setup

### *Act I Continued: The Pointers Point Both Ways (And the Project Begins)*

[↑ Back to Navigation](#-quick-navigation)

> **Note:** This week picks up remaining LeetCode from Week 1, adds Two Pointers, and gets the project started. You've got momentum from the interview.

## CTCI Reading

**Chapter 1 (continued):** Focus on in-place manipulation, string problems

## Learning SQL

**Chapter 5: Querying Multiple Tables** — INNER JOIN, table aliases

## Templates to Memorize

### Hash Map Frequency Counter

```java
public Map<Integer, Integer> frequencyCount(int[] arr) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int num : arr) {
        freq.put(num, freq.getOrDefault(num, 0) + 1);
    }
    return freq;
}
```

**Use for:** Anagrams, duplicates, counting problems, two-sum variants

### Hash Set for O(1) Lookup

```java
public boolean hasDuplicate(int[] arr) {
    Set<Integer> seen = new HashSet<>();
    for (int num : arr) {
        if (seen.contains(num)) {
            return true;
        }
        seen.add(num);
    }
    return false;
}
```

**Use for:** Duplicate detection, membership testing, complement finding

### Prefix Sum Array

```java
public int[] prefixSum(int[] arr) {
    int[] prefix = new int[arr.length + 1];
    for (int i = 0; i < arr.length; i++) {
        prefix[i + 1] = prefix[i] + arr[i];
    }
    // Range sum [i, j] = prefix[j+1] - prefix[i]
    return prefix;
}
```

**Use for:** Range sum queries, subarray sums

### Two Pointers — Opposite Ends

```java
public int[] twoSumSorted(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left < right) {
        int sum = arr[left] + arr[right];
        if (sum == target) {
            return new int[]{left, right};
        } else if (sum < target) {
            left++;
        } else {
            right--;
        }
    }
    return new int[]{};
}
```

**Use for:** Two-sum on sorted array, container problems, palindrome validation

### Two Pointers — Same Direction (Fast/Slow)

```java
public int removeDuplicates(int[] arr) {
    if (arr.length == 0) return 0;
    int slow = 0;
    for (int fast = 1; fast < arr.length; fast++) {
        if (arr[fast] != arr[slow]) {
            slow++;
            arr[slow] = arr[fast];
        }
    }
    return slow + 1;
}
```

**Use for:** Remove duplicates, partitioning, linked list cycle detection

## LeetCode Problems (20)

### Remaining Arrays & Hashing (10 problems)

11. **Product of Array Except Self** — Prefix/suffix products
12. **Valid Sudoku** — Hash sets for rows, cols, boxes
13. **Encode and Decode Strings** — Delimiter strategy
14. **Longest Consecutive Sequence** — Hash set with sequence building
15. **Subarray Sum Equals K** — Prefix sum + hash map
16. **Find All Duplicates in an Array** — In-place index marking
17. **Sort Colors** — Dutch National Flag (three-way partition)
18. **Set Matrix Zeroes** — In-place markers
19. **First Missing Positive** (Hard) — Cyclic sort / index as hash
20. **Longest Substring with At Most K Distinct Characters** (Hard) — Hash map sliding window intro

### Two Pointers (10 problems)

21. **Valid Palindrome** (Easy) — Two pointers opposite ends with char filtering
22. **Two Sum II - Sorted Array** (Medium) — Classic opposite ends
23. **3Sum** (Medium) — Sort + two pointers with outer loop
24. **Container With Most Water** (Medium) — Greedy two pointers
25. **Trapping Rain Water** (Hard) — Two pointers or stack
26. **Remove Duplicates from Sorted Array** (Easy) — Same direction
27. **Remove Element** (Easy) — Same direction partition
28. **Move Zeroes** (Easy) — Same direction swap
29. **Squares of a Sorted Array** (Easy) — Two pointers merge
30. **Boats to Save People** (Medium) — Greedy two pointers

## Project: Ticket Support System — Week 2

### Goals

- [ ] Set up PostgreSQL database
- [ ] Create schema
- [ ] Set up Spring Boot project
- [ ] Create model classes

### Database Schema

```sql
-- Create the database
CREATE DATABASE ticket_support;

-- Users table
CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    full_name VARCHAR(100) NOT NULL,
    role VARCHAR(20) CHECK (role IN ('customer', 'agent', 'admin')) DEFAULT 'customer',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tickets table
CREATE TABLE tickets (
    ticket_id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(user_id),
    subject VARCHAR(255) NOT NULL,
    description TEXT,
    status VARCHAR(20) CHECK (status IN ('open', 'in_progress', 'resolved', 'closed')) DEFAULT 'open',
    priority VARCHAR(10) CHECK (priority IN ('low', 'medium', 'high', 'urgent')) DEFAULT 'medium',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Categories table
CREATE TABLE categories (
    category_id SERIAL PRIMARY KEY,
    name VARCHAR(50) UNIQUE NOT NULL,
    description TEXT
);

-- Add category reference to tickets
ALTER TABLE tickets ADD COLUMN category_id INTEGER REFERENCES categories(category_id);

-- Ticket assignments (agents assigned to tickets)
CREATE TABLE ticket_assignments (
    assignment_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id),
    agent_id INTEGER REFERENCES users(user_id),
    assigned_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Spring Boot Setup

1. **Go to start.spring.io** with these dependencies:
   - Spring Web
   - Spring JDBC
   - PostgreSQL Driver

2. **Project structure:**
```
src/main/java/com/ticketsupport/
├── TicketSupportApplication.java
├── controller/
├── service/
├── repository/
├── model/
└── config/
```

3. **application.properties:**
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/ticket_support
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### Week 2 Tasks

- [ ] Read Learning SQL Chapter 5
- [ ] Memorize 5 templates from memory
- [ ] Complete 20 LeetCode problems (11-30 total)
- [ ] Install PostgreSQL locally
- [ ] Create ticket_support database
- [ ] Create all tables (users, tickets, categories, ticket_assignments)
- [ ] Insert 20+ sample users
- [ ] Insert 50+ sample tickets
- [ ] Generate Spring Boot project from start.spring.io
- [ ] Set up project structure
- [ ] Configure database connection
- [ ] Create model classes: User, Ticket, Category

---

# Week 3: Sliding Window & Binary Search

### *Act II: The Windows Slide and the Search Gets Binary*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 3: Stacks and Queues** — Stack operations, implementing with arrays/linked lists  
**Chapter 10: Sorting and Searching** — Binary search fundamentals

## Learning SQL

**Chapter 6: Working with Sets** — UNION, INTERSECT, EXCEPT  
**Chapter 7: Data Generation, Manipulation, and Conversion** — String/number/date functions

## Templates to Memorize

### Fixed-Size Sliding Window

```java
public int maxSumSubarray(int[] arr, int k) {
    int windowSum = 0;
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }
    int maxSum = windowSum;
    for (int i = k; i < arr.length; i++) {
        windowSum += arr[i] - arr[i - k];
        maxSum = Math.max(maxSum, windowSum);
    }
    return maxSum;
}
```

### Variable-Size Sliding Window

```java
public int minSubarrayLen(int target, int[] arr) {
    int left = 0, windowSum = 0;
    int minLen = Integer.MAX_VALUE;
    for (int right = 0; right < arr.length; right++) {
        windowSum += arr[right];
        while (windowSum >= target) {
            minLen = Math.min(minLen, right - left + 1);
            windowSum -= arr[left];
            left++;
        }
    }
    return minLen == Integer.MAX_VALUE ? 0 : minLen;
}
```

### Binary Search — Find Exact Value

```java
public int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) {
            return mid;
        } else if (arr[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1;
}
```

### Binary Search — Find Boundary

```java
public int binarySearchBoundary(int[] arr) {
    int left = 0, right = arr.length;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (condition(mid)) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }
    return left;
}
```

## LeetCode Problems (20)

### Sliding Window (10 problems)

1. **Best Time to Buy and Sell Stock** (Easy)
2. **Maximum Average Subarray I** (Easy)
3. **Longest Substring Without Repeating Characters** (Medium)
4. **Longest Repeating Character Replacement** (Medium)
5. **Permutation in String** (Medium)
6. **Minimum Size Subarray Sum** (Medium)
7. **Fruit Into Baskets** (Medium)
8. **Max Consecutive Ones III** (Medium)
9. **Minimum Window Substring** (Hard)
10. **Sliding Window Maximum** (Hard)

### Binary Search (10 problems)

11. **Binary Search** (Easy)
12. **Search Insert Position** (Easy)
13. **Guess Number Higher or Lower** (Easy)
14. **First Bad Version** (Easy)
15. **Find Minimum in Rotated Sorted Array** (Medium)
16. **Search in Rotated Sorted Array** (Medium)
17. **Search a 2D Matrix** (Medium)
18. **Koko Eating Bananas** (Medium)
19. **Find Peak Element** (Medium)
20. **Median of Two Sorted Arrays** (Hard)

## Project: Week 3 — JDBC Repository Layer

### Goals

- [ ] Build JDBC repository layer
- [ ] Create REST controllers
- [ ] Implement basic CRUD operations

### Repository Layer

```java
@Repository
public class TicketRepository {
    
    @Autowired
    private JdbcTemplate jdbcTemplate;
    
    public List<Ticket> findAll() {
        return jdbcTemplate.query(
            "SELECT * FROM tickets ORDER BY created_at DESC",
            new TicketRowMapper()
        );
    }
    
    public Optional<Ticket> findById(Long id) {
        List<Ticket> results = jdbcTemplate.query(
            "SELECT * FROM tickets WHERE ticket_id = ?",
            new TicketRowMapper(),
            id
        );
        return results.isEmpty() ? Optional.empty() : Optional.of(results.get(0));
    }
    
    public Ticket save(Ticket ticket) {
        jdbcTemplate.update(
            "INSERT INTO tickets (user_id, subject, description, status, priority) VALUES (?, ?, ?, ?, ?)",
            ticket.getUserId(),
            ticket.getSubject(),
            ticket.getDescription(),
            ticket.getStatus(),
            ticket.getPriority()
        );
        return ticket;
    }
}
```

### REST Controller

```java
@RestController
@RequestMapping("/api/tickets")
public class TicketController {
    
    @Autowired
    private TicketService ticketService;
    
    @GetMapping
    public List<Ticket> getAllTickets() {
        return ticketService.findAll();
    }
    
    @GetMapping("/{id}")
    public ResponseEntity<Ticket> getTicket(@PathVariable Long id) {
        return ticketService.findById(id)
            .map(ResponseEntity::ok)
            .orElse(ResponseEntity.notFound().build());
    }
    
    @PostMapping
    public Ticket createTicket(@RequestBody Ticket ticket) {
        return ticketService.save(ticket);
    }
}
```

### Week 3 Tasks

- [ ] Read CTCI Chapters 3, 10
- [ ] Read Learning SQL Chapters 6-7
- [ ] Memorize 4 templates
- [ ] Complete 20 LeetCode problems
- [ ] Create TicketRepository with JDBC
- [ ] Create UserRepository with JDBC
- [ ] Create TicketService layer
- [ ] Create TicketController
- [ ] Create UserController
- [ ] Test endpoints with Postman

---

# Week 4: Stacks, Linked Lists & React Setup

### *Act II Continued: The Stack Overflows and React Renders*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 2: Linked Lists** — Runner technique, recursive approaches

## Learning SQL

**Chapter 8: Grouping and Aggregates** — GROUP BY, HAVING, COUNT, SUM, AVG  
**Chapter 9: Subqueries** — Scalar, correlated, EXISTS

## Templates to Memorize

### Monotonic Stack

```java
public int[] nextGreaterElement(int[] arr) {
    int n = arr.length;
    int[] result = new int[n];
    Arrays.fill(result, -1);
    Deque<Integer> stack = new ArrayDeque<>();
    
    for (int i = 0; i < n; i++) {
        while (!stack.isEmpty() && arr[i] > arr[stack.peek()]) {
            result[stack.pop()] = arr[i];
        }
        stack.push(i);
    }
    return result;
}
```

### Stack for Matching

```java
public boolean validParentheses(String s) {
    Deque<Character> stack = new ArrayDeque<>();
    Map<Character, Character> mapping = Map.of(')', '(', '}', '{', ']', '[');
    
    for (char c : s.toCharArray()) {
        if (mapping.containsKey(c)) {
            if (stack.isEmpty() || stack.peek() != mapping.get(c)) {
                return false;
            }
            stack.pop();
        } else {
            stack.push(c);
        }
    }
    return stack.isEmpty();
}
```

### Linked List Reversal

```java
public ListNode reverseList(ListNode head) {
    ListNode prev = null;
    ListNode curr = head;
    while (curr != null) {
        ListNode nextTemp = curr.next;
        curr.next = prev;
        prev = curr;
        curr = nextTemp;
    }
    return prev;
}
```

### Fast/Slow Pointers

```java
public ListNode findMiddle(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;
}
```

## LeetCode Problems (20)

### Stacks (10 problems)

1. **Valid Parentheses** (Easy)
2. **Min Stack** (Medium)
3. **Evaluate Reverse Polish Notation** (Medium)
4. **Daily Temperatures** (Medium)
5. **Next Greater Element I** (Easy)
6. **Next Greater Element II** (Medium)
7. **Simplify Path** (Medium)
8. **Basic Calculator II** (Medium)
9. **Decode String** (Medium)
10. **Largest Rectangle in Histogram** (Hard)

### Linked Lists (10 problems)

11. **Reverse Linked List** (Easy)
12. **Merge Two Sorted Lists** (Easy)
13. **Linked List Cycle** (Easy)
14. **Linked List Cycle II** (Medium)
15. **Remove Nth Node From End** (Medium)
16. **Reorder List** (Medium)
17. **Middle of the Linked List** (Easy)
18. **Palindrome Linked List** (Easy)
19. **Add Two Numbers** (Medium)
20. **Copy List with Random Pointer** (Medium)

## Project: Week 4 — React Frontend

### React Setup

```bash
npm create vite@latest ticket-frontend -- --template react
cd ticket-frontend
npm install axios
npm run dev
```

### API Service

```javascript
// src/services/api.js
import axios from 'axios';

const API_BASE = import.meta.env.VITE_API_URL || 'http://localhost:8080/api';

export const ticketService = {
    getAll: () => axios.get(`${API_BASE}/tickets`),
    getById: (id) => axios.get(`${API_BASE}/tickets/${id}`),
    create: (ticket) => axios.post(`${API_BASE}/tickets`, ticket),
    update: (id, ticket) => axios.put(`${API_BASE}/tickets/${id}`, ticket),
};
```

### Enable CORS

```java
@Configuration
public class CorsConfig implements WebMvcConfigurer {
    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/api/**")
            .allowedOrigins("http://localhost:5173")
            .allowedMethods("GET", "POST", "PUT", "DELETE");
    }
}
```

### Week 4 Tasks

- [ ] Read CTCI Chapter 2
- [ ] Read Learning SQL Chapters 8-9
- [ ] Memorize 4 templates
- [ ] Complete 20 LeetCode problems
- [ ] Set up Vite + React project
- [ ] Create api.js service layer
- [ ] Build TicketList component
- [ ] Build TicketForm component
- [ ] Add CORS config to Spring Boot
- [ ] Get basic list view working

---

# Week 5: Trees & MVP SHIP 🚀

### *Act III: The Hero Ships*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 4: Trees and Graphs** — Tree traversals, BST properties

## Templates to Memorize

### Tree DFS

```java
public List<Integer> inorder(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;
    result.addAll(inorder(root.left));
    result.add(root.val);
    result.addAll(inorder(root.right));
    return result;
}
```

### Tree BFS

```java
public List<List<Integer>> levelOrder(TreeNode root) {
    List<List<Integer>> result = new ArrayList<>();
    if (root == null) return result;
    
    Queue<TreeNode> queue = new LinkedList<>();
    queue.offer(root);
    
    while (!queue.isEmpty()) {
        int levelSize = queue.size();
        List<Integer> level = new ArrayList<>();
        
        for (int i = 0; i < levelSize; i++) {
            TreeNode node = queue.poll();
            level.add(node.val);
            if (node.left != null) queue.offer(node.left);
            if (node.right != null) queue.offer(node.right);
        }
        result.add(level);
    }
    return result;
}
```

## LeetCode Problems (20)

### Trees (20 problems)

1. **Maximum Depth of Binary Tree** (Easy)
2. **Same Tree** (Easy)
3. **Invert Binary Tree** (Easy)
4. **Symmetric Tree** (Easy)
5. **Subtree of Another Tree** (Easy)
6. **Diameter of Binary Tree** (Easy)
7. **Balanced Binary Tree** (Easy)
8. **Binary Tree Level Order Traversal** (Medium)
9. **Binary Tree Right Side View** (Medium)
10. **Count Good Nodes in Binary Tree** (Medium)
11. **Validate Binary Search Tree** (Medium)
12. **Lowest Common Ancestor of BST** (Medium)
13. **Lowest Common Ancestor of Binary Tree** (Medium)
14. **Kth Smallest Element in BST** (Medium)
15. **Construct Binary Tree from Preorder and Inorder** (Medium)
16. **Binary Tree Maximum Path Sum** (Hard)
17. **Serialize and Deserialize Binary Tree** (Hard)
18. **Binary Search Tree Iterator** (Medium)
19. **Flatten Binary Tree to Linked List** (Medium)
20. **Path Sum III** (Medium)

## Project: Week 5 — MVP COMPLETE + DEPLOY 🚀

### MVP Checklist

**Backend:**
- [ ] Users CRUD
- [ ] Tickets CRUD
- [ ] Categories
- [ ] Ticket assignments
- [ ] Filter by status/priority

**Frontend:**
- [ ] Ticket list view
- [ ] Ticket detail view
- [ ] Create/edit forms
- [ ] Status/priority filters
- [ ] Basic navigation

### Deploy Backend (Railway)

1. Push to GitHub
2. Connect Railway to repo
3. Add PostgreSQL plugin
4. Deploy

### Deploy Frontend (Vercel)

1. Push to GitHub
2. Connect Vercel to repo
3. Set `VITE_API_URL` env variable
4. Deploy

### Week 5 Tasks

- [ ] Read CTCI Chapter 4
- [ ] Memorize 2 templates
- [ ] Complete 20 LeetCode problems
- [ ] Finish all React components
- [ ] Add basic styling
- [ ] Deploy backend to Railway
- [ ] Deploy frontend to Vercel
- [ ] **UPDATE RESUME**
- [ ] **UPDATE LINKEDIN**

---

# Week 6: Trees (Advanced) & Graphs

### *The Forest Deepens*

[↑ Back to Navigation](#-quick-navigation)

## Templates to Memorize

### Graph BFS

```java
public Set<Integer> bfs(Map<Integer, List<Integer>> graph, int start) {
    Set<Integer> visited = new HashSet<>();
    Queue<Integer> queue = new LinkedList<>();
    
    visited.add(start);
    queue.offer(start);
    
    while (!queue.isEmpty()) {
        int node = queue.poll();
        for (int neighbor : graph.getOrDefault(node, new ArrayList<>())) {
            if (!visited.contains(neighbor)) {
                visited.add(neighbor);
                queue.offer(neighbor);
            }
        }
    }
    return visited;
}
```

### Graph DFS

```java
public void dfs(Map<Integer, List<Integer>> graph, int node, Set<Integer> visited) {
    visited.add(node);
    for (int neighbor : graph.getOrDefault(node, new ArrayList<>())) {
        if (!visited.contains(neighbor)) {
            dfs(graph, neighbor, visited);
        }
    }
}
```

## LeetCode Problems (20)

1-10: Advanced tree problems  
11-20: Graph problems (Number of Islands, Clone Graph, Course Schedule, etc.)

## Project: Feature — Comments System

- [ ] Create ticket_comments table
- [ ] Create CommentRepository and Controller
- [ ] Add comments section to ticket detail view

---

# Week 7: Backtracking & Heaps

### *Try Every Path*

[↑ Back to Navigation](#-quick-navigation)

## Templates to Memorize

### Backtracking — Subsets

```java
public List<List<Integer>> subsets(int[] nums) {
    List<List<Integer>> result = new ArrayList<>();
    backtrack(nums, 0, new ArrayList<>(), result);
    return result;
}

private void backtrack(int[] nums, int start, List<Integer> path, List<List<Integer>> result) {
    result.add(new ArrayList<>(path));
    for (int i = start; i < nums.length; i++) {
        path.add(nums[i]);
        backtrack(nums, i + 1, path, result);
        path.remove(path.size() - 1);
    }
}
```

### Heap — Top K

```java
public int[] topKLargest(int[] nums, int k) {
    PriorityQueue<Integer> minHeap = new PriorityQueue<>();
    for (int num : nums) {
        minHeap.offer(num);
        if (minHeap.size() > k) {
            minHeap.poll();
        }
    }
    // Convert to array
}
```

## LeetCode Problems (20)

1-10: Backtracking (Subsets, Permutations, Combinations, Word Search)  
11-20: Heaps (Top K, Merge K Sorted Lists, Find Median)

## Project: Feature — Dashboard Metrics

- [ ] Create dashboard stats endpoint
- [ ] Build Dashboard component with charts

---

# Week 8: Dynamic Programming

### *The Final Boss*

[↑ Back to Navigation](#-quick-navigation)

## Templates to Memorize

### Bottom-Up DP

```java
public int climbStairs(int n) {
    if (n <= 2) return n;
    int[] dp = new int[n + 1];
    dp[1] = 1;
    dp[2] = 2;
    for (int i = 3; i <= n; i++) {
        dp[i] = dp[i-1] + dp[i-2];
    }
    return dp[n];
}
```

### Include/Exclude Pattern

```java
public int houseRobber(int[] nums) {
    if (nums.length == 0) return 0;
    if (nums.length == 1) return nums[0];
    
    int[] dp = new int[nums.length];
    dp[0] = nums[0];
    dp[1] = Math.max(nums[0], nums[1]);
    
    for (int i = 2; i < nums.length; i++) {
        dp[i] = Math.max(dp[i-1], dp[i-2] + nums[i]);
    }
    return dp[nums.length - 1];
}
```

## LeetCode Problems (20)

Climbing Stairs, House Robber, Coin Change, LIS, Word Break, etc.

## Project: Final Polish

- [ ] Bug fixes
- [ ] UI improvements
- [ ] Update README with screenshots
- [ ] **FULL INTERVIEW MODE**

---

# 📊 Progress Tracker

[↑ Back to Navigation](#-quick-navigation)

## Weekly Checklist

### Week 1: Arrays & Hashing + Interview Prep Sprint
**Already Completed (Early Week):**
- [x] Read CTCI Chapter 1
- [x] Complete LeetCode problems 1-10

**Interview Prep Sprint (Weekend Focus):**
- [ ] Read Learning SQL Chapters 2-4
- [ ] Learn ACID properties
- [ ] Understand ETL concepts
- [ ] Review projects
- [ ] Prepare behavioral stories
- [ ] Research BNBuilders
- [ ] Mock interview practice

### Week 2: Two Pointers & Project Setup
- [ ] Read Learning SQL Chapter 5
- [ ] Memorize 5 templates
- [ ] Complete LeetCode problems 11-30
- [ ] Set up PostgreSQL + schema
- [ ] Generate Spring Boot project
- [ ] Create model classes

### Week 3-8: Continue the grind...

---

# 🎬 The Climax

[↑ Back to Navigation](#-quick-navigation)

**After 8 Weeks:**

- ✅ 150+ algorithm problems solved
- ✅ 25+ templates memorized cold
- ✅ SQL fundamentals complete
- ✅ **Full-stack project deployed**
- ✅ **BNBuilders interview crushed**
- ✅ **REDEMPTION ARC COMPLETE** 🏆

---

# 💡 Daily Reminders

[↑ Back to Navigation](#-quick-navigation)

1. **Write templates from memory first**
2. **Understand, don't memorize solutions**
3. **Time yourself** — Medium in 25 min, Hard in 40 min
4. **Ship by Week 5** — Deployed > Perfect
5. **Keep job apps going** — 3-5 daily
6. **Trust the process**
7. **Baby #2 incoming** — January deadline is real

---

# 🎬 Credits

[↑ Back to Navigation](#-quick-navigation)

**Starring:** Tiger 🐯  
**Directed by:** Determination  
**Tech Stack:** Spring Boot + JDBC + PostgreSQL + React  
**First Boss:** BNBuilders Data Engineer Interview

*No recruiters were harmed in the making of this redemption arc.*

---

**You've got this, Tiger. Crush Monday, ship by Week 5, land the role. Let's get it! 🔥**
