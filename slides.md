---
theme: seriph
title: "MTH252"
background: https://mth252.fastzhong.com/images/cover.webp
highlighter: shiki
lineNumbers: true
colorSchema: "light"
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
6 weeks (Jan ~ Mar), 6 seminars & 6 labs:

<p class="norm">
<ol>
<li><span class="hl-bg">Priority Queue</span>, <span class="hl-bg">Binary Heap</span>, <span class="hl-bg">Hash Table</span> & <span class="hl-bg">Skip List</span></li>
<li>Search Trees: <span class="hl-bg">Binary Search Tree</span>, <span class="hl-bg">AVL</span></li>
<li>Sorting: <span class="hl-bg">Merge-Sort</span>, <span class="hl-bg">Quick Sort</span> <br/> Selection: <span class="hl-bg">Binary Search</span>, <span class="hl-bg">Prune-and-Search</span>, <span class="hl-bg">Randomized-Quicksort</span></li> 
<li>Text Processing: <span class="hl-bg">Brute-Force</span>, <span class="hl-bg">Boyer-Moore</span>, <span class="hl-bg">Knuth-Morris-Pratt</span>(KMP) and <span class="hl-bg">Dynamic Programming</span>(DP)</li> 
<li>Graph: <span class="hl-bg">Depth-First Search</span>, <span class="hl-bg">Breadth-First Search</span>, <span class="hl-bg">Dijkstra's Shortest Path</span>, <span class="hl-bg">Min-Spanning Tree</span>, and <span class="hl-bg">Directed Acyclic Grap</span>(DAG) </li>
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

👉 MTH252 is much more difficult than MTH251

---

# Slides & Notebooks

<br/>

slides online: [https://mth252.fastzhong.com/](https://mth252.fastzhong.com/)

<mdi-file-pdf /> [https://mth252.fastzhong.com/mth252.pdf](https://mth251.fastzhong.com/mth252.pdf)

<logos-github-octocat /> labs: [https://github.com/fastzhong/mth252/tree/main/public/notebooks](https://github.com/fastzhong/mth252/tree/main/public/notebooks)

<br/>

<br/>

👉 Python & Big O review:

MTH251 slides: [https://mth252.fastzhong.com/](https://mth252.fastzhong.com/)

<logos-github-octocat /> [MTH251 lab1](https://github.com/fastzhong/mth252/tree/main/public/notebooks)

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

[<mdi-file-code /> Leetcode](https://leetcode.com/)

<img src="/images/leetcode.png" style="border-radius: 8px; width: 70%"/>

<p class="norm">
🏃‍♂️ learning by doing, implementing the algo from scratch  <br/>
🙇🏻‍♂️ problem solving 
</p>

---

# Learning Resource

📚 books

if you want to dive deeper into proofs and the mathematics of computer science:

[Building Blocks for Theoretical Computer Science](https://mfleck.cs.illinois.edu/building-blocks/index-sp2020.html) by Margaret M. Fleck

---

# Priority Queue

-   FIFO/LILO
-   <span class="hl">each element (k, v) has a certain priority k and k must be compariable</span>
-   min priority queue (smaller k, higher priority)
-   max priority queue (bigger k, higher priority)

e.g. printer queue, cpu task scheduler, etc.

<!--
You cannot sort the elements/tasks first, and pick up the highest task, as the first task is finished, there could be some new coming tasks. in another word we need a data structure to DYNAMICALLY maintain the ordering.
-->

---

# Priority Queue: Operations (Min PQ)

<br/>

-   <span class="hl-strong">add(k, v)</span> (enqueue) − adding an element to the queue
-   <span class="hl-strong">remove_min()</span> (dequeue) − obtain the first element with a pair of (k,v), where k is the mininum value of keys in Min PQ, and remove it from the queue
-   <span class="hl-strong">min()</span> (first/peek) − obtain the first element with a pair of (k,v) where k is the mininum value of keys in Min PQ
-   size(), is_empty()

---

# Priority Queue Complexity

<logos-jupyter />

<br/>

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Priority Queue</th>
        <th id="">unsorted list</th>
        <th id="">sorted list</th>
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

# Binary Heap

<br/>

-   <span class="hl">Complete Binary Tree</span>

-   k value for any node in the tree <span class="hl">smaller than any child node</span>

<img src="/images/binary_heap.png" style="width: 80%"/>

<span class="norm">👉 A complete binary tree is a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible.
</span>

---

# Binary Heap

<br/>

-   from root to any leaf, the key values are in non-decreasing order

-   key of root is always the smallest

-   given height <span class="norm">h</span>, total nodes of binary heap: $2^h \leq n \leq 2^{h+1} - 1$

-   given total nodes <span class="norm">n</span>, binary heap height: $\log_2(n+1) - 1 \leq h \leq \log_2n$

<!--
if exclude the bottom level, binary heap is a perfect binary tree and nodes is 2^h - 1

low level node is always smaller than the high level node? NO.
-->

---

# Binary Heap

<br/>

<div grid="~ cols-2 gap-12">
  <div>
    <img src="/images/binary_heap_index.png"/>
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
          <td>2</td>
          <td>3</td>
          <td>4</td>
          <td>5</td>
          <td>6</td>
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
        <td align="right">parent(i)</td>
        <td align="center">=</td>
        <td align="left">(i - 1) / 2</td>
      </tr>
      <tr>
        <td align="right">left_child(i)</td>
        <td align="center">=</td>
        <td align="left">2 * i + 1</td>
      </tr>
      <tr align="left">
        <td align="right">right_child(i)</td>
        <td align="center">=</td>
        <td align="left">2 * i + 2</td>
      </tr>    
      </tbody>
    </table>  
  </div>
</div>
---

# Binary Heap

<logos-jupyter />

<br/>

-   add new element:

    1. append to the last (so its still complete binary tree)
    2. "sift up" if new element is smaller

-   remove the min:
    1. replace the first element with the last (so its still complete binary tree)
    2. "sift down" if the last element is bigger

👉 [https://www.cs.usfca.edu/~galles/visualization/Heap.html](https://www.cs.usfca.edu/~galles/visualization/Heap.html)

---

# Priority Queue Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Priority Queue</th>
        <th id="">unsorted list</th>
        <th id="">sorted list</th>
        <th id="">binary heap</th>
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

# When & Where is a Priority Queue (PQ) used?

<br/>

-   used in certain implementations of <span class="hl-bg">Dijkstra's Shortest Path</span> algorithm

-   <span class="hl-bg">Best First Search</span> (BFS) algorithms such as A\* uses PQ to continuously grab the next most promising node

-   used in <span class="hl-bg">Huffman coding</span> (which is often used for lossless data compression)

-   Used by <span class="hl-bg">Minimum Spanning Tree</span> (MST) algorithms

-   anytime you need to dynamically fetch the "next best" or "next worst" element

<!--
Technically Priority Queue can be considered same as binary heap, but Priority Queue is ADT as it can be implemented by other data structure.

There are trees other than binary tree, so there are heaps other than binary heap - D-ary Heap, Fibonacci Heap, Index heap, Binomial Heap, Pairing Heap, etc. But binary heap is very useful and important data structure.
-->

---

# Heap Sort

<logos-jupyter />

<br/>

1. create a binary heap

2. add all elements to the heap

3. recursively obtain the min/max element from the heap

---

# Heapify

<logos-jupyter />

<br/>

<span class="hl">Heapify</span>: convert the array to be a binary heap (array)

by "sift down" the non-leaf node one by one from bottom to top

time complexity: $O(N)$  
space complexity: $O(1)$

<!--
last non-leaf node: parent of last leaf node
-->

---
layout: two-cols
---

# Heapify

<br/>

Complete Binary Tree (Perfect Binary Tree)

<br/>

<table style="font-family: 'Open Sans'; font-size: 0.8rem;">
  <tbody>
  <tr>
    <td align="right">last level nodes:</td>
    <td align="left">n/2</td>
    <td align="right">sift_down:</td>
    <td align="left">n/2 * 0</td>
  </tr>
  <tr>
    <td align="right">2nd last level nodes:</td>
    <td align="left">n/4</td>
    <td align="right">sift_down:</td>
    <td align="left">n/4 * 1</td>
  </tr>
  <tr>
    <td align="center">......</td>
  </tr>
  <tr>
    <td align="right">h+1 last level nodes:</td>
    <td align="left">n/2^(h+1)</td>
    <td align="right">sift_down:</td>
    <td align="left">n/2^(h+1) * h</td>
  </tr>
  </tbody>
</table>

::right::

<div align="center">

<br/>

<br/>

<br/>

Time Complexity: $O(n)$

<br/>

<img src="/images/heapify_complexity.png" style="width: 80%"/>

</div>

---

# Heap Sort

<br/>

<img src="/images/heap_sort.png" style="height: 85%"/>

---

# Map

<br/>

A Map is an abstract data structure (ADT):

-   a collection of kye-value (k,v) paris
-   there cannot be duplicate keys (key can be viewed as a unique identifier for the object/value)

k - unique  
v - can be repeated

<span class="norm">🤔 Can we use **none**/**null** key?</span>

---

# Map

<br/>

a shopping cart:

| Product(key)   | Quantity(value) |
| :------------- | :-------------- |
| tiger beer:    | 12 (cans)       |
| us apple:      | 4 (pieces)      |
| chicken wings: | 12 (pieces)     |
| ...            | ...             |

---

# Map Operations

<br/>

for a map

<pre class="norm">
- map[k], map.get(k)
- map.pop(k)
- map[k] = v, map.set(k), map.setdefault(k, default)
- map.keys()
- map.values()
- del map[k], map.clear()
- size(map)
- iter(map), map.items()
</pre>

---

# Sorted Map

<br/>

A Sorted Map is an abstract data structure (ADT):

-   extension of Map and keys are sorted in increasing order

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
-   Hash Table

---

# Map Implementation: Linked List

<br/>

-   store (k,v) in a doubly linked list

-   get(k)

    -   loop through the list until find the element with key k

-   set(k,v)

    -   create a new node (k,v) and add it at the front

-   delete(k)
    -   loop through the list until find the element with key k
    -   remove it by updating the pre and next elements

Complexity: $O(n)$

---

# Hash Table

<br/>

A <span class="hl-color">Hash table</span> is a data structure that provides a mapping from keys to values using a technique called <span class="hl-color">hashing</span>.

A hash function <span class="hl-color">H(x)</span> is a function that maps a <span class="uline">general</span> key ‘x’ to a whole number in a fixed range [0, N-1].

<!--
large keys → small keys (indexable)
-->

---

# Hash Function

<br/>

step1. Hash Code: abitrary object → integer

<p class="norm">An element is converted into an integer by using a hash function. This element can be used as an index to store the original element, which falls into the hash table.</p>

step2. Compression: $integer \in [0, N-1]$

<p class="norm">
The element is stored in the hash table where it can be quickly retrieved using hashed key.
<br/>
hash = hashfunc(key)<br/>
index = hash % array_size<br/>
</p>

---
layout: two-cols
---

# Hash Function

<br/>

a number of (k, v) pairs with key set {“abcdef”, “bcdefa”, “cdefab” , “defabc”}

The ASCII values of a, b, c, d, e, and f are 97, 98, 99, 100, 101, and 102 respectively.

| key    |            Hash Function             | Index |
| :----- | :----------------------------------: | :---- |
| abcdef | (97 + 98 + 99 + 100 + 101 + 102)%599 | 2     |
| bcdefa | (98 + 99 + 100 + 101 + 102 + 97)%599 | 2     |
| cdefab | (99 + 100 + 101 + 102 + 97 + 98)%599 | 2     |
| defabc | (100 + 101 + 102 + 97 + 98 + 99)%599 | 2     |

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

| key    |               Hash Function                | Index |
| :----- | :----------------------------------------: | :---- |
| abcdef | (971 + 982 + 993 + 1004 + 1015 + 1026)%599 | 38    |
| bcdefa | (981 + 992 + 1003 + 1014 + 1025 + 976)%599 | 23    |
| cdefab | (991 + 1002 + 1013 + 1024 + 975 + 986)%599 | 14    |
| defabc | (1001 + 1012 + 1023 + 974 + 985 + 996)%599 | 11    |

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

# Hash Code: Bit Representation
 
```python
# XOR byte by byte
def byte_xor(ba1, ba2):
    return bytes([_a ^ _b for _a, _b in zip(ba1, ba2)])

# produce 32-byte hash code 
# chop the data into 32-byte long chunks (pad with zeros if required)
# compute XOR on all chunks 
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

---

# Hash Code: Polynomial & Cyclic-Shift

<br/>

### Polynomial
for n-tuple ($x_0, x_1, x_2, ..., x_{n-1}$), if position is important, we can multiply $a^{n-1}$ for position n, e.g.:    

$x_0·a^0 + x_1·a^1  + x_2·a^2  + ...  + x_{n-1}·a^{n-1}$

### Cyclic-Shift

for bitwise, we can also apply cyclic-shift function instead of multiplication, e.g. shift(x, y) means cyclic-shift y bits:      

$shift(x_0, 0\;mod\;32) \oplus shift(x_1, 1\;mod\;32)  \oplus shift(x_2, 2\;mod\;32)  \oplus ...  \oplus shift(x_{n-1}, (n-1)\;mod\;32)$



---

# Compression Function

<br/>

for hash code $i$: 

- Division Method: $i\;mod\;N$

- MAD: $[(a·i\;+\;b)\;mod\;p]\;mod\;N$  
  where $p$ is a prime number, $p > N$, $a$ and $b$ are random number, $a\in[0, p-1]$, $b\in[0, p-1]$


---

Hash Function

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering

---

# Skip List

<br/>

blablablan

---

# Binary Search Tree

<br/>

blablablan

---

# AVL

<br/>

blablablan

---

# Merge-Sort

<br/>

blablablan

---

# Quick Sort

<br/>

blablablan

---

# Brute Force Pattern Matching

<br/>

blablablan

---

# Boyer-Moore

<br/>

blablablan

---

# KMP

<br/>

blablablan

---

# Depth-First Search (DFS)

<br/>

blablablan

---

# Breadth-First Search (BFS)

<br/>

blablablan

---

# Dijkstra's Shortest Path

<br/>

blablablan

---

# Min-Spanning Tree (MST)

<br/>

blablablan

---

# DAG

<br/>

blablablan

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

<br/>

blablablan

---

# Lab 2

<br/>

blablablan

---

# Lab 3

<br/>

blablablan

---

# Lab 4

<br/>

blablablan

---

# Lab 5

<br/>

blablablan

---

# Lab 6

<br/>

blablablan
