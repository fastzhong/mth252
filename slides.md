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
    6 weeks (Jan ~ Mar), 6 seminars & 6 labs:
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

⚠️ Algo implementation in related DSA questions:

-   always seek the best time and space complexity by appling DSA taught in MTH251 & MTH252
-   in principle, only the standard ADT operations allowed to use by default as the solution has to be language indenpendent
-   advanced features and built-in functions from Python not allowed if not clearly asked by the question, e.g. sort/search/find (in)/min(list)/max(list)/set/match ... , as the complexity becomes unknown and Python dependent


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

<logos-jupyter />

Min PQ  

-   <span class="hl-strong">add(k, v)</span> (enqueue) − adding an element to the queue
-   <span class="hl-strong">remove_min()</span> (dequeue) − obtain the first element with a pair of (k,v), where k is the mininum value of keys in Min PQ, and remove it from the queue
-   <span class="hl-strong">min()</span> (first/peek) − obtain the first element with a pair of (k,v) where k is the mininum value of keys in Min PQ
-   size(), is_empty()

<br/>

Max PQ   
<span class="hl-strong">add(k, v)</span>, <span class="hl-strong">remove_max()</span>, <span class="hl-strong">max()</span>, size(), is_empty()

---

# Priority Queue Complexity

<logos-jupyter />

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

<span class="norm">👉 A <strong>complete binary tree</strong> is a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible.
</span>

---

# Binary Heap

<br/>


💡  key of root is always the smallest

💡  subtree is also a binary heap 

💡  from root to any leaf, the key values are in non-decreasing order

💡  given height $h$, total nodes of binary heap: $2^h \leq n \leq 2^{h+1} - 1$

💡  given total nodes $n$, binary heap height: $\log_2(n+1) - 1 \leq h \leq \log_2n$

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
          <td><span style="color: orange">2</span></td>
          <td>3</td>
          <td>4</td>
          <td><span style="color: orange">5</span></td>
          <td><span style="color: orange">6</span></td>
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
2. "sift up" if new element is smaller

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
2. "sift down" if the last element is bigger

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

# Heap Sort

<logos-jupyter />

<br/>

1. create a binary heap

2. add all elements to the heap

3. recursively obtain the min/max element from the heap

---
layout: two-cols
---

# Heapify

<logos-jupyter />

<span class="hl">Heapify</span>: convert the array to be a binary heap

by "sift down" the non-leaf node one by one from bottom to top

Complete Binary Tree (Perfect Binary Tree)
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

class score:

| Student(key) | Score(value) |
| :----------- | :----------- |
| A:           | 80           |
| B:           | 70           |
| C:           | 60           |
| ...          | ...          |

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
-   Hash Table

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
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
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

```python
# XOR byte by byte
def byte_xor(ba1, ba2):
    return bytes([_a ^ _b for _a, _b in zip(ba1, ba2)])

# produce 32-byte hash code
# chop the data into 32-byte long chunks (padding with zeros if required) then XOR on all chunks
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

👉 <span class="norm">[MD5](https://en.wikipedia.org/wiki/MD5)&nbsp;&nbsp;&nbsp; [SHA-256](https://en.wikipedia.org/wiki/SHA-2)</span>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Code: Polynomial & Cyclic-Shift

<br/>

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

<br/>

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

<span class="hl">Guidelines:</span>

-   $H(x)$ must be deterministic
-   $H(x)$ need to be fast $O(1)$
-   $H(x)\;mod\;N$ evenly distributed
-   if $x = y$, H(x) and H(y) <span class="uline">must be equal</span>
-   if $H(x) = H(y)$, x and y <span class="uline">might be equal</span>
-   if $H(x) \neq H(y)$, x and y <span class="uline">certainly not equal</span>

<br/>

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering

::right::

<br/>

<span class="norm">💡 coding tips:</span>

-   <span class="norm">avoid to use real or big number as key: $H(0.0) == H(-0.0)$ ⁇</span>
-   <span class="norm">compare hash code first, before compare x and y</span>
-   <span class="norm">overwrite either both of **eq** and **hash** or neither of them</span>

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

<span class="norm">when table size $n$ is $2^y$: </span> $x\;\%\;2^y = x\;\&\;(2^y - 1)$

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
- Linear Search
- Binary Search
-->

---

# BST: Operations

<logos-jupyter />

-   search()
-   insert()
-   delete() <span class="norm">💬 1962, Hibbard Deletion</span>
-   first()
-   last()
-   before()
-   after()
-   is_empty()

<br/>

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/BST.html](https://www.cs.usfca.edu/~galles/visualization/BST.html)</span>


---

# BST: Hibbard Deletion

<logos-jupyter />


- del min

- del max


---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div align="center">
  <img src="/images/hibbard.png" style="width:80%"/>
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

---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div align="center">
  <img src="/images/hibbard.png" style="width:80%"/>
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

---

# BST: Traversal

- pre-order
- in-order: sorted list 👈
- post-order
- level order

<!--

pre/in/post depends on when we want to proces the node, e.g. for memory management in C++, we probably want to do GC for the node when GC is done for left & right subtree, so post-order may be a choice.

min, max
floor, ceil
rank, select


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

# Heap vs. BST

<br/>

-   Heap is <span class="uline">balanced</span> tree, BST is not

-   Heap allows duplicates, BST doesnot

-   BST is ordered data structure, Heap is not

-   worst case for building $n$ nodes of BST $O(n \cdot log(n))$, Heap is $O(n)$

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/binary_search_tree4.png" style="width:40%"/>
</div>

---
layout: center
---

# AVL

---
layout: two-cols
---

# AVL

<br/>

-   named after inventors G.M. <span class="hl-color">A</span>del’son-<span class="hl-color">V</span>el’skii and E.M. <span class="hl-color">L</span>andis, 1962

-   first type of <span class="hl-bg">Balanced Binary Search Tree</span> (BBST)

-   height balanced: $BF$ - balance factor
    $BF = H(node.right) - H(node.left)$
    $BF \in {-1, 0, 1}$

-   heigh and no. of nodes: $O(logN)$

<br/>

Examples:
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

Rebalance ⁇  
- when: insert(), delete()
- where: backtracking from the node

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

- y.right = x

- x.left = T3

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

- y.left = x

- x.right = T3

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


1. LR → LL: left rotate

2. LL: right rotate


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

1. RL → RR: right rotate

2. RR: left rotate

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

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/AVLtree.html](https://www.cs.usfca.edu/~galles/visualization/AVLtree.html)</span>


<!--

- Height: after re-compute height, if no change, there is no need to re-balance for all parent nodes

- Red Black Tree better than AVL

-->

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
    <h3><logos-jupyter /> search key</h3>
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
    <h3><logos-jupyter /> delete key</h3>
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
    <h3><logos-jupyter /> insert key</h3>
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
    <h3><logos-jupyter /> insert key</h3>
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

<div style="width: 50%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="60%">Time Complexity avg</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN) 👈</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

[Skip Lists: A Probabilistic Alternative to Balanced Trees](https://15721.courses.cs.cmu.edu/spring2018/papers/08-oltpindexes1/pugh-skiplists-cacm1990.pdf), William Pugh, 1990

<!--
Insert & Delete need to update the searching path, so it depends on Search.
-->

---

# Skip List vs. Hash Table, Balanced Tree

<br/>

- keys in order, better for range search
- operations (linkedlist+ operations) simpler than balanced tree (AVL, Red Black Tree, etc.)
- for Skip List node, avg no. of pointers $\frac{p}{1-p}$, when $p = \frac{1}{4}$, 1.33 < 2
- single key search, Hash Table close to O(1)
- Skip List implementation simpler

---
layout: center
---

# Sorting

---

# Sorting

<br/>

-   make data in order
-   different **Algorithmic Thinking**

---

# Sorting: Selection

<logos-jupyter />

<br/>

- sort the arr from left to right
- every time select the smallest
- for position i:
  - [0, i) sorted
  - [i,n) unsorted
  - find the smallest from arr[i, n) and place at arr[i]
- Complexity: $1 + 2 + 3 + ... + n = \frac{(n + 1) * n}{2}$

<br/>

<img src="/images/sort_selection.gif" style="width:50%"/>

---

# Sorting: Insertion

<logos-jupyter />

<br/>

- sort the arr from left to right
- for postion i:
  - [0, i) sorted
  - [i, n) unsorted
  - insert arr[i] to the proper position on the left
- Complexity: $O(n^2)$, if already sorted, $O(n)$ 👍

<br/>

<img src="/images/sort_insertion.gif" style="height:40%"/>

---

# Sorting: Bubble

<logos-jupyter />

<br/>

- sort the arr from right to left
- for postion postion n-i-1
  - [n-i, n) sorted
  - [0, n-i-1) unsorted
  - bubble the biggest to arr[n-i-1]
- Complexity: $O(n^2)$

<br/>

<img src="/images/sort_bubble.gif" style="width:50%"/>

<!--

bubble up = swap, more time consuming

improve the data overall ordering while bubble up

-->

---

# Sorting: Merge

<logos-jupyter /> John von Neumann  

- recursively [l, m, r]:
  - sort [l, m]
  - sort [m+1, r]
  - merge two sorted array [l, m] & [m+1, r]

<br/>

<div class="inline-grid grid-cols-[1fr,3fr] gap-8">
  <div>
    <img src="/images/JohnvonNeumann.jpeg" style="height:50%"/>
  </div>
  <div>
    <img src="/images/sort_merge.gif" style="height:60%"/>
  </div>
</div>


<!--
John von Neumann
-->

---

# Sorting: Merge

<logos-jupyter />

<br/>

- merge top down:
  - <span class="norm">[On finding the average of two unsigned integers without overflow](https://devblogs.microsoft.com/oldnewthing/20220207-00/?p=106223)</span>
  - insertion
  - tmp

- merge buttom up

- worst case:
    - <span class="norm">sorted array</span>
    - <span class="norm">sorted array (reversed order)</span>
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
  <img src="/images/sort_merge_complexity.png" style="width:80%"/>
</div>


<!--
Analysis of Algorithms:

- worst case
- ignore constant factors, lower-order terms
- asymptotic analysis (large input size)

Algo analysis: lose a little bit of granularity of information but we dont lose what we really care about which is accurate guidence about what algorithms are gonna be faster than the others.
-->

---

# Sorting: Quick

<logos-jupyter /> Tony Hoare

- partition: select v, so that [l, p-1] smaller than v and [p+1, r] bigger than v
- recursive sort [l, p-1]
- recursive sort [p+1, r]

<br/>

<div class="inline-grid grid-cols-[1fr,3fr] gap-8">
  <div>
    <img src="/images/TonyHoare.jpeg" style="height:80%"/>
  </div>
  <div>
    <img src="/images/sort_quick.gif"  style="height:80%"/>
  </div>
</div>

<!--
Tony Hoare

Quick is faster than Merge because partion func is faster than merge function
-->

---

# Sorting: Quick

<br/>

- worst case: $O(n^2)$
    - <span class="norm">sorted array</span>
    - <span class="norm">sorted array (reversed order)</span>
    - <span class="norm">duplicates</span>
    - $O(n^2)$ possibility: $\frac{1}{n} * \frac{1}{n-1} * \frac{1}{n-2} * ... = \frac{1}{n!}$

- recusion stack overflow

- random algorithm, time complexity $O(n \cdot log_2n)$ 👉 [Introduction to Algorithms]()

- two-way quicksort, [3-way radix quicksort ](https://en.wikipedia.org/wiki/Multi-key_quicksort), [dual pivot quicksort](https://arxiv.org/abs/1503.08498)

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

👉 <span class="norm"><span class="hl-color">1hr</span> vs.  <span class="hl-color">31days</span> (≈ 753hrs)</span>

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

<mdi-link/>[Timsort](https://bugs.python.org/file4451/timsort.txt)

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

- <span class="norm">size < 64, insertion sort</span>
- <span class="norm">"adaptive merge sort"</span>

::right::

<br/>

<br/>

<br/>

<br/>

sort operations:

1. <span class="norm">moving or coping objects (just one step)</span>
2. <span class="norm">comparing two objects:</span>
    <span class="norm">compare class type → compare method → if not, ...</span>

<br/>

<span class="norm"> comparing objects is very expensive</span>

---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

- run: parts that are strictly increasing (if decreasing, reverse it)
- split into multiple runs
- merge runs - **Galloping**:

<br/>

<pre class="norm">
[1, 2, 3, ..., 100, ..., 101, 102, 103, ..., 200]  
run1 = [1, 2, 3, , ..., 100]  
run2 = [101, 102, 103, , ..., 200]  
......
</pre>

$run2[2^{n-1} - 1] <pre run1[0] \leq run2[2^n - 1]$  

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

In computer science, a <span class="hl-color">selection algorithm</span> is an algorithm for finding the k<sup>th</sup> smallest number in a list or array; such a number is called the k<sup>th</sup> order statistic. This includes the cases of finding the minimum, maximum, and median elements.

selectK

topK

---
# Binary Search

<mdi-timer-sand />

TBD

---

# Heap

selectK

-  Max Heap: pop k times (remove_max)
-  Max Heap Complexity: $O(KlogN)$

<br/>

-  Min Heap: create Min Heap with size K, add element one by one:
    - if bigger than the top (min), replace it;
    - else skip it
-  Min Heap Complexity: $O(NlogK)$


merge sort O(NlogN)
quick sort O(n) selectK, topK

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

Algorithms on Strings

- docs editors, emails, messages

- web sites, search engine

- bio-data (genonme sequencing)

- natual language processing (NLP)

- ...

<br/>

<pre class="norm">
“Hello World”
“http://www.google.com”
“CGTAAACTGCTTTAATCAAACGC”
</pre>

---

# Pattern Matching

<br/>

<span class="hl">Pattern Matching</span>: For a text string $S$ with a length of $n$, and a pattern string $P$ with length of $m$, decides if $P$ is a substring of $S$.

<br/>

<span class="hl">Approximate Pattern Matching</span>:

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

<br/>  

For a text string $S$ with a length of $n$, and a pattern string $P$ with length of $m$, $i = m-1...n - 1$, compute hashing $h(i)$ for substring S[i...i + m - 1]:

$B = 256$   
$M = 1e9 + 7$  
$BP = B^{m-1}\;\%\;M$  

  h(i): S[i-m+1] ... S[i]  
h(i+1): <span style="text-decoration: line-through red;">S[i-m+1]</span> ... S[i] S[i+1]  

-   $h[i] = (h * B + S[i]) % M$

-   $h = h[i] - s[i-m+1] * B^{m-1}$  
    $h = h[i] - s[i-m+1] * B^{m-1}\;\%\;M$  
    $h = (h[i] - s[i-m+1] * B^{m-1}\;\%\;M + M)\;\%\;M$   
    $h = (h[i] - s[i-m+1] * BP\;\%\;M + M)\;\%\;M$ 
     


::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

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
  
$(a + b)\;\%\;M = (a\;\%\;M + b\;\%\;M)\;\%\;M$   
$(a * b)\;\%\;M = (a\;\%\;M * b\;\%\;M)\;\%\;M$ 

<!--

Rabin-Karp = rolling hashing

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

# Boyer-Moore

---
layout: two-cols
---
# Boyer-Moore (BM)

<br/>

<div align="center">
  <img src="/images/string_matching_bm1.png" style="width: 80%"/>
  <img src="/images/string_matching_bm2.png" style="width: 80%"/>
  <img src="/images/string_matching_bm3.png" style="width: 80%"/>
  <img src="/images/string_matching_bm4.png" style="width: 80%"/>
  <img src="/images/string_matching_bm5.png" style="width: 80%"/>
</div>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_bm6.jpeg" style="width: 80%"/><br/>
  <img src="/images/string_matching_bm7.jpeg" style="width: 80%"/>
  <br/>
  <br/>
  "<span class="hl">bad char</span>"
</div>

<!--

E mistach and not in Pattern 
B mistach and in Pattern 
D mistach and in Pattern 

if there are two or more bad char in Pattern

-->

---
layout: two-cols
---

# Boyer-Moore (BM)

<span class="hl-color">S: "B" → "B"</span>

<span class="hl">bad char</span> shift $d$: $d = j - b$   

- where $P[j]$ is the bad char("C") , $P[b]$ is the right most bad char ("D")
- if cannot find bad char ("D") in $P$ let $b = -1$ 

<span class="norm">💬 bad char offset $b$ can be pre-built in a bad char dictionary</span> 

<br/>

::right::

<br/>

<br/> 

<br/>

<br/>

<br/>

<br/>


<div align="center">
  <img src="/images/string_matching_bm11.jpeg" style="width: 90%"/>
</div>


---
layout: two-cols
---

# Boyer-Moore (BM)

<logos-jupyter />

<span class="hl">bad char</span> shift for Pattern $P$ lookup table $badchar\_dict$:   

- all possible bad char (ascii "0-255") and default $-1$
- for each char $P[b]$ in P (i = 0...m-1): $badchar\_dict[P[b]] = b$

<br/>

<br/>

<br/>

<br/>

<span class="norm">"b" appears twice in P, and shift to <span class="uline">the right most</span> "b", $d = j - b$ is $4 - 2$ instead of $4 - 0$</span>

<span class="norm">the offset in lookup table, 2nd "b" will replace the first as iterating P from left to right: $badchar\_dict['b'] = 0$ → $badchar\_dict['b'] = 2$</span>

::right::

<br/>

<br/> 

<br/>

<div align="center">
  <img src="/images/string_matching_bm11.jpeg" style="width: 90%"/><br/>
  <img src="/images/bm_bad_char1.png" style="width: 90%"/>
  <img src="/images/bm_bad_char2.png" style="width: 90%"/>
  <img src="/images/bm_bad_char3.png" style="width: 90%"/>
</div>


---
layout: two-cols
---
# Boyer-Moore (BM)

<br/>

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

<span class="hl-color">S: "A" → "B"</span>

<span class="hl">good suffix</span> on the left, shift $d$: $d = j - s$ 

- where $P[j]$ is the bad char("A") , good suffix length is $k = m - 1 - j$ ("CD")

- $P[s:s+k]$ is the right most suffix 

<span class="norm">💬 offset $s$ for right most suffix with length $k$ can be pre-built in a "suffix" array</span> 

::right::

<br/>

<br/> 

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_bm12.jpeg" style="width: 90%"/>
</div>

---
layout: two-cols
---

# Boyer-Moore (BM)

<span class="hl-color">S: "A" → "D"</span>

<span class="hl">good suffix</span> NOT on the left, shift $d$: $d = m$ 

<br/>

<br/>

<br/>

<span class="norm">⚠️ bad char: "c", good suffix: "d c a"</span>

<table class="grid">
  <tbody>
    <tr class="odd">
      <td style="font-weight:bolder">S</td>
      <td>a</td>
      <td>b</td>
      <td>c</td>
      <td  style="color:orange">b</td>
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
      <td style="color:orange">c</td>
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

::right::

<br/>

<br/> 

<br/>

<br/>

<br/>


<div align="center">
  <img src="/images/string_matching_bm15.jpeg" style="width: 90%"/>
</div>

---
layout: two-cols
---

# Boyer-Moore (BM)

<span class="hl-color">S: "B" → "C"</span>

a prefix in <span class="hl">good suffix</span>, shift $d$: $d = r$ 

- $P[j]$: bad char ("B")
- $P[j+1:m]$: good suffix ("ACD")
- $P[j+2:m]$: potential prefix 
- $P[r:m]$: the largest prefix ($P[0:m-r]$) with length $m - r$, where $j+2 \leq r \leq m-1$   

<span class="norm">💬 prefix with length $m - r$ can be pre-built in a prefix array</span> 

::right::

<br/>

<br/> 

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_bm14.jpeg" style="width: 90%"/>
</div>

---  
layout: two-cols
---
# Boyer-Moore (BM)

<logos-jupyter />

<span class="hl">Suffix</span> & <span class="hl">Prefix</span> array

- suffix: start position of the right most suffix 

- prefix: True if it is a prefix 

::right::

<br/>

<br/>

<br/>

<div style="">
  <p class="norm">P: "abcdab"</p>
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
</div>

---  

# Boyer-Moore (BM)

<logos-jupyter />

locate bad char $P[j]$, decide $d$:   

- <span class="strong">bad char</span> $d1 = j - b$ 

- <span class="strong">good suffix</span>
    1. $d2 = j - s$ ($s$ - right most suffix offset)
    2. $d2 = r$ (prefix $P[r:m]$ where $j+2 \leq r \leq m-1$) 
    3. $d2 = m$

- $d = max(d1, d2)$

---

# Boyer-Moore (BM)

<br/>


Time Complexity
- best case: $O(m + n/m)$ 
- worst case: $O(m + n*m)$ ($\approx 3n\;or\;5n$, see linkes below)

<br/>

Space Complexity: 
- bad char dict: $O(1)$
- suffix: $O(m)$
- prefix: $O(m)$

<br/>

<span class="norm">👉 [A new proof of the linearity of the Boyer-Moore string searching algorithm](https://dl.acm.org/doi/10.1109/SFCS.1977.3)</span>  
<span class="norm">👉 [Tight bounds on the complexity of the Boyer-Moore string matching algorithm](https://dl.acm.org/doi/10.5555/127787.127830)</span>

---
layout: center
---

# Sunday

---
layout: two-cols
---

# Sunday

<logos-jupyter />

<br/>

<br/>

<br/>

<br/>

<span class="hl">bad char</span>: shift $m + 1$

<br/>

<br/>

<br/>

otherwise: shift the distance from the rightmost character ($P[i]$) to the end of the string + 1 ($m - i$)

::right::

<br/>

<br/> 

<br/>

<br/>

<div align="center">
  <img src="/images/string_matching_sunday1.png" style="width: 70%"/><br/>
  <img src="/images/string_matching_sunday2.png" style="width: 70%"/>
  <img src="/images/string_matching_sunday3.png" style="width: 70%"/><br/><br/>
  <img src="/images/string_matching_sunday4.png" style="width: 70%"/>
  <img src="/images/string_matching_sunday5.png" style="width: 70%"/>
  <img src="/images/string_matching_sunday6.png" style="width: 70%"/>
</div>



---
layout: center
---

# Knuth-Morris-Pratt

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

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
      <td  style="color:orange">d</td>
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
      <td style="color:orange">e</td>
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
      <td style="color:orange">c</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
      <td rowspan="2" style="background-color: white">❌</td>      
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td style="color:orange">b</td>
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
      <td  style="color:orange">d</td>
      <td>b</td>
      <td>c</td>
      <td>b</td>
      <td>e</td>
      <td rowspan="2" style="background-color: white">✅</td>
    </tr>
    <tr class="even">
      <td style="font-weight:bolder">P</td>
      <td> </td>
      <td> </td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="font-weight:bold; color:green">c</td>
      <td style="font-weight:bold; color:green">b</td>
      <td style="color:orange">c</td>
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
b, b c, b c b, b c b c, b c b c e, b c b c e a  

</pre>

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<br/>

<span class="hl">next array</span>

<div style="width: 90%">
  <span class="norm">P: b c b c e a</span>
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
      <td  style="color:orange">d</td>
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
      <td style="color:orange">e</td>
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
      <td style="color:orange">5</td>
      <td></td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

<br/>

<span class="norm">bad char: $P[5]$</span>  
<span class="norm">substring: $P[0:5]$</span>  
<span class="norm">now shift j to the char after the prefix: $j = next[4] + 1 = 2 + 1 = 3$</span>  

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
      <td  style="color:orange">d</td>
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
      <td style="color:orange">c</td>
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
      <td style="color:orange">3</td>
      <td></td>
      <td></td>
      <td> </td>
      <td> </td>
    </tr>
  </tbody>
</table>


---

# Knuth-Morris-Pratt (KMP)

<logos-jupyter />

for i = 0...n, compare $S[i]$ and $P[j]$:   

- $S[i] == P[j]$
  - if $j = m$, $P$ is found in $S$
  - else move both $S$ and $P$ to next char $i = i+1$ and $j = j+1$


- $S[i] != P[j]$
  - if longest prefix-suffix exists, move $P$: $j = next[j-1] + 1$
  - else starts from the begining of P: $j = -1 + 1 = 0$ (∵ $next[j-1] = -1$)

---
layout: two-cols
---

# Knuth-Morris-Pratt (KMP)

<logos-jupyter />

<span class="hl">next array</span>

$next[i-1] = k$ and $P[i+1] = x$ → $next[i]$ ?  

case1: $P[k+1] == x$, than $next[i] = k + 1$  

case2: always look for $k$, so that $P[k+1] == x$ ?

$next[i-1]$ → $next[k]$ → $next[next[k]]$ → $next[next[k]]$ .....

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/kmp2.png" style="width: 80%"/>
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


---
layout: center
---

# Dynamic Programming

---

# Dynamic Programming

<br/>




<!--

Patterns: brute-force, hashing, devide-and-conquer, recursion, ...

-->

---
layout: center
---

# Graph

---

# Graph

- Implement Graph ADT using different internal representation

- Learn Graph associated algorithms

- How Graph can be used to solve a wide variety of problems


<pre class="norm">

- trees are sub-set of graphs

- graph can model many things in real world such as roads, airline routes, social media connections, etc.

</pre>
---

# Graph Terminology

<mdi-timer-sand />

TBD

---

# Depth-First Search (DFS)

<mdi-timer-sand />

TBD

---

# Breadth-First Search (BFS)

<mdi-timer-sand />

TBD

---

# Dijkstra's Shortest Path

<mdi-timer-sand />

TBD

---

# Min-Spanning Tree (MST)

<mdi-timer-sand />

TBD

---

# Prim-Jarnik Algorithm

<mdi-timer-sand />

TBD

---

# Kruskal's Algorithm

<mdi-timer-sand />

TBD

---
layout: center
---

# Red Black Tree

---

# Red Black Tree

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

<mdi-timer-sand />

TBD

---

# Lab 2

<mdi-timer-sand />

TBD

---

# Lab 3

<mdi-timer-sand />

TBD

---

# Lab 4

<mdi-timer-sand />

TBD

---

# Lab 5

<mdi-timer-sand />

TBD

---

# Lab 6

<br/>

TMA review