package Practice.JavaPractive;

import java.util.*;
import java.util.stream.Collectors;

/**
 * Comprehensive examples of Collections and Comparators for interview preparation
 * Organized by priority: HIGH, MEDIUM, LOW
 */
public class CollectionsVsComparatorsExamples {
    
    public static void main(String[] args) {
        System.out.println("=== COLLECTIONS vs COMPARATORS - INTERVIEW EXAMPLES ===\n");
        
        // HIGH PRIORITY - Most Asked in Interviews
        demonstrateHighPriorityMethods();
        
        // MEDIUM PRIORITY - Frequently Asked
        demonstrateMediumPriorityMethods();
        
        // LOW PRIORITY - Good to Know
        demonstrateLowPriorityMethods();
        
        // Interview Scenarios
        demonstrateInterviewScenarios();
        
        // Common Interview Questions
        demonstrateCommonQuestions();
    }
    
    /**
     * 🔥 HIGH PRIORITY - Most Asked in Interviews
     */
    public static void demonstrateHighPriorityMethods() {
        System.out.println("🔥 HIGH PRIORITY - MOST ASKED IN INTERVIEWS");
        System.out.println("=============================================");
        
        // 1. Collections.sort() - The Most Important Method
        System.out.println("\n1. Collections.sort() - Basic Sorting");
        System.out.println("--------------------------------------");
        
        List<String> names = Arrays.asList("John", "Alice", "Bob", "Charlie");
        System.out.println("Original: " + names);
        
        // Natural ordering
        Collections.sort(names);
        System.out.println("Sorted (natural): " + names);
        
        // Custom ordering - reverse
        Collections.sort(names, Collections.reverseOrder());
        System.out.println("Sorted (reverse): " + names);
        
        // 2. Comparator Interface - Core Concept
        System.out.println("\n2. Comparator Interface - Lambda & Method References");
        System.out.println("----------------------------------------------------");
        
        List<Person> people = Arrays.asList(
            new Person("Alice", 25),
            new Person("Bob", 30),
            new Person("Charlie", 20)
        );
        
        // Lambda expression
        Collections.sort(people, (p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()));
        System.out.println("Sorted by age (lambda): " + people);
        
        // Method reference
        Collections.sort(people, Comparator.comparing(Person::getName));
        System.out.println("Sorted by name (method ref): " + people);
        
        // 3. Comparable vs Comparator
        System.out.println("\n3. Comparable vs Comparator");
        System.out.println("----------------------------");
        
        List<Student> students = Arrays.asList(
            new Student("John", 85),
            new Student("Alice", 92),
            new Student("Bob", 78)
        );
        
        // Using Comparable (natural ordering)
        Collections.sort(students);
        System.out.println("Sorted by Comparable: " + students);
        
        // Using Comparator (external ordering)
        Collections.sort(students, Comparator.comparing(Student::getGrade));
        System.out.println("Sorted by Comparator: " + students);
        
        // 4. Collections.reverse() and Collections.reverseOrder()
        System.out.println("\n4. Collections.reverse() vs Collections.reverseOrder()");
        System.out.println("-------------------------------------------------------");
        
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        System.out.println("Original: " + numbers);
        
        // reverse() - modifies original list
        Collections.reverse(numbers);
        System.out.println("After reverse(): " + numbers);
        
        // reverseOrder() - returns comparator
        List<Integer> numbers2 = Arrays.asList(1, 2, 3, 4, 5);
        Collections.sort(numbers2, Collections.reverseOrder());
        System.out.println("After reverseOrder(): " + numbers2);
        
        // 5. Collections.binarySearch()
        System.out.println("\n5. Collections.binarySearch()");
        System.out.println("-----------------------------");
        
        List<Integer> sortedList = Arrays.asList(1, 3, 5, 7, 9, 11, 13);
        System.out.println("Sorted list: " + sortedList);
        
        int index = Collections.binarySearch(sortedList, 7);
        System.out.println("Index of 7: " + index);
        
        int notFound = Collections.binarySearch(sortedList, 6);
        System.out.println("Index of 6 (not found): " + notFound);
        System.out.println("Insertion point: " + (-notFound - 1));
    }
    
    /**
     * ⚡ MEDIUM PRIORITY - Frequently Asked
     */
    public static void demonstrateMediumPriorityMethods() {
        System.out.println("\n\n⚡ MEDIUM PRIORITY - FREQUENTLY ASKED");
        System.out.println("======================================");
        
        // 6. Collections.shuffle()
        System.out.println("\n6. Collections.shuffle()");
        System.out.println("------------------------");
        
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        System.out.println("Original: " + numbers);
        
        Collections.shuffle(numbers);
        System.out.println("Shuffled: " + numbers);
        
        // 7. Collections.max() and Collections.min()
        System.out.println("\n7. Collections.max() and Collections.min()");
        System.out.println("-------------------------------------------");
        
        List<Integer> numbers2 = Arrays.asList(3, 1, 4, 1, 5, 9, 2, 6);
        System.out.println("List: " + numbers2);
        
        Integer max = Collections.max(numbers2);
        Integer min = Collections.min(numbers2);
        System.out.println("Max: " + max + ", Min: " + min);
        
        // With custom comparator
        List<String> words = Arrays.asList("apple", "banana", "cherry");
        String longest = Collections.max(words, Comparator.comparing(String::length));
        System.out.println("Longest word: " + longest);
        
        // 8. Collections.frequency()
        System.out.println("\n8. Collections.frequency()");
        System.out.println("--------------------------");
        
        List<String> words2 = Arrays.asList("apple", "banana", "apple", "cherry", "apple");
        int appleCount = Collections.frequency(words2, "apple");
        System.out.println("Apple appears " + appleCount + " times");
        
        // 9. Collections.copy() and Collections.fill()
        System.out.println("\n9. Collections.copy() and Collections.fill()");
        System.out.println("---------------------------------------------");
        
        List<String> source = Arrays.asList("A", "B", "C");
        List<String> destination = new ArrayList<>(Arrays.asList("X", "Y", "Z", "W"));
        
        System.out.println("Source: " + source);
        System.out.println("Destination before copy: " + destination);
        
        Collections.copy(destination, source);
        System.out.println("Destination after copy: " + destination);
        
        Collections.fill(destination, "FILL");
        System.out.println("Destination after fill: " + destination);
        
        // 10. Collections.synchronizedList()
        System.out.println("\n10. Collections.synchronizedList()");
        System.out.println("----------------------------------");
        
        List<String> list = new ArrayList<>();
        List<String> syncList = Collections.synchronizedList(list);
        
        // Thread-safe operations
        synchronized(syncList) {
            syncList.add("thread-safe");
            syncList.add("operation");
        }
        System.out.println("Synchronized list: " + syncList);
    }
    
    /**
     * 📚 LOW PRIORITY - Good to Know
     */
    public static void demonstrateLowPriorityMethods() {
        System.out.println("\n\n📚 LOW PRIORITY - GOOD TO KNOW");
        System.out.println("===============================");
        
        // 11. Collections.rotate()
        System.out.println("\n11. Collections.rotate()");
        System.out.println("------------------------");
        
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        System.out.println("Original: " + numbers);
        
        Collections.rotate(numbers, 2);
        System.out.println("Rotated by 2: " + numbers);
        
        // 12. Collections.swap()
        System.out.println("\n12. Collections.swap()");
        System.out.println("----------------------");
        
        List<String> list = Arrays.asList("A", "B", "C", "D");
        System.out.println("Original: " + list);
        
        Collections.swap(list, 0, 3);
        System.out.println("After swap(0, 3): " + list);
        
        // 13. Collections.addAll()
        System.out.println("\n13. Collections.addAll()");
        System.out.println("------------------------");
        
        List<String> list2 = new ArrayList<>();
        Collections.addAll(list2, "A", "B", "C");
        System.out.println("After addAll: " + list2);
        
        // 14. Collections.disjoint()
        System.out.println("\n14. Collections.disjoint()");
        System.out.println("--------------------------");
        
        List<String> list3 = Arrays.asList("A", "B", "C");
        List<String> list4 = Arrays.asList("D", "E", "F");
        List<String> list5 = Arrays.asList("A", "D", "G");
        
        boolean disjoint1 = Collections.disjoint(list3, list4);
        boolean disjoint2 = Collections.disjoint(list3, list5);
        
        System.out.println("list3 and list4 disjoint: " + disjoint1);
        System.out.println("list3 and list5 disjoint: " + disjoint2);
        
        // 15. Collections.nCopies()
        System.out.println("\n15. Collections.nCopies()");
        System.out.println("-------------------------");
        
        List<String> copies = Collections.nCopies(3, "Hello");
        System.out.println("nCopies(3, 'Hello'): " + copies);
    }
    
    /**
     * 🎯 Interview-Specific Scenarios
     */
    public static void demonstrateInterviewScenarios() {
        System.out.println("\n\n🎯 INTERVIEW-SPECIFIC SCENARIOS");
        System.out.println("=================================");
        
        // Scenario 1: Sort Employee by Multiple Criteria
        System.out.println("\nScenario 1: Sort Employee by Multiple Criteria");
        System.out.println("------------------------------------------------");
        
        List<Employee> employees = Arrays.asList(
            new Employee("John", 25, 50000),
            new Employee("Alice", 30, 60000),
            new Employee("Bob", 25, 55000),
            new Employee("Charlie", 30, 55000)
        );
        
        // Sort by salary (descending), then by name (ascending)
        Collections.sort(employees, Comparator
            .comparing(Employee::getSalary, Comparator.reverseOrder())
            .thenComparing(Employee::getName)
        );
        
        System.out.println("Sorted by salary (desc), then name (asc):");
        employees.forEach(System.out::println);
        
        // Scenario 2: Custom Sorting for Complex Objects
        System.out.println("\nScenario 2: Custom Sorting for Complex Objects");
        System.out.println("-----------------------------------------------");
        
        List<String> words = Arrays.asList("apple", "pie", "banana", "cake", "zebra");
        
        // Sort by string length, then alphabetically
        Collections.sort(words, Comparator
            .comparing(String::length)
            .thenComparing(Comparator.naturalOrder())
        );
        
        System.out.println("Sorted by length, then alphabetically: " + words);
        
        // Scenario 3: Null-Safe Sorting
        System.out.println("\nScenario 3: Null-Safe Sorting");
        System.out.println("------------------------------");
        
        List<String> listWithNulls = Arrays.asList("apple", null, "banana", null, "cherry");
        System.out.println("Original with nulls: " + listWithNulls);
        
        Collections.sort(listWithNulls, Comparator.nullsLast(Comparator.naturalOrder()));
        System.out.println("Sorted with nulls last: " + listWithNulls);
        
        Collections.sort(listWithNulls, Comparator.nullsFirst(Comparator.naturalOrder()));
        System.out.println("Sorted with nulls first: " + listWithNulls);
    }
    
    /**
     * 💡 Common Interview Questions
     */
    public static void demonstrateCommonQuestions() {
        System.out.println("\n\n💡 COMMON INTERVIEW QUESTIONS");
        System.out.println("==============================");
        
        // Q1: Sort in descending order
        System.out.println("\nQ1: How to sort in descending order?");
        System.out.println("-------------------------------------");
        
        List<Integer> numbers = Arrays.asList(3, 1, 4, 1, 5, 9, 2, 6);
        System.out.println("Original: " + numbers);
        
        // Method 1: Collections.reverseOrder()
        List<Integer> method1 = new ArrayList<>(numbers);
        Collections.sort(method1, Collections.reverseOrder());
        System.out.println("Method 1 (reverseOrder): " + method1);
        
        // Method 2: Lambda with reversed()
        List<Integer> method2 = new ArrayList<>(numbers);
        Collections.sort(method2, Comparator.naturalOrder().reversed());
        System.out.println("Method 2 (reversed): " + method2);
        
        // Method 3: Custom comparator
        List<Integer> method3 = new ArrayList<>(numbers);
        Collections.sort(method3, (a, b) -> b.compareTo(a));
        System.out.println("Method 3 (custom): " + method3);
        
        // Q2: Binary search on unsorted list
        System.out.println("\nQ2: What happens with binarySearch on unsorted list?");
        System.out.println("---------------------------------------------------");
        
        List<Integer> unsorted = Arrays.asList(5, 2, 8, 1, 9);
        System.out.println("Unsorted list: " + unsorted);
        
        int result = Collections.binarySearch(unsorted, 8);
        System.out.println("Binary search for 8: " + result + " (unpredictable!)");
        
        // Correct way
        List<Integer> sorted = new ArrayList<>(unsorted);
        Collections.sort(sorted);
        System.out.println("Sorted list: " + sorted);
        
        int correctResult = Collections.binarySearch(sorted, 8);
        System.out.println("Binary search for 8 (correct): " + correctResult);
        
        // Q3: Performance demonstration
        System.out.println("\nQ3: Performance of Collections.sort()");
        System.out.println("-------------------------------------");
        
        List<Integer> largeList = new ArrayList<>();
        for (int i = 1000; i >= 1; i--) {
            largeList.add(i);
        }
        
        long startTime = System.nanoTime();
        Collections.sort(largeList);
        long endTime = System.nanoTime();
        
        System.out.println("Sorted " + largeList.size() + " elements in " + 
                         (endTime - startTime) / 1_000_000 + " ms");
        System.out.println("Time complexity: O(n log n)");
    }
    
    // Helper classes for examples
    static class Person {
        private String name;
        private int age;
        
        public Person(String name, int age) {
            this.name = name;
            this.age = age;
        }
        
        public String getName() { return name; }
        public int getAge() { return age; }
        
        @Override
        public String toString() {
            return name + "(" + age + ")";
        }
    }
    
    static class Student implements Comparable<Student> {
        private String name;
        private int grade;
        
        public Student(String name, int grade) {
            this.name = name;
            this.grade = grade;
        }
        
        public String getName() { return name; }
        public int getGrade() { return grade; }
        
        @Override
        public int compareTo(Student other) {
            return this.name.compareTo(other.name);
        }
        
        @Override
        public String toString() {
            return name + "(" + grade + ")";
        }
    }
    
    static class Employee {
        private String name;
        private int age;
        private double salary;
        
        public Employee(String name, int age, double salary) {
            this.name = name;
            this.age = age;
            this.salary = salary;
        }
        
        public String getName() { return name; }
        public int getAge() { return age; }
        public double getSalary() { return salary; }
        
        @Override
        public String toString() {
            return name + "(" + age + ", $" + salary + ")";
        }
    }
}
