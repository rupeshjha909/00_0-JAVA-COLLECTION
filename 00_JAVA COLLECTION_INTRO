# Java Collection Framework - Complete Guide

## Overview
The Java Collection Framework is a unified architecture for representing and manipulating collections. 
It provides a set of interfaces, implementations, and algorithms to work with groups of objects.

## Collection Framework Hierarchy

```
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
```

## Detailed Explanation of Each Interface

### 1. Iterable Interface
**Purpose**: The root interface that allows an object to be the target of the "for-each loop" statement.

**Key Methods**:
- `iterator()`: Returns an iterator over elements
- `forEach(Consumer<? super T> action)`: Performs action for each element
- `spliterator()`: Creates a Spliterator over elements

**Characteristics**:
- Foundation for all collection types
- Enables enhanced for-loop
- Provides default methods for iteration

### 2. Collection Interface
**Purpose**: The root interface in the collection hierarchy. Represents a group of objects known as elements.

**Key Methods**:
- `add(E e)`: Adds an element
- `remove(Object o)`: Removes an element
- `contains(Object o)`: Checks if element exists
- `size()`: Returns number of elements
- `isEmpty()`: Checks if collection is empty
- `clear()`: Removes all elements
- `toArray()`: Converts to array

**Characteristics**:
- No direct implementations
- Defines common operations for all collections
- Supports bulk operations

### 3. List Interface
**Purpose**: An ordered collection (sequence) that allows duplicate elements and positional access.

**Key Methods** (in addition to Collection):
- `get(int index)`: Gets element at position
- `set(int index, E element)`: Sets element at position
- `add(int index, E element)`: Adds element at position
- `remove(int index)`: Removes element at position
- `indexOf(Object o)`: Returns first occurrence index
- `lastIndexOf(Object o)`: Returns last occurrence index
- `subList(int fromIndex, int toIndex)`: Returns view of portion

**Characteristics**:
- Ordered collection
- Allows duplicates
- Index-based access
- Supports range operations

**Implementations**:

#### ArrayList
- **Internal Structure**: Dynamic array
- **Access Time**: O(1) for random access
- **Insertion/Deletion**: O(n) for middle operations
- **Memory**: Contiguous memory allocation
- **Use Cases**: Frequent random access, less frequent insertions/deletions

#### LinkedList
- **Internal Structure**: Doubly linked list
- **Access Time**: O(n) for random access
- **Insertion/Deletion**: O(1) for known position
- **Memory**: Non-contiguous memory allocation
- **Use Cases**: Frequent insertions/deletions, sequential access

#### Vector
- **Internal Structure**: Dynamic array (synchronized)
- **Access Time**: O(1) for random access
- **Thread Safety**: Synchronized (thread-safe)
- **Performance**: Slower than ArrayList due to synchronization
- **Use Cases**: Multi-threaded environments (legacy)

#### Stack
- **Internal Structure**: Extends Vector
- **Behavior**: LIFO (Last In, First Out)
- **Key Methods**: `push()`, `pop()`, `peek()`
- **Use Cases**: Expression evaluation, undo operations

### 4. Set Interface
**Purpose**: A collection that contains no duplicate elements. Models mathematical set abstraction.

**Key Methods** (in addition to Collection):
- `add(E e)`: Adds element (returns false if duplicate)
- No index-based methods
- Set-specific operations: `union`, `intersection`, `difference`

**Characteristics**:
- No duplicate elements
- No positional access
- Mathematical set operations
- Equality based on content

**Implementations**:

#### HashSet
- **Internal Structure**: Hash table
- **Ordering**: No guaranteed order
- **Performance**: O(1) average for add, remove, contains
- **Null Values**: Allows one null element
- **Use Cases**: General-purpose set, fast lookups

#### LinkedHashSet
- **Internal Structure**: Hash table + linked list
- **Ordering**: Insertion order maintained
- **Performance**: Slightly slower than HashSet
- **Use Cases**: When insertion order matters

#### TreeSet
- **Internal Structure**: Red-black tree
- **Ordering**: Natural ordering or custom comparator
- **Performance**: O(log n) for all operations
- **Use Cases**: When sorted order is required

### 5. Queue Interface
**Purpose**: A collection designed for holding elements prior to processing. Typically FIFO (First In, First Out).

**Key Methods**:
- `offer(E e)`: Adds element (returns false if full)
- `poll()`: Retrieves and removes head
- `peek()`: Retrieves but doesn't remove head
- `remove()`: Retrieves and removes head (throws exception if empty)
- `element()`: Retrieves head (throws exception if empty)

**Characteristics**:
- FIFO behavior (typically)
- Head and tail operations
- Capacity restrictions possible
- Priority-based ordering possible

**Implementations**:

#### PriorityQueue
- **Internal Structure**: Binary heap
- **Ordering**: Natural ordering or custom comparator
- **Performance**: O(log n) for insertion/deletion
- **Use Cases**: Task scheduling, priority-based processing

#### ArrayDeque
- **Internal Structure**: Resizable array
- **Behavior**: Double-ended queue
- **Performance**: O(1) for both ends
- **Use Cases**: Stack and queue operations

### 6. Map Interface
**Purpose**: An object that maps keys to values. Cannot contain duplicate keys; each key maps to at most one value.

**Key Methods**:
- `put(K key, V value)`: Associates value with key
- `get(Object key)`: Returns value for key
- `remove(Object key)`: Removes mapping for key
- `containsKey(Object key)`: Checks if key exists
- `containsValue(Object value)`: Checks if value exists
- `keySet()`: Returns set of keys
- `values()`: Returns collection of values
- `entrySet()`: Returns set of key-value pairs

**Characteristics**:
- Key-value pairs
- No duplicate keys
- Not part of Collection hierarchy
- Three collection views: keys, values, entries

**Implementations**:

#### HashMap
- **Internal Structure**: Hash table
- **Ordering**: No guaranteed order
- **Performance**: O(1) average for get, put, remove
- **Null Values**: Allows one null key, multiple null values
- **Use Cases**: General-purpose map, fast lookups

#### LinkedHashMap
- **Internal Structure**: Hash table + linked list
- **Ordering**: Insertion order or access order
- **Performance**: Slightly slower than HashMap
- **Use Cases**: When insertion/access order matters

#### TreeMap
- **Internal Structure**: Red-black tree
- **Ordering**: Natural ordering or custom comparator
- **Performance**: O(log n) for all operations
- **Use Cases**: When sorted order is required

#### Hashtable
- **Internal Structure**: Hash table (legacy)
- **Thread Safety**: Synchronized
- **Null Values**: No null keys or values allowed
- **Use Cases**: Legacy code, multi-threaded environments

## Performance Comparison

| Collection | Access | Search | Insertion | Deletion | Space |
|------------|--------|--------|-----------|----------|-------|
| ArrayList | O(1) | O(n) | O(n) | O(n) | O(n) |
| LinkedList | O(n) | O(n) | O(1) | O(1) | O(n) |
| HashSet | N/A | O(1) | O(1) | O(1) | O(n) |
| TreeSet | N/A | O(log n) | O(log n) | O(log n) | O(n) |
| HashMap | O(1) | O(1) | O(1) | O(1) | O(n) |
| TreeMap | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |

## When to Use Which Collection

### Use ArrayList when:
- You need random access to elements
- You have more reads than writes
- Memory usage is a concern
- You don't need thread safety

### Use LinkedList when:
- You frequently insert/delete at the beginning or middle
- You don't need random access
- You're implementing stacks or queues

### Use HashSet when:
- You need fast lookups
- Order doesn't matter
- You want to eliminate duplicates
- You don't need thread safety

### Use TreeSet when:
- You need sorted order
- You need range operations
- You can accept O(log n) performance

### Use HashMap when:
- You need fast key-value lookups
- Order doesn't matter
- You don't need thread safety

### Use TreeMap when:
- You need sorted keys
- You need range operations on keys
- You can accept O(log n) performance

## Best Practices

1. **Choose the right collection**: Consider your access patterns and requirements
2. **Use generics**: Always specify type parameters
3. **Prefer interfaces**: Declare variables with interface types
4. **Consider thread safety**: Use concurrent collections for multi-threaded code
5. **Initialize with capacity**: If you know the size, specify initial capacity
6. **Use enhanced for-loop**: Prefer for-each over traditional loops
7. **Avoid raw types**: Don't use raw collection types

## Common Pitfalls

1. **Modifying collections during iteration**: Use Iterator.remove() or collect to new collection
2. **Using == instead of equals()**: Collections use equals() for comparison
3. **Not implementing hashCode()**: Required for HashMap and HashSet
4. **Using Vector/Stack**: Prefer ArrayList and ArrayDeque
5. **Not considering thread safety**: Use concurrent collections for multi-threading

This comprehensive guide covers the Java Collection Framework with detailed explanations, performance characteristics, and practical usage guidelines.
