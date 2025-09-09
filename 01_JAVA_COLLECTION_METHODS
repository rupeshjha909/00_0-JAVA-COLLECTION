                    JAVA COLLECTION FRAMEWORK HIERARCHY
                    =====================================

                                    Iterable
                                       |
                                   Collection
                                       |
                    ┌──────────────────┼──────────────────┐
                    |                  |                  |
                   List               Set                Queue
                    |                  |                  |
            ┌───────┼───────┐          |                  |
            |       |       |          |                  |
        ArrayList LinkedList Vector   HashSet         PriorityQueue
            |       |       |          |                  |
        (Random    (Sequential    (Synchronized)    (Heap-based)
         Access)    Access)                          Priority)
            |       |       |          |
            |       |       |       LinkedHashSet
            |       |       |          |
            |       |       |       TreeSet
            |       |       |          |
            |       |       |    (Sorted Set)
            |       |       |
            |       |    Stack
            |       |    (LIFO)
            |       |
            |    CopyOnWriteArrayList
            |    (Thread-safe)
            |
        CopyOnWriteArraySet
        (Thread-safe)

                    Map (Separate from Collection)
                         |
            ┌────────────┼────────────┐
            |            |            |
         HashMap    TreeMap    LinkedHashMap
            |            |            |
        (Hash-based) (Sorted)   (Insertion Order)
            |            |            |
        Hashtable   ConcurrentHashMap
        (Legacy)     (Thread-safe)
            |
        Properties
        (Key-Value pairs)

                    DETAILED INTERFACE TREE
                    =======================

1. ITERABLE (Root Interface)
   ├── iterator()
   ├── forEach()
   └── spliterator()

2. COLLECTION (Extends Iterable)
   ├── Basic Operations
   │   ├── add(E e)
   │   ├── remove(Object o)
   │   ├── contains(Object o)
   │   ├── size()
   │   ├── isEmpty()
   │   └── clear()
   ├── Bulk Operations
   │   ├── addAll(Collection<? extends E> c)
   │   ├── removeAll(Collection<?> c)
   │   ├── retainAll(Collection<?> c)
   │   └── containsAll(Collection<?> c)
   └── Array Operations
       ├── toArray()
       └── toArray(T[] a)

3. LIST (Extends Collection)
   ├── Positional Access
   │   ├── get(int index)
   │   ├── set(int index, E element)
   │   ├── add(int index, E element)
   │   └── remove(int index)
   ├── Search Operations
   │   ├── indexOf(Object o)
   │   └── lastIndexOf(Object o)
   ├── Range Operations
   │   ├── subList(int fromIndex, int toIndex)
   │   └── listIterator()
   └── Implementations
       ├── ArrayList
       │   ├── Dynamic array
       │   ├── O(1) random access
       │   └── O(n) insertion/deletion
       ├── LinkedList
       │   ├── Doubly linked list
       │   ├── O(n) random access
       │   └── O(1) insertion/deletion
       ├── Vector
       │   ├── Synchronized array
       │   ├── Thread-safe
       │   └── Legacy implementation
       └── Stack
           ├── LIFO behavior
           ├── push(), pop(), peek()
           └── Extends Vector

4. SET (Extends Collection)
   ├── Mathematical Set Operations
   │   ├── Union (addAll)
   │   ├── Intersection (retainAll)
   │   └── Difference (removeAll)
   ├── No Duplicate Elements
   ├── No Positional Access
   └── Implementations
       ├── HashSet
       │   ├── Hash table
       │   ├── No ordering
       │   └── O(1) operations
       ├── LinkedHashSet
       │   ├── Hash table + linked list
       │   ├── Insertion order
       │   └── O(1) operations
       └── TreeSet
           ├── Red-black tree
           ├── Sorted order
           └── O(log n) operations

5. QUEUE (Extends Collection)
   ├── FIFO Operations
   │   ├── offer(E e) - Add element
   │   ├── poll() - Remove and return head
   │   ├── peek() - Return head without removing
   │   ├── remove() - Remove head (throws exception)
   │   └── element() - Return head (throws exception)
   ├── Capacity Restrictions
   └── Implementations
       ├── PriorityQueue
       │   ├── Binary heap
       │   ├── Priority-based ordering
       │   └── O(log n) operations
       └── ArrayDeque
           ├── Resizable array
           ├── Double-ended queue
           └── O(1) operations

6. MAP (Separate from Collection)
   ├── Key-Value Pairs
   ├── No Duplicate Keys
   ├── Three Collection Views
   │   ├── keySet() - Set of keys
   │   ├── values() - Collection of values
   │   └── entrySet() - Set of key-value pairs
   └── Implementations
       ├── HashMap
       │   ├── Hash table
       │   ├── No ordering
       │   └── O(1) operations
       ├── LinkedHashMap
       │   ├── Hash table + linked list
       │   ├── Insertion/access order
       │   └── O(1) operations
       ├── TreeMap
       │   ├── Red-black tree
       │   ├── Sorted order
       │   └── O(log n) operations
       ├── Hashtable
       │   ├── Legacy synchronized map
       │   ├── No null keys/values
       │   └── Thread-safe
       └── ConcurrentHashMap
           ├── Thread-safe hash map
           ├── Better performance than Hashtable
           └── Concurrent operations

                    PERFORMANCE SUMMARY
                    ===================

Collection Type    | Access    | Search    | Insertion | Deletion  | Space
-------------------|-----------|-----------|-----------|-----------|-------
ArrayList         | O(1)      | O(n)      | O(n)      | O(n)      | O(n)
LinkedList        | O(n)      | O(n)      | O(1)      | O(1)      | O(n)
HashSet           | N/A       | O(1)      | O(1)      | O(1)      | O(n)
TreeSet           | N/A       | O(log n)  | O(log n)  | O(log n)  | O(n)
HashMap           | O(1)      | O(1)      | O(1)      | O(1)      | O(n)
TreeMap           | O(log n)  | O(log n)  | O(log n)  | O(log n)  | O(n)
PriorityQueue     | N/A       | N/A       | O(log n)  | O(log n)  | O(n)

                    WHEN TO USE WHICH COLLECTION
                    =============================

ARRAYLIST:
✓ Random access to elements
✓ More reads than writes
✓ Memory efficiency important
✗ Frequent insertions/deletions in middle

LINKEDLIST:
✓ Frequent insertions/deletions
✓ Implementing stacks/queues
✓ Sequential access patterns
✗ Random access required

HASHSET:
✓ Fast lookups
✓ Order doesn't matter
✓ Eliminate duplicates
✗ Sorted order needed

TREESET:
✓ Sorted order required
✓ Range operations needed
✓ Can accept O(log n) performance
✗ Maximum performance critical

HASHMAP:
✓ Fast key-value lookups
✓ Order doesn't matter
✓ General-purpose mapping
✗ Sorted keys needed

TREEMAP:
✓ Sorted keys required
✓ Range operations on keys
✓ Can accept O(log n) performance
✗ Maximum performance critical
