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
| 1 | Arrays & Hashing | [Week 1](#week-1-arrays--hashing) |
| 2 | Two Pointers & Sliding Window | [Week 2](#week-2-two-pointers--sliding-window) |
| 3 | Binary Search & Stacks | [Week 3](#week-3-binary-search--stacks) |
| 4 | Linked Lists & Trees | [Week 4](#week-4-linked-lists--trees-basics) |
| 5 | Trees (Advanced) & Graphs | [Week 5](#week-5-trees-advanced--graphs) |
| 6 | Backtracking & Heaps | [Week 6](#week-6-backtracking--heaps) |
| 7 | Dynamic Programming (1D) | [Week 7](#week-7-dynamic-programming-1d) |
| 8 | DP 2D, Tries, Union-Find, Intervals | [Week 8](#week-8-dp-2d-tries-union-find-intervals) |

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
| 1 | Arrays & Hashing | 20 | Ch 1 | Ch 2-3 | Schema + Spring Boot skeleton |
| 2 | Two Pointers & Sliding Window | 20 | Ch 1 (cont.) | Ch 4-5 | JDBC repos + REST endpoints |
| 3 | Binary Search & Stacks | 20 | Ch 3, 10 | Ch 6-7 | React basics + API integration |
| 4 | Linked Lists & Trees | 20 | Ch 2, 4 | Ch 8-9 | **MVP COMPLETE + DEPLOY** |
| 5 | Trees (cont.) & Graphs | 20 | Ch 4 (cont.) | — | Feature: Comments system |
| 6 | Backtracking & Heaps | 20 | Ch 8 | — | Feature: Dashboard metrics |
| 7 | Dynamic Programming (1D) | 20 | Ch 8 (cont.) | — | Feature: Search + filters |
| 8 | DP (2D), Tries, Intervals | 20 | Ch 8, 16 | — | Polish + interview prep |

**Total: 160 algorithm problems + SQL fundamentals + deployed full-stack project**

---

# Week 1: Arrays & Hashing

### *Act I: The Hero Discovers Hash Maps Exist*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 1: Arrays and Strings**

- Hash table fundamentals
- String manipulation techniques
- Big O for array operations

## Learning SQL

**Chapter 2: Creating and Populating a Database** — CREATE TABLE, INSERT, data types  
**Chapter 3: Query Primer** — SELECT basics, WHERE, ORDER BY, LIMIT

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

## LeetCode Problems (20)

### Easy (8 problems)

1. **Two Sum** — Hash map lookup pattern
2. **Contains Duplicate** — Set membership
3. **Valid Anagram** — Frequency counter comparison
4. **Two Sum II - Input Array Is Sorted** — Precursor to two pointers
5. **Majority Element** — Boyer-Moore or hash map
6. **Contains Duplicate II** — Hash map with index tracking
7. **Missing Number** — Math or XOR approach
8. **Find All Numbers Disappeared in Array** — In-place marking

### Medium (10 problems)

9. **Group Anagrams** — Hash map with sorted key
10. **Top K Frequent Elements** — Hash map + heap or bucket sort
11. **Product of Array Except Self** — Prefix/suffix products
12. **Valid Sudoku** — Hash sets for rows, cols, boxes
13. **Encode and Decode Strings** — Delimiter strategy
14. **Longest Consecutive Sequence** — Hash set with sequence building
15. **Subarray Sum Equals K** — Prefix sum + hash map
16. **Find All Duplicates in an Array** — In-place index marking
17. **Sort Colors** — Dutch National Flag (three-way partition)
18. **Set Matrix Zeroes** — In-place markers

### Hard (2 problems)

19. **First Missing Positive** — Cyclic sort / index as hash
20. **Longest Substring with At Most K Distinct Characters** — Hash map sliding window intro

## Project: Ticket Support System — Week 1

### Goals

- [ ] Design database schema
- [ ] Set up Spring Boot project
- [ ] Create project structure
- [ ] Connect to PostgreSQL

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

### Week 1 Tasks

- [ ] Install PostgreSQL locally
- [ ] Create ticket_support database
- [ ] Create users, tickets, categories tables
- [ ] Insert 20+ sample users (mix of customers, agents, admins)
- [ ] Insert 50+ sample tickets with varying statuses/priorities
- [ ] Generate Spring Boot project from start.spring.io
- [ ] Set up project structure (controller/service/repository/model)
- [ ] Configure database connection
- [ ] Create model classes: User, Ticket, Category

---

# Week 2: Two Pointers & Sliding Window

### *Act I Continued: The Pointers Point Both Ways*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 1 (continued):** Focus on in-place manipulation, string problems

## Learning SQL

**Chapter 4: Filtering** — WHERE conditions, AND/OR/NOT, BETWEEN, IN, LIKE  
**Chapter 5: Querying Multiple Tables** — INNER JOIN basics

## Templates to Memorize

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

### Fixed-Size Sliding Window

```java
public int maxSumSubarray(int[] arr, int k) {
    int windowSum = 0;
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }
    int maxSum = windowSum;
    for (int i = k; i < arr.length; i++) {
        windowSum += arr[i] - arr[i - k];  // slide: add right, remove left
        maxSum = Math.max(maxSum, windowSum);
    }
    return maxSum;
}
```

**Use for:** Max/min/avg of fixed window, any k-element aggregate

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

**Use for:** Minimum window, maximum with constraint, substring problems

## LeetCode Problems (20)

### Two Pointers (10 problems)

1. **Valid Palindrome** (Easy) — Two pointers opposite ends with char filtering
2. **Two Sum II - Sorted Array** (Medium) — Classic opposite ends
3. **3Sum** (Medium) — Sort + two pointers with outer loop
4. **Container With Most Water** (Medium) — Greedy two pointers
5. **Trapping Rain Water** (Hard) — Two pointers or stack
6. **Remove Duplicates from Sorted Array** (Easy) — Same direction
7. **Remove Element** (Easy) — Same direction partition
8. **Move Zeroes** (Easy) — Same direction swap
9. **Squares of a Sorted Array** (Easy) — Two pointers merge
10. **Boats to Save People** (Medium) — Greedy two pointers

### Sliding Window (10 problems)

11. **Best Time to Buy and Sell Stock** (Easy) — Track min price
12. **Maximum Average Subarray I** (Easy) — Fixed window
13. **Longest Substring Without Repeating Characters** (Medium) — Variable window + set
14. **Longest Repeating Character Replacement** (Medium) — Variable window + frequency
15. **Permutation in String** (Medium) — Fixed window + frequency match
16. **Minimum Size Subarray Sum** (Medium) — Variable window
17. **Fruit Into Baskets** (Medium) — Variable window, at most 2 distinct
18. **Max Consecutive Ones III** (Medium) — Variable window with k flips
19. **Minimum Window Substring** (Hard) — Variable window + hash map
20. **Sliding Window Maximum** (Hard) — Monotonic deque

## Project: Week 2

### Goals

- [ ] Build JDBC repository layer
- [ ] Create REST controllers
- [ ] Implement basic CRUD operations

### New Table

```sql
-- Ticket assignments (agents assigned to tickets)
CREATE TABLE ticket_assignments (
    assignment_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id),
    agent_id INTEGER REFERENCES users(user_id),
    assigned_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Repository Layer (JDBC)

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
    
    public void update(Ticket ticket) {
        jdbcTemplate.update(
            "UPDATE tickets SET subject = ?, description = ?, status = ?, priority = ?, updated_at = NOW() WHERE ticket_id = ?",
            ticket.getSubject(),
            ticket.getDescription(),
            ticket.getStatus(),
            ticket.getPriority(),
            ticket.getTicketId()
        );
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
    
    @PutMapping("/{id}")
    public ResponseEntity<Ticket> updateTicket(@PathVariable Long id, @RequestBody Ticket ticket) {
        ticket.setTicketId(id);
        ticketService.update(ticket);
        return ResponseEntity.ok(ticket);
    }
}
```

### Week 2 Tasks

- [ ] Create TicketRepository with JDBC
- [ ] Create UserRepository with JDBC
- [ ] Create TicketService layer
- [ ] Create TicketController (GET all, GET by id, POST, PUT)
- [ ] Create UserController (GET all, GET by id)
- [ ] Test endpoints with Postman or curl
- [ ] Add ticket_assignments table
- [ ] Practice JOINs: tickets with users, tickets with categories

---

# Week 3: Binary Search & Stacks

### *Act II: The Plot Thickens (Logarithmically)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 3: Stacks and Queues** — Stack operations, implementing with arrays/linked lists  
**Chapter 10: Sorting and Searching** — Binary search fundamentals

## Learning SQL

**Chapter 6: Working with Sets** — UNION, INTERSECT, EXCEPT  
**Chapter 7: Data Generation, Manipulation, and Conversion** — String/number/date functions

## Templates to Memorize

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

**Use for:** Finding exact element in sorted array

### Binary Search — Find Boundary (Leftmost True)

```java
public int binarySearchBoundary(int[] arr) {
    int left = 0, right = arr.length;  // or min/max of search space
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (condition(mid)) {  // Define condition that becomes true at boundary
            right = mid;  // mid might be answer, keep it
        } else {
            left = mid + 1;  // mid definitely not answer
        }
    }
    return left;
}
```

**Use for:** First bad version, search insert position, capacity problems

### Monotonic Stack (Decreasing)

```java
public int[] nextGreaterElement(int[] arr) {
    int n = arr.length;
    int[] result = new int[n];
    Arrays.fill(result, -1);
    Deque<Integer> stack = new ArrayDeque<>();  // stores indices
    
    for (int i = 0; i < n; i++) {
        while (!stack.isEmpty() && arr[i] > arr[stack.peek()]) {
            int idx = stack.pop();
            result[idx] = arr[i];
        }
        stack.push(i);
    }
    return result;
}
```

**Use for:** Next greater/smaller element, daily temperatures, histogram problems

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

**Use for:** Balanced parentheses, expression evaluation

## LeetCode Problems (20)

### Binary Search (10 problems)

1. **Binary Search** (Easy) — Classic implementation
2. **Search Insert Position** (Easy) — Boundary finding
3. **Guess Number Higher or Lower** (Easy) — Interactive binary search
4. **First Bad Version** (Easy) — Boundary template
5. **Find Minimum in Rotated Sorted Array** (Medium) — Modified binary search
6. **Search in Rotated Sorted Array** (Medium) — Two-phase approach
7. **Search a 2D Matrix** (Medium) — Treat as 1D sorted array
8. **Koko Eating Bananas** (Medium) — Binary search on answer
9. **Find Peak Element** (Medium) — Binary search on unsorted
10. **Median of Two Sorted Arrays** (Hard) — Binary search on partition

### Stacks (10 problems)

11. **Valid Parentheses** (Easy) — Matching brackets
12. **Min Stack** (Medium) — Stack with O(1) minimum
13. **Evaluate Reverse Polish Notation** (Medium) — Expression evaluation
14. **Daily Temperatures** (Medium) — Monotonic decreasing stack
15. **Next Greater Element I** (Easy) — Monotonic stack with hash map
16. **Next Greater Element II** (Medium) — Circular array
17. **Simplify Path** (Medium) — Stack for path processing
18. **Basic Calculator II** (Medium) — Stack-based expression
19. **Decode String** (Medium) — Nested structure with stack
20. **Largest Rectangle in Histogram** (Hard) — Monotonic stack classic

## Project: Week 3

### Goals

- [ ] Learn React fundamentals
- [ ] Set up React + Vite frontend
- [ ] Create basic components
- [ ] Connect to Spring Boot API

### React Project Setup

```bash
npm create vite@latest ticket-frontend -- --template react
cd ticket-frontend
npm install
npm install axios
npm run dev
```

### Project Structure

```
ticket-frontend/
├── src/
│   ├── components/
│   │   ├── TicketList.jsx
│   │   ├── TicketCard.jsx
│   │   ├── TicketForm.jsx
│   │   └── Navbar.jsx
│   ├── services/
│   │   └── api.js
│   ├── App.jsx
│   └── main.jsx
```

### API Service

```javascript
// src/services/api.js
import axios from 'axios';

const API_BASE = 'http://localhost:8080/api';

export const ticketService = {
    getAll: () => axios.get(`${API_BASE}/tickets`),
    getById: (id) => axios.get(`${API_BASE}/tickets/${id}`),
    create: (ticket) => axios.post(`${API_BASE}/tickets`, ticket),
    update: (id, ticket) => axios.put(`${API_BASE}/tickets/${id}`, ticket),
};
```

### Basic Component

```jsx
// src/components/TicketList.jsx
import { useState, useEffect } from 'react';
import { ticketService } from '../services/api';

function TicketList() {
    const [tickets, setTickets] = useState([]);
    
    useEffect(() => {
        ticketService.getAll()
            .then(response => setTickets(response.data))
            .catch(error => console.error(error));
    }, []);
    
    return (
        <div>
            <h2>Tickets</h2>
            {tickets.map(ticket => (
                <div key={ticket.ticketId}>
                    <h3>{ticket.subject}</h3>
                    <p>Status: {ticket.status}</p>
                    <p>Priority: {ticket.priority}</p>
                </div>
            ))}
        </div>
    );
}

export default TicketList;
```

### Enable CORS in Spring Boot

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

### Week 3 Tasks

- [ ] Complete React tutorial on react.dev
- [ ] Set up Vite + React project
- [ ] Create api.js service layer
- [ ] Build TicketList component
- [ ] Build TicketCard component
- [ ] Build TicketForm component (create/edit)
- [ ] Add CORS config to Spring Boot
- [ ] Get list view working end-to-end

---

# Week 4: Linked Lists & Trees (Basics)

### *Act II Continued: Pointers Get Weird — AND WE SHIP 🚀*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 2: Linked Lists** — Runner technique, recursive approaches  
**Chapter 4: Trees and Graphs** — Tree traversals, BST properties

## Learning SQL

**Chapter 8: Grouping and Aggregates** — GROUP BY, HAVING, COUNT, SUM, AVG, MIN, MAX  
**Chapter 9: Subqueries** — Scalar, correlated, EXISTS

## Templates to Memorize

### Linked List Reversal (Iterative)

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

**Use for:** Reverse entire list, reverse portions, palindrome check

### Fast/Slow Pointers in Linked List

```java
public ListNode findMiddle(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;  // middle node (second middle if even)
}
```

**Use for:** Find middle, detect cycle (Floyd's), find cycle start

### Tree DFS (Recursive)

```java
// Preorder: root -> left -> right
public List<Integer> preorder(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;
    result.add(root.val);
    result.addAll(preorder(root.left));
    result.addAll(preorder(root.right));
    return result;
}

// Inorder: left -> root -> right
public List<Integer> inorder(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;
    result.addAll(inorder(root.left));
    result.add(root.val);
    result.addAll(inorder(root.right));
    return result;
}

// Postorder: left -> right -> root
public List<Integer> postorder(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;
    result.addAll(postorder(root.left));
    result.addAll(postorder(root.right));
    result.add(root.val);
    return result;
}
```

**Use for:** Any tree traversal, path problems, tree construction

### Tree BFS (Level Order)

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

**Use for:** Level-based problems, finding depth, right/left view

## LeetCode Problems (20)

### Linked Lists (10 problems)

1. **Reverse Linked List** (Easy) — Iterative and recursive
2. **Merge Two Sorted Lists** (Easy) — Dummy head technique
3. **Linked List Cycle** (Easy) — Floyd's algorithm
4. **Linked List Cycle II** (Medium) — Find cycle start
5. **Remove Nth Node From End** (Medium) — Two pointer gap
6. **Reorder List** (Medium) — Find middle, reverse, merge
7. **Middle of the Linked List** (Easy) — Fast/slow
8. **Palindrome Linked List** (Easy) — Reverse second half
9. **Add Two Numbers** (Medium) — Digit-by-digit with carry
10. **Copy List with Random Pointer** (Medium) — Hash map or interleaving

### Trees Basics (10 problems)

11. **Maximum Depth of Binary Tree** (Easy) — Basic DFS recursion
12. **Same Tree** (Easy) — Parallel recursion
13. **Invert Binary Tree** (Easy) — Recursive swap
14. **Symmetric Tree** (Easy) — Mirror check
15. **Subtree of Another Tree** (Easy) — Tree comparison
16. **Diameter of Binary Tree** (Easy) — Global max with recursion
17. **Balanced Binary Tree** (Easy) — Height with balance check
18. **Binary Tree Level Order Traversal** (Medium) — BFS template
19. **Binary Tree Right Side View** (Medium) — BFS or DFS
20. **Count Good Nodes in Binary Tree** (Medium) — DFS with max tracking

## Project: Week 4 — MVP SHIP DATE 🚀

### Goals

- [ ] Complete React frontend
- [ ] Deploy backend (Railway or Render)
- [ ] Deploy frontend (Vercel or Netlify)
- [ ] **PUT IT ON YOUR RESUME**

### MVP Features Checklist

**Backend (Spring Boot):**
- [x] Users CRUD
- [x] Tickets CRUD
- [x] Categories
- [x] Ticket assignments
- [ ] Filter tickets by status/priority

**Frontend (React):**
- [ ] Ticket list view
- [ ] Ticket detail view
- [ ] Create ticket form
- [ ] Edit ticket form
- [ ] Status/priority filters
- [ ] Basic navigation

### Deployment — Backend (Railway)

1. Push Spring Boot project to GitHub
2. Go to railway.app, connect GitHub
3. Add PostgreSQL plugin
4. Set environment variables:
   ```
   SPRING_DATASOURCE_URL=${DATABASE_URL}
   ```
5. Deploy

### Deployment — Frontend (Vercel)

1. Push React project to GitHub
2. Go to vercel.com, connect GitHub
3. Set environment variable:
   ```
   VITE_API_URL=https://your-railway-app.railway.app/api
   ```
4. Deploy

### Update api.js for Production

```javascript
const API_BASE = import.meta.env.VITE_API_URL || 'http://localhost:8080/api';
```

### Week 4 Tasks

- [ ] Add status/priority filter endpoints
- [ ] Complete all React components
- [ ] Add basic styling (keep it simple)
- [ ] Deploy backend to Railway
- [ ] Deploy frontend to Vercel
- [ ] Test production deployment
- [ ] **UPDATE RESUME WITH PROJECT**
- [ ] **UPDATE LINKEDIN WITH PROJECT**

---

# Week 5: Trees (Advanced) & Graphs

### *Act III: The Hero Enters the Forest (Of Nodes) — With a Deployed Project*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 4: Trees and Graphs (continued)** — BST operations, graph representations, BFS/DFS on graphs

## Templates to Memorize

### BST Search and Validation

```java
public TreeNode searchBST(TreeNode root, int target) {
    if (root == null || root.val == target) {
        return root;
    }
    if (target < root.val) {
        return searchBST(root.left, target);
    }
    return searchBST(root.right, target);
}

public boolean isValidBST(TreeNode root) {
    return isValidBST(root, Long.MIN_VALUE, Long.MAX_VALUE);
}

private boolean isValidBST(TreeNode node, long min, long max) {
    if (node == null) return true;
    if (node.val <= min || node.val >= max) return false;
    return isValidBST(node.left, min, node.val) && 
           isValidBST(node.right, node.val, max);
}
```

**Use for:** BST search, validation, insert, delete

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

**Use for:** Shortest path (unweighted), level-based problems, connectivity

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

**Use for:** Connectivity, cycle detection, path finding, topological concepts

### Grid BFS (Islands Pattern)

```java
public int numIslands(char[][] grid) {
    if (grid == null || grid.length == 0) return 0;
    int rows = grid.length, cols = grid[0].length;
    int count = 0;
    
    int[][] directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
    
    for (int r = 0; r < rows; r++) {
        for (int c = 0; c < cols; c++) {
            if (grid[r][c] == '1') {
                count++;
                Queue<int[]> queue = new LinkedList<>();
                queue.offer(new int[]{r, c});
                grid[r][c] = '0';
                
                while (!queue.isEmpty()) {
                    int[] cell = queue.poll();
                    for (int[] dir : directions) {
                        int nr = cell[0] + dir[0];
                        int nc = cell[1] + dir[1];
                        if (nr >= 0 && nr < rows && nc >= 0 && nc < cols 
                            && grid[nr][nc] == '1') {
                            grid[nr][nc] = '0';
                            queue.offer(new int[]{nr, nc});
                        }
                    }
                }
            }
        }
    }
    return count;
}
```

**Use for:** Island counting, flood fill, any grid connectivity

## LeetCode Problems (20)

### Trees Advanced (10 problems)

1. **Validate Binary Search Tree** (Medium) — Range checking
2. **Lowest Common Ancestor of BST** (Medium) — BST property
3. **Lowest Common Ancestor of Binary Tree** (Medium) — General tree
4. **Kth Smallest Element in BST** (Medium) — Inorder traversal
5. **Construct Binary Tree from Preorder and Inorder** (Medium) — Recursive build
6. **Binary Tree Maximum Path Sum** (Hard) — Global variable pattern
7. **Serialize and Deserialize Binary Tree** (Hard) — BFS or preorder
8. **Binary Search Tree Iterator** (Medium) — Controlled inorder
9. **Flatten Binary Tree to Linked List** (Medium) — Preorder modification
10. **Path Sum III** (Medium) — Prefix sum on tree

### Graphs (10 problems)

11. **Number of Islands** (Medium) — Grid BFS/DFS
12. **Clone Graph** (Medium) — BFS with hash map
13. **Max Area of Island** (Medium) — Grid DFS with counting
14. **Pacific Atlantic Water Flow** (Medium) — Multi-source BFS
15. **Surrounded Regions** (Medium) — Border-connected BFS
16. **Rotting Oranges** (Medium) — Multi-source BFS
17. **Course Schedule** (Medium) — Cycle detection
18. **Course Schedule II** (Medium) — Topological sort
19. **Number of Connected Components** (Medium) — Union-Find or DFS
20. **Graph Valid Tree** (Medium) — Cycle detection + connectivity

## Project: Week 5 — Feature: Comments System

### New Table

```sql
CREATE TABLE ticket_comments (
    comment_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id) ON DELETE CASCADE,
    user_id INTEGER REFERENCES users(user_id),
    comment_text TEXT NOT NULL,
    is_internal BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Week 5 Tasks

- [ ] Create ticket_comments table
- [ ] Create CommentRepository
- [ ] Create CommentController (GET by ticket, POST)
- [ ] Add comments section to ticket detail view in React
- [ ] Add comment form component
- [ ] Continue interview applications

---

# Week 6: Backtracking & Heaps

### *Act III Continued: The Hero Tries Every Path (Recursively)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 8: Recursion and Dynamic Programming** — Focus on backtracking section, permutations/combinations

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

**Use for:** All subsets, combinations, power set

### Backtracking — Permutations

```java
public List<List<Integer>> permutations(int[] nums) {
    List<List<Integer>> result = new ArrayList<>();
    backtrack(nums, new boolean[nums.length], new ArrayList<>(), result);
    return result;
}

private void backtrack(int[] nums, boolean[] used, List<Integer> path, List<List<Integer>> result) {
    if (path.size() == nums.length) {
        result.add(new ArrayList<>(path));
        return;
    }
    
    for (int i = 0; i < nums.length; i++) {
        if (used[i]) continue;
        
        used[i] = true;
        path.add(nums[i]);
        backtrack(nums, used, path, result);
        path.remove(path.size() - 1);
        used[i] = false;
    }
}
```

**Use for:** All permutations, arrangement problems

### Heap — Top K Pattern

```java
public int[] topKLargest(int[] nums, int k) {
    PriorityQueue<Integer> minHeap = new PriorityQueue<>();
    
    for (int num : nums) {
        minHeap.offer(num);
        if (minHeap.size() > k) {
            minHeap.poll();
        }
    }
    
    int[] result = new int[k];
    for (int i = 0; i < k; i++) {
        result[i] = minHeap.poll();
    }
    return result;
}
```

**Use for:** K largest/smallest, k most frequent

### Two Heaps — Median

```java
class MedianFinder {
    private PriorityQueue<Integer> small;  // max heap
    private PriorityQueue<Integer> large;  // min heap
    
    public MedianFinder() {
        small = new PriorityQueue<>(Collections.reverseOrder());
        large = new PriorityQueue<>();
    }
    
    public void addNum(int num) {
        small.offer(num);
        
        if (!small.isEmpty() && !large.isEmpty() && small.peek() > large.peek()) {
            large.offer(small.poll());
        }
        
        if (small.size() > large.size() + 1) {
            large.offer(small.poll());
        } else if (large.size() > small.size()) {
            small.offer(large.poll());
        }
    }
    
    public double findMedian() {
        if (small.size() > large.size()) {
            return small.peek();
        }
        return (small.peek() + large.peek()) / 2.0;
    }
}
```

**Use for:** Running median, sliding window median

## LeetCode Problems (20)

### Backtracking (10 problems)

1. **Subsets** (Medium) — Core template
2. **Subsets II** (Medium) — With duplicates
3. **Permutations** (Medium) — Core template
4. **Permutations II** (Medium) — With duplicates
5. **Combinations** (Medium) — Choose k from n
6. **Combination Sum** (Medium) — Unlimited reuse
7. **Combination Sum II** (Medium) — Each element once
8. **Letter Combinations of Phone Number** (Medium) — String building
9. **Palindrome Partitioning** (Medium) — String partitioning
10. **Word Search** (Medium) — Grid backtracking

### Heaps (10 problems)

11. **Kth Largest Element in Array** (Medium) — Heap or quickselect
12. **Top K Frequent Elements** (Medium) — Heap with frequency map
13. **K Closest Points to Origin** (Medium) — Min heap
14. **Find Median from Data Stream** (Hard) — Two heaps
15. **Merge K Sorted Lists** (Hard) — Min heap of list heads
16. **Task Scheduler** (Medium) — Max heap + cooldown
17. **Kth Largest Element in Stream** (Easy) — Min heap of size k
18. **Last Stone Weight** (Easy) — Max heap simulation
19. **Reorganize String** (Medium) — Max heap for spacing
20. **Meeting Rooms II** (Medium) — Min heap for end times

## Project: Week 6 — Feature: Dashboard Metrics

### New Endpoints

```java
@GetMapping("/api/dashboard/stats")
public DashboardStats getStats() {
    return new DashboardStats(
        ticketService.countByStatus("open"),
        ticketService.countByStatus("in_progress"),
        ticketService.countByStatus("resolved"),
        ticketService.getAverageResolutionTime()
    );
}
```

### Week 6 Tasks

- [ ] Create dashboard stats endpoint
- [ ] Create DashboardStats DTO
- [ ] Build Dashboard component in React
- [ ] Add simple charts (ticket counts by status/priority)
- [ ] Continue interview applications

---

# Week 7: Dynamic Programming (1D)

### *The Dark Night of the Soul: DP Makes Everything Click (Or Doesn't)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 8: Recursion and Dynamic Programming (continued)** — Memoization, bottom-up approach, classic DP problems

## Templates to Memorize

### Top-Down Memoization

```java
public int fibMemo(int n) {
    int[] memo = new int[n + 1];
    Arrays.fill(memo, -1);
    return fibHelper(n, memo);
}

private int fibHelper(int n, int[] memo) {
    if (n <= 1) return n;
    if (memo[n] != -1) return memo[n];
    memo[n] = fibHelper(n - 1, memo) + fibHelper(n - 2, memo);
    return memo[n];
}
```

**Use for:** Understanding subproblem structure, easier to conceptualize

### Bottom-Up Tabulation

```java
public int fibTab(int n) {
    if (n <= 1) return n;
    int[] dp = new int[n + 1];
    dp[0] = 0;
    dp[1] = 1;
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```

**Use for:** Production code, often more space-efficient

### Space-Optimized DP

```java
public int fibOptimized(int n) {
    if (n <= 1) return n;
    int prev2 = 0, prev1 = 1;
    for (int i = 2; i <= n; i++) {
        int curr = prev1 + prev2;
        prev2 = prev1;
        prev1 = curr;
    }
    return prev1;
}
```

**Use for:** When only need previous 1-2 states

### Include/Exclude Pattern

```java
public int houseRobber(int[] nums) {
    if (nums.length == 0) return 0;
    if (nums.length == 1) return nums[0];
    
    int[] dp = new int[nums.length];
    dp[0] = nums[0];
    dp[1] = Math.max(nums[0], nums[1]);
    
    for (int i = 2; i < nums.length; i++) {
        dp[i] = Math.max(dp[i - 1], dp[i - 2] + nums[i]);
    }
    
    return dp[nums.length - 1];
}
```

**Use for:** House robber, stock problems, any skip/take decision

## LeetCode Problems (20)

### 1D Dynamic Programming (20 problems)

1. **Climbing Stairs** (Easy) — Fibonacci variant
2. **Min Cost Climbing Stairs** (Easy) — DP with cost
3. **House Robber** (Medium) — Include/exclude
4. **House Robber II** (Medium) — Circular array
5. **Coin Change** (Medium) — Unbounded knapsack
6. **Coin Change II** (Medium) — Count combinations
7. **Maximum Subarray** (Medium) — Kadane's algorithm
8. **Maximum Product Subarray** (Medium) — Track min and max
9. **Longest Increasing Subsequence** (Medium) — Classic LIS
10. **Word Break** (Medium) — String DP
11. **Decode Ways** (Medium) — String parsing DP
12. **Perfect Squares** (Medium) — Min squares summing to n
13. **Partition Equal Subset Sum** (Medium) — 0/1 knapsack
14. **Target Sum** (Medium) — Count ways with +/-
15. **Longest Palindromic Substring** (Medium) — Expand around center or DP
16. **Palindromic Substrings** (Medium) — Count all palindromes
17. **Delete and Earn** (Medium) — House robber variant
18. **Jump Game** (Medium) — Greedy or DP
19. **Jump Game II** (Medium) — Min jumps
20. **Maximum Length of Pair Chain** (Medium) — Sort + DP or greedy

## Project: Week 7 — Feature: Search & Filters

### Week 7 Tasks

- [ ] Add search endpoint (search tickets by subject/description)
- [ ] Add advanced filter endpoint (combine status, priority, date range)
- [ ] Build search component in React
- [ ] Add filter UI with dropdowns
- [ ] Polish existing features
- [ ] Heavy focus on interview prep

---

# Week 8: DP (2D), Tries, Union-Find, Intervals

### *The Final Battle: The Hero Faces All Remaining Patterns At Once*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading

**Chapter 8 (continued):** 2D DP patterns  
**Chapter 16: Moderate Problems** — Interval problems, various techniques

## Templates to Memorize

### 2D DP Grid

```java
public int uniquePaths(int m, int n) {
    int[][] dp = new int[m][n];
    
    for (int i = 0; i < m; i++) dp[i][0] = 1;
    for (int j = 0; j < n; j++) dp[0][j] = 1;
    
    for (int i = 1; i < m; i++) {
        for (int j = 1; j < n; j++) {
            dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
        }
    }
    return dp[m - 1][n - 1];
}
```

**Use for:** Path counting, grid minimum/maximum paths

### Trie Implementation

```java
class TrieNode {
    Map<Character, TrieNode> children = new HashMap<>();
    boolean isEnd = false;
}

class Trie {
    private TrieNode root = new TrieNode();
    
    public void insert(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            node.children.putIfAbsent(c, new TrieNode());
            node = node.children.get(c);
        }
        node.isEnd = true;
    }
    
    public boolean search(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            if (!node.children.containsKey(c)) {
                return false;
            }
            node = node.children.get(c);
        }
        return node.isEnd;
    }
    
    public boolean startsWith(String prefix) {
        TrieNode node = root;
        for (char c : prefix.toCharArray()) {
            if (!node.children.containsKey(c)) {
                return false;
            }
            node = node.children.get(c);
        }
        return true;
    }
}
```

**Use for:** Prefix matching, autocomplete, word search problems

### Union-Find with Path Compression

```java
class UnionFind {
    private int[] parent;
    private int[] rank;
    
    public UnionFind(int n) {
        parent = new int[n];
        rank = new int[n];
        for (int i = 0; i < n; i++) {
            parent[i] = i;
        }
    }
    
    public int find(int x) {
        if (parent[x] != x) {
            parent[x] = find(parent[x]);
        }
        return parent[x];
    }
    
    public boolean union(int x, int y) {
        int px = find(x), py = find(y);
        if (px == py) return false;
        
        if (rank[px] < rank[py]) {
            int temp = px; px = py; py = temp;
        }
        parent[py] = px;
        if (rank[px] == rank[py]) {
            rank[px]++;
        }
        return true;
    }
}
```

**Use for:** Connected components, cycle detection, dynamic connectivity

### Interval Merge

```java
public int[][] mergeIntervals(int[][] intervals) {
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
    
    List<int[]> merged = new ArrayList<>();
    for (int[] interval : intervals) {
        if (merged.isEmpty() || merged.get(merged.size() - 1)[1] < interval[0]) {
            merged.add(interval);
        } else {
            merged.get(merged.size() - 1)[1] = 
                Math.max(merged.get(merged.size() - 1)[1], interval[1]);
        }
    }
    return merged.toArray(new int[merged.size()][]);
}
```

**Use for:** Merge overlapping intervals, insert interval, meeting rooms

## LeetCode Problems (20)

### 2D DP (5 problems)

1. **Unique Paths** (Medium) — Basic grid DP
2. **Unique Paths II** (Medium) — With obstacles
3. **Minimum Path Sum** (Medium) — Grid minimum
4. **Longest Common Subsequence** (Medium) — Classic string DP
5. **Edit Distance** (Medium) — String transformation

### Tries (5 problems)

6. **Implement Trie** (Medium) — Core operations
7. **Design Add and Search Words** (Medium) — Trie with wildcards
8. **Word Search II** (Hard) — Trie + backtracking
9. **Replace Words** (Medium) — Prefix replacement
10. **Search Suggestions System** (Medium) — Autocomplete

### Union-Find (5 problems)

11. **Number of Connected Components** (Medium) — Basic UF
12. **Redundant Connection** (Medium) — Cycle detection
13. **Accounts Merge** (Medium) — Group by common element
14. **Longest Consecutive Sequence** (Medium) — UF or hash set
15. **Number of Provinces** (Medium) — UF or DFS

### Intervals (5 problems)

16. **Merge Intervals** (Medium) — Core template
17. **Insert Interval** (Medium) — Insert and merge
18. **Non-overlapping Intervals** (Medium) — Min removals
19. **Meeting Rooms** (Easy) — Overlap detection
20. **Meeting Rooms II** (Medium) — Min rooms needed

## Project: Week 8 — Final Polish

### Week 8 Tasks

- [ ] Bug fixes and polish
- [ ] Improve UI/UX
- [ ] Add any missing error handling
- [ ] Update README with screenshots
- [ ] Record demo video (optional but nice)
- [ ] **FULL FOCUS ON INTERVIEWS**

---

# 📊 Progress Tracker

### *The Montage Checklist*

[↑ Back to Navigation](#-quick-navigation)

## Weekly Checklist

### Week 1: Arrays & Hashing
- [x] Read CTCI Chapter 1
- [ ] Read Learning SQL Chapters 2-3
- [x] Memorize 3 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Set up PostgreSQL + create schema
- [ ] Generate Spring Boot project
- [ ] Create model classes

### Week 2: Two Pointers & Sliding Window
- [ ] Read Learning SQL Chapters 4-5
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Build JDBC repository layer
- [ ] Create REST controllers
- [ ] Test with Postman

### Week 3: Binary Search & Stacks
- [ ] Read CTCI Chapters 3, 10
- [ ] Read Learning SQL Chapters 6-7
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Learn React basics
- [ ] Set up Vite + React
- [ ] Connect frontend to backend

### Week 4: Linked Lists & Trees Basics — **MVP SHIP**
- [ ] Read CTCI Chapters 2, 4
- [ ] Read Learning SQL Chapters 8-9
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Complete React frontend
- [ ] Deploy backend to Railway
- [ ] Deploy frontend to Vercel
- [ ] **UPDATE RESUME**
- [ ] **UPDATE LINKEDIN**

### Week 5: Trees Advanced & Graphs
- [ ] Read CTCI Chapter 4 (graphs)
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add comments feature
- [ ] Interview applications

### Week 6: Backtracking & Heaps
- [ ] Read CTCI Chapter 8 (backtracking)
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add dashboard metrics
- [ ] Interview applications

### Week 7: Dynamic Programming (1D)
- [ ] Read CTCI Chapter 8 (DP)
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add search/filter features
- [ ] Interview prep heavy

### Week 8: DP 2D, Tries, Union-Find, Intervals
- [ ] Read CTCI Chapter 8, 16
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Final polish
- [ ] **INTERVIEW MODE**

---

# 🎬 The Climax

### *The Hero Emerges, Transformed*

[↑ Back to Navigation](#-quick-navigation)

**After 8 Weeks:**

- ✅ 160 algorithm problems solved
- ✅ 30+ templates memorized cold (in Java! ☕)
- ✅ CTCI read cover-to-cover (relevant chapters)
- ✅ SQL fundamentals complete (Ch 2-9)
- ✅ **Full-stack project deployed and on resume**
- ✅ Spring Boot + JDBC + PostgreSQL + React
- ✅ **REDEMPTION ARC COMPLETE** 🏆

*[Inspirational music swells]*

*[Hero walks into interview room with slow-motion confidence]*

*[Interviewer asks about system design]*

*[Hero pulls up deployed ticket system]*

*[Interviewer nods approvingly]*

---

# 💡 Daily Reminders

### *Words To Live By During Your Redemption Arc*

[↑ Back to Navigation](#-quick-navigation)

1. **Write templates from memory first** — If you can't write it cold, you haven't learned it
2. **Understand, don't memorize solutions** — Know WHY the pattern works
3. **Time yourself** — Medium problems in 25 min, Hard in 40 min
4. **Ship by Dec 31** — A deployed project beats a perfect plan
5. **Keep job apps going** — 3-5 applications daily, non-negotiable
6. **Trust the process** — Consistent daily effort beats sporadic cramming
7. **Remember why you're here** — Baby #2 is coming, January deadline is real
8. **Java will feel natural by Week 3** — Push through the initial friction

---

# 🎬 Credits

[↑ Back to Navigation](#-quick-navigation)

**Starring:** Tiger 🐯  
**Supporting Cast:** Claude, NeetCode, CTCI, Learning SQL, PostgreSQL, Spring Boot, React, Java ☕  
**Produced by:** Necessity  
**Directed by:** Determination  
**Original Score:** Lo-fi beats to grind LeetCode to  
**Tech Stack:** Spring Boot + JDBC + PostgreSQL + React + Vite  
**Deadline:** End of January or bust

*No recruiters were harmed in the making of this redemption arc.*

*Coming soon: "employment-arc" (Q1 2025)*

---

**You've got this, Tiger. Ship by December 31, interview in January, land the role. Let's get it! 🔥**

*[Roll credits]*
