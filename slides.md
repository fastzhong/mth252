---
theme: seriph
title: "MTH252"
background: https://mth252.fastzhong.com/images/cover.webp
highlighter: shiki
lineNumbers: false
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
    Learning Objectives (Mar ~ Apr 6 weeks, 6 lectures & 6 labs):
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

#### Solution related to DSA questions:

⚠️  <span class="norm">always seek the best time and space complexity by appling DSA taught in MTH251 & MTH252</span>   
  
⚠️  <span class="norm">in principle, only the standard ADT operations allowed to use by default as the solution has to be language indenpendent</span>  
  
⚠️  <span class="norm">advanced features and built-in functions from Python not allowed if not clearly asked by the question, e.g. sort/search/find (in)/min(list)/max(list)/set/match ... , as the complexity becomes unknown and Python dependent</span>


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

- key of root is always the smallest (MinHeap) or the largest (MaxHeap)

- subtree is also a binary heap 

- from root to any leaf, the key values are in non-decreasing order

- given height $h$, total nodes of binary heap: $2^h \leq n \leq 2^{h+1} - 1$

- given total nodes $n$, binary heap height: $\log_2(n+1) - 1 \leq h \leq \log_2n$

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
|                       |                     |            |                             |
| --------------------: | :------------------ | ---------: | :-------------------------- |
|     last level nodes: | $\frac{n}{2}$       | sift_down: | $\frac{n}{2} * 0$           |
| 2nd last level nodes: | $\frac{n}{4}$       | sift_down: | $\frac{n}{4} * 1$           |
|                   ... |                     |        ... |                             |
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
| :---------- | :----------- |
| A           | 80           |
| B           | 70           |
| C           | 60           |
| ...         | ...          |

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
layout: two-cols
---

# Hash Function

<br/>
   
-   $H(x)$ must be deterministic
-   $H(x)$ need to be fast $O(1)$
-   $H(x)\;mod\;N$ evenly distributed
-   if $x = y$, H(x) and H(y) <span class="uline">must be equal</span>
-   if $H(x) = H(y)$, x and y <span class="uline">might be equal</span>
-   if $H(x) \ne H(y)$, x and y <span class="uline">certainly not equal</span>

<br/>

<div style="width: 90%;">

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering

</div>

::right::

<br/>

<span class="norm">💡 coding tips:</span>  
-   <span class="norm">avoid to use real or big number as key: $H(0.0) == H(-0.0)$ ?</span>
-   <span class="norm">compare hash code first, before compare x and y</span>
-   <span class="norm">overwrite either both of **eq** and **hash** or neither of them</span>
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
Linear Search vs. Binary Search
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

- del min

- del max

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

- pre-order
- in-order: "sorted list" 👈
- post-order
- level order

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

# BST vs. Heap

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
- <span class="norm">perfect binary tree (minimum heigh)</span>
- <span class="norm">complete binary tree</span>
- <span class="norm">Binary Heap, Red Black Tree, Segment Tree, etc.</span>

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
- When: insert(), delete()
- Where: backtracking from the node

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
- y.right = x
- x.left = T3
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
- y.left = x
- x.right = T3
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

# BST vs. AVL Complexity

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

- <span class="hl">2-node</span>: node with two child nodes 
- <span class="hl">3-node</span>: node with three child nodes
- <span class="hl-strong">a perfectly balanced tree</span>: all leaf nodes at the same level  

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

- "black balanced" 

- $N$ nodes → height: $2logN$, Complexity: $O(logN)$

- Red Black Tree vs. AVL Tree

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

insert a red node →  a blank tree

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

#### Left Rotate

<div style="width: 90%;">

```md
- node.right = x.left 
- x.left = node
- x.color = node.color
- node.color = RED
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

#### Flip Colors

<div style="width: 90%;">

```md
- node.color = RED 
- node.left.color = BLACK
- node.right.color = BLACK 
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

#### Right Rotate

<div style="width: 90%;">

```md
- node.left = T1 
- x.right = node
- x.color = node.color
- node.color = RED 
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

#### insertion: LR → RR → FC

<br/>

<img src="/images/rb-LR-RR-FC.png" style="height: 40%"/>


---

# Red Black Tree

<logos-jupyter />

<br/>

<br/>

#### insertion: LR → RR → FC

- 2-node 
- 3-node

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

# Skip List vs. Hash Table, Balanced Tree

<br/>

- single key search, Hash Table close to $O(1)$
- for Skip List node, avg no. of pointers $\frac{p}{1-p}$, when $p = \frac{1}{4}$, $1.33 < 2$
- keys in order, better for range search
- Skip List operations (linkedlist++) simpler than balanced tree (AVL, Red Black Tree, etc.)
- Skip List overall implementation simpler

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

- sort the arr from left to right
- every time select the smallest
- for position $i$:
  - $[0, i)$ sorted
  - $[i,n)$ unsorted
  - find the smallest from $arr[i, n)$ and place at $arr[i]$
- Complexity: $1 + 2 + 3 + ... + n = \frac{(n + 1) * n}{2}$

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

- sort the arr from left to right
- for postion $i$:
  - $[0, i)$ sorted
  - $[i, n)$ unsorted
  - insert $arr[i]$ to the proper position on the left
- Complexity: $O(n^2)$, if already sorted → $O(n)$ 👍

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

- sort the arr from right to left
- for postion postion $n-i-1$: 
  - $[n-i, n)$ sorted
  - $[0, n-i-1)$ unsorted
  - bubble the biggest to $arr[n-i-1]$
- Complexity: $O(n^2)$

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

- recursively $[l, m, r]$:
  - sort $[l, m]$
  - sort $[m+1, r]$
  - <span class="hl-strong">merge</span> two sorted array $[l, m]$ & $[m+1, r]$

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

- merge top down: <span class="norm">sort_merge_bottomup_v1</span>   
  improvement: <span class="norm">sort_merge_recusive_v2</span>
  - <span class="norm">✅ insertion</span>
  - <span class="norm">❌ tmp</span>

- merge buttom up: <span class="norm">sort_merge_bottomup</span>

- worst case ?
    - <span class="norm">almost sorted array</span>
    - <span class="norm">duplicates</span>

---
layout: two-cols
---

# Sorting: Merge

<br/>

- Time Complexity $O(n \cdot log_2n)$
- Space Complexity $O(n)$

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

- <span class="hl-strong">partition</span>: select $v$, so that $[l, p-1] \leq v$ and $[p+1, r] \geq v$ 
- recursive sort $[l, p-1]$
- recursive sort $[p+1, r]$

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

- worst case: $O(n^2)$
    - <span class="norm">sorted array</span>
    - <span class="norm">duplicates</span>
    - <span class="norm">$O(n^2)$ possibility: $\frac{1}{n} * \frac{1}{n-1} * \frac{1}{n-2} * ... = \frac{1}{n!}$</span>
    - <span class="norm">recusion stack overflow</span>

- improvement:
    - <span class="norm">2-way quicksort </span>
    - <span class="norm">3-way quicksort </span>
    - <span class="norm">[3-way radix quicksort ](https://en.wikipedia.org/wiki/Multi-key_quicksort)</span>
    - <span class="norm">[dual pivot quicksort](https://arxiv.org/abs/1503.08498)</span>

<span class="norm"> 👉 random algorithm, time complexity $O(N \cdot log_2N)$ (📚 Introduction to Algorithms)</span>

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

👉 <span class="norm"><span class="hl-strong">1hr</span> vs.  <span class="hl-strong">31days</span> (≈ 753hrs)</span>

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
<span class="norm">✅  otherwise → "adaptive merge sort"</span>

::right::

<br/>

<br/>

<br/>

<br/>

2 types of sorting operations:

- <span class="norm">moving or coping objects (just one step)</span>
- <span class="norm">comparing two objects:</span>
    <span class="norm">compare class type → compare method → if not, ...</span>

<br/>

<span class="norm">⚠️ comparing objects is very expensive</span>

---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

- **run**: parts that are strictly increasing (if decreasing, reverse it)
- split into multiple runs
- **Galloping**: merge runs 

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

- primitive array: **Dual Pivot Quicksort**

- object array: **Timsort**

---
layout: center
---

# Selection

---

# Selection

<br/>

In computer science, a <span class="hl-color">selection algorithm</span> is an algorithm for finding the k<sup>th</sup> smallest number in a list or array; such a number is called the k<sup>th</sup> order statistic (selectK/topK). This includes the cases of finding the minimum, maximum, and median elements. 

---

# Selection

#### Binary Search

<mdi-timer-sand />



<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Selection

#### Heap

-  pop k times (remove_min, remove_max)
-  complexity: $O(N) + O(KlogN)$

<br/>

-  create Heap with size K, add element one by one:
    - if bigger than the top (min), replace it;
    - else skip it
-  complexity: $O(K) + O(NlogK)$

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Selection

#### BTS


<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Selection

#### Sorting 

merge sort O(NlogN)
quick sort O(n) selectK, topK

<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Prune-and-Search

<mdi-timer-sand />

TBD

---

# Randomised Quick Sort

<mdi-timer-sand />

TBD

---
layout: center
---

# Text Processing

---

# Text Processing

#### Algorithms on Strings

- docs editors, emails, messages

- web sites, search engine

- bio-data (genonme sequencing)

- natual language processing (NLP)

- ...

<br/>

<span class="norm">Example:  </span>
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

- input: a text string $S$ with a length of $n$, a pattern string $P$ with length of $m$, and an integer $d$

- output: all positions in $S$ where $P$ appears as a substrign <span class="ul">with at most $d$ mismatches</span>

<!--

Approximate Pattern Matching (fuzzle matching?) in genome sequencing detection

Pattern Matching is a searching problem.

-->

---

# Pattern Matching

<br/>

- <span class="hl-bg">Brute Force</span>

- <span class="hl-bg">Rabin-Karp</span> <span class="norm">(Michael O. Rabin and Richard M. Karp, 1987)</span>

- <span class="hl-bg">Boyer-Moore Algorithm</span> (BM) <span class="norm">(Robert S. Boyer and J Strother Moore, 1970, 1974, 1977 )</span>

- <span class="hl-bg">Sunday Algorithm</span> (Sunday) <span class="norm">(Daniel M.Sunday, 1990)</span>

- <span class="hl-bg">Knuth-Morris-Pratt Algorithm</span> (KMP) <span class="norm">(Knuth, Morris and Pratt, 1977)</span>

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

#### Rolling Hash  

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

- $S[i]\;==\;P[j]$
  - if $j = m$, $P$ is found in $S$
  - else move both $S$ and $P$ to next char   
  $i++$, $j++$


- $S[i]\;!=\;P[j]$ (bad char)
  - if longest common prefix/suffx found, next char to compare:   
  $j = next[j-1] + 1$
  - else compare from the begining (∵ $next[j-1] = -1$):   
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

- where $S[i+j]$ is the bad char, and $P[b] == S[i+j]$ is the right most bad char 
- if $P[b]$ doesnot exist, let $b = -1$

<br/>

<span class="norm">💬 bad char offset $b$ can be pre-built for bad char position $j$ ($P[j]$) for all possible missing char in <span class="hl-strong">2-D</span> lookup table $badchar\_tbl$ ?</span> 

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
  
- case1: bad char not found $d = j - b = j - (-1)$ 

- case2: bad char found and $b < j$, $d = j - b$ 

- case3: when $d \leq 0$, let $d = 1$ (might not be the optimized shift)
 
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

$badchar\_tbl$ becomes <span class="hl-strong">1-D</span> table: 
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

- $P[j]$: bad char
- $P[j+1:m]$ = $P[s:s+k]$: good suffix with length $k = (m-1) - j$ 

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

- $P[j]$: bad char
- $P[j+1:m]$: good suffix 
- $P[j+2:m]$: potential prefix 
- $P[r:m]$: the largest prefix ($P[0:m-r]$), where $j+2 \leq r \leq m-1$   

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

- <span class="hl">Suffix</span><span class="norm"> array: start position of the right most suffix</span>  
- <span class="hl">Prefix</span><span class="norm"> array: True if it is a prefix </span>

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

- <span class="strong">bad char</span> $d1$  

- <span class="strong">good suffix</span> $d2$

- $d = max(d1, d2)$

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

#### Time Complexity

- best case: $O(m + n/m)$ 
- worst case: $O(m + n*m)$ <span class="norm">👉 $\approx 3n$, see linkes below</span>

<br/>

#### Space Complexity: 

- bad char table: $O(256 * m)$ or $O(m)$
- suffix: $O(m)$
- prefix: $O(m)$

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

# Dynamic Programming

---

# Dynamic Programming

<br/>

<span class="hl-bg">Dynamic Programming</span>(DP) solves problems by combining the solutions to subproblems. It can be analogous to "divide-and-conquer" method, where problem is partitioned into disjoint subproblems, subproblems are recursively solved and then combined to find the solution of the original problem. 

- subproblems may share subsubproblems (subproblem overlap)
- DP solves each subproblems once and saves its answer to a table (memorization)  
- technique of constructing DP solution:
  - iterative (using for loop)
  - recusive  (using recursion)

<span class="norm">💡 usually DP problem is hard</span>    
<span class="norm">💡 different DP through exercises</span>  
<!--

Patterns: brute-force, hashing, devide-and-conquer, recursion, ...

-->

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

# Graph

---

# Graph

<br/>

- Implement graph ADT using different internal representation

- Learn graph associated algorithms

- How graph can be used to solve a wide variety of problems

<br/>

<span class="norm">💡 graph can model many things in real world such as roads, airline routes, social media connections, etc.
</span>

---

# Graph Terminology

<br/>

A <span class="hl-bg">graph</span> is an ordered pair $G = (V, E)$ comprising a set $V$ of <span class="hl">vertices</span> or nodes and a collection of pairs of vertices from $V$, known as <span class="hl">edges</span> of a graph. For example, for the graph below:  


$V = { 1, 2, 3, 4, 5, 6 }$  
$E = { (1, 4), (1, 6), (2, 6), (4, 5), (5, 6) }$  

<img src="/images/graph01.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Undirected Graph 

An <span class="hl-strong">Undirected</span> graph(graph) is a graph in which edges have no orientation. The edge $(x, y)$ is identical to edge $(y, x)$, i.e., they are not ordered pairs. The maximum number of edges possible in an undirected graph without a loop is $n×(n-1)/2$.

<img src="/images/graph-undirected.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Directed Graph 

A <span class="hl-strong">Directed</span> graph (digraph) is a graph in which edges have orientations, i.e., The edge $(x, y)$ is not identical to edge $(y, x)$.

<img src="/images/graph-directed.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Directed Acyclic Graph (DAG) 

A <span class="hl-strong">Directed Acyclic Graph</span> (DAG) is a directed graph that contains no cycles.

<img src="/images/graph-dag.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Weighted and Unweighted graph

A weighted graph associates a value (<span class="hl-strong">weight</span>) with every edge in the graph. We can also use words cost or length instead of weight.

An unweighted graph does not have any value (weight) associated with every edge in the graph. In other words, an unweighted graph is a weighted graph with all edge weight as 1. Unless specified otherwise, all graphs are assumed to be unweighted by default.

<img src="/images/graph-weighted.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Simple and Multi graph

A <span class="hl-strong">multigraph</span> is an undirected graph in which multiple edges (and sometimes loops) are allowed. Multiple edges are two or more edges that connect the same two vertices. A loop is an edge (directed or undirected) that connects a vertex to itself; it may be permitted or not.

A <span class="hl-strong">simple</span> graph is an undirected graph in which both multiple edges and loops are disallowed as opposed to a multigraph. In a simple graph with $n$ vertices, every vertex’s degree is at most $n-1$.

<img src="/images/graph-simple.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Complete graph

A complete graph is one in which every two vertices are adjacent: all edges that could exist are present.

<img src="/images/graph-complete.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

#### Connected graph

A Connected graph has a path between every pair of vertices. In other words, there are no unreachable vertices. A disconnected graph is a graph that is not connected.

<img src="/images/graph-connected.png" style="height: 40%"/>

---

# Graph Terminology

<br/>

- an **edge** is (together with vertices) one of the two basic units out of which graphs are constructed, each edge has two vertices to which it is attached, called its **endpoints**.
- two vertices are called **adjacent** if they are endpoints of the same edge.
- **outgoing** edges of a vertex are directed edges that the vertex is the origin.
- **incoming** edges of a vertex are directed edges that the vertex is the destination.
- the **degree** of a vertex in a graph is the total number of edges incident to it.
- in a directed graph, the **out-degree** of a vertex is the total number of outgoing edges, and the **in-degree** is the total number of incoming edges.
- a vertex with in-degree zero is called a **source** vertex, while a vertex with out-degree zero is called a **sink** vertex.
- an **isolated** vertex is a vertex with degree zero, which is not an endpoint of an edge.
- **path** is a sequence of alternating vertices and edges such that the edge connects each successive vertex.
- **cycle** is a path that starts and ends at the same vertex
- **simple** path is a path with distinct vertices.


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

- a graph is **Strongly Connected** if it contains a directed path from u to v and a directed path from v to u for every pair of vertices u, v.
- a directed graph is called **Weakly Connected** if replacing all of its directed edges with undirected edges produces a connected (undirected) graph. The vertices in a weakly connected graph have either out-degree or in-degree of at least 1.
- **connected component** is the maximal connected subgraph of an unconnected graph.
- a **bridge** is an edge whose removal would disconnect the graph.
- **forest** is a graph without cycles.
- **tree** is a connected graph with no cycles. If we remove all the cycles from DAG (Directed Acyclic Graph), it becomes a tree, and if we remove any edge in a tree, it becomes a forest.
- **spanning tree** of an undirected graph is a subgraph that is a tree that includes all the vertices of the graph.


<style>
li {
    font-family: "Open Sans";
    font-size: 0.8rem;
    margin-bottom: 8px;
}
</style>

---

# Graph Properties

<br/>

- If a graph G has vertex set $V$ and $m$ edges, then $\sum\limits_{v\;in\;V} deg(v) = 2m$

- If a directed graph G has vertex set $V$ and $m$ edges, then $\sum\limits_{v\;in\;V} indeg(v) = \sum\limits_{v\;in\;V} outdeg(v) = m$

- A simple graph G has $n$ vertices and $m$ edges: 
  - undirected, then $m \leq n*(n-1)/2$
  - directed, then $m \leq n*(n-1)$

- An undirected graph G has $n$ vertices and $m$ edges: 
  - connected, then $m \geq (n-1)$
  - tree, then $m = (n-1)$
  - forest, then $m \leq (n-1)$

---

# Graph ADT 

<br/>

<pre class="norm">
endpoint()
opposite(v)
vertex_count()
vertices()
vertex_edge()
edges()
get_edge(Vi, Vj)
degree(v, out=True)
degree(v, out=False)
incident_edge(v, out=True)
incident_edge(v, out=False)
insert_vertex(w=None)
insert_edge(Vi,Vj,e=None)
remove_vertex(v)
remove_edge(e)
</pre>

---
layout: two-cols
---

# Graph ADT 

#### Adjacency Matrix Representation

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

#### Adjacency List Representation

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

# Depth-First Search (DFS)

<mdi-timer-sand />

---

# Breadth-First Search (BFS)

<mdi-timer-sand />

---

# Dijkstra's Shortest Path

<mdi-timer-sand />

---

# Min-Spanning Tree (MST)

<mdi-timer-sand />

---

# Prim-Jarnik Algorithm

<mdi-timer-sand />

---

# Kruskal's Algorithm

<mdi-timer-sand />

---
layout: center
---

# Trie


---

# Trie

<mdi-timer-sand />


---
layout: center
---

# Trie


---

# Suffix Tree

<mdi-timer-sand />


---
layout: center
---

# Segment Tree

---

# Segment Tree

<mdi-timer-sand />


---
layout: center
---

# B Tree

---

# B Tree

<mdi-timer-sand />


---
layout: center
---

# B+ Tree

---

# B+ Tree

<mdi-timer-sand />


---

# DSA

<mdi-timer-sand />

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

2. Give an <strong>O(logN * logN)</strong> algorithm to merge two binary heap.

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

2. before(k) & after(k) in BST would not work if BST doesnot contain the key $k$, pls improve the algorithm to support such case. 

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

TBD

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

TBD

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

TMA review

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