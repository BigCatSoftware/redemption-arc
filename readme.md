# 🎬 redemption-arc

### *From "we'll keep your resume on file" to "when can you start?"*

> **Mission:** Deep-dive into algorithm patterns and SQL fundamentals to land a software engineering role ASAP. This is the training montage. The dramatic music is playing. The interviewer doesn't stand a chance.

**Start Date:** Week of December 9, 2024  
**Daily Commitment:** 3-4 hours focused work  
**Philosophy:** Depth over breadth. Master each pattern before moving on.  
**Vibe:** Rocky running up the steps, but the steps are LeetCode problems and the meat punching is PostgreSQL.  
**Language:** Java ☕ — Because we're going full enterprise-ready for this redemption arc.

---

## 📍 Quick Navigation

> *Jump around like your career depends on it (because it does)*

### Main Sections
- [📚 Resources](#-resources)
- [☕ Java Quick Reference](#-java-quick-reference) ← *Your new best friend*
- [🗓️ Daily Structure](#️-daily-structure)
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
- **Learning SQL, 3rd Edition by Alan Beaulieu** — Primary textbook
- **PostgreSQL** — Your database of choice
- **LeetCode SQL** — Supplementary practice

### Your Project
- **Ticket Support Database** — Build incrementally each week, use in future larger project

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
| **Afternoon (1 hr)** | SQL reading + database project |
| **Evening (30 min)** | Review templates, job applications |

**Sundays:** Review week's templates from memory. Re-attempt any problems you struggled with. Stare dramatically out a window contemplating your journey.

---

## 📋 Weekly Overview

[↑ Back to Navigation](#-quick-navigation)

| Week | Algorithm Topics | Problems | CTCI Chapters | Learning SQL Chapters |
|------|------------------|----------|---------------|----------------------|
| 1 | Arrays & Hashing | 20 | Ch 1 | Ch 1-3 |
| 2 | Two Pointers & Sliding Window | 20 | Ch 1 (cont.) | Ch 4-5 |
| 3 | Binary Search & Stacks | 20 | Ch 3, 10 | Ch 6-7 |
| 4 | Linked Lists & Trees | 20 | Ch 2, 4 | Ch 8-9 |
| 5 | Trees (cont.) & Graphs | 20 | Ch 4 (cont.) | Ch 10-11 |
| 6 | Backtracking & Heaps | 20 | Ch 8 | Ch 12-13 |
| 7 | Dynamic Programming (1D) | 20 | Ch 8 (cont.) | Ch 14-15 |
| 8 | DP (2D), Tries, Intervals | 20 | Ch 8, 16 | Ch 16 + Review |

**Total: 160 algorithm problems + complete SQL fundamentals**

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
**Chapter 1: A Little Background** — Database history, SQL overview  
**Chapter 2: Creating and Populating a Database** — CREATE TABLE, INSERT  
**Chapter 3: Query Primer** — SELECT basics, WHERE, ORDER BY

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

## SQL Project: Ticket Support Database — Week 1

### Schema Design
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
```

### Week 1 Tasks
- [ ] Install PostgreSQL locally
- [ ] Create ticket_support database
- [ ] Create users, tickets, categories tables
- [ ] Insert 20+ sample users (mix of customers, agents, admins)
- [ ] Insert 50+ sample tickets with varying statuses/priorities
- [ ] Practice SELECT with WHERE, ORDER BY, LIMIT

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

## SQL Project: Week 2

### New Table
```sql
-- Ticket assignments (agents assigned to tickets)
CREATE TABLE ticket_assignments (
    assignment_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id),
    agent_id INTEGER REFERENCES users(user_id),
    assigned_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Ticket-category relationship
ALTER TABLE tickets ADD COLUMN category_id INTEGER REFERENCES categories(category_id);
```

### Week 2 Tasks
- [ ] Add categories (Technical, Billing, General, etc.)
- [ ] Assign categories to existing tickets
- [ ] Create ticket_assignments table
- [ ] Assign agents to tickets
- [ ] Practice JOINs: tickets with users, tickets with categories
- [ ] Write query: "Show all tickets with customer name and assigned agent name"

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

## SQL Project: Week 3

### New Table
```sql
-- Ticket comments/replies
CREATE TABLE ticket_comments (
    comment_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id) ON DELETE CASCADE,
    user_id INTEGER REFERENCES users(user_id),
    comment_text TEXT NOT NULL,
    is_internal BOOLEAN DEFAULT FALSE,  -- internal notes vs customer-visible
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Week 3 Tasks
- [ ] Create ticket_comments table
- [ ] Insert sample comments (50+ across various tickets)
- [ ] Practice string functions: CONCAT, SUBSTRING, UPPER/LOWER
- [ ] Practice date functions: DATE_PART, AGE, date arithmetic
- [ ] Write query: "Show tickets created in the last 7 days with comment count"

---

# Week 4: Linked Lists & Trees (Basics)
### *Act II Continued: Pointers Get Weird*

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

## SQL Project: Week 4

### New Tables
```sql
-- Tags for tickets
CREATE TABLE tags (
    tag_id SERIAL PRIMARY KEY,
    name VARCHAR(50) UNIQUE NOT NULL
);

CREATE TABLE ticket_tags (
    ticket_id INTEGER REFERENCES tickets(ticket_id) ON DELETE CASCADE,
    tag_id INTEGER REFERENCES tags(tag_id) ON DELETE CASCADE,
    PRIMARY KEY (ticket_id, tag_id)
);

-- SLA (Service Level Agreement) tracking
CREATE TABLE sla_policies (
    sla_id SERIAL PRIMARY KEY,
    priority VARCHAR(10),
    response_hours INTEGER,
    resolution_hours INTEGER
);
```

### Week 4 Tasks
- [ ] Create tags and ticket_tags tables
- [ ] Insert tags (bug, feature-request, question, etc.)
- [ ] Tag existing tickets
- [ ] Practice GROUP BY with HAVING
- [ ] Write aggregation queries:
  - Tickets per status
  - Average resolution time by priority
  - Agents ranked by tickets resolved
- [ ] Write subquery: "Tickets with more than average comments"

---

# Week 5: Trees (Advanced) & Graphs
### *Act III: The Hero Enters the Forest (Of Nodes)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading
**Chapter 4: Trees and Graphs (continued)** — BST operations, graph representations, BFS/DFS on graphs

## Learning SQL
**Chapter 10: Joins Revisited** — OUTER JOINs, self-joins, cross joins  
**Chapter 11: Conditional Logic** — CASE expressions, COALESCE, NULLIF

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
                // BFS to mark all connected land
                Queue<int[]> queue = new LinkedList<>();
                queue.offer(new int[]{r, c});
                grid[r][c] = '0';  // mark visited
                
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

## SQL Project: Week 5

### New Table
```sql
-- Audit log for ticket changes
CREATE TABLE ticket_audit_log (
    log_id SERIAL PRIMARY KEY,
    ticket_id INTEGER REFERENCES tickets(ticket_id),
    changed_by INTEGER REFERENCES users(user_id),
    field_changed VARCHAR(50),
    old_value TEXT,
    new_value TEXT,
    changed_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Week 5 Tasks
- [ ] Create audit log table
- [ ] Insert sample audit entries
- [ ] Practice LEFT/RIGHT/FULL OUTER JOINs
- [ ] Write self-join: "Find tickets reassigned from one agent to another"
- [ ] Practice CASE expressions:
  - Ticket age buckets (< 1 day, 1-3 days, 3-7 days, > 7 days)
  - Priority scoring system
- [ ] Write query: "Show all tickets with their current agent and previous agent (if reassigned)"

---

# Week 6: Backtracking & Heaps
### *Act III Continued: The Hero Tries Every Path (Recursively)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading
**Chapter 8: Recursion and Dynamic Programming** — Focus on backtracking section, permutations/combinations

## Learning SQL
**Chapter 12: Transactions** — ACID, BEGIN/COMMIT/ROLLBACK  
**Chapter 13: Indexes and Constraints** — CREATE INDEX, UNIQUE, CHECK

## Templates to Memorize

### Backtracking — Subsets
```java
public List<List<Integer>> subsets(int[] nums) {
    List<List<Integer>> result = new ArrayList<>();
    backtrack(nums, 0, new ArrayList<>(), result);
    return result;
}

private void backtrack(int[] nums, int start, List<Integer> path, List<List<Integer>> result) {
    result.add(new ArrayList<>(path));  // add current subset
    
    for (int i = start; i < nums.length; i++) {
        path.add(nums[i]);           // make choice
        backtrack(nums, i + 1, path, result);
        path.remove(path.size() - 1); // undo choice
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
    // Min heap of size k (keeps k largest)
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
    private PriorityQueue<Integer> small;  // max heap for lower half
    private PriorityQueue<Integer> large;  // min heap for upper half
    
    public MedianFinder() {
        small = new PriorityQueue<>(Collections.reverseOrder());
        large = new PriorityQueue<>();
    }
    
    public void addNum(int num) {
        small.offer(num);
        
        // Balance: small's max <= large's min
        if (!small.isEmpty() && !large.isEmpty() && small.peek() > large.peek()) {
            large.offer(small.poll());
        }
        
        // Size balance: small can have at most 1 more than large
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

## SQL Project: Week 6

### Schema Updates
```sql
-- Add indexes for common queries
CREATE INDEX idx_tickets_status ON tickets(status);
CREATE INDEX idx_tickets_priority ON tickets(priority);
CREATE INDEX idx_tickets_created ON tickets(created_at);
CREATE INDEX idx_tickets_user ON tickets(user_id);
CREATE INDEX idx_comments_ticket ON ticket_comments(ticket_id);

-- Add constraint
ALTER TABLE tickets ADD CONSTRAINT valid_status_priority 
    CHECK (NOT (priority = 'urgent' AND status = 'closed'));
```

### Week 6 Tasks
- [ ] Add indexes to commonly queried columns
- [ ] Use EXPLAIN ANALYZE to compare query performance
- [ ] Practice transactions:
  - Transfer ticket between agents (atomic operation)
  - Batch status updates
- [ ] Write query with explicit transaction handling
- [ ] Add CHECK constraints for data integrity

---

# Week 7: Dynamic Programming (1D)
### *The Dark Night of the Soul: DP Makes Everything Click (Or Doesn't)*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading
**Chapter 8: Recursion and Dynamic Programming (continued)** — Memoization, bottom-up approach, classic DP problems

## Learning SQL
**Chapter 14: Views** — CREATE VIEW, updatable views, materialized views  
**Chapter 15: Metadata** — Information schema, system catalogs

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
        dp[i] = Math.max(dp[i - 1], dp[i - 2] + nums[i]);  // skip or take
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

## SQL Project: Week 7

### Views
```sql
-- View: Active tickets with full details
CREATE VIEW active_tickets_detail AS
SELECT 
    t.ticket_id,
    t.subject,
    t.status,
    t.priority,
    t.created_at,
    u.full_name AS customer_name,
    u.email AS customer_email,
    c.name AS category,
    a.full_name AS assigned_agent,
    (SELECT COUNT(*) FROM ticket_comments tc WHERE tc.ticket_id = t.ticket_id) AS comment_count
FROM tickets t
JOIN users u ON t.user_id = u.user_id
LEFT JOIN categories c ON t.category_id = c.category_id
LEFT JOIN ticket_assignments ta ON t.ticket_id = ta.ticket_id
LEFT JOIN users a ON ta.agent_id = a.user_id
WHERE t.status NOT IN ('resolved', 'closed');

-- View: Agent performance metrics
CREATE VIEW agent_metrics AS
SELECT 
    u.user_id,
    u.full_name,
    COUNT(DISTINCT ta.ticket_id) AS tickets_assigned,
    COUNT(DISTINCT CASE WHEN t.status = 'resolved' THEN t.ticket_id END) AS tickets_resolved,
    ROUND(AVG(EXTRACT(EPOCH FROM (t.updated_at - t.created_at))/3600), 2) AS avg_resolution_hours
FROM users u
LEFT JOIN ticket_assignments ta ON u.user_id = ta.agent_id
LEFT JOIN tickets t ON ta.ticket_id = t.ticket_id
WHERE u.role = 'agent'
GROUP BY u.user_id, u.full_name;
```

### Week 7 Tasks
- [ ] Create active_tickets_detail view
- [ ] Create agent_metrics view
- [ ] Query information_schema for table metadata
- [ ] Practice view usage in complex queries
- [ ] Write documentation comments for tables/columns

---

# Week 8: DP (2D), Tries, Union-Find, Intervals
### *The Final Battle: The Hero Faces All Remaining Patterns At Once*

[↑ Back to Navigation](#-quick-navigation)

## CTCI Reading
**Chapter 8 (continued):** 2D DP patterns  
**Chapter 16: Moderate Problems** — Interval problems, various techniques

## Learning SQL
**Chapter 16: Analytic Functions** — Window functions: ROW_NUMBER, RANK, LAG, LEAD, SUM OVER  
**Review:** Go back through any weak areas

## Templates to Memorize

### 2D DP Grid
```java
public int uniquePaths(int m, int n) {
    int[][] dp = new int[m][n];
    
    // First row and column are all 1s
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
            parent[x] = find(parent[x]);  // path compression
        }
        return parent[x];
    }
    
    public boolean union(int x, int y) {
        int px = find(x), py = find(y);
        if (px == py) return false;
        
        // Union by rank
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

## SQL Project: Week 8 — Final Polish

### Window Functions
```sql
-- Running total of tickets created per day
SELECT 
    DATE(created_at) AS date,
    COUNT(*) AS daily_tickets,
    SUM(COUNT(*)) OVER (ORDER BY DATE(created_at)) AS running_total
FROM tickets
GROUP BY DATE(created_at)
ORDER BY date;

-- Rank agents by tickets resolved this month
SELECT 
    u.full_name,
    COUNT(*) AS resolved_count,
    RANK() OVER (ORDER BY COUNT(*) DESC) AS rank
FROM users u
JOIN ticket_assignments ta ON u.user_id = ta.agent_id
JOIN tickets t ON ta.ticket_id = t.ticket_id
WHERE t.status = 'resolved'
    AND t.updated_at >= DATE_TRUNC('month', CURRENT_DATE)
GROUP BY u.user_id, u.full_name;

-- Compare each ticket's resolution time to category average
SELECT 
    t.ticket_id,
    t.subject,
    c.name AS category,
    EXTRACT(EPOCH FROM (t.updated_at - t.created_at))/3600 AS resolution_hours,
    AVG(EXTRACT(EPOCH FROM (t.updated_at - t.created_at))/3600) 
        OVER (PARTITION BY t.category_id) AS category_avg_hours
FROM tickets t
JOIN categories c ON t.category_id = c.category_id
WHERE t.status = 'resolved';
```

### Week 8 Tasks
- [ ] Master window functions: ROW_NUMBER, RANK, DENSE_RANK
- [ ] Practice LAG/LEAD for comparing consecutive rows
- [ ] Write running totals and moving averages
- [ ] Create final documentation for your ticket database
- [ ] Export schema for use in larger project

---

# 📊 Progress Tracker
### *The Montage Checklist*

[↑ Back to Navigation](#-quick-navigation)

## Weekly Checklist

### Week 1: Arrays & Hashing
- [ ] Read CTCI Chapter 1
- [ ] Read Learning SQL Chapters 1-3
- [ ] Memorize 3 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Set up PostgreSQL + create ticket database schema
- [ ] Insert sample data

### Week 2: Two Pointers & Sliding Window
- [ ] Read Learning SQL Chapters 4-5
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add ticket_assignments table
- [ ] Practice JOIN queries

### Week 3: Binary Search & Stacks
- [ ] Read CTCI Chapters 3, 10
- [ ] Read Learning SQL Chapters 6-7
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add ticket_comments table
- [ ] Practice string/date functions

### Week 4: Linked Lists & Trees Basics
- [ ] Read CTCI Chapters 2, 4
- [ ] Read Learning SQL Chapters 8-9
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add tags tables
- [ ] Practice GROUP BY and subqueries

### Week 5: Trees Advanced & Graphs
- [ ] Read CTCI Chapter 4 (graphs)
- [ ] Read Learning SQL Chapters 10-11
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add audit log table
- [ ] Practice OUTER JOINs and CASE

### Week 6: Backtracking & Heaps
- [ ] Read CTCI Chapter 8 (backtracking)
- [ ] Read Learning SQL Chapters 12-13
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Add indexes
- [ ] Practice transactions

### Week 7: Dynamic Programming (1D)
- [ ] Read CTCI Chapter 8 (DP)
- [ ] Read Learning SQL Chapters 14-15
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Create views
- [ ] Query metadata

### Week 8: DP 2D, Tries, Union-Find, Intervals
- [ ] Read CTCI Chapter 8, 16
- [ ] Read Learning SQL Chapter 16
- [ ] Memorize 4 templates from memory
- [ ] Complete 20 LeetCode problems
- [ ] Master window functions
- [ ] Finalize database documentation

---

# 🎬 The Climax

### *The Hero Emerges, Transformed*

[↑ Back to Navigation](#-quick-navigation)

**After 8 Weeks:**
- ✅ 160 algorithm problems solved
- ✅ 30+ templates memorized cold (in Java! ☕)
- ✅ CTCI read cover-to-cover (relevant chapters)
- ✅ Learning SQL completed
- ✅ Production-ready ticket support database
- ✅ **REDEMPTION ARC COMPLETE** 🏆

*[Inspirational music swells]*

*[Hero walks into interview room with slow-motion confidence]*

*[Interviewer asks about binary search]*

*[Hero smiles knowingly]*

*[Writes Java without looking up syntax]*

---

# 💡 Daily Reminders

### *Words To Live By During Your Redemption Arc*

[↑ Back to Navigation](#-quick-navigation)

1. **Write templates from memory first** — If you can't write it cold, you haven't learned it
2. **Understand, don't memorize solutions** — Know WHY the pattern works
3. **Time yourself** — Medium problems in 25 min, Hard in 40 min
4. **Review on Sundays** — Re-attempt problems you struggled with
5. **Keep job apps going** — 3-5 applications daily, non-negotiable
6. **Trust the process** — Consistent daily effort beats sporadic cramming
7. **Remember why you're here** — Baby #2 is coming, and this hero has bills to pay
8. **Java will feel natural by Week 3** — Push through the initial friction

---

# 🎬 Credits

[↑ Back to Navigation](#-quick-navigation)

**Starring:** Tiger 🐯  
**Supporting Cast:** Claude, NeetCode, CTCI, Learning SQL, PostgreSQL, Java ☕  
**Produced by:** Necessity  
**Directed by:** Determination  
**Original Score:** Lo-fi beats to grind LeetCode to  
**Language:** Java — because we're going enterprise-ready for this redemption

*No recruiters were harmed in the making of this redemption arc.*

*Stay tuned for the sequel: "employment-arc" (coming Q1 2025)*

---

**You've got this, Tiger. 8 weeks of focused work and you'll be ready. Let's get it! 🔥**

*[Roll credits]*
