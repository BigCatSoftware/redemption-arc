# 🎬 redemption-arc

### *From "we'll keep your resume on file" to "when can you start?"*

> **Mission:** Deep-dive into algorithm patterns and SQL fundamentals to land a software engineering role ASAP. This is the training montage. The dramatic music is playing. The interviewer doesn't stand a chance.

**Start Date:** Week of December 9, 2024  
**Daily Commitment:** 3-4 hours focused work  
**Philosophy:** Depth over breadth. Master each pattern before moving on.  
**Vibe:** Rocky running up the steps, but the steps are LeetCode problems and the meat punching is PostgreSQL.

---

## 📚 Resources

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

*Every redemption arc needs a training montage. This is yours.*

**Sundays:** Review week's templates from memory. Re-attempt any problems you struggled with. Stare dramatically out a window contemplating your journey.

---

## 📋 Weekly Overview

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
```python
def frequency_count(arr):
    freq = {}
    for num in arr:
        freq[num] = freq.get(num, 0) + 1
    return freq
```
**Use for:** Anagrams, duplicates, counting problems, two-sum variants

### Hash Set for O(1) Lookup
```python
def has_duplicate(arr):
    seen = set()
    for num in arr:
        if num in seen:
            return True
        seen.add(num)
    return False
```
**Use for:** Duplicate detection, membership testing, complement finding

### Prefix Sum Array
```python
def prefix_sum(arr):
    prefix = [0] * (len(arr) + 1)
    for i in range(len(arr)):
        prefix[i + 1] = prefix[i] + arr[i]
    # Range sum [i, j] = prefix[j+1] - prefix[i]
    return prefix
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

## CTCI Reading
**Chapter 1 (continued):** Focus on in-place manipulation, string problems

## Learning SQL
**Chapter 4: Filtering** — WHERE conditions, AND/OR/NOT, BETWEEN, IN, LIKE  
**Chapter 5: Querying Multiple Tables** — INNER JOIN basics

## Templates to Memorize

### Two Pointers — Opposite Ends
```python
def two_sum_sorted(arr, target):
    left, right = 0, len(arr) - 1
    while left < right:
        curr_sum = arr[left] + arr[right]
        if curr_sum == target:
            return [left, right]
        elif curr_sum < target:
            left += 1
        else:
            right -= 1
    return []
```
**Use for:** Two-sum on sorted array, container problems, palindrome validation

### Two Pointers — Same Direction (Fast/Slow)
```python
def remove_duplicates(arr):
    if not arr:
        return 0
    slow = 0
    for fast in range(1, len(arr)):
        if arr[fast] != arr[slow]:
            slow += 1
            arr[slow] = arr[fast]
    return slow + 1
```
**Use for:** Remove duplicates, partitioning, linked list cycle detection

### Fixed-Size Sliding Window
```python
def max_sum_subarray(arr, k):
    window_sum = sum(arr[:k])
    max_sum = window_sum
    for i in range(k, len(arr)):
        window_sum += arr[i] - arr[i - k]  # slide: add right, remove left
        max_sum = max(max_sum, window_sum)
    return max_sum
```
**Use for:** Max/min/avg of fixed window, any k-element aggregate

### Variable-Size Sliding Window
```python
def min_subarray_len(target, arr):
    left = 0
    window_sum = 0
    min_len = float('inf')
    for right in range(len(arr)):
        window_sum += arr[right]
        while window_sum >= target:
            min_len = min(min_len, right - left + 1)
            window_sum -= arr[left]
            left += 1
    return min_len if min_len != float('inf') else 0
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

## CTCI Reading
**Chapter 3: Stacks and Queues** — Stack operations, implementing with arrays/linked lists  
**Chapter 10: Sorting and Searching** — Binary search fundamentals

## Learning SQL
**Chapter 6: Working with Sets** — UNION, INTERSECT, EXCEPT  
**Chapter 7: Data Generation, Manipulation, and Conversion** — String/number/date functions

## Templates to Memorize

### Binary Search — Find Exact Value
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = left + (right - left) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```
**Use for:** Finding exact element in sorted array

### Binary Search — Find Boundary (Leftmost True)
```python
def binary_search_boundary(arr):
    def condition(mid):
        # Define condition that becomes True at some point
        pass
    
    left, right = 0, len(arr)  # or min/max of search space
    while left < right:
        mid = left + (right - left) // 2
        if condition(mid):
            right = mid  # mid might be answer, keep it
        else:
            left = mid + 1  # mid definitely not answer
    return left
```
**Use for:** First bad version, search insert position, capacity problems

### Monotonic Stack (Decreasing)
```python
def next_greater_element(arr):
    n = len(arr)
    result = [-1] * n
    stack = []  # stores indices
    for i in range(n):
        while stack and arr[i] > arr[stack[-1]]:
            idx = stack.pop()
            result[idx] = arr[i]
        stack.append(i)
    return result
```
**Use for:** Next greater/smaller element, daily temperatures, histogram problems

### Stack for Matching
```python
def valid_parentheses(s):
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in mapping:
            if not stack or stack[-1] != mapping[char]:
                return False
            stack.pop()
        else:
            stack.append(char)
    return len(stack) == 0
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

## CTCI Reading
**Chapter 2: Linked Lists** — Runner technique, recursive approaches  
**Chapter 4: Trees and Graphs** — Tree traversals, BST properties

## Learning SQL
**Chapter 8: Grouping and Aggregates** — GROUP BY, HAVING, COUNT, SUM, AVG, MIN, MAX  
**Chapter 9: Subqueries** — Scalar, correlated, EXISTS

## Templates to Memorize

### Linked List Reversal (Iterative)
```python
def reverse_list(head):
    prev = None
    curr = head
    while curr:
        next_temp = curr.next
        curr.next = prev
        prev = curr
        curr = next_temp
    return prev
```
**Use for:** Reverse entire list, reverse portions, palindrome check

### Fast/Slow Pointers in Linked List
```python
def find_middle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow  # middle node (second middle if even)
```
**Use for:** Find middle, detect cycle (Floyd's), find cycle start

### Tree DFS (Recursive)
```python
def dfs_preorder(root):
    if not root:
        return []
    return [root.val] + dfs_preorder(root.left) + dfs_preorder(root.right)

def dfs_inorder(root):
    if not root:
        return []
    return dfs_inorder(root.left) + [root.val] + dfs_inorder(root.right)

def dfs_postorder(root):
    if not root:
        return []
    return dfs_postorder(root.left) + dfs_postorder(root.right) + [root.val]
```
**Use for:** Any tree traversal, path problems, tree construction

### Tree BFS (Level Order)
```python
from collections import deque

def bfs_level_order(root):
    if not root:
        return []
    result = []
    queue = deque([root])
    while queue:
        level_size = len(queue)
        level = []
        for _ in range(level_size):
            node = queue.popleft()
            level.append(node.val)
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
        result.append(level)
    return result
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

## CTCI Reading
**Chapter 4: Trees and Graphs (continued)** — BST operations, graph representations, BFS/DFS on graphs

## Learning SQL
**Chapter 10: Joins Revisited** — OUTER JOINs, self-joins, cross joins  
**Chapter 11: Conditional Logic** — CASE expressions, COALESCE, NULLIF

## Templates to Memorize

### BST Search and Validation
```python
def search_bst(root, target):
    if not root or root.val == target:
        return root
    if target < root.val:
        return search_bst(root.left, target)
    return search_bst(root.right, target)

def is_valid_bst(root, min_val=float('-inf'), max_val=float('inf')):
    if not root:
        return True
    if root.val <= min_val or root.val >= max_val:
        return False
    return (is_valid_bst(root.left, min_val, root.val) and 
            is_valid_bst(root.right, root.val, max_val))
```
**Use for:** BST search, validation, insert, delete

### Graph BFS
```python
from collections import deque

def bfs(graph, start):
    visited = set([start])
    queue = deque([start])
    while queue:
        node = queue.popleft()
        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
    return visited
```
**Use for:** Shortest path (unweighted), level-based problems, connectivity

### Graph DFS
```python
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)
    return visited
```
**Use for:** Connectivity, cycle detection, path finding, topological concepts

### Grid BFS (Islands Pattern)
```python
from collections import deque

def num_islands(grid):
    if not grid:
        return 0
    rows, cols = len(grid), len(grid[0])
    count = 0
    
    def bfs(r, c):
        queue = deque([(r, c)])
        grid[r][c] = '0'  # mark visited
        while queue:
            row, col = queue.popleft()
            for dr, dc in [(0,1), (0,-1), (1,0), (-1,0)]:
                nr, nc = row + dr, col + dc
                if 0 <= nr < rows and 0 <= nc < cols and grid[nr][nc] == '1':
                    grid[nr][nc] = '0'
                    queue.append((nr, nc))
    
    for r in range(rows):
        for c in range(cols):
            if grid[r][c] == '1':
                bfs(r, c)
                count += 1
    return count
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

## CTCI Reading
**Chapter 8: Recursion and Dynamic Programming** — Focus on backtracking section, permutations/combinations

## Learning SQL
**Chapter 12: Transactions** — ACID, BEGIN/COMMIT/ROLLBACK  
**Chapter 13: Indexes and Constraints** — CREATE INDEX, UNIQUE, CHECK

## Templates to Memorize

### Backtracking — Subsets
```python
def subsets(nums):
    result = []
    
    def backtrack(start, path):
        result.append(path[:])  # add current subset
        for i in range(start, len(nums)):
            path.append(nums[i])
            backtrack(i + 1, path)
            path.pop()  # undo choice
    
    backtrack(0, [])
    return result
```
**Use for:** All subsets, combinations, power set

### Backtracking — Permutations
```python
def permutations(nums):
    result = []
    
    def backtrack(path, used):
        if len(path) == len(nums):
            result.append(path[:])
            return
        for i in range(len(nums)):
            if used[i]:
                continue
            used[i] = True
            path.append(nums[i])
            backtrack(path, used)
            path.pop()
            used[i] = False
    
    backtrack([], [False] * len(nums))
    return result
```
**Use for:** All permutations, arrangement problems

### Heap — Top K Pattern
```python
import heapq

def top_k_largest(nums, k):
    # Min heap of size k (keeps k largest)
    heap = []
    for num in nums:
        heapq.heappush(heap, num)
        if len(heap) > k:
            heapq.heappop(heap)
    return heap  # or heap[0] for kth largest
```
**Use for:** K largest/smallest, k most frequent

### Two Heaps — Median
```python
import heapq

class MedianFinder:
    def __init__(self):
        self.small = []  # max heap (negate values)
        self.large = []  # min heap
    
    def addNum(self, num):
        heapq.heappush(self.small, -num)
        # Balance: small's max <= large's min
        if self.small and self.large and -self.small[0] > self.large[0]:
            heapq.heappush(self.large, -heapq.heappop(self.small))
        # Size balance
        if len(self.small) > len(self.large) + 1:
            heapq.heappush(self.large, -heapq.heappop(self.small))
        elif len(self.large) > len(self.small):
            heapq.heappush(self.small, -heapq.heappop(self.large))
    
    def findMedian(self):
        if len(self.small) > len(self.large):
            return -self.small[0]
        return (-self.small[0] + self.large[0]) / 2
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

## CTCI Reading
**Chapter 8: Recursion and Dynamic Programming (continued)** — Memoization, bottom-up approach, classic DP problems

## Learning SQL
**Chapter 14: Views** — CREATE VIEW, updatable views, materialized views  
**Chapter 15: Metadata** — Information schema, system catalogs

## Templates to Memorize

### Top-Down Memoization
```python
def fib_memo(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fib_memo(n-1, memo) + fib_memo(n-2, memo)
    return memo[n]
```
**Use for:** Understanding subproblem structure, easier to conceptualize

### Bottom-Up Tabulation
```python
def fib_tab(n):
    if n <= 1:
        return n
    dp = [0] * (n + 1)
    dp[1] = 1
    for i in range(2, n + 1):
        dp[i] = dp[i-1] + dp[i-2]
    return dp[n]
```
**Use for:** Production code, often more space-efficient

### Space-Optimized DP
```python
def fib_optimized(n):
    if n <= 1:
        return n
    prev2, prev1 = 0, 1
    for _ in range(2, n + 1):
        curr = prev1 + prev2
        prev2 = prev1
        prev1 = curr
    return prev1
```
**Use for:** When only need previous 1-2 states

### Include/Exclude Pattern
```python
def house_robber(nums):
    if not nums:
        return 0
    if len(nums) == 1:
        return nums[0]
    
    dp = [0] * len(nums)
    dp[0] = nums[0]
    dp[1] = max(nums[0], nums[1])
    
    for i in range(2, len(nums)):
        dp[i] = max(dp[i-1], dp[i-2] + nums[i])  # skip or take
    
    return dp[-1]
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

## CTCI Reading
**Chapter 8 (continued):** 2D DP patterns  
**Chapter 16: Moderate Problems** — Interval problems, various techniques

## Learning SQL
**Chapter 16: Analytic Functions** — Window functions: ROW_NUMBER, RANK, LAG, LEAD, SUM OVER  
**Review:** Go back through any weak areas

## Templates to Memorize

### 2D DP Grid
```python
def unique_paths(m, n):
    dp = [[1] * n for _ in range(m)]
    for i in range(1, m):
        for j in range(1, n):
            dp[i][j] = dp[i-1][j] + dp[i][j-1]
    return dp[m-1][n-1]
```
**Use for:** Path counting, grid minimum/maximum paths

### Trie Implementation
```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.is_end = False

class Trie:
    def __init__(self):
        self.root = TrieNode()
    
    def insert(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]
        node.is_end = True
    
    def search(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                return False
            node = node.children[char]
        return node.is_end
    
    def starts_with(self, prefix):
        node = self.root
        for char in prefix:
            if char not in node.children:
                return False
            node = node.children[char]
        return True
```
**Use for:** Prefix matching, autocomplete, word search problems

### Union-Find with Path Compression
```python
class UnionFind:
    def __init__(self, n):
        self.parent = list(range(n))
        self.rank = [0] * n
    
    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])  # path compression
        return self.parent[x]
    
    def union(self, x, y):
        px, py = self.find(x), self.find(y)
        if px == py:
            return False
        if self.rank[px] < self.rank[py]:
            px, py = py, px
        self.parent[py] = px
        if self.rank[px] == self.rank[py]:
            self.rank[px] += 1
        return True
```
**Use for:** Connected components, cycle detection, dynamic connectivity

### Interval Merge
```python
def merge_intervals(intervals):
    intervals.sort(key=lambda x: x[0])
    merged = []
    for interval in intervals:
        if not merged or merged[-1][1] < interval[0]:
            merged.append(interval)
        else:
            merged[-1][1] = max(merged[-1][1], interval[1])
    return merged
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

**After 8 Weeks:**
- ✅ 160 algorithm problems solved
- ✅ 30+ templates memorized cold
- ✅ CTCI read cover-to-cover (relevant chapters)
- ✅ Learning SQL completed
- ✅ Production-ready ticket support database
- ✅ **REDEMPTION ARC COMPLETE** 🏆

*[Inspirational music swells]*

*[Hero walks into interview room with slow-motion confidence]*

*[Interviewer asks about binary search]*

*[Hero smiles knowingly]*

---

# 💡 Daily Reminders

### *Words To Live By During Your Redemption Arc*

1. **Write templates from memory first** — If you can't write it cold, you haven't learned it
2. **Understand, don't memorize solutions** — Know WHY the pattern works
3. **Time yourself** — Medium problems in 25 min, Hard in 40 min
4. **Review on Sundays** — Re-attempt problems you struggled with
5. **Keep job apps going** — 3-5 applications daily, non-negotiable
6. **Trust the process** — Consistent daily effort beats sporadic cramming
7. **Remember why you're here** — Baby #2 is coming, and this hero has bills to pay

---

# 🎬 Credits

**Starring:** Tiger 🐯  
**Supporting Cast:** Claude, NeetCode, CTCI, Learning SQL, PostgreSQL  
**Produced by:** Necessity  
**Directed by:** Determination  
**Original Score:** Lo-fi beats to grind LeetCode to  

*No recruiters were harmed in the making of this redemption arc.*

*Stay tuned for the sequel: "employment-arc" (coming Q1 2025)*

---

**You've got this, Tiger. 8 weeks of focused work and you'll be ready. Let's get it! 🔥**

*[Roll credits]*
