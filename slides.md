---
theme: seriph
title: 'MTH252'
background: https://mth252.fastzhong.com/images/cover.webp
highlighter: shiki
lineNumbers: false
colorSchema: 'light'
---

# MTH252

Data Structures and Algorithms II

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Zhong Lun
  </span>
</div>

---

# About Me

<br/>

<i class="fab fa-linkedin"></i> [https://www.linkedin.com/in/zhonglun/](https://www.linkedin.com/in/zhonglun/)  
<i class="far fa-envelope"></i> [zhonglun@gmail.com](zhonglun@gmail.com)  
<i class="fas fa-mobile-alt"></i> 9647 7009

<br/>

<img src="/images/linkedin.png" style="border-radius: 8px; width:50%"/>

---

# Course Structure

<br/>

<div grid="~ cols-2 gap-4">
  <div>
    <p>
      Mar ~ Apr 6 weeks, 6 lectures & 6 labs
    </p>  
    <p>Learning Objectives:</p>
    <p class="norm">
      <ol>
        <li><span class="hl-bg">Priority Queue</span>, <span class="hl-bg">Binary Heap</span>, <span class="hl-bg">Hash Table</span></li>
        <li>Search Trees: <span class="hl-bg">Binary Search Tree</span>, <span class="hl-bg">AVL</span>, and <span class="hl-bg">Skip List</span></li>
        <li>Sorting: <span class="hl-bg">Insertion Sort</span>, <span class="hl-bg">Selection Sort</span>, <span class="hl-bg">Bubble Sort</span>, <span class="hl-bg">Merge-Sort</span>, <span class="hl-bg">Quick Sort</span> <br/> Selection: <span class="hl-bg">Prune-and-Search</span>, <span class="hl-bg">Randomized-Quicksort</span></li>
        <li>Text Processing: <span class="hl-bg">Brute-Force</span>, <span class="hl-bg">Boyer-Moore</span>, <span class="hl-bg">Knuth-Morris-Pratt</span> and <span class="hl-bg">Dynamic Programming</span></li>
        <li>Graph: <span class="hl-bg">Depth-First Search</span>, <span class="hl-bg">Breadth-First Search</span>, <span class="hl-bg">Dijkstra's Shortest Path</span>, and <span class="hl-bg">Min-Spanning Tree</span> </li>
        <li>Review and more</li>
      </ol>
    </p>
  </div>
  <div>
    3 assignments & open book exam:
    <p class="norm">
      <img src="/images/assessment.png" style="width:80%"/>
    </p>
  </div>
</div>

---

# Slides & Notebooks

<br/>

slides online: [https://mth252.fastzhong.com/](https://mth252.fastzhong.com/)

<mdi-file-pdf /> [https://mth252.fastzhong.com/mth252.pdf](https://mth251.fastzhong.com/mth252.pdf)

<logos-github-octocat /> labs: [https://github.com/fastzhong/mth252/tree/main/public/notebooks](https://github.com/fastzhong/mth252/tree/main/public/notebooks)

<br/>

<br/>

👉 Python & Big O review: [MTH251 lab1](https://mth252.fastzhong.com/)

<br/>

<p class="norm">
🏃‍♂️ learning by doing, implementing the algo from scratch  <br/>
🙇🏻‍♂️ problem solving
</p>

---

# Learning Resource

[📚 books](https://github.com/fastzhong/mth251/tree/main/public/resources)

<div grid="~ cols-4 gap-4">
  <div><img src="/images/study_guide.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/study_book.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/common-sense.jpg" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/grokking.jpg" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/algorithms.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/intro_algorithms.png" style="width: 140px; height: 180px"/></div>
</div>

---

# Learning Resource

<br/>

if you want to dive deeper into proofs and the mathematics of computer science:

📚 [Building Blocks for Theoretical Computer Science](https://mfleck.cs.illinois.edu/building-blocks/index-sp2020.html) by Margaret M. Fleck

---

# Clarification

<br/>

### Solution related to DSA questions:

⚠️ <span class="norm">always seek the best time and space complexity by appling DSA taught in MTH251 & MTH252</span>

⚠️ <span class="norm">in principle, only the standard ADT operations allowed to use by default as the solution has to be language indenpendent</span>

⚠️ <span class="norm">advanced features and built-in functions from Python not allowed if not clearly asked by the question, e.g. sort/search/find (in)/min(list)/max(list)/set/match ... , as the complexity becomes unknown and Python dependent</span>

---
layout: center
---

# Priority Queue

---

# Priority Queue (PQ)

<br/>

-   FIFO/LILO
-   <span class="hl">each element (k, v) has a certain priority k and k must be compariable</span>
-   min priority queue (smaller k, higher priority)
-   max priority queue (bigger k, higher priority)

<br/>

<span class="norm">e.g. printer queue, cpu task scheduler, etc.</span>

<!--
You cannot sort the elements/tasks first, and pick up the highest task, as the first task is finished, there could be some new coming tasks. in another word we need a data structure to DYNAMICALLY maintain the ordering.
-->

---

# Priority Queue: Operations

### Min PQ

-   <span class="hl-strong">add(k, v)</span> (enqueue) − adding an element to the queue
-   <span class="hl-strong">remove_min()</span> (dequeue) − obtain the first element with a pair of (k,v), where k is the mininum value of keys in Min PQ, and remove it from the queue
-   <span class="hl-strong">min()</span> (first/peek) − obtain the first element with a pair of (k,v) where k is the mininum value of keys in Min PQ
-   size(), is_empty()

<br/>

### Max PQ

<span class="hl-strong">add(k, v)</span>, <span class="hl-strong">remove_max()</span>, <span class="hl-strong">max()</span>, size(), is_empty()

---

# Priority Queue Complexity

<br/>

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="30%">unsorted list</th>
        <th id="" width="30%">sorted list</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>is_empty</th>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="even">
        <th>size</th>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>add</th>
        <td>O(1)</td>
        <td>O(n) 👈 </td>
      </tr>
      <tr class="even">
        <th>remove_min</th>
        <td>O(n) 👈 </td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>min</th>
        <td>O(n) 👈 </td>
        <td>O(1)</td>
      </tr>
    </tbody>
  </table>
</div>

---
layout: center
---

# Binary Heap

---

# Binary Heap

<br/>

-   <span class="hl">Complete Binary Tree</span>

-   k value for any node in the tree <span class="hl">smaller than any child node</span>

<br/>

<img src="/images/binary_heap.png" style="width: 60%"/>

<br/>

<span class="norm">👉 A <strong>perfect binary tree</strong> is a tree of which every non-leaf node has two child nodes.</span>  
<span class="norm">👉 A <strong>complete binary tree</strong> is a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible.
</span>

---

# Binary Heap

<br/>

-   key of root is always the smallest (MinHeap) or the largest (MaxHeap)

-   subtree is also a binary heap

-   from root to any leaf, the key values are in non-decreasing order

-   given height $h$, total nodes of binary heap: $2^h \leq n \leq 2^{h+1} - 1$

-   given total nodes $n$, binary heap height: $\log_2(n+1) - 1 \leq h \leq \log_2n$

<!--
if exclude the bottom level, binary heap is a perfect binary tree and nodes is 2^h - 1

low level node is always smaller than the high level node? NO.

child of binary tree is still a binary tree, recusion can be usually considered for tree operations.

-->

---

# Binary Heap

<br/>

<div grid="~ cols-2 gap-12">
  <div>
    <img src="/images/binary_heap_index2.png"/>
  </div>
  <div>
    <br/>
    <table class="grid">
      <tbody>
        <tr class="odd">
          <td>2</td>
          <td>4</td>
          <td>3</td>
          <td>5</td>
          <td>6</td>
          <td>6</td>
          <td>9</td>
          <td>6</td>
          <td>7</td>
          <td>8</td>
        </tr>
        <tr class="even">
          <td>0</td>
          <td>1</td>
          <td><span style="color: orangered">2</span></td>
          <td>3</td>
          <td>4</td>
          <td><span style="color: orangered">5</span></td>
          <td><span style="color: orangered">6</span></td>
          <td>7</td>
          <td>8</td>
          <td>9</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div></div>
  <div>
    <table style="width:60%; font-family: 'Open Sans'; font-size: 0.8rem;">
      <tbody>
      <tr>
        <td align="right">current node</td>
        <td align="center">:</td>
        <td align="left"><span style="font-weight: bolder; color: #357ec7;">i</span></td>
      </tr>
      <tr>
        <td align="right">parent(i)</td>
        <td align="center">=</td>
        <td align="left"><span style="font-weight: bolder; color: #357ec7;">(i - 1) / 2</span></td>
      </tr>
      <tr>
        <td align="right">left_child(i)</td>
        <td align="center">=</td>
        <td align="left"><span style="font-weight: bolder; color: #357ec7;">2 * i + 1</span></td>
      </tr>
      <tr align="left">
        <td align="right">right_child(i)</td>
        <td align="center">=</td>
        <td align="left"><span style="font-weight: bolder; color: #357ec7;">2 * i + 2</span></td>
      </tr>
      </tbody>
    </table>
  </div>
</div>

---
layout: two-cols
---

# Binary Heap

<logos-jupyter />

<br/>

add new element:

1. append to the last (so its still complete binary tree)
2. <span class="hl-strong">sift up</span> if new element is smaller

<br/>

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/Heap.html](https://www.cs.usfca.edu/~galles/visualization/Heap.html)</span>

::right::

<br/>

<br/>

<br/>

<div align="center">
<img src="/images/binary_heap_siftup.jpeg" style="width: 80%"/>
</div>

---
layout: two-cols
---
# Binary Heap

<logos-jupyter />

<br/>

remove the min:

1. replace the first element with the last (so its still complete binary tree)
2. <span class="hl-strong">sift down</span> if the last element is bigger

<br/>

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/Heap.html](https://www.cs.usfca.edu/~galles/visualization/Heap.html)</span>

::right::

<br/>

<br/>

<br/>

<div align="center">
<img src="/images/binary_heap_siftdown.jpeg" style="width: 80%"/>
</div>

---

# Priority Queue Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="25%">Operation</th>
        <th id="" width="25%">unsorted list</th>
        <th id="" width="25%">sorted list</th>
        <th id="" width="25%">binary heap</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>is_empty</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="even">
        <th>size</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>add</th>
        <td>O(1)</td>
        <td>O(n)</td>
        <td>O(logN) 👈 </td>
      </tr>
      <tr class="even">
        <th>remove_min</th>
        <td>O(n)</td>
        <td>O(1)</td>
        <td>O(logN) 👈 </td>
      </tr>
      <tr class="odd">
        <th>min</th>
        <td>O(n)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
    </tbody>
  </table>
</div>

<!--
Binary Heap is always a complete binary tree, so the height is always O(logN), note that the worst case of binary tree is O(N) == linked list.
-->

---

# When & Where

<br/>

Priority Queue (PQ) is used:

-   used in certain implementations of <span class="hl-bg">Dijkstra's Shortest Path</span> algorithm

-   used by <span class="hl-bg">Minimum Spanning Tree</span> (MST) algorithms

-   <span class="hl-bg">Best First Search</span> (BFS) algorithms such as A\* uses PQ to continuously grab the next most promising node

-   used in <span class="hl-bg">Huffman coding</span> (which is often used for lossless data compression)

-   anytime you need to dynamically fetch the "next best" or "next worst" element

-   ...

<!--
Technically Priority Queue can be considered same as binary heap, but Priority Queue is ADT as it can be implemented by other data structure.

There are trees other than binary tree, so there are heaps other than binary heap - D-ary Heap, Fibonacci Heap, Index heap, Binomial Heap, Pairing Heap, etc. But binary heap is very useful and important data structure.
-->

---
layout: two-cols
---
# Heap Sort

<logos-jupyter />

<br/>

Steps:

1. create a binary heap

2. add all elements to the heap

3. recursively obtain the min/max element from the heap

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div style="width: 80%;padding-left: 10px;">

```python
# heap sort

# time complexity: O(NlogN)
# space complexity: O(N)
def heap_sort(nums: []) -> []:
    if not nums:
        return []
    minH = MinHeap()
    for e in nums:
        minH.add((e, e))
    nums_sorted = []
    for i in range(len(nums)):
        nums[i] = minH.remove_min()[0]
    return nums
```

</div>

---
layout: two-cols
---

# Heapify

<logos-jupyter />

<span class="hl">Heapify</span>: convert the array to be a binary heap

by "sift down" the non-leaf node one by one from top to bottom

Complete Binary Tree (Perfect Binary Tree in worst case)
| | | | |
| --------------------: | :------------------ | ---------: | :-------------------------- |
| last level nodes: | $\frac{n}{2}$ | sift_down: | $\frac{n}{2} * 0$ |
| 2nd last level nodes: | $\frac{n}{4}$ | sift_down: | $\frac{n}{4} * 1$ |
| ... | | ... | |
| h+1 last level nodes: | $\frac{n}{2^{h+1}}$ | sift_down: | $\frac{n}{2^{h+1}} \cdot h$ |

::right::

<br/>

<br/>

<br/>

Time Complexity: $O(n)$

<br/>

<div align="center">
  <img src="/images/heapify_complexity.png" style="width: 80%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.6rem;
}
</style>

<!--
last non-leaf node: parent of last leaf node
-->

---
layout: two-cols
---

# Heap Sort

<logos-jupyter />

<br/>

<div style="width: 90%;">

```python
"""
heap_sort: sort nums in place

time complexity: O(N)
space complexity: O(1)
"""
def heap_sort2(nums: []) -> []:
    nums = heapify(nums)
    print("    heapify: ", nums)
    # swap from the last element
    for i in range(len(nums) - 1, 0, -1):
        # move the biggest to the end
        nums[0], nums[i] = nums[i], nums[0]
        # sift down the first element after swap
        # so nums[0, i) is still a max heap
        heapify_sift_down(nums, 0, i)
    return nums
```

</div>

::right::

<br/>

<br/>

<br/>

<img src="/images/heap_sort.png" style="height: 70%"/>

---
layout: center
---

# Map/Hash Table

---

# Map

<br/>

A <span class="hl-bg">Map</span> is an abstract data structure (ADT):

-   a collection of key-value (k,v) paris
-   key can be viewed as a unique identifier for the object/value

<span class="hl-color">k - unique</span>  
v - can be repeated

<br/>

A <span class="hl">Sorted Map</span> is an extension of Map and keys are sorted in increasing order.

<br/>

<span class="norm">🤔 Can we use **none**/**null** for key?</span>

---

# Map

<br/>

students score:

<div style="width: 50%;">

| Student(key) | Score(value) |
| :----------- | :----------- |
| A            | 80           |
| B            | 70           |
| C            | 60           |
| ...          | ...          |

</div>

---

# Map Operations

<br/>

for a map

<pre class="norm">
- map[k], map.get(k)
- map.pop(k)
- map[k] = v, map.set(k) = v, map.put(k,v), map.setdefault(k, default)
- map.keys()
- map.values()
- del map[k], map.clear()
- size(map)
- iter(map), map.items()
</pre>

---

# Map Operations

<br/>

for a sortedMap

<pre class="norm">
- sortedMap.find_min()
- sortedMap.find_max()
- sortedMap.find_lt(k)
- sortedMap.find_le(k)
- sortedMap.find_gt(k)
- sortedMap.find_ge(k)
- sortedMap.find_range(k1, k2)
- sortedMap.reversed()
</pre>

---

# Map Implementation

<br/>

-   Array/ArrayList
-   Linked List
-   Binary Search Tree
-   <span class="hl-color">Hash Table</span>
-   <span class="hl-color">Skip List</span>

---

# Map Implementation: Linked List

<br/>

-   store (k,v) in a doubly linked list
-   get(k)
    -   <span class="norm">loop through the list until find the element with key k</span>
-   set(k,v)
    -   <span class="norm">create a new node (k,v) and add it at the front</span>
-   delete(k)
    -   <span class="norm">loop through the list until find the element with key k</span>
    -   <span class="norm">remove it by updating the pre and next elements</span>

<span class="norm">👉 Complexity: $O(n)$</span>

<style>

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}

</style>

---

# Hash Table

<br/>

A <span class="hl-bg">Hash table</span> is a data structure that provides a mapping from keys to values using a technique called <span class="hl-color">hashing</span>.

A hash function <span class="hl-color">H(x)</span> is a function that maps a <span class="uline">general</span> key ‘x’ to a whole number in a fixed range [0, N-1].

💡 <span class="norm">locate the element without searching: </span>$O(n)$ → $O(1)$

<!--
large keys → small keys (indexable)
-->

---

# Hash Function

<br/>

step1. Hash Code: abitrary object → integer

<p class="norm">An element is converted into an integer by using a hash function. This element can be used as an index to store the original element, which falls into the hash table.
<br/>

```
hash = hashcode(key)
```

</p>

step2. Compression: $integer \in [0, N-1]$ (N is the size of hash table)

<p class="norm">
The element is stored in the hash table where it can be quickly retrieved using hashed key.
<br/>

```
index = hash % array_size
```

</p>

---

# Hash Code: Bit Representation

<div style="width: 80%;">

```python
# XOR byte by byte
def byte_xor(ba1, ba2):
    return bytes([_a ^ _b for _a, _b in zip(ba1, ba2)])

# produce 32-byte hash code
# chop the data into 32-byte long chunks (padding with zeros if required)
# then XOR on all chunks
def bitwise_xor(data):
    chunks = [data[i:i+32] for i in range(0, len(data), 32)]
    for i in range(len(chunks)):
        chunk = chunks[i]
        hexchunk = chunk.hex()
        len_diff = 32 - len(chunk)
        if len_diff:
            hexchunk += '00' * len_diff
            chunk = bytearray.fromhex(hexchunk)
            chunks[i] = chunk
    res = bytes.fromhex('00' * 32)
    for chunk in chunks:
        res = byte_xor(res, chunk)
    return res
```

</div>

👉 <span class="norm">[MD5](https://en.wikipedia.org/wiki/MD5)&nbsp;&nbsp;&nbsp; [SHA-256](https://en.wikipedia.org/wiki/SHA-2)</span>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Code: Polynomial & Cyclic-Shift

### Polynomial

for n-tuple $(x_0, x_1, x_2, ..., x_{n-1})$, if position is important, we can multiply $a^{n-1}$ for position $n$, e.g.:

$x_0·a^0 + x_1·a^1  + x_2·a^2  + ...  + x_{n-1}·a^{n-1}$

### Cyclic-Shift

for bitwise, we can also apply cyclic-shift function instead of multiplication, e.g. shift(x, y) means cyclic-shift y bits:

$shift(x_0, 0\;mod\;32) \oplus shift(x_1, 1\;mod\;32)  \oplus shift(x_2, 2\;mod\;32)  \oplus ...  \oplus shift(x_{n-1}, (n-1)\;mod\;32)$

💬 5-bit cyclic shift operation can achieve the smallest total collisions when 230,000 English words

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Compression

<br/>

for hash code $x$:

-   Division Method: $x\;mod\;N$

-   MAD: $(a\;\cdot\;x + b)\;mod\;p$
    where $p$ is a prime number, $p > N$, $a$ and $b$ are random number, $a\in[0, p-1]$, $b\in[0, p-1]$

<br/>

👉 <span class="norm">[good hash table primes](https://planetmath.org/goodhashtableprimes) </span>

---
layout: two-cols
---

# Hash Function

<br/>

a number of (k, v) pairs with key set {“abcdef”, “bcdefa”, “cdefab” , “defabc”}

The ASCII values of a, b, c, d, e, and f are 97, 98, 99, 100, 101, and 102 respectively.

| key    |             Hash Function              | Index |
| :----- | :------------------------------------: | :---- |
| abcdef | (97 + 98 + 99 + 100 + 101 + 102) % 599 | 2     |
| bcdefa | (98 + 99 + 100 + 101 + 102 + 97) % 599 | 2     |
| cdefab | (99 + 100 + 101 + 102 + 97 + 98) % 599 | 2     |
| defabc | (100 + 101 + 102 + 97 + 98 + 99) % 599 | 2     |

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hash_example1.jpeg" style="width:70%; height: 70%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---
layout: two-cols
---

# Hash Function

<br/>

a number of (k, v) with key set {“abcdef”, “bcdefa”, “cdefab” , “defabc”}

The ASCII values of a, b, c, d, e, and f are 97, 98, 99, 100, 101, and 102 respectively.

| key    |                 Hash Function                 | Index |
| :----- | :-------------------------------------------: | :---- |
| abcdef | (971 + 982 + 993 + 1004 + 1015 + 1026) % 2069 | 38    |
| bcdefa | (981 + 992 + 1003 + 1014 + 1025 + 976) % 2069 | 23    |
| cdefab | (991 + 1002 + 1013 + 1024 + 975 + 986) % 2069 | 14    |
| defabc | (1001 + 1012 + 1023 + 974 + 985 + 996) % 2069 | 11    |

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hash_example2.jpeg" style="width:70%; height: 70%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---
layout: two-cols
---

# Hash Function: Collision

### chaining (open hashing)

-   one element: $O(1)$

-   more than one element: **linked list** $O(1) + O(n)$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/hash_chaining.png" style="width:60%"/>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Collision

### open address (closed hashing)

Finding an unused, or open, location in the hash table is called <span class="hl-strong">open addressing</span>.

The process of locating an open location in the hash table is called <span class="hl-strong">probing</span>.

Various probing techniques:

<br/>

<div grid="~ cols-3 gap-4">
  <div class="norm">
    <span class="hl">linear probing</span><br/><br/>
    <img src="/images/probing_linear.svg"/><br/>
    index = (index + 1) % hashTableSize<br/>
    index = (index + 2) % hashTableSize<br/>
    index = (index + 3) % hashTableSize<br/>
    ...
  </div>
  <div class="norm">
    <span class="hl">quadratic probing</span><br/><br/>
    <img src="/images/probing_quadratic.svg"/><br/>
    index = (index + 1^2) % hashTableSize<br/>
    index = (index + 2^2) % hashTableSize<br/>
    index = (index + 3^2) % hashTableSize<br/>
    ...
  </div>
  <div class="norm">
    <span class="hl">double probing</span><br/><br/>
    <img src="/images/probing_double.svg"/><br/>
    index = (index + 1 * H2) % hashTableSize<br/>
    index = (index + 2 * H2) % hashTableSize<br/>
    index = (index + 3 * H2) % hashTableSize<br/>
    ...
  </div>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Collision

<br/>

⚠️ probing may go into cycles (**an infinite loop**) (hashing attack)

⚠️ chaos when removing element from hash table

<br/>

<div grid="~ cols-2 gap-4" class="norm">
  <div>k % 10, linear probing, k1=11, k2=21, k3=31</div>
  <div>&nbsp;</div>
  <div>
    - put(k1,v1)&nbsp;&nbsp;&nbsp;(probing: 1)<br/>
    - put(k2,v2)&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>
    - put(k3,v3)&nbsp;&nbsp;&nbsp;(probing: 1 → 2 → 3)<br/>
  </div>
  <div><img src="/images/hash_linear1.png"></div>
  <div>
    - del(k2)&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>
    - <span style="color:red">get(k3)</span>&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>
  </div>
  <div><img src="/images/hash_linear2.png"></div>
</div>

---
layout: two-cols
---

# Hash Table: resize

<br/>

$M$<span class="norm">: total num of map elements</span>  
$O$<span class="norm">: num of occupied buckets</span>  
$N$<span class="norm">: size of hash table</span>  
$P$<span class="norm">: new size of hash table (expand or shrink)</span>

when:

-   load factor (for open addressing): $\frac{O}{N}$
-   tolerance factor (for closed addressing): $\frac{M}{N}$

how:

-   size(<span class="norm">[good hash table primes](https://planetmath.org/goodhashtableprimes)</span>): $N$ → $P$
-   rehashing: $H(x)\;mod\;N$ → $H(x)\;mod\;P$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/hash_chaining.png" style="width:60%"/>

---

# Hash Function

<br/>

$H(x)$:

-   deterministic
-   fast as $O(1)$
-   universal input
-   evenly distributed
-   randomly distributed

<br/>

<div style="width: 90%;">

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering.

</div>

---
layout: two-cols
---

# Hash Function

<br/>

-   if $x = y$, H(x) and H(y) <span class="uline">must be equal</span>
-   if $H(x) = H(y)$, x and y <span class="uline">might be equal</span>
-   if $H(x) \ne H(y)$, x and y <span class="uline">certainly not equal</span>

<br/>

<span class="norm">💡 coding tips:</span>

-   <span class="norm">avoid to use real or big number as key: $H(0.0) == H(-0.0)$ ?</span>
-   <span class="norm">compare hash code first, before compare x and y</span>
-   <span class="norm">overwrite either both of **eq** and **hash** or neither of them</span>

::right::

<br/>

<br/>

<br/>

<br/>

```python
class UserGroup:

  def __init__(self, name, status):
    self.name = name
    self.status = status

  def __hash__(self):
    result = 17
    result = 31 * result + hash(name)
    if not status:
      result = 31 * result + hash(status)
    return result

  def __eq__(self, other):
    if isinstance(other, UserGroup):
      return self.__hash__() == other.__hash__()
    return False
```

---

# Map/Hash Table Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Operation</th>
        <th id="">avg case</th>
        <th id="">best case</th>
        <th id="">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---
layout: two-cols
---

# Industrial Implementation

<logos-java/> HashMap

-   hash code

<table style="width:90%; font-family: 'Open Sans'; font-size: 0.8rem;">
  <tbody>
    <tr>
      <td align="right"><strong>Key Type</strong></td>
      <td align="left"><strong>hashCode(k)</strong></td>
    </tr>
    <tr>
      <td align="right">boolean</td>
      <td align="left">k? 0 : 1</td>
    </tr>
    <tr>
      <td align="right">byte, char, short, int</td>
      <td align="left">k</td>
    </tr>
    <tr>
      <td align="right">long</td>
      <td align="left">(int)(k XOR (k >>> 32))</td>
    </tr>
    <tr>
      <td align="right">float</td>
      <td align="left">Float.floatToIntBits(k)</td>
    </tr>
    <tr>
      <td align="right">double</td>
      <td align="v">long l = Double.doubleToIntLongBits(k)<br/>(int)(l XOR (l >>> 32))</td>
    </tr>
    <tr>
      <td align="right">string/array</td>
      <td align="v">s[0]*31^(n-1) + s[1]*31^(n-2)+ ... + s[n-1]</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">similarly for compound data type, like Object k with $n$ fields, a way to implement hashCode():</span>

$h = h(k_0)*31^{n-1} + h(k_1)*31^{n-2} + ... + h(k_{n-1})$

```java
String name;
int age;

@Override
public int hashCode() {
    int result = name != null ? name.hashCode() : 0;
    result = 31 * result + age;
    return result;
}
```

---
layout: two-cols
---

# Industrial Implementation

<logos-java/> HashMap

-   compression/indexing: $h\;\&\;(n - 1)$

<span class="norm">when table size $n$ is $2^y$: </span> $x\;\%\;2^y = x\;\&\;(y - 1)$

<span class="norm">e.g.</span>

$6\;\%\;8 = 6$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$6\;\&\;7 = 6$
$10\;\%\;8 = 2$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$10\;\&\;7 = 2$

<img src="/images/hashmap_index.webp" style="height:20%"/>

<br/>

<span class="norm">👉 binary bit operation <span class="hl">&</span> is much faster then decimal mod</span>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">then XOR between the first 16 bits and the last 16 bits:</span>

$H(k) =  (h\;XOR\;(h\;>>>\;16))\;\&\;(n - 1)$

<br/>

<div>
  <img src="/images/hashmap_hash.png" style="width:80%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

<logos-java/> HashMap

-   Collision: chaining
    -   **linked list** $O(1) + O(n)$
    -   $< Java 8$, insert at the beginneing (⚠️ deadlock in concurrent insertion);
        $> Java 8$, append to the tail
    -   **treemap/red black tree** (more than 8 elements and table size ≧ 64) $O(1) + O(logN)$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hashmap_collision1.jpeg" style="width:80%"/>
  <img src="/images/hashmap_collision2.png" style="width:80%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

<logos-java/> HashMap

-   hash table size
    -   always $2^n$,&nbsp;&nbsp;&nbsp;default: $16$, &nbsp;&nbsp;&nbsp;max: $2^{30}$
    -   load factor: $0.75$
    -   optimize rehashing

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">size $16$ → $16 * 2$: </span>

<div>
  <img src="/images/hashmap_rehash1.png" style="width:80%"/>
  <img src="/images/hashmap_rehash2.png" style="width:80%"/>
</div>

---

# Industrial Implementation

<logos-java/> HashMap

-   HashMap for HashSet: HashSet&#60;E&#62; → HashMap&#60;E, Object&#62;
    -   <span class="norm">{e1, e2, e3, ...} → (e1, PRESENT), (e2, PRESENT), (e3, PRESENT), ... </span>

<br/>

<span class="norm">👉 source code: [https://github.com/frohoff/jdk8u-jdk/blob/master/src/share/classes/java/util/HashMap.java](https://github.com/frohoff/jdk8u-jdk/blob/master/src/share/classes/java/util/HashMap.java)</span>

<!--

We dont have another section to study Set data structure, as it can be converted from Map/HashTable. Map/HashTable can be converted from Set also.

-->

---
layout: center
---

# Binary Search Tree

---
layout: two-cols
---

# Binary Search Tree (BST)

<br/>

<span class="hl-bg">Binary Search Tree</span> (BST) is a binary tree and:

-   left subtree has smaller elements
-   right subtree has bigger elements

<br/>

💡 any BST subtree is still a BST  
💡 BST node must be comparable

<br/>

<span class="norm">💬 in some BST implementation all values are unique, so we exclude duplicates now</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/binary_search_tree1.png" style="width:70%"/>
</div>

<!--
Linear Search vs Binary Search
-->

---

# BST: Operations

<br/>

-   search()
-   insert()
-   delete()
-   first()
-   last()
-   before()
-   after()
-   is_empty()

<br/>

<span class="norm">💬 1962, Hibbard Deletion</span>

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/BST.html](https://www.cs.usfca.edu/~galles/visualization/BST.html)</span>

---
layout: two-cols
---

# BST: Hibbard Deletion

<logos-jupyter />

<br/>

-   del min

-   del max

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div>
  <img src="/images/hibbard1.png" style="width:90%"/>
</div>

---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div>
  <img src="/images/hibbard2.png" style="width:90%"/>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div class="inline-grid grid-cols-[4fr,1fr,4fr] gap-2">
  <div>
    <img src="/images/binary_search_tree1.png"/>
  </div>
  <div style="color: green; text-align: center;">
    <br/><br/>
    <mdi-arrow-right-bold/> <br/>
    <span class="norm">del 10</span>
  </div>
  <div>
    <img src="/images/binary_search_tree2.png"/>
  </div>
</div>

<span class="norm">"node with 1 child node"</span>

---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div>
  <img src="/images/hibbard2.png" style="width:90%"/>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div class="inline-grid grid-cols-[4fr,1fr,4fr] gap-2">
  <div>
    <img src="/images/binary_search_tree2.png"/>
  </div>
  <div style="color: green; text-align: center;">
    <br/><br/>
    <mdi-arrow-right-bold/> <br/>
    <span class="norm">del 77</span>
  </div>
  <div>
    <img src="/images/binary_search_tree3.png"/>
  </div>
</div>

<span class="norm">"node with 2 child nodes"</span>

---

# BST: Traversal

<br/>

-   pre-order
-   in-order: "sorted list" 👈
-   post-order
-   level order

<!--

pre/in/post depends on when we want to proces the node, e.g. for memory management in C++, we probably want to do GC for the node when GC is done for left & right subtree, so post-order may be a choice.

-->

---

# Binary Search Tree Complexity

<br/>

<div style="width: 60%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="30%">avg case</th>
        <th id="" width="30%">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---

# When & Where

<br/>

Binary Search Tree (BST) is used:

-   implementation of <span class="hl-bg">AVL Tree</span> <span class="hl-bg">Red Black Tree</span> etc.

-   syntax trees used by compiler and calculator

-   <span class="hl-bg">Treap</span> - a probabilistic data structure

-   ...

---
layout: two-cols
---

# BST vs Heap

<br/>

-   <span class="hl">Heap</span> is <span class="uline">balanced</span> tree, <span class="hl">BST</span> is not

-   <span class="hl">Heap</span> allows duplicates, <span class="hl">BST</span> doesnot

-   <span class="hl">BST</span> is ordered data structure, <span class="hl">Heap</span> is not

-   worst case for building $n$ nodes of <span class="hl">BST</span> $O(n \cdot log(n))$, <span class="hl">Heap</span> is $O(n)$ (heapify)

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/binary_search_tree4.png" style="width:30%"/>
</div>

---
layout: center
---

# AVL

---
layout: two-cols
---

# AVL

-   named after inventors G.M. <span class="hl-color">A</span>del’son-<span class="hl-color">V</span>el’skii and E.M. <span class="hl-color">L</span>andis, 1962

-   first type of <span class="hl-bg">Balanced Binary Search Tree</span> (BBST)

-   height balanced: $BF$ - balance factor  
    $BF = H(node.right) - H(node.left)$  
    $BF \in {-1, 0, 1}$

-   heigh and no. of nodes: $O(logN)$

<br/>

<span class="norm">Examples:</span>

-   <span class="norm">perfect binary tree (minimum heigh)</span>
-   <span class="norm">complete binary tree</span>
-   <span class="norm">Binary Heap, Red Black Tree, Segment Tree, etc.</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl1.png" style="width:70%"/>
</div>

<!--
The example is a binary search tree, not complete binary tree, but it is balanced.
-->

---
layout: two-cols
---

# AVL Balance Factor

<logos-jupyter />

<div align="center">
  <img src="/images/avl1.png"/>
</div>

::right::

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl2.png"/>
</div>

<br/>

Rebalance ?

-   When: insert(), delete()
-   Where: backtracking from the node

<!--
As we implement insert(), delete() with recurion, backtracking can be done with recursion.
-->

---

# AVL insert & delete

<logos-jupyter />

<br/>

Steps:

1. update Height

2. compute Balance Factor

3. left/right rotation if unbalanced

<br/>

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/AVLtree.html](https://www.cs.usfca.edu/~galles/visualization/AVLtree.html)</span>

<!--

delete:

1. _delete_max rebalance?
2. reb_node could be None? (delete leaf node)

-->

---
layout: two-cols
---

# AVL Right Rotate (LL)

<logos-jupyter />

$T1 < z < T2 < y < T3 < z < T4$

<div style="width: 80%;">

```md
-   y.right = x
-   x.left = T3
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl-right-rotate.png"/>
</div>

---
layout: two-cols
---

# AVL Left Rotate (RR)

<logos-jupyter />

$T4 < x < T3 < y < T1 < z < T2$

<div style="width: 80%;">

```md
-   y.left = x
-   x.right = T3
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl-left-rotate.png"/>
</div>

---
layout: two-cols
---

# AVL LR → LL

<logos-jupyter />

<br/>

<br/>

<div style="width: 80%;">

```md
1. LR → LL: left rotate
2. LL: right rotate
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl-LR.png"/>
</div>

---
layout: two-cols
---

# AVL RL → RR

<logos-jupyter />

<br/>

<br/>

<div style="width: 80%;">

```md
1. RL → RR: right rotate
2. RR: left rotate
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl-RL.png"/>
</div>

---

# BST vs AVL Complexity

<br/>

<div style="width: 80%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Operation</th>
        <th id="">BST avg</th>
        <th id="">BST worst</th>
        <th id="">AVL avg</th>
        <th id="">AVL worst</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

AVL: $O(N)$ → $O(logN)$

<!--

- Height: after re-compute height, if no change, there is no need to re-balance for all parent nodes

- Red Black Tree better than AVL

-->

---
layout: center
---

# Red Black Tree

---

# Red Black Tree

<br/>

A <span class="hl-bg">red-black tree</span> is a binary tree that satisfies the following <span class="uline">red-black properties</span>:

1. every node is either red or black
2. the root is black
3. every leaf (NIL) is black
4. if a node is red, both its children are black
5. for each node, all simple paths from the node to descendant leaves contain the same number of black nodes

---
layout: two-cols
---

# 2-3 Tree

<br/>

A <span class="hl-bg">2-3 tree</span> is a B-tree of order 3:

-   <span class="hl">2-node</span>: node with two child nodes
-   <span class="hl">3-node</span>: node with three child nodes
-   <span class="hl-strong">a perfectly balanced tree</span>: all leaf nodes at the same level

::right::

<br/>

<br/>

<div grid="~ cols-2 gap-4">
  <div align="center">
    <span class="norm">2-node</span>
  </div>
  <div align="center">
    <span class="norm">3-node</span>
  </div>
  <div align="center">
    <img src="/images/2-3_tree_2-node.png" style="height: 50%"/>
  </div>
  <div align="center">
        <img src="/images/2-3_tree_3-node.png" style="height: 50%"/>
  </div>  
  <div align="center" style="grid-column: 1 / span 2;">
    <img src="/images/2-3-tree-example.png" style="width: 70%" />
  </div>
</div>

---

# 2-3 Tree

<div style="width: 50%;">

> Insertion is always done on leaf

</div>

<br/>

<div class="inline-grid grid-cols-[5fr,2fr,2fr] gap-2">
  <div style="font-family: 'Open Sans'; font-size: 0.8rem;">
    <img src="/images/2-3-tree-insert.png" style="width: 60%"/>
    <ul>  
      <li><strong>merge</strong>: insert into a node with only data element (2-node leaf)</li>
      <li><strong>merge</strong> & <strong>split</strong>: insert into a node with two data element (3-node leaf) whose parent contains only one data element (2-node parent)</li>
      <li><strong>merge⁺⁺</strong> & <strong>split⁺⁺ </strong>: insert into a node with two data element (3-node leaf) whose parent contains two data element (3-node parent)</li>
    </ul>
  </div>
  <div align="center">
    <img src="/images/avl-insert.png"/>
  </div>
  <div align="center">
    <img src="/images/bs-tree-insert.png"/>
  </div>
</div>

<span class="norm">👉 [https://people.ksp.sk/~kuko/gnarley-trees/23tree.html](https://people.ksp.sk/~kuko/gnarley-trees/23tree.html)</span>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Red Black Tree

<div style="width: 60%;">

> Red Black Tree is equivalent 2-3 Tree

</div>

<br/>

<img src="/images/2-3-red-black.png" style="height: 40%"/>

<!--

red node together with its parent node represents a 3-node in 2-3 tree.

-->

---

# Red Black Tree

<div style="width: 60%;">

> Red Black Tree is equivalent 2-3 Tree

</div>

<br/>

<div class="inline-grid grid-cols-[2fr,1fr,1fr] gap-2">
  <div style="font-family: 'Open Sans'; font-size: 0.8rem;">
    <img src="/images/rb-23-tree.png" style="width: 80%"/>
  </div>
  <div align="center">
    <img src="/images/2-3-tree-insert.png"/>
  </div>
  <div align="center">
    <img src="/images/avl-insert.png"/>
  </div>
</div>

-   "black balanced"

-   $N$ nodes → height: $2logN$, Complexity: $O(logN)$

-   Red Black Tree vs AVL Tree

<!--

1. every node is either red or black
2. the root is black

3. every leaf (NIL) is black
NIL is leaf node also a root of empty tree → 2

4. if a node is red, both its children are black
the child node of 3-node is 2-node or 3-node, so in either case, the child node is a black node
this is not true for black node, for black node, only the right node is black

5. for each node, all simple paths from the node to descendant leaves contain the same number of black nodes
2-3 tree, the paths from a node to leaf nodes, the number of node in the path should be same because 2-3 tree is perfectly balanced
in red-black tree, when we visit a black node, we visit a 2-node or 3-node in the 2-3 tree, so the total number of black node means the total number of nodes for the same path in 2-3 tree.

black-balanced != balanced tree

-->

---

# Red Black Tree

<br/>

insert a red node → a blank tree

<!--

always insert Red node

insert new node to empty tree, change red to black

-->

---
layout: two-cols
---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

### Left Rotate

<div style="width: 90%;">

```md
-   node.right = x.left
-   x.left = node
-   x.color = node.color
-   node.color = RED
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div>
  <img src="/images/rb-LR.png"/>
</div>

---
layout: two-cols
---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

### Flip Colors

<div style="width: 90%;">

```md
-   node.color = RED
-   node.left.color = BLACK
-   node.right.color = BLACK
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div>
  <img src="/images/rb-FC.png"/>
</div>

---
layout: two-cols
---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

### Right Rotate

<div style="width: 90%;">

```md
-   node.left = T1
-   x.right = node
-   x.color = node.color
-   node.color = RED
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div>
  <img src="/images/rb-RR.png"/>
</div>

---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

### insertion: LR → RR → FC

<br/>

<img src="/images/rb-LR-RR-FC.png" style="height: 40%"/>

---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

### insertion: LR → RR → FC

-   2-node
-   3-node

<br/>

<img src="/images/rb-insertion.png" style="height: 40%"/>

---
layout: center
---

# Skip List

---

# Skip List

<div class="inline-grid grid-cols-[2fr,5fr] gap-4">

  <div align="right">1 Level:</div>
  <div><img src="/images/skip1.webp" style="width:50%"/></div>

  <div align="right">2 Levels:</div>
  <div><img src="/images/skip2.webp" style="width:50%"/></div>

  <div align="right">3 Levels:</div>
  <div><img src="/images/skip3.webp" style="width:50%"/></div>

</div>

<!--
sorted linked list for sorted map
-->

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3>search key</h3>
    <logos-jupyter />
  </div>
  <div>
    <br/>
    <img src="/images/skip_search.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3>delete key</h3>
    <logos-jupyter />
  </div>
  <div>
    <br/>
    <img src="/images/skip_del.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3>insert key</h3>
    <logos-jupyter /> 
  </div>
  <div>
    <br/>
    <img src="/images/skip_add1.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3>insert key</h3>
    <logos-jupyter />
  </div>
  <div>
    <br/>
    <img src="/images/skip_add2.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <p>
    Skip List node with an array of pointers: position pointers[0] stores a level 0 pointer, position pointers[1] stores a level 1 pointer, and so on. <br/> <br/>
    When inserting a new value, the levels (depth) for the new node is randomized.
    </p>
  </div>
  <div>
    <br/>
    <img src="/images/skip_pointers.png" style="width:70%"/>
  </div>

</div>

---

# Skip List Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="20%">Operation</th>
        <th id="" width="40%">Skip List avg</th>
        <th id="" width="40%">Link List avg</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN) 👈</td>
        <td>O(N)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
        <td>O(N)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
        <td>O(N)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

<span class="norm">👉 [Skip Lists: A Probabilistic Alternative to Balanced Trees (William Pugh, 1990)](https://15721.courses.cs.cmu.edu/spring2018/papers/08-oltpindexes1/pugh-skiplists-cacm1990.pdf)</span>

<!--
Insert & Delete need to update the searching path, so it depends on Search.
-->

---

# Skip List vs Hash Table, Balanced Tree

<br/>

-   single key search, Hash Table close to $O(1)$
-   for Skip List node, avg no. of pointers $\frac{p}{1-p}$, when $p = \frac{1}{4}$, $1.33 < 2$
-   keys in order, better for range search
-   Skip List operations (linkedlist++) simpler than balanced tree (AVL, Red Black Tree, etc.)
-   Skip List overall implementation simpler

---
layout: center
---

# Sorting

---

# Sorting

<br/>

-   make data in order
-   different <span class="uline">algorithmic thinking</span>

---
layout: two-cols
---

# Sorting: Selection

<logos-jupyter />

<br/>

-   sort the arr from left to right
-   every time select the smallest
-   for position $i$:
    -   $[0, i)$ sorted
    -   $[i,n)$ unsorted
    -   find the smallest from $arr[i, n)$ and place at $arr[i]$
-   Complexity: $1 + 2 + 3 + ... + n = \frac{(n + 1) * n}{2}$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/sort_selection.gif" style="width:90%"/>
</div>

---
layout: two-cols
---

# Sorting: Insertion

<logos-jupyter />

<br/>

-   sort the arr from left to right
-   for postion $i$:
    -   $[0, i)$ sorted
    -   $[i, n)$ unsorted
    -   insert $arr[i]$ to the proper position on the left
-   Complexity: $O(n^2)$, if already sorted → $O(n)$ 👍

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/sort_insertion.gif" style="width:90%"/>
</div>

---
layout: two-cols
---

# Sorting: Bubble

<logos-jupyter />

<br/>

-   sort the arr from right to left
-   for postion $n-i-1$:
    -   $[n-i, n)$ sorted
    -   $[0, n-i-1)$ unsorted
    -   bubble the biggest to $arr[n-i-1]$
-   Complexity: $O(n^2)$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/sort_bubble.gif" style="width:90%"/>
</div>

<!--

bubble up = swap, more time consuming

improve the data overall ordering while bubble up

-->

---
layout: two-cols
---

# Sorting: Merge

<logos-jupyter /> John von Neumann

<img src="/images/JohnvonNeumann.jpeg" style="height:30%"/>

<br/>

-   recursively $[l, m, r]$:
    -   sort $[l, m]$
    -   sort $[m+1, r]$
    -   <span class="hl-strong">merge</span> two sorted array $[l, m]$ & $[m+1, r]$

<br/>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/sort_merge.gif" style="width:90%"/>
</div>

<!--
John von Neumann
-->

---

# Sorting: Merge

<logos-jupyter />

<br/>

-   merge top down: <span class="norm">sort_merge_bottomup_v1</span>  
    improvement: <span class="norm">sort_merge_recusive_v2</span>

    -   <span class="norm">✅ insertion</span>
    -   <span class="norm">❌ tmp</span>

-   merge buttom up: <span class="norm">sort_merge_bottomup</span>

-   worst case ?
    -   <span class="norm">almost sorted array</span>
    -   <span class="norm">duplicates</span>

---
layout: two-cols
---

# Sorting: Merge

<br/>

-   Time Complexity $O(n \cdot log_2n)$
-   Space Complexity $O(n)$

<span class="norm">at each level i = $0,1,2, ..., log_2n$</span>  
<span class="norm">there are $2^i$ subproblems, each of size $\frac{n}{2^i}$</span>  
<span class="norm">total # of operations at level i $\le 2^i \cdot c(\frac{n}{2^i}) = c \cdot n$ </span>  
<span class="norm">complexity on each level is $O(n)$</span>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

"recursion tree"

<div align="left">
  <img src="/images/sort_merge_complexity.png" style="width:90%"/>
</div>

---
layout: two-cols
---

# Sorting: Quick

<logos-jupyter /> Tony Hoare

<img src="/images/TonyHoare.jpeg" style="height:30%"/>

<br/>

-   <span class="hl-strong">partition</span>: select $v$, so that $[l, p-1] \leq v$ and $[p+1, r] \geq v$
-   recursive sort $[l, p-1]$
-   recursive sort $[p+1, r]$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/sort_quick.gif" style="width:90%"/>
</div>

<!--
Tony Hoare

Quick is faster than Merge because partion func is faster than merge function
-->

---

# Sorting: Quick

-   worst case: $O(n^2)$

    -   <span class="norm">sorted array</span>
    -   <span class="norm">duplicates</span>
    -   <span class="norm">$O(n^2)$ possibility: $\frac{1}{n} * \frac{1}{n-1} * \frac{1}{n-2} * ... = \frac{1}{n!}$</span>
    -   <span class="norm">recusion stack overflow</span>

-   improvement:
    -   <span class="norm">2-way quicksort </span>
    -   <span class="norm">3-way quicksort </span>
    -   <span class="norm">[dual pivot quicksort](https://arxiv.org/abs/1503.08498)</span>

<span class="norm"> 👉 random algorithm, time complexity $O(N \cdot log_2N)$ (📚 Introduction to Algorithms)</span>

<!--

Why 3-way: all elements are same, no need to continue as after partition, we can know this if we have 3 partitions:

v (pivot) <v ==v >v

we can continue with <v and >v only

-->

---
layout: two-cols
---

# Sorting

<br/>

Simple Sort:

-   <span class="hl">Selection</span>
-   <span class="hl">Insertion</span>
-   <span class="hl">Bubble</span>

::right::

<br/>

<br/>

<br/>

<br/>

Efficient Sort:

-   <span class="hl">Heap</span>
-   <span class="hl">Merge</span>
-   <span class="hl">Quick</span>

<!--
- element comparable
- optimize
- simple sorts vs efficient sorts
- stability
-->

---

# Sorting: Complexity

<br/>

<div style="width:100%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">sorting</th>
        <th id="">avg</th>
        <th id="" width="25%">best</th>
        <th id="">worst</th>
        <th id="">inplacement</th>
        <th id="">space</th>
        <th id="">stability</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Selection</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>
      <tr class="even">
        <th>Insertion</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n) 👍</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="odd">
        <th>Bubble</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n)<sup>*</sup></td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="even">
        <th>Heap</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>
      <tr class="odd">
        <th>Merge</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n) → O(n)<sup>*</sup></td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td><span class="norm">OUT-place</span></td>
        <td>O(n) 👎</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="even">
        <th>Quick</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n) → O(n)<sup>*</sup></td>
        <td>O(n<sup><span class="norm">2</span></sup>) 👈</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>
    </tbody>
  </table>
</div>

---

# Sorting

<br/>

<div style="width: 80%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="30%"> </th>
        <th id="" width="30%">n<sup><span class="norm">2</span></sup></th>
        <th id="" width="20%">n<sub><span class="norm">log</span></sub>n</th>
        <th id="" width="20%">faster</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>n = 10</th>
        <td>100</td>
        <td>33</td>
        <td>3</td>
      </tr>
      <tr class="even">
        <th>n = 100</th>
        <td>10,000</td>
        <td>664</td>
        <td>15</td>
      </tr>
      <tr class="odd">
        <th>n = 1,000</th>
        <td>1,000,000</td>
        <td>9,966</td>
        <td>100</td>
      </tr>
      <tr class="even">
        <th>n = 10,000</th>
        <td>100,000,000</td>
        <td>132,877</td>
        <td>753</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

👉 <span class="norm"><span class="hl-strong">1hr</span> vs <span class="hl-strong">31days</span> (≈ 753hrs)</span>

---

# Sorting: stability

<br/>

Stable sort algorithms sort equal elements in the same order that they appear in the input:

<br/>

<div align="center">
  <img src="/images/sort_stability.png" style="width: 20%"/>
</div>

---

# Sorting

<br/>

<div align="center">
  <img src="/images/sorting_algos.png" style="width: 70%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

<span class="hl-color"><mdi-link/>[Timsort](https://bugs.python.org/file4451/timsort.txt)</span>

<div style="width:90%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">sorting</th>
        <th id="">best</th>
        <th id="">avg</th>
        <th id="">worst</th>
      </tr>
    </thead>
    <tbody>
      <tr class="even">
        <th>Merge</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
      </tr>
      <tr class="odd">
        <th>Quick</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
      </tr>
      <tr class="even">
        <th class="hl-color">Timsort</th>
        <td>O(n) 👈</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

<span class="norm">✅ size < 64 → insertion sort</span>  
<span class="norm">✅ otherwise → "adaptive merge sort"</span>

::right::

<br/>

<br/>

<br/>

<br/>

2 types of sorting operations:

-   <span class="norm">moving or coping objects (just one step)</span>
-   <span class="norm">comparing two objects:</span>
    <span class="norm">compare class type → compare method → if not, ...</span>

<br/>

<span class="norm">⚠️ comparing objects is very expensive</span>

---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

-   **run**: parts that are strictly increasing (if decreasing, reverse it)
-   split into multiple runs
-   **Galloping**: merge runs

<br/>

<pre class="norm">
[1, 2, 3, ..., 100, ..., 101, 102, 103, ..., 200]  
run1 = [1, 2, 3, , ..., 100]  
run2 = [101, 102, 103, , ..., 200]  
......
</pre>

$run2[2^{n-1} - 1] \leq run1[0] \leq run2[2^n - 1]$

<span class="norm">binary search: $O(N)$ → $O(logN)$</span>

---

# Industrial Implementation

<logos-java/> Arrays.sort() or Collections.sort()

-   primitive array: **Dual Pivot Quicksort**

-   object array: **Timsort**

---
layout: center
---

# Selection

---

# Selection

<br/>

In computer science, a <span class="hl-color">selection algorithm</span> is an algorithm for finding the k<sup>th</sup> smallest number in a list or array; such a number is called the k<sup>th</sup> order statistic. This includes the cases of finding the minimum, maximum, and median elements.

<span class="norm">🙂 sort the array first $O(NlogN)$</span>

---

# Select K

### Heap

Solution 1: complexity $O(N) + O(KlogN)$

1.  heapify (Min Heap)
2.  pop $k$ times (remove_min)

<br/>

Solution 2: complexity $O(K) + O(NlogK)$

1. create a Max Heap with size $k$, add element one by one:

    - if smaller than the top, replace it;
    - else skip it

2. min()

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Select K

### Quick Sort

<br/>

```python
p = partition(arr, l, r)
sort_quick_recursive(arr, l, p - 1)
sort_quick_recursive(arr, p + 1, r)
```

$k == p?$  
$k < p?$  
$k > p?$

complexity $O(n + n/2 + n/4 + ... + 1) = O(2n) = O(n)$

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Pruning

<br/>

-   brute force
    -   BFS
    -   DFS
-   Do not visit any subtree that be judged to be irrelevant to the final results.

<br/>

The elimination of a large group of possibilities in one step is known as pruning:  
<span class="norm">👉 binary search </span>  
<span class="norm">👉 [alpha-beta pruning](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_pruning)</span>  
<span class="norm">👉 [decision tree pruning](https://en.wikipedia.org/wiki/Decision_tree_pruning)</span>

---
layout: center
---

# Text Processing

---

# Text Processing

### Algorithms on Strings

-   docs editors, emails, messages

-   web sites, search engine

-   bio-data (genonme sequencing)

-   natual language processing (NLP)

-   ...

<br/>

<span class="norm">Example: </span>

<pre class="norm">
“Hello World”
“http://www.google.com”
“CGTAAACTGCTTTAATCAAACGC”
</pre>

---

# Pattern Matching

<br/>

<span class="hl">Pattern Matching</span>  
For a text string $S$ with a length of $n$, and a pattern string $P$ with length of $m$, decides if $P$ is a substring of $S$.

<br/>

<span class="hl">Approximate Pattern Matching</span>

-   input: a text string $S$ with a length of $n$, a pattern string $P$ with length of $m$, and an integer $d$

-   output: all positions in $S$ where $P$ appears as a substrign <span class="ul">with at most $d$ mismatches</span>

<!--

Approximate Pattern Matching (fuzzle matching?) in genome sequencing detection

Pattern Matching is a searching problem.

-->

---

# Pattern Matching

<br/>

-   <span class="hl-bg">Brute Force</span>

-   <span class="hl-bg">Rabin-Karp</span> <span class="norm">(Michael O. Rabin and Richard M. Karp, 1987)</span>

-   <span class="hl-bg">Knuth-Morris-Pratt Algorithm</span> (KMP) <span class="norm">(Knuth, Morris and Pratt, 1977)</span>

-   <span class="hl-bg">Boyer-Moore Algorithm</span> (BM) <span class="norm">(Robert S. Boyer and J Strother Moore, 1970, 1974, 1977 )</span>

-   <span class="hl-bg">Sunday Algorithm</span> (Sunday) <span class="norm">(Daniel M.Sunday, 1990)</span>

---
layout: center
---

# Brute Force

---

# Brute Force

<logos-jupyter />

<br/>

<img src="/images/string_matching_brute_force.png" style="width:80%"/>

<!--

in worst case, scan the whole pattern

if string -> integer

compare two strings O(n) -> compare two integers O(1)

-->

---
layout: center
--- 

# Rabin-Karp

---

# Rabin-Karp

<br/>

<div align="center">
  <img src="/images/string_matching_rabin_karp.png" style="width:70%"/>
</div>

---
layout: two-cols
---

# Rabin-Karp

<logos-jupyter />

### Rolling Hash

$S$ with a length of $n$, and a pattern string $P$ with length of $m$  
for $i = m-1...n - 1$, compute hashing $h(i)$ for substring S[i-m+1...i]:

$B = 256$  
$M = 1e9 + 7$  
$BP = B^{m-1}\;\%\;M$

h(i-1): S[i-m+1] ... S[i-1]  
&nbsp;&nbsp;&nbsp;h(i): <span style="text-decoration: line-through red;">S[i-m+1]</span> ... S[i-1] S[i]

-   $h[i] = (h * B + S[i])\;\%\;M$

-   $h = h[i-1] - s[i-m+1] * B^{m-1}\;\%\;M$  
    $h = (h[i-1] - s[i-m+1] * B^{m-1}\;\%\;M + M)\;\%\;M$ ⏰  
    $h = (h[i-1] - s[i-m+1] * BP\;\%\;M + M)\;\%\;M$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">e.g. m = 5</span>  
"54321": $5 * 10^4 + 4 * 10^3 + 3 * 10^2 + 2 * 10^1 + 1 * 10^0$  
"bbabc": $b * 256^4 + b * 256^3 + a * 256^2 + b * 256^1 + c * 256^0$

<br/>

<br/>

<br/>

<br/>

<br/>

$(a + b)\;\%\;M = (a\;\%\;M + b\;\%\;M)\;\%\;M$  
$(a * b)\;\%\;M = (a\;\%\;M * b\;\%\;M)\;\%\;M$

<!--

Rabin-Karp = rolling hashing (sliding window)

Rabin-Karp worst case: find all "aaa" from "aaaaaaaaa"

Brute-Force not so bad for usual case

-->

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.6rem;
}
</style>

---
layout: center
---

# Knuth-Morris-Pratt

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<span class="hl-color">prefix/suffix</span>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>b</td>
      <td>c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td  style="color:orangered">d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td>c</td>
      <td>b</td>
      <td style="color:orangered">e</td>
      <td>a</td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>b</td>
      <td style="color:orangered">c</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
      <td rowspan="2" style="background-color: white">👎</td>      
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td style="color:orangered">b</td>
      <td>c</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
      <td>a</td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>b</td>
      <td>c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td  style="color:orangered">d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
      <td rowspan="2" style="background-color: white">👍</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td> </td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="color:orangered">c</td>
      <td>b</td>
      <td>e</td>
      <td>a</td>
      <td> </td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/kmp1.png" style="width: 80%"/>
  <br/>
  <br/>
  <br/>
  longest common "<span class="hl">prefix/suffix</span>"
</div>

<br/>

<br/>

<pre class="norm">
P: b c b c e a  

prebuild the array to store the next position to shift for any substrings of P: 
b, b c, b c b, b c b c, b c b c e, b c b c e  

</pre>

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<br/>

<span class="hl">next array</span>

<div style="width: 90%">
  <span class="norm">P: b c b c b e a</span>
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="30%">substring</th>
        <th id="">last pos</th>
        <th id="">prefix last char</th>
        <th id="" width="30%">next pos</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>b</th>
        <td>0</td>
        <td>-1</td>
        <td>next[0] = -1</td>
      </tr>
      <tr class="even">
        <th>b c</th>
        <td>1</td>
        <td>-1</td>
        <td>next[1] = -1</td>
      </tr>
      <tr class="odd">
        <th>b c b</th>
        <td>2</td>
        <td>0 (b)</td>
        <td>next[2] = 0</td>
      </tr>
      <tr class="even">
        <th>b c b c</th>
        <td>3</td>
        <td>1 (b c)</td>
        <td>next[3] = 1</td>
      </tr>
      <tr class="odd">
        <th>b c b c b</th>
        <td>4</td>
        <td>2 (b c b)</td>
        <td>next[4] = 2</td>
      </tr>
      <tr class="even">
        <th>b c b c b e</th>
        <td>5</td>
        <td>-1</td>
        <td>next[5] = -1</td>
      </tr>
    </tbody>
  </table>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>b</td>
      <td>c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td  style="color:orangered">d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td>c</td>
      <td>b</td>
      <td style="color:orangered">e</td>
      <td>a</td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">j</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td style="color:orangered">5</td>
      <td></td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

<br/>

<span class="norm">char to compare in pattern: $j = 5$</span>  
<span class="norm">bad char: $P[5]$</span>  
<span class="norm">substring: $P[0:5]$ (b c b c b)</span>  
<span class="norm">look for longest common prefix/suffix: $next[5-1]$</span>  
<span class="norm">next char to compare in pattern: $j = next[5-1] + 1 = 2 + 1 = 3$</span>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>b</td>
      <td>c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td  style="color:orangered">d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td> </td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="color:orangered">c</td>
      <td>b</td>
      <td>e</td>
      <td>a</td>
      <td> </td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">j</td>
      <td> </td>
      <td> </td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td style="color:orangered">3</td>
      <td></td>
      <td></td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<logos-jupyter />

for i = 0...n, compare $S[i]$ and $P[j]$:

-   $S[i]\;==\;P[j]$

    -   if $j = m$, $P$ is found in $S$
    -   else move both $S$ and $P$ to next char  
        $i++$, $j++$

-   $S[i]\;!=\;P[j]$ (bad char)
    -   if longest common prefix/suffx found, next char to compare:  
        $j = next[j-1] + 1$
    -   else compare from the begining (∵ $next[j-1] = -1$):  
        $j = next[j-1] + 1 = -1 + 1 = 0$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

```python
for i in range(len_s):
        while j > 0 and s[i] != p[j]:
            # refer to slides: "bad char" found
            j = next_arr[j - 1] + 1
        if s[i] == p[j]:
            j += 1
        if j == len_p:
            return i - len_p + 1
```

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<logos-jupyter />

<span class="hl">next array</span>

Give $next[i-1] = k$ and $P[i] = x$ then $next[i]$?

case1: $P[k+1] == x$, than $next[i] = k + 1$

case2: if not, continuously look for $k'$, so that $P[k'+1] == x$

$k$: $next[i-1]$ → $next[k]$ → $next[next[k]]$ → $next[next[next[k]]]$ .....

$x?$: $P[k]$ → $P[next[k]]$ → $P[next[next[k]]]$ → ......

```python
while k != -1 and p[k + 1] != p[i]:
    k = next_arr[k]
if p[k + 1] == p[i]:
    k += 1
next_arr[i] = k
```

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/kmp2.png" style="width: 80%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

</style>

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<br />

<span class="hl">worst case: $O(n + (m-1)*n/m + m)$</span>

<img src="/images/kmp_worst.jpeg" style="width: 80%"/>

::right::

<br/>

<br/>

<br/>

<br/>

<span class="hl">best case: $O(n + 1*n/m + m)$</span>

<img src="/images/kmp_best.jpeg" style="width: 80%"/>

---
layout: center
---

# Boyer-Moore

---
layout: two-cols
---

# Boyer-Moore (BM)

### bad char heuristic

<br/>

<div align="center"> 
  <img src="/images/string_matching_bm1.png" style="width: 80%"/>
  <img src="/images/string_matching_bm2.png" style="width: 80%"/>
  <br/>
  <img src="/images/string_matching_bm3.png" style="width: 80%"/>
  <img src="/images/string_matching_bm4.png" style="width: 80%"/>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_bm5.png" style="width: 80%"/>
  <img src="/images/string_matching_bm6.jpeg" style="width: 80%"/>
  <br/>
  <img src="/images/string_matching_bm7.jpeg" style="width: 80%"/>
  <br/>
  
  <span class="hl">"bad char"</span>

</div>

<!--

E mistach and not in Pattern
B mistach and in Pattern, bad char lookup good, align
D mistach and in Pattern, bad char lookup good, align

if there are two or more bad char in Pattern? right most

-->

---

# Boyer-Moore (BM)

### bad char heuristic

look for the <span class="uline">right most</span> bad char:

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
    <img src="/images/bm_bad_char1.png"/>
  </div>
  <div>&nbsp</div>
  <div>
    <img src="/images/bm_bad_char2.png"/>
  </div>
  <div>❌</div>
  <div>
    <img src="/images/bm_bad_char3.png"/>
  </div>
  <div>✅</div>
</div>

---
layout: two-cols
---

# Boyer-Moore (BM)

### bad char heuristic

<span class="hl">bad char</span> shift $d = j - b$

-   where $S[i+j]$ is the bad char, and $P[b] == S[i+j]$ is the right most bad char
-   if $P[b]$ doesnot exist, let $b = -1$

<br/>

<span class="norm">💬 bad char offset $b$ can be pre-built for bad char position $j$ ($P[j]$) for all possible missing char in <span class="hl">2-D</span> lookup table $badchar\_tbl$ ?</span>

<br/>

::right::

<br/>

<br/>

<div style="margin:5%; width:90%">
  <img src="/images/string_matching_bm5.png" style="width: 90%"/>
  <img src="/images/string_matching_bm6.jpeg" style="width: 90%"/>
</div>

<div style="margin:5%; width:90%">
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>B</td>
        <td>D</td>
        <td>C</td>
        <td>B</td>
        <td>C</td>
        <td style="color:orangered">D</td>
        <td>D</td>
        <td>B</td>
        <td>B</td>
        <td>C</td>
        <td>D</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td>B</td>
        <td>C</td>
        <td style="font-weight:bold; color:green">D</td>
        <td>B</td>
        <td>A</td>
        <td style="color:orangered">C</td>
        <td>D</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">j</td>
        <td>0</td>
        <td>1</td>
        <td style="font-weight:bold; color:green">2</td>
        <td>3</td>
        <td>4</td>
        <td style="color:orangered">5</td>
        <td></td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
      </tr>
    </tbody>
  </table>

$d = 5 - 2 = 3$

  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>B</td>
        <td>D</td>
        <td>C</td>
        <td>B</td>
        <td>C</td>
        <td style="color:orangered">D</td>
        <td>D</td>
        <td>B</td>
        <td>B</td>
        <td>C</td>
        <td>D</td>
      </tr>
      <tr class="odd">
        <td style="font-weight:bolder">i</td>
        <td>0</td>
        <td>1</td>
        <td>2</td>
        <td>3</td>
        <td></td>
        <td></td>
        <td></td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td></td>
        <td></td>
        <td></td>
        <td>B</td>
        <td>C</td>
        <td style="font-weight:bold; color:green">D</td>
        <td>B</td>
        <td>A</td>
        <td style="color:orangered">C</td>
        <td>D</td>
        <td></td>
      </tr>
    </tbody>
  </table>

</div>

---
layout: two-cols
---

# Boyer-Moore (BM)

### bad char heuristic

let $P[b]$ be the right most char <span class="uline">regardless $j$</span>

-   case1: bad char not found $d = j - b = j - (-1)$

-   case2: bad char found and $b < j$, $d = j - b$

-   case3: when $d \leq 0$, let $d = 1$ (might not be the optimized shift)

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">P</td>
      <td>a</td>
      <td>b</td>
      <td>d</td>
      <td>a</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">index</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
  </tbody>
</table>

$badchar\_tbl$ becomes <span class="hl">1-D</span> table:

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">bad char</td>
      <td>0</td>
      <td>1</td>
      <td>...</td>
      <td>97</td>
      <td>98</td>
      <td>99</td>
      <td>100</td>
      <td>...</td>
      <td>255</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">b</td>
      <td>-1</td>
      <td>-1</td>
      <td>...</td>
      <td style="font-weight:bold; color:green">3</td>
      <td style="font-weight:bold; color:green">1</td>
      <td>-1</td>
      <td style="font-weight:bold; color:green">2</td>
      <td>...</td>
      <td>-1</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

**case1**:

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td>b</td>
        <td>c</td>
        <td style="font-weight:bolder; color:orangered">d</td>
        <td>e</td>
        <td>f</td>
        <td>g</td>
        <td>f</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td>e</td>
        <td>f</td>
        <td>g</td>
        <td>f</td>
      </tr>
    </tbody>
  </table>  
  </div>
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td>b</td>
        <td>c</td>
        <td style="font-weight:bolder; color:orangered">d</td>
        <td>e</td>
        <td>f</td>
        <td>g</td>
        <td>f</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>e</td>
        <td>f</td>
        <td>g</td>
        <td>f</td>
      </tr>
    </tbody>
  </table>  
  </div>
</div>

**case2**:

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td>b</td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">e</td>
        <td>c</td>
        <td>d</td>
        <td>g</td>
        <td>f</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">e</td>
        <td>c</td>
        <td>d</td>
      </tr>
    </tbody>
  </table>  
  </div>
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td>b</td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">e</td>
        <td>c</td>
        <td>d</td>
        <td>g</td>
        <td>f</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td></td>
        <td></td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">e</td>
        <td>c</td>
        <td>d</td>
      </tr>
    </tbody>
  </table> 
  </div>
</div>

**case3**:

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td></td>
        <td style="font-weight:bolder; color:orangered">b</td>
        <td>a</td>
        <td>a</td>
      </tr>
    </tbody>
  </table>  
  </div>
  <div>
  <table class="grid">
    <tbody>
      <tr class="odd">
        <td style="font-weight:bolder">S</td>
        <td>a</td>
        <td style="font-weight:bolder; color:orangered">a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
        <td>a</td>
      </tr>
      <tr class="even">
        <td style="font-weight:bolder">P</td>
        <td></td>
        <td></td>
        <td style="font-weight:bolder; color:orangered">b</td>
        <td>a</td>
        <td>a</td>
      </tr>
    </tbody>
  </table>
  </div>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

<br/>

<div align="center">
  <img src="/images/string_matching_bm8.png" style="width: 80%"/>
  <img src="/images/string_matching_bm9.png" style="width: 80%"/>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_bm10.jpeg" style="width: 80%"/>
  <br/>
  <br/>
  <br/>
  "<span class="hl">good suffix</span>"
</div>

<!--
similar to "bad char":

suffix CD exists E mistach and in Pattern
if suffix exists but not in Pattern, shift to the char after good suffix

-->

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

<span class="hl">good suffix</span> on the left, shift $d = j - s$

-   $P[j]$: bad char
-   $P[j+1:m]$ = $P[s:s+k]$: good suffix with length $k = (m-1) - j$

<span class="norm">💬 good suffix with offset $s$ for bad char $P[j]$ can be pre-built in a $suffix$ array</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/bm-suffix.png" style="width: 90%"/>
</div>

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

<br/>

<span class="hl">good suffix</span> NOT on the left, shift $d = m$ ?

<br/>

⚠️ <span class="hl-strong">Prefix</span>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">bad char: "c", good suffix: "d c a", prefix: "c a"</span>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>a</td>
      <td>b</td>
      <td>c</td>
      <td  style="color:orangered">b</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>d</td>
      <td>c</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>c</td>
      <td>c</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td>c</td>
      <td>a</td>
      <td>d</td>
      <td style="color:orangered">c</td>
      <td style="font-weight:bold; color:green">d</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">a</td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>a</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>d</td>
      <td>c</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>c</td>
      <td>c</td>
      <td rowspan="2" style="background-color: white">❌</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td>c</td>
      <td>a</td>
      <td>d</td>
      <td>c</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
    </tr>
  </tbody>
</table>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>a</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>d</td>
      <td>c</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td>c</td>
      <td>c</td>
      <td rowspan="2" style="background-color: white">✅</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">a</td>
      <td>d</td>
      <td>c</td>
      <td>d</td>
      <td>c</td>
      <td>a</td>
      <td> </td>
      <td> </td>      
    </tr>
  </tbody>
</table>

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

a prefix in <span class="hl">good suffix</span>, shift $d = r$

-   $P[j]$: bad char
-   $P[j+1:m]$: good suffix
-   $P[j+2:m]$: potential prefix
-   $P[r:m]$: the largest prefix ($P[0:m-r]$), where $j+2 \leq r \leq m-1$

<span class="norm">💬 prefix for length $m-r$ checking can be pre-built in a $prefix$ array</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/bm-prefix.png" style="width: 90%"/>
</div>

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

-   <span class="hl">Suffix</span><span class="norm"> array: start position of the right most suffix</span>
-   <span class="hl">Prefix</span><span class="norm"> array: True if it is a prefix </span>

<span class="norm">P: "abcdab"</span>

<table class="ops">
  <thead>
    <tr>
      <th id="">good suffix</th>
      <th id="">len</th>
      <th id="" width="30%">suffix</th>
      <th id="" width="40%">prefix</th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <th>b</th>
      <td>1</td>
      <td>suffix[1] = 1</td>
      <td>prefix[1] = false</td>
    </tr>
    <tr class="even">
      <th>ab</th>
      <td>2</td>
      <td>suffix[2] = 0</td>
      <td>prefix[2] = true</td>
    </tr>
    <tr class="odd">
      <th>dab</th>
      <td>3</td>
      <td>suffix[3] = -1</td>
      <td>prefix[3] = false</td>
    </tr>
    <tr class="even">
      <th>cdab</th>
      <td>4</td>
      <td>suffix[4] = -1</td>
      <td>prefix[4] = false</td>
    </tr>
    <tr class="odd">
      <th>bcdab</th>
      <td>5</td>
      <td>suffix[5] = -1</td>
      <td>prefix[5] = false</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<div style="display:flex; justify-content:center; width:100%">

```python
def build_goodsuffix_arr(p):
    m = len(p)
    suffix = [-1 for _ in range(m)]
    prefix = [False for _ in range(m)]
    for i in range(m - 1):
        # two pointers to compare suffix
        j = i
        k = 0
        while j >= 0 and p[j] == p[m - 1 - k]:
            k += 1
            suffix[k] = j
            j -= 1
        if j == -1:
            prefix[k] = True
    return suffix, prefix
```

</div>

<div align="center">
  <img src="/images/bm-prefix-suffix.png" style="width: 80%"/>
</div>

---
layout: two-cols
---

# Boyer-Moore (BM)

### good suffix heuristic

<br/>

1. $d = j - s$ <span class="norm">($s$: right most suffix offset)</span>
2. $d = r$ <span class="norm">(prefix $P[r:m]$ true, where $j+2 \leq r \leq m-1$) </span>
3. $d = m$ <span class="norm">(neither 1 or 2)</span>

::right::

<br/>

<br/>

<br/>

<br/>

```python
def search_bm_shift_goodsuffix(suffix, prefix, m, j):
    k =  m - 1 - j # length of good suffix
    # look for right most suffix with length k
    if suffix[k] != -1:
        # "suffix" exists
        return j - suffix[k] + 1
    # look for the largest prefix in P[j+2...m]: j+2 <= r <= m-1
    for r in range(j+2, m, 1):
        if prefix[m-r]:
            # "prefix" exists
            return r
    # no suffix, no prefix
    return m
```

---
layout: two-cols
---

# Boyer-Moore (BM)

<logos-jupyter />

locate bad char $P[j]$ then decide $d$:

-   <span class="strong">bad char</span> $d1$

-   <span class="strong">good suffix</span> $d2$

-   $d = max(d1, d2)$

::right::

<br/>

<br/>

<br/>

<br/>

```python
# comapre backward to find "bad char"
for i in range(len_s - len_p + 1):
        j = len_p - 1
        # comapre backward to find "bad char"
        while j >= 0 and s[i+j] == p[j]:
            j -= 1
        if j < 0:
            # p is found
            return i
        # bad char found at s[i+j] != p[j]
        # bad char shift d1
        d1 = j - badchar_tbl[ord(s[i+j])]
        d1 = 1 if d1 <= 0 else d1
        # good suffix shift d2
        d2 = 0
        if len_p - 1 - j > 0:
            d2 = search_bm_shift_goodsuffix(suffix, prefix, len_p, j)
        i += max(d1, d2)
```

---
layout: two-cols
---

# Boyer-Moore (BM)

### Time Complexity

-   best case: $O(m + n/m)$
-   worst case: $O(m + n*m)$ <span class="norm">👉 $\approx 3n$, see linkes below</span>

<br/>

### Space Complexity:

-   bad char table: $O(256 * m)$ or $O(m)$
-   suffix: $O(m)$
-   prefix: $O(m)$

<br/>

<span class="norm">👉 [A new proof of the linearity of the Boyer-Moore string searching algorithm](https://dl.acm.org/doi/10.1109/SFCS.1977.3)</span>

<span class="norm">👉 [Tight bounds on the complexity of the Boyer-Moore string matching algorithm](https://dl.acm.org/doi/10.5555/127787.127830)</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/bm-best.jpeg" style="width: 90%"/>
  <br/>
    <img src="/images/bm-worst.jpeg" style="width: 90%"/>
</div>

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: center
---

# Sunday

---

# Sunday

<logos-jupyter />

<div class="inline-grid grid-cols-[2fr,4fr] gap-4">
  <div></div>
  <div><img src="/images/string_matching_sunday1.png" style="width: 60%"/></div>
  <div class="norm"></div>
  <div><img src="/images/string_matching_sunday2.png" style="width: 60%"/></div>
  <div class="norm">✅ <strong>bad char</strong> → shift <span style="color: #357EC7">m + 1</span></div>
  <div><img src="/images/string_matching_sunday3.png" style="width: 60%"/></div>
  <div></div>
  <div><img src="/images/string_matching_sunday4.png" style="width: 60%"/></div>
  <div></div>
  <div><img src="/images/string_matching_sunday5.png" style="width: 60%"/></div>
  <div class="norm">✅ otherwise → shift <span style="color: #357EC7">m -i</span> (from the rightmost char to the end of the string + 1)</div>
  <div><img src="/images/string_matching_sunday6.png" style="width: 60%"/></div>
</div>

---

# Complexity: KMP vs BM vs Sunday

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="25%">Pattern Matching</th>
        <th id="" width="25%">avg.</th>
        <th id="" width="25%">best</th>
        <th id="" width="25%">worst</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>KMP</th>
        <td>O(m + n)</td>
        <td>O(n)</td>
        <td>O(m + n)</td>
      </tr>
      <tr class="even">
        <th>BP</th>
        <td>O(m + n)</td>
        <td>O(m + n/m)</td>
        <td>O(m + n·m)</td>
      </tr>
      <tr class="odd">
        <th>Sunday</th>
        <td>O(m + n)</td>
        <td>O(m + n/m)</td>
        <td>O(m + n·m)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

<span class="norm">👉 KMP always linear</span>

---
layout: center
---

# Graph

---

# Graph

<br/>

-   Implement graph ADT using different internal representation
-   Learn graph associated algorithms
-   How graph can be used to solve a wide variety of problems

<span class="norm">💡 graph can model many things in real world such as roads, airline routes, social media connections, etc.
</span>  
<span class="norm">💡 **graph theory**, the study of graphs, is a field of discrete mathematics.
</span>

<div grid="~ cols-3 gap-6">
  <div>
    <img src="/images/singapore-mrt.jpeg" style="height: 80%">
  </div>
  <div>
    <img src="/images/network-route.png" style="height: 80%">
  </div>
  <div>
    <img src="/images/state-machine.png" style="height: 80%">
  </div>

</div>

<!--

Graph is not picture. Graph is a data structure.

Linear and Tree data structure is more about data storage structure and how to use that structure for data CRUD. Data storage structure for Graph is not difficult and the challenge is how to use Graph algorithm to solve different problems.

Similar to previous algorithm study, we focus on the understanding and implemetation of graph algorithm, not the math proof.

-->

---

# Graph Terminology

<br/>

A <span class="hl-bg">graph</span> is an ordered pair $G = (V, E)$ comprising a set $V$ of <span class="hl-strong">vertices</span> or nodes and a collection of pairs of vertices from $V$, known as <span class="hl-strong">edges</span> of a graph. For example, for the graph below:

$V = { 1, 2, 3, 4, 5, 6 }$  
$E = { (1, 4), (1, 6), (2, 6), (4, 5), (5, 6) }$

<img src="/images/graph01.png" style="height: 40%"/>

<!--

Layman's definition of a Graph: network that define and visualize relationships between various componetnts

-->

---

# Graph Terminology

<br/>

-   an **edge** is (together with vertices) one of the two basic units out of which graphs are constructed, each edge has two vertices to which it is attached, called its **endpoints**.
-   two vertices are called **adjacent** or **neighbors** if they are endpoints of the same edge.
-   **outgoing** edges of a vertex are directed edges that the vertex is the origin.
-   **incoming** edges of a vertex are directed edges that the vertex is the destination.
-   the **degree** of a vertex in a graph is the total number of edges incident to it.
-   in a directed graph, the **out-degree** of a vertex is the total number of outgoing edges, and the **in-degree** is the total number of incoming edges.
-   a vertex with in-degree zero is called a **source** vertex, while a vertex with out-degree zero is called a **sink** vertex.
-   an **isolated** vertex is a vertex with degree zero, which is not an endpoint of an edge.
-   if two or more undirected edges have the same two endpoint, or both origin and destination for two or more directed edges are the same, those edges are called **parallel edges** or **multiple edges**.
-   if two endpoints for an edge are the same vertex, th edge become **self-loop**.

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph Terminology

<br/>

-   **path** is a sequence of alternating vertices and edges such that the edge connects each successive vertex.
-   if a path only has the directed edges and traverse along the edges' direction, the path is called a **directed path**.
-   **path length** is number of edges in a path.
-   **cycle** is a path that starts and ends at the same vertex.
-   **simple** path is a path with distinct vertices.
-   two vertices are **connected** if a path exists between them.
-   in a directed graph, if there is a path from vertex v to vertex w, it is said that w is **reachable** from v.

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph Terminology

<br/>

-   a graph is **connect** when all vertices are connected.
-   A **connected component** or simply **component** of an undirected graph is a subgraph in which each pair of nodes is connected with each other via a path.
-   a directed graph is **strongly connected** if for any pair of vertice v and w, w is reachable from v and v also reachable from w.
-   a directed graph is called **weakly connected** if replacing all of its directed edges with undirected edges produces a connected (undirected) graph. The vertices in a weakly connected graph have either out-degree or in-degree of at least 1.
-   if a graph H's vertices and edges belong to a graph G's vertices and edges, then graph H is a **subgraph** of G.
-   if all vertices in G are in its subgraph H, then H is a **spanning subgraph** of G.
-   a **bridge** is an edge whose removal would disconnect the graph.
-   **forest** is a graph without cycles.
-   **tree** is a connected graph with no cycles.
-   if a spanning subgraph is a tree, then the spanning subgraph is called a **spanning tree**.

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph Terminology

<br/>

-   **root node** is the ancestor of all other nodes in a graph. It does not have any ancestor. Each graph consists of exactly one root node. Generally, you must start traversing a graph from the root node.
-   **leaf node** represents the node that do not have any successors. These nodes only have ancestor nodes. They can have any number of incoming edges but they will not have any outgoing edges.

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Types of Graphs

<br/>

### Undirected and Directed Graph

An <span class="hl-strong">undirected</span> graph(graph) is a graph in which edges have no orientation. The edge $(x, y)$ is identical to edge $(y, x)$, i.e., they are not ordered pairs. The maximum number of edges possible in an undirected graph without a loop is $n×(n-1)/2$.

<div grid="~ cols-2 gap-4">
  <div align="center">
    <img src="/images/graph-undirected.png" style="width: 70%"/>
  </div>
  <div align="center">
    <img src="/images/social-friends.png" style="width: 60%"/>
    <p class="norm">social: friends</p>
  </div>
</div>

---

# Types of Graphs

<br/>

### Undirected and Directed Graph

A <span class="hl-strong">directed</span> graph (digraph) is a graph in which edges have orientations, i.e., The edge $(x, y)$ is not identical to edge $(y, x)$.

<div grid="~ cols-2 gap-4">
  <div align="center">
    <img src="/images/graph-directed.png" style="width: 70%"/>
  </div>
  <div align="center">
    <img src="/images/social-follows.png" style="width: 60%"/>
    <p class="norm">social: follows</p>
  </div>
</div>

---

# Types of Graphs

<br/>

### Undirected and Directed Graph

A <span class="hl-strong">mixed</span> graph has both undirected and directed edges.

---

# Types of Graphs

<br/>

### Weighted and Unweighted Graph

A <span class="hl-strong">weighted</span> graph associates a value (<span class="hl">weight</span>) with every edge in the graph.

An <span class="hl-strong">unweighted</span> graph does not have any value (weight) associated with every edge in the graph. In other words, an unweighted graph is a weighted graph with all edge weight as 1. Unless specified otherwise, all graphs are assumed to be unweighted by default.

<img src="/images/graph-weighted.png" style="height: 40%"/>

---

# Types of Graphs

<br/>

### Simple and Multi Graph

A <span class="hl-strong">multigraph</span> is an undirected graph in which multiple edges (and sometimes loops) are allowed.

A <span class="hl-strong">simple</span> graph is an undirected graph in which both multiple edges and loops are disallowed as opposed to a multigraph. In a simple graph with $n$ vertices, every vertex’s degree is at most $n-1$.

<img src="/images/graph-simple.png" style="height: 40%"/>

---

# Types of Graphs

<br/>

### Connected Graph

A <span class="hl-strong">connected</span> graph has a path between every pair of vertices. In other words, there are no unreachable vertices. A <span class="hl-strong">disconnected</span> graph is a graph that is not connected.

<img src="/images/graph-connected.png" style="height: 40%"/>

---

# Types of Graphs

<br/>

### Directed (Cyclic) Graph and DAG

A <span class="hl-strong">Directed Acyclic Graph</span> (DAG) is a directed graph that contains no cycles.

<img src="/images/graph-dag.png" style="height: 40%"/>

---

# Types of Graphs

<br/>

### Complete Graph

A <span class="hl-strong">complete</span> graph is one in which every two vertices are adjacent: all edges that could exist are present.

$E = \frac{V·(V-1)}{2}$

<img src="/images/graph-complete.png" style="height: 40%"/>

---

# Graph Properties

<br/>

-   If a graph G has vertex set $V$ and $m$ edges, then $\sum\limits_{v\;in\;V} deg(v) = 2m$

-   If a directed graph G has vertex set $V$ and $m$ edges, then $\sum\limits_{v\;in\;V} indeg(v) = \sum\limits_{v\;in\;V} outdeg(v) = m$

-   A simple graph G has $n$ vertices and $m$ edges:

    -   undirected, then $m \leq n*(n-1)/2$
    -   directed, then $m \leq n*(n-1)$

-   An undirected graph G has $n$ vertices and $m$ edges:
    -   connected, then $m \geq (n-1)$
    -   tree, then $m = (n-1)$
    -   forest, then $m \leq (n-1)$

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Graph ADT

### Adjacency Matrix Representation

An adjacency matrix is a square matrix used to represent a finite graph. The elements of the matrix indicate whether pairs of vertices are adjacent or not in the graph. For a simple unweighted graph with vertex set $V$, the adjacency matrix is a square $|V| × |V|$ matrix A such that its element:

$A_{ij} = 1$, when there is an edge from vertex $V_i$ to vertex $V_j$, and  
$A_{ij} = 0$, when there is no edge.

Each row in the matrix represents source vertices, and each column represents destination vertices. The diagonal elements of the matrix are all zero since edges from a vertex to itself, i.e., loops are not allowed in simple graphs. If the graph is undirected, the adjacency matrix will be symmetric. Also, for a weighted graph, $A_{ij}$ can represent edge weights.

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/graph-directed.png" style="width: 50%"/>
  <br/>
  <img src="/images/graph-matrix.png" style="width: 50%"/>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Graph ADT

### Adjacency List Representation

An adjacency list representation for the graph associates each vertex in the graph with the collection of its neighboring vertices or edges, i.e., every vertex stores a list of adjacent vertices. There are many variations of adjacency list representation depending upon the implementation. This data structure allows the storage of additional data on the vertices but is practically very efficient when the graph contains only a few edges. i.e. the graph is sparse.

<logos-jupyter />

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/graph-directed.png" style="width: 50%"/>
  <br/>
  <img src="/images/graph-list.png" style="width: 50%"/>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph ADT

<br/>

vertex_count()  
edge_count()  
vertices()  
edges()  
get_edge(v<sub>i</sub>, v<sub>j</sub>)  
degree(v, out=True), degree(v, out=False)  
incident_edge(v, out=True), incident_edge(v, out=False)  
insert_vertex(w=None)  
insert_edge(v<sub>i</sub>,v<sub>j</sub>,e=None)  
remove_vertex(v)  
remove_edge(e)

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph ADT

<div style="width: 80%">
  <table class="ops">
    <thead>
      <tr>
        <th id=""> </th>
        <th id="">Space Complexity</th>
        <th id="">construction</th>
        <th id="">has_edge</th>
        <th id="">adj</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Adjacency Matrix</th>
        <td>O(V^2)</td>
        <td>O(E)</td>
        <td>O(1)</td>
        <td>O(V) 👈</td>
      </tr>
      <tr class="even">
        <th>Adjacency List</th>
        <td>O(V + E)</td>
        <td>O(E), O(E * V)</td>
        <td>O(deg(v)), O(V)</td>
        <td>O(deg(v)), O(V)</td>
      </tr>
    </tbody>
  </table>
</div>

<span class="norm">Red-Black Tree?</span>  
<span class="norm">HashSet?</span>

<!--

Consider

HashSet: O(1)
Red-Black Tree: O(log)
1. ordering
2. space

-->

---
layout: two-cols
---

# Depth-First Search (DFS)

<br/>

<br/>

<img src="/images/dfs_tree.png" style="height: 40%"/>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/dfs_graph.png" style="height: 40%"/>

---
layout: two-cols
---

# Depth-First Search (DFS)

<br/>

<br/>

<div style="width: 80%; padding-left: 10px;">

```python
preorder(root)

preorder(TreeNode node):
  if node != None:
    list.add(node.val)
    preorder(node.left)
    preorder(node.right)
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div style="width: 80%; padding-left: 10px;">

```python
visited[0..V-1] = false
dfs(0)

dfs(int v):
  visited[v] = true
  list.add(v)
  for (int w: incident_edges(v)):
    if !visited[w]:
      dfs(w)
```

</div>

---
layout: two-cols
---

# Depth-First Search (DFS)

<logos-jupyter />

<div style="width: 80%; padding-left: 10px;">

```python
visited[0..V-1] = false
dfs(0)

dfs(int v):
  visited[v] = true
  list.add(v)
  for (int w: incident_edges(v)):
    if !visited[w]:
      dfs(w)
```

<br/>

<pre class="norm">
dfs(0) → dfs(1) → dfs(3) → dfs(2) → dfs(6) → dfs(5)
dfs(0) → dfs(1)
dfs(0) → dfs(1) → dfs(4) 
</pre>

<pre class="norm">
list: 0 1 3 2 6 5 4
</pre>

$O(V+E)$

</div>

::right::

<br/>

<br/>

<br/>

<img src="/images/dfs_undirected.png" style="height: 50%"/>

<pre class="norm">
0 : 1 2
1 : 0 3 4
2 : 0 3 6
3 : 1 2 5
4 : 1
5 : 3 6
6 : 2 5
</pre>

<!--

Q1. not connected

Q2.
✅ pre-order
✅ post-order
? in-order

-->

---
layout: two-cols
---

# Depth-First Search (DFS)

<br/>

<br/>

**prev[]**:

1 ← 0  
2 ← 3  
3 ← 1  
4 ← 1  
6 ← 2

<br/>

path from 0 to 6: **6 ← 2 ← 3 ← 1 ← 0**

::right::

<br/>

<br/>

<br/>

<br/>

<img src="/images/dfs_path.png" style="height: 50%"/>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Depth-First Search (DFS)

<br/>

-   connected component
-   a path between two vertices → Shortest path, Eulerian graph, Eulerian cycle, Hamiltonian path
-   check cycle
-   check a **bipartite** graph
-   find bridge
-   [Tarjan's strongly connected components algorithm](https://en.wikipedia.org/wiki/Tarjan%27s_strongly_connected_components_algorithm)
-   ......

<div class="inline-grid grid-cols-[1fr,1fr] gap-8">
  <div>
    <p>a bipartite graph (or bigraph)  is a graph whose vertices can be divided into two disjoint and independent sets U and V, that is every edge connects a vertex in U to one in V.</p>
  </div>
  <div>
    <img src="/images/bipartite.jpeg" style="width:60%"/>
  </div>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Breadth-First Search (BFS)

<br/>

Queue  
0 :  
2 → 1 : **0**  
4 → 3 → 2 : **1**  
6 → 5 → 4 → 3 : **2**  
6 → 5 → 4 : **3**  
6 → 5 : **4**  
6 : **5**  
: **6**

BFS order: **0 1 2 3 4 5 6**

::right::

<br/>

<br/>

<br/>

<br/>

<img src="/images/bfs_tree.png" style="height: 50%"/>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Breadth-First Search (BFS)

<logos-jupyter />

Queue  
0 :  
2 → 1 : **0**  
4 → 3 → 2 : **1**  
6 → 4 → 3 : **2**  
5 → 6 → 4 : **3**  
5 → 6 : **4**  
5 : **6**  
: **5**

BFS order: **0 1 2 3 4 6 5**

$O(V+E)$

::right::

<br/>

<br/>

<br/>

<br/>

<img src="/images/bfs_undirected.png" style="height: 50%"/>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Depth-First Search (DFS)

<br/>

<br/>

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
    <span class="norm">0</span>
  </div>
  <div>
    <span class="norm">distance from 0: 0</span>
  </div>
  <div>
    <span class="norm">1 2</span>
  </div>
  <div>
    <span class="norm">distance from 0: 1</span>
  </div>  
  <div>
    <span class="norm">3 4 6</span>
  </div>
  <div>
    <span class="norm">distance from 0: 2</span>
  </div>  
  <div>
    <span class="norm">5</span>
  </div>
  <div>
    <span class="norm">distance from 0: 3</span>
  </div>  
</div>

<br/>

<br/>

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div align="right">
    <span class="norm">BFS order:</span>
  </div>
  <div>
    <span class="norm"><strong>0 1 2 3 4 6 5</strong></span>
  </div> 
  <div align="right">
    <span class="norm">dist[]:</span>
  </div>
  <div>
    <span class="norm"><strong>0 1 1 2 2 2 3</strong></span>
  </div>   
</div>

<br/>

<br/>

👉 shortest path

::right::

<br/>

<br/>

<br/>

<br/>

<img src="/images/bfs_path.png" style="height: 50%"/>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Dijkstra's Algorithm

<logos-jupyter />

Each iteration:

1. from unvisited vertices, find the best vertex with shortest distance
2. mark this vertex visited
3. from this vertex, update distance to other unvisited vertices

<br/>

<div class="inline-grid grid-cols-[1fr,2fr] gap-2">
  <div>
    <table class="grid">
      <tbody>
        <tr class="odd">
          <td style="font-weight:bolder">0</td>
          <td style="font-weight:bolder">1</td>
          <td style="font-weight:bolder">2</td>
          <td style="font-weight:bolder">3</td>
          <td style="font-weight:bolder">4</td>
        </tr>
        <tr class="even">
          <td style="color:red">0</td>
          <td>&#8734;</td>
          <td>&#8734;</td>
          <td>&#8734;</td>
          <td>&#8734;</td>
        </tr>
        <tr class="even">
          <td style="color:red">0</td>
          <td>4</td>
          <td style="color:red">2</td>
          <td>&#8734;</td>
          <td>&#8734;</td>
        </tr>
        <tr class="even">
          <td style="color:red">0</td>
          <td>3</td>
          <td style="color:red">2</td>
          <td>6</td>
          <td>7</td>
        </tr>    
        <tr class="even">
          <td style="color:red">0</td>
          <td style="color:red">3</td>
          <td style="color:red">2</td>
          <td>6</td>
          <td>7</td>
        </tr>    
        <tr class="even">
          <td style="color:red">0</td>
          <td style="color:red">3</td>
          <td style="color:red">2</td>
          <td>5</td>
          <td>6</td>
        </tr>    
        <tr class="even">
          <td style="color:red">0</td>
          <td style="color:red">3</td>
          <td style="color:red">2</td>
          <td style="color:red">5</td>
          <td>6</td>
        </tr>    
        <tr class="even">
          <td style="color:red">0</td>
          <td style="color:red">3</td>
          <td style="color:red">2</td>
          <td style="color:red">5</td>
          <td style="color:red">6</td>
        </tr>     
      </tbody>
    </table>
  </div>
  <div>
    <pre class="norm">
Path (0 —> 1): Minimum cost = 3, Route = [0, 2, 1]
Path (0 —> 2): Minimum cost = 2, Route = [0, 2]
Path (0 —> 3): Minimum cost = 5, Route = [0, 2, 1, 3]
Path (0 —> 4): Minimum cost = 6, Route = [0, 2, 1, 4]    
    </pre>
  </div> 
</div>

::right::

<br/>

<br/>

<div align="center">
  <img src="/images/dijkstra1.png" style="width: 70%"/>
  <img src="/images/dijkstra2.png" style="width: 70%"/>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Depth-First Search (DFS)

<br/>

-   Space Complexity: $O(V)$

-   Time Complexity: $O(V^2)$ → $O(ElogV)$ → $O(E + VlogV)$

-   shortest path from $src$ to $dest$

-   all possible shortest path: $O(V * ElogV)$

-   negative weight?  
    👉 [Bellman-Ford](https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm)  
    👉 [Floyd–Warshall](https://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm)

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Min-Spanning Tree (MST)

<br/>

Spanning Tree: DFS & BFS

<img src="/images/mst_dfs_bfs.png" style="width: 70%"/>

---
layout: two-cols
---

# Kruskal's Algorithm

<br/>

<br/>

-   repeatedly add the next lightest edge if this doesn’t producea cycle

-   greedy algorithm

<br/>

<pre class="norm">
1, 2: 1
3, 4: 1 
0, 1: 2
0, 5: 2 
1, 4: 3
1, 3 ❌   2, 4 ❌   2, 5 ❌ 
3, 6: 5
0, 3 ❌   4, 6 ❌
</pre>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/mst_kruskal.png" style="width: 70%"/>
</div>

---

# The Cut Property

<br/>

In graph theory, a cut can be defined as a partition that divides a graph into two <span class="hl-color">disjoint subsets</span>.

A cut $C = (S_1, S_2)$ in a connected graph $G(V, E)$, partitions the vertex set $V$ into two disjoint subsets $S_1$, and $S_2$.

A <span class="hl">cut set</span> of a cut $C(S_1, S_2)$ of a connected graph $G(V, E)$ can be defined as the set of edges that have one endpoint in $S_1$ and the other in $S_2$. For example the $C(S_1, S_2)$ of $G(V, E) = {(i, j) \in E | i \in S_1, j \in S_2 }$

An edge is a <span class="hl">crossing edge</span> as an edge which connects a node from one set to a node from the other set.

<br/>

<span class="norm">👉 bipartitie graph: find a cut, so that every edge is crossing edge</span>

---

# The Cut Property

<br/>

> **According to the cut property, given any cut, the minimum weight crossing edge is in the MST.**

<br/>

<div class="inline-grid grid-cols-[1fr,1fr] gap-8">
  <div>
    <img src="/images/cutp5.png" style="width: 60%"/><br/>
    <pre class="norm">
    0, 3: 7
    1, 3: 4 
    1, 4: 3 👈
    2, 4: 4
    </pre>
  </div>
  <div>
    <img src="/images/cutp6.png" style="width: 60%"/>
  </div>
</div>

---

# Kruskal's Algorithm

<logos-jupyter />

<br/>

🙇🏻‍♂️ implementation

$O(ElogE)$

<!--

- check cycle? → check connectivity/find a path

- DFS? → O(V+E)

- dynamic? → Disjoin Set $O(ElogE)$

-->

---
layout: two-cols
---

# Prim's Algorithm

<br/>

<br/>

-   start from 0, find the lightest crossing edge, and repeatly expand the cut

-   greedy algorithm

<br/>

<pre class="norm">
0, 1: 2   S1 = 0          
1, 2: 1   S1 = 0, 1         
0, 5: 2   S1 = 0, 1, 2      
1, 4: 3   S1 = 0, 1, 2, 5    
3, 4: 1   S1 = 0, 1, 2, 5, 4
3, 6: 5   S1 = 0, 1, 2, 5, 4, 3
             S1 = 0, 1, 2, 5, 4, 3, 6
</pre>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/mst_prim.png" style="width: 70%"/>
</div>

---

# Prim's Algorithm

<logos-jupyter />

<br/>

🙇🏻‍♂️ implementation

$O(V^2)$, $O(ElogV)$, $O(ElogE)$

---

# Min-Spanning Tree (MST)

<br/>

-   Fedman-Tarjan $O(E + VlogV)$

    -   <span class="norm">Fredman, M. L.; Willard, D. E. (1994), "Trans-dichotomous algorithms for minimum spanning trees and shortest paths", Journal of Computer and System Sciences, 48 (3): 533–551, doi:10.1016/S0022-0000(05)80064-9, MR 1279413.</span>

-   Chazelle $O(E^*)$
    -   <span class="norm">Chazelle, Bernard (2000), "A minimum spanning tree algorithm with inverse-Ackermann type complexity", Journal of the Association for Computing Machinery, 47 (6): 1028–1047, doi:10.1145/355541.355562, MR 1866456, S2CID 6276962.</span>
    -   <span class="norm">Chazelle, Bernard (2000), "The soft heap: an approximate priority queue with optimal error rate" (PDF), Journal of the Association for Computing Machinery, 47 (6): 1012–1027, doi:10.1145/355541.355554, MR 1866455, S2CID 12556140.</span>

---
layout: center
---

# Algorithm Design Technique

---

# Divide-and-Conquer

<br/>

Input: Problem $P$  

Algorithm <span class="norm">divideAndConquer($P$)</span>:  

1. Base case: if size of $P$ is small, solve it (e.g. brute force) and return solution, else:
2. <span class="hl">Divide</span>: divide $P$ into smaller problems $P1$, $P2$
3. <span class="hl">Conquer</span>: solve the smaller subproblems recursively, by calling <span class="norm">divideAndConquer($P1$)</span> and <span class="norm">divideAndConquer($P2$)</span>
4. <span class="hl">Combine</span>: combine solutions to $P1$, $P2$ into solution for $P$.

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# Divide-and-Conquer

<br/>

<div style="width: 90%;padding-left: 10px;">

Merge-sort an array of $n$ elements:  
  
- base-case: if size of input is $1$, return  
- else:   
         - **Divide**: Divide the array into two arrays of $n/2$ elements each  
         - **Conquer**: Sort the two arrays recursively  
         - **Combine**: Merge the two sorted arrays of $n/2$ elements into one sorted array of size $n$  

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div style="width: 80%;padding-left: 10px;">
  <img src="/images/merge-sort-tree.png">
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Greedy Algorithm

<br/>

A <span class="hl-bg">greedy algorithm</span> is a simple and efficient algorithmic approach for solving any given problem by selecting the best available option at that moment of time, without bothering about the future results.

<br/>

To create greedy algorithm:

- Firstly, the solution set (that is supposed to contain answers) is set to empty.
- Secondly, at each step, an item is pushed to the solution set.
- Only if the solution set is deemed feasible, the current item is kept for future purpose.
- Else, the current item is rejected and is never considered again (no reversal of decision)

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

<!--

A greedy algorithm, as the name suggests, always makes the choice that seems to be the best at that moment. This means that it makes a locally-optimal choice in the hope that this choice will lead to a globally-optimal solution.

The difficult part is that for greedy algorithms you have to work much harder to understand correctness issues. Even with the correct algorithm, it is hard to prove why it is correct. 

How to create a Greedy Algorithm?

-->

---

# Greedy Algorithm

<br/>

0-1 Knapsack: greedy and most valuable item? 

$w = [1, 2, 3]$, $v = [6, 10, 12]$, $C=5$

<div style="width: 60%;padding-left: 10px;">
  <table class="grid">
    <tbody>
      <tr class="id">
        <th> </th>
        <th>0</th>
        <th>1</th>
        <th>2</th>
      </tr>    
      <tr class="even">
        <th>weight</th>
        <td>1</td>
        <td>2</td>
        <td>3</td>
      </tr>
      <tr class="even">
        <th>value</th>
        <td>6</td>
        <td>10</td>
        <td>12</td>
      </tr>
      <tr class="even">
        <th>v/w</th>
        <td>6</td>
        <td>5</td>
        <td>4</td>
      </tr>
    </tbody>
  </table>
</div>

$6 + 10 = 16$ ❌  
$10 + 12 = 22$ ✅ 

---

# Greedy Algorithm

<logos-jupyter />

Given an array of intervals intervals where intervals[i] = [start<sub>i</sub>, end<sub>i</sub>], return the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.

Input: intervals = [[1,2],[2,3],[3,4],[1,3]]  
Output: 1  
Explanation: [1,3] can be removed and the rest of the intervals are non-overlapping.  

Input: intervals = [[1,2],[1,2],[1,2]]  
Output: 2  
Explanation: You need to remove two [1,2] to make the rest of the intervals non-overlapping.    

**Greedy**:  sort end<sub>i</sub>, select the smaller end<sub>i</sub> and non-overlapping intervals[i]

why correct? 

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Backtracking

<br/>

- <span class="hl-bg">Backtracking</span> Backtracking is an algorithmic technique for finding all solutions to some computational problems that have certain constraints and incrementally builds candidates to the solutions while abandoning a candidate if it does not lead to valid solutions.
- It is known for solving problems recursively one step at a time and removing those solutions that that do not satisfy the problem constraints at any point of time.
- It is a <span class="uline">refined brute force</span> approach that tries out all the possible solutions and chooses the best possible ones out of them.
- The backtracking approach is generally used in the cases where there are possibilities of multiple solutions.

<div align="center">
  <img src="/images/backtracking.png" style="width: 40%"/>
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

<!--

The term backtracking implies - if the current solution is not suitable, then eliminate that and backtrack (go back) and check for other solutions.

Here S is the starting point of the problem. We start from S, we go to find solution S1 via the intermediate point I1. But we find that the solution S1 is not a feasible solution to our problem. Hence, we backtrack (go back) from S1, go back to I1, go back to S and then check for the feasible solution S2. This process happens till we arrive at a feasible solution.
Here, S1 and S2 are not the feasible solutions. Only S3 is a feasible solution as per our example. When we look at this example, we can see that we traverse through all possible combinations, till we arrive at the feasible solution. This is why, we say that backtracking is a brute-force algorithmic technique.
The above tree representation of a problem is called as a “space state tree”. It represents all possible states (solution or non-solution) of that given problem.
The final algorithm can be summarised as:
Step 1 − if current point is a feasible solution, return success
Step 2 − else if all paths are exhausted (i.e current point is an end point), return failure, since we have no feasible solution.
Step 3 − else if current point is not an end point, backtrack and explore other points and repeat above steps

-->

---

# Backtracking: Sudoku 

<div class="inline-grid grid-cols-[1fr,1fr] gap-4">
  <div>
    <img src="/images/sudoku1.png" style="width: 70%"/>
  </div>
  <div>
    <pre class="hg-strong">Input</pre>  
    <pre class="norm">
[["5","3",".",".","7",".",".",".","."],
["6",".",".","1","9","5",".",".","."],
[".","9","8",".",".",".",".","6","."],
["8",".",".",".","6",".",".",".","3"],
["4",".",".","8",".","3",".",".","1"],
["7",".",".",".","2",".",".",".","6"],
[".","6",".",".",".",".","2","8","."],
[".",".",".","4","1","9",".",".","5"],
[".",".",".",".","8",".",".","7","9"]]    
    </pre>
  </div>
  <div>
    <img src="/images/sudoku2.png" style="width: 70%"/>
  </div>
  <div>
    <pre class="hg-strong">Output</pre>  
    <pre class="norm">
[["5","3","4","6","7","8","9","1","2"],
["6","7","2","1","9","5","3","4","8"],
["1","9","8","3","4","2","5","6","7"],
["8","5","9","7","6","1","4","2","3"],
["4","2","6","8","5","3","7","9","1"],
["7","1","3","9","2","4","8","5","6"],
["9","6","1","5","3","7","2","8","4"],
["2","8","7","4","1","9","6","3","5"],
["3","4","5","2","8","6","1","7","9"]]  
    </pre>
  </div>  
</div>

---

# Backtracking

<br/>

backtracking vs brute force: 
- <span class="norm">brute force algorithms are those which computes every possible solution to a problem and then selects the best one among them that fulfills the given requirements.</span>
- <span class="norm">Whereas, backtracking is a refined brute force technique where the implicit constraints are evaluated after every choice (not as in brute force where evaluation is done after all solutions have been generated). This means that potential non-satisfying solutions can be rejected before the computations have been ‘completed’.</span>

backtracking vs recursion: 
- <span class="norm">In recursion, a function simply calls itself until reaches a base case.</span>
- <span class="norm">Whereas, in backtracking we use recursion for exploring all the possibilities until we get the best and feasible result for any given problem.</span>


---

# Dynamic Programming

<br/>

<span class="hl-bg">Dynamic Programming</span> (DP) is a method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems just one, and storing their solutions - ideally, using a memory-based data structure.

<br/>


Writes down "1+1+1+1+1+ =" on a sheet of paper.  
"What's that equal to?"  
Counting "Five!"  
Writes down another "1+" on the left.  
"What about that?"  
"Six!" " How'd you know it was nine so fast?"  
"You just added one more!"  
"So you didn't need to recount because you remembered there were five!    
Dynamic Programming is just a fancy way to say remembering stuff to save time later!"  


<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: Fibonacci

<br/>

<div style="width: 90%;padding-left: 10px;">

```md
Fibonacci sequence: 0,1,1,2,3,5,8, ...

when n = 1, fib(1) = 0
when n = 2, fib(2) = 1
when n > 2, fib(n) = fib(n-1) + fib(n-2)
```

<br/>

```python
# Time Complexity: O(2^n)
def fib_recursive(n):
    global fib_run 
    fib_run += 1
    if (n == 1):
        return 0
    if (n == 2):
        return 1 
    return fib_recursive(n-1) + fib_recursive(n-2)
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div style="padding-left: 10px;">
  <img src="/images/fib_recursion.png">
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: Fibonacci

<br/>

<div style="padding-left: 10px;">

> Any problem is said to have overlapping subproblems if calculating its solution involves solving the same subproblem multiple times.

> This method of remembering the solutions of already solved subproblems is called **Memoization**.

<br/>

```python
# Time Complexity: O(n)
def fib_recursive_memo(n): 
    global fib_run, fib_memo
    fib_run += 1
    # return directly from cache if found
    if (n in fib_memo): 
        return fib_memo[n]
    if (n == 1):
        return 0
    if (n == 2):
        return 1 
    # cache the result
    fib_memo[n] = fib_recursive_memo(n-1) + fib_recursive_memo(n-2)
    return fib_memo[n]
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div style="padding-left: 10px;">
  <img src="/images/fib_topdown.png">
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: Fibonacci

<br/>

<div style="padding-left: 10px;">

> bottom up is the opposite of the top-down approach which avoids recursion by solving all the related subproblems first.

<br/>

```python
# Time Complexity: O(n)
def fib_dp(n): 
    dp_memo = {}
    dp_memo[0] = 0
    dp_memo[1] = 0 
    dp_memo[2] = 1
    for i in range(2, n+1, 1): 
        dp_memo[i] = dp_memo[i-1] + dp_memo[i-2]
    return dp_memo[n]
```

</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div style="padding-left: 10px;">
  <img src="/images/fib_bottomup.png">
</div>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# DP Solution 

<br/>

DP in a nutshell: 

1. check for <span class="uline">optimal substructure</span> and formulate the problem <span class="uline">recursively</span>, and
2. use a table to “cache” the solutions to subproblems, in order to avoid recomputing them.

<br/>

<div align="center">

<img src="/images/dp1.png" style="width: 50%"/>

</div>

<br/>

<span class="norm">💡 usually DP problem is hard</span>  
<span class="norm">💡 different DP through exercises</span>

<!--
- Step 1. Think of a recursive approach to solving the problem which essentially expresses a problem, say $P(X)$, in terms of smaller subproblem, say $P(Y)$ or an expression involving multiple smaller subproblems, say $P(Yi)$. Here we expect $Yi < X$
- Step 2. Once you have a approach, write a recursive code for that. Consider your recursive code function definition to be as below: solve (K1, K2, K3 ... )
- Step 3. Keep track of the results of each function by saving them after every function call so that if the same function solve $(K1, K2, K3 ... ) is called again, we need not compute again.
- Step 4. Once we are done, analyze the space and time complexities of the solution developed, and try to improve them if possible.
-->

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# DP: 0-1 Knapsack Problem

<br/>

Given weights and values of n items, put these items in a knapsack of capacity $C$ to get the maximum total value in the knapsack. In other words, given two integer arrays $v[0..n-1]$ and $w[0..n-1]$ which represent values and weights associated with $n$ items respectively. Also given an integer $C$ which represents knapsack capacity, find out the maximum value subset of $v$ such that sum of the weights of this subset is smaller than or equal to $C$. You cannot break an item, either pick the complete item or don’t pick it (0-1 property).

$w=[10,20,30]$, $v=[60,100,120]$, $C=50$  
**solution: 200**

w=10; v=60;  
w=20; v=100;  
w=30; v=120;  
w=(20+10); v=(100+60);  
w=(30+10); v=(120+60);  
w=(30+20); v=(120+100);  
w=(30+20+10) > 50

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: 0-1 Knapsack Problem

<logos-jupyter />

$k(n, C)$: $n$ items, capacity $C$, return max value

$k(i, C)$:

1. include $i^{th}$ item: $v[i] + k(i-1, C - w[i])$
2. not included: $k(i-1, C)$

$k(i, C) = max(k(i-1, C), v[i] + k(i-1, C - w[i]))$

Time Complexity: $O(2^n)$

::right::

<br/>

<br/>

<br/>

<br/>

$w=[1, 1, 1]$  
$v=[10,20,30]$  
$C=2$

<img src="/images/dp-k.png" style="width: 70%"/>

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

<!--
some k are evaluated more than one time
-->

---
layout: two-cols
---

# DP: 0-1 Knapsack Problem

<br/>

$id =[0, 1,  2]$  
$w = [1, 2,  3]$  
$v = [6, 10, 12]$  
$C = 5$

$k(i, c) = max(k(i-1, c), v[i] + k(i-1, c - w[i]))$

<table class="grid">
  <tbody>
    <tr class="odd">
      <th> </th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
    </tr>    
    <tr class="even">
      <th>0</th>
      <td>0</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
    </tr>
    <tr class="even">
      <th>1</th>
      <td>0</td>
      <td>6</td>
      <td>10</td>
      <td>16</td>
      <td>16</td>
      <td>16</td>
    </tr>
    <tr class="even">
      <th>2</th>
      <td>0</td>
      <td>6</td>
      <td>10</td>
      <td>16</td>
      <td>18</td>
      <td>22</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

Time Complexity: $O(n)$  
Space Complexity: $O(n * C)$

```python
def knapsack2(w, v, n, C):
    k = [[0 for x in range(C+1)] for x in range(n+1)]
    # build table k from bottom up
    for i in range(n+1):
        for c in range(C+1):
            if i==0 or c==0:
                k[i][c] = 0
            elif w[i-1] > c:
                k[i][c] = k[i-1][c]
            else:
                k[i][c] = max(v[i-1] + k[i-1][c - w[i-1]], k[i-1][c])
    return k[n][C]
```

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: 0-1 Knapsack Problem

<br/>

$k(i, c) = max(k(i-1, c), v[i] + k(i-1, c - w[i]))$

row $i$ depends on row $i-1$, so only 2 rows required:

-   row0 == even rows
-   row1 == odd rows

::right::

<br/>

<br/>

<br/>

<br/>

Time Complexity: $O(n)$  
Space Complexity: $O(2 * C)$

```python
def knapsack3(w, v, n, C):
    # 2 rows only: i%2
    k = [[0 for x in range(C+1)] for x in range(2)]
    # build table k from bottom up
    for i in range(n+1):
        for c in range(C+1):
            if i==0 or c==0:
                k[i % 2][c] = 0
            elif w[i-1] > c:
                k[i % 2][c] = k[(i-1) % 2][c]
            else:
                k[i % 2][c] = max(v[i-1] + k[(i-1) % 2][c - w[i-1]], k[(i-1) % 2][c])
    return k[n % 2][C]
```

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---
layout: two-cols
---

# DP: 0-1 Knapsack Problem

<br/>

$id =[0, 1,  2]$  
$w = [1, 2,  3]$  
$v = [6, 10, 12]$  
$C = 5$

$k(i, c) = max(k(i-1, c), v[i] + k(i-1, c - w[i]))$

<table class="grid">
  <tbody>
    <tr class="odd">
      <th> </th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
    </tr>    
    <tr class="even">
      <th> </th>
      <td>0</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
      <td>6</td>
    </tr>
  </tbody>
</table>

<br/>

<table class="grid">
  <tbody>
    <tr class="odd">
      <th> </th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
    </tr>    
    <tr class="even">
      <th> </th>
      <td>0</td>
      <td>6</td>
      <td>10</td>
      <td>16</td>
      <td>16</td>
      <td>16</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

Time Complexity: $O(n)$  
Space Complexity: $O(C)$

```python
def knapsack4(w, v, n, C):
    k = [0 for i in range(C+1)]
    for i in range(1, n+1):
        # compute from the back (right to left)
        for c in range(C, 0, -1):
            if w[i-1] <= c:
                k[c] = max(v[i-1] + k[c - w[i-1]], k[c])
    return k[C]
```

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# DP: Egg Drop

<br/>

You are given $k$ identical eggs and you have access to a building with $n$ floors labeled from $1$ to $n$.

You know that there exists a floor $f$ where $0 <= f <= n$ such that any egg dropped at a floor higher than $f$ will break, and any egg dropped at or below floor f will not break.

In each move, you may take an unbroken egg and drop it from any floor $x$ (where $1 <= x <= n$). If the egg breaks, you can no longer use it. However, if the egg does not break, you may reuse it in future moves.

Return the **minimum number of moves** that you need to determine **with certainty** what the value of $f$ is.

<br/>

Input: k = 2, n = 100  
Output: 14  

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

<!--

if we have many eggs, with binary search, we know the answer is logN. 

if one egg, test floor by floor

if two egg, follow binary searc

-->

---

# DP: Egg Drop

<br/>

- $k = 1$: $n$ 
- $k = \infty$: $logN$ 
- $k = 2$, $n = 100$: 
  - A = 10, 20, 30, ..., 100, B = x1, x2, x3, ..., x9: 10 + 9 = 19
  - A = 14, 27, 39, ..., 95, 99, 100: 14  

<br/>

if drop at floor $f$:  
1. broken, $floor[1...f-1]$: $drop(k-1, f-1)$  
2. unbroken, $floor[f+1...n]$: $drop(k, n-f)$  
we need to try: $max(drop(k-1, f-1), drop(k, n-f)) + 1$      

<br/>

drop $m$ times: $floor[k][m] = floor[k-1][m-1] + floor[k][m-1] + 1$   
when $floor[k][m] == n$, $m = ?$

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 2px;
}
</style>

<!--


-->

---

# DP vs Divide-and-Conquer

<br/>

- The most important difference in Divide and Conquer strategy is that the subproblems are independent of each other. When a problem is divided into subproblems, they do not overlap which is why each subproblem is to be solved only once.

- Whereas in DP, a subproblem solved as part of a bigger problem may be required to be solved again as part of another subproblem (concept of overlapping subproblem), so the results of a subproblem is solved and stored so that the next time it is encountered, the result is simply fetched and returned.

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# DP vs Greedy

<br/>

<div style="width: 100%">
  <table class="flashcard">
    <thead>
      <tr>
        <th id="">Parameters</th>
        <th id="">Dynamic Programming</th>
        <th id="">Greedy Approach</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Optimality</th>
        <td>There is guaranteed optimal solution as DP considers all possible cases and then choose the best among them.</td>
        <td>Provides no guarantee of getting optimum approach.</td>
      </tr>
      <tr class="even">
        <th>Memory</th>
        <td>DP requires a table or cache for remembering and this increases it’s memory complexity.</td>
        <td>More memory efficient as it never looks back or revises its previous choices.</td>
      </tr>
      <tr class="odd">
        <th>Time complexity</th>
        <td>DP is generally slower due to considering all possible cases and then choosing the best among them.</td>
        <td>Generally faster.</td>
      </tr>
      <tr class="even">
        <th>Feasibility</th>
        <td>Decision at each step is made after evaluating current problem and solution to previously solved subproblem to calculate optimal solution.</td>
        <td>Choice is made which seems best at the moment in the hope of getting global optimal solution.</td>
      </tr>
    </tbody>
  </table>
</div>

---

<div id="labs">
</div>

<style>

#labs {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: url('/images/lab.jpg');
  background-repeat: no-repeat;
  background-size: cover;
}

</style>

---

# Lab 1

<mdi-clipboard-list-outline />

1. Review "sift up" and "sift down", implement your <strong>MaxHeap</strong>.

2. Give an <strong>O(logN \* logN)</strong> algorithm to merge two binary heap.

3. Design a <strong>Min-Max Heap</strong> that supports both remove_min and remove_max in <strong>O(logN)</strong> per operation.

    - how to find min and max element?
    - how to insert/add an element?
    - how to build a Min-Max Heap(heapify) in linear time?

4. Implement a classic <strong>Cuckoo Hash Table</strong> ([Cuckoo hashing](https://en.wikipedia.org/wiki/Cuckoo_hashing)) and support the basic operations: insert, get and remove a key.

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Lab 2

<mdi-clipboard-list-outline />

1. Implement BST search operation with iterative solution.

2. before(k) & after(k) in <strong>BST</strong> would not work if BST doesnot contain the key $k$, pls improve the algorithm to support such case.

3. (a) convert a BST into a Min Heap  
   (b) convert a Min Heap into a BST

4. Optimize <strong>AVL</strong> tree so when there is no change to the hight of nodes, the rebalance process can be stopped.

5. Implement a map data structure with <strong>AVL</strong> tree and support the basic operations: insert, get and remove a key.

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Lab 3

<mdi-clipboard-list-outline />

1. Implement your <strong>Insertion Sort</strong> and sort the number array from right to left.

2. Implement your <strong>Bubble Sort</strong> and sort the number array from left to right.

3. Implement your <strong>Merge Sort</strong> and use bottom-up approach.

4. <strong>[Shell Sort](https://en.wikipedia.org/wiki/Shellsort)</strong> is an optimization of Insertion Sort. Implement your Shell Short.

5. <strong>[Dual Pivot Quick Sort](https://arxiv.org/abs/1503.08498)</strong> by Vladimir Yaroslavskiy, Jon Bentley, and Joshua Bloch, this algorithm offers $O(NlogN)$ performance on many data sets that cause other quicksorts to degrade to quadratic performance, and is typically faster than traditional (one-pivot) Quicksort implementations. Implement your Dual Pivot Quick Sort.

6. Given an integer array nums and an integer k, return the kth largest element in the array. Note that it is the kth largest element in the sorted order, not the kth distinct element.

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Lab 4

<mdi-clipboard-list-outline />

1. Review **KMP** and implementate your solution

2. Review **BM** and implementate your solution

3. Review **Sunday** and implement your solution

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";                                            
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Lab 5

<mdi-clipboard-list-outline />

1. Iterative implementation of **DFS** with **Adjacency List**

2. Iterative implementation of **BFS** with **Adjacency List**

3. Modify **DFS** to detect cycle in undirected graph

4. Modify **BFS** to find a path (Single Source Shortest Path) in a undirected graph

5. Implement your **Dijkstra** algorithm with WeightdeGraph class

6. Implement your **Kruskal** algorithm with WeightdeGraph class

7. Implement your **Prim** algorithm with WeightdeGraph class

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Lab 6

<mdi-clipboard-list-outline />

Q&A  

<style>
p {
    font-family: 'Open Sans';
    font-size: 0.8rem;
    line-height: 1.2em;
}

li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>
