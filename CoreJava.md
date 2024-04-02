1. 	What is Java?
A. 	Java is an object oriented programming language.
    Supports Inheritance, Polymorphism, Encapsulation and Abstraction. Does not support multiple inheritance.
    It is a statically typed language (type of the variable should be known at compile time or else compiler will guess the type for you).

2.	What is the Object class in Java?
A.	The super class of every class.
    In Java, a class can only extend 1 class as multiple inheritance is not supported by Java.
    Internally, every class extend Object class in Java.

3.	Can you site methods from Object class?
A.	toString(), equals() and hashCode()
    getClass(), wait(), notify(), notifyAll() -> used in concurrent programming and never use until you really need it
    finalize() is deprecated
    clone()

4.	Differences between String and char[](character array)
A.	String is a class with many useful methods that char[] has not
    String is non modifiable
    Size of an array is fixed and once initialized we cannot change it but can replace the elements
    String uses "equals" method for comparison
    Use Arrays.equals() method for comparing arrays and use Arrays.toString() method to print an array properly
    We can create a string by using below method:
    char[] letters = {'h', 'e', 'l', 'l', 'o'};
    String str = new String(letters);

5. 	Summing an array of ints
A.	a. iterate over an array and add it one by one
    b. use stream over an array as below:
    int[] ints = {2, 1, 3};
    int sum = Arrays.stream(ints).sum();
    there are also other useful methods like average, min, max, etc.

6.	What is the JVM?
A.	JVM: Java Virtual Machine
    JVM is responsible to run the application. Also it manages Garbage Collector(GC), optimizes the code using Just In-Time Compiler(JIT)
    JVM makes sure that no undesired code sneak inside the application environment
    HotSpot is the JVM from Open JDK

7.	How can you sort an array?
A.	Arrays.sort() method sorts an array
    Learn sorting algorithms: QuickSort, HeapSort, TimSort

8.	The main characteristics of the String class
A.	String class is non-modifiable
    There is no way to modify an instance of a String class
    For ex. using str.toUpperCase() method creates a new String
    Use StringBuilder for modifiable strings (which internally handles using char[]). Always use "+" for string concatenation
    Use StringBuffer for modifiable strings in multi-threading environment

9.	Difference between == and equals()
A.	== compares references and equals() is a method
    For ex. comparing strings using "==" may give you false
    == is for int, long, chars. but not for float and double. use Math.abs for float, double before using ==
    equals() is for objects

10.	Relation between equals() and hashCode()
A.	Two objects are equals() then they must have the same hashCode()
    If you override equals() then you must also override hashCode()
    Java says, 2 objects are equal then they must have the same hashCode but vise versa is not correct (means objects having same hashCode might not be equal)

11.	Duplicating an Array
A.	Arrays.copyOf() and System.arrayCopy()
    Don't use array.clone() as it not good performance wise
    Both Arrays.copyOf() and System.arrayCopy() needs destination array in which they will copy the source array.
    Arrays.copyOf() will truncate if is smaller or span if it is larger  
    System.arrayCopy() is a richer API which offers to copy "some" portion of array to the destination array
    Arrays.copyOf() internally uses System.arrayCopy() so, you can use any as per your convenience

12.	Reversing a String
A.	Create a StringBuilder and call reverse() method on it and then call toString() method
    String class is a non-modifiable and cannot change the string object(it will create a new object if you try to reverse)
    StringBuilder's reverse() method internally loops over the letters of the string and reverse it as StringBuilder is a modifiable class

13. Functional Interface
A.	An interface with only one abstract method
    Lambdas implement functional interfaces (because, Java is a statically typed language so all varibles must have a type which needs to be known at compile time)
    Functional interface contains any number of default and static methods
    Functional interface can have any method of Object class as an abstract class
    You may use @FunctionalInterface annotation to verify its qualifications

14.	Overloading and Overriding
A.	Overriding has to do with inheritance, overloading does not
    Overloading: same methods with different parameters
    Overriding: redefinition of the method from a super(parent) class in a sub(child) class
    Overloading: Compiler decides to call which method at compile time (called early binding)
    Overriding: Compiler cannot resolve it and it is resolved at run time (called late binding)
    "Final" keyword can prevent overriding but you cannot prevent different overloads

15.	What is a Map?
A.	An object which maps keys to values.
    Map is an interface from collections framework and its canonical implementation is Hashmap.
    No duplicate key and you cannot map multiple values with a single key. A value can be a list to achieve this.
    Only use non-modifiable keys (small strings or prefer double over integers).
    Hashmap class supports null key and null values but don't use it.

16.	What is an ArrayList?
A.	An implementation of List interface backed by an Array.
    ArrayList is sometimes called a dynamic array because when an internal array of an arraylist becomes full, it can grow transparently and dynamically. Be careful as these arrays can only grow, it never shrinks. It can eat up large memory so be cautious.
    Prefer ArrayList over LinkedList as LinkedList are good for stack.

17.	What is finally?
A.	Finally marks a block after a try block which is executed always after the try block exits.
    The finally block is the key tool to properly clean up the resources that are not auto closable.

18. How to make a class immutable?
A.	Use Records
    Final fields, final class, defensive copy (for ex. lists, maps, sets, etc.) of modifiable objects in the constructor and the accessors.
    String, Integer, Long, etc all wrapper classes are immutable(non-modifiable).

19.	String vs. StringBuilder vs. StringBuffer
A.	String is non-modifiable. StringBuilder is modifiable and StringBuffer is modifiable and thread safe.
    Prefer String.
    For certain string manipulation operations, use StringBuilder(for reverse() and insert() a character in between of a string).
    After Java 9, for string concatination, "+" operation has been modified and optimized.
    To join strings from an array or list, consider String.join(), StringJoiner class and Collectors.joining()

20.	How to implement a Singleton?
A.	Use an enum with a single value.
    It is super simple, thread-safe, guaranteed bug free at JVM level and recommended by best experts(Effective Java by Joshua Bloch).
    This enum based pattern is used at many places is JDK.

21.	What is a static method?
A.	A method declared with static keyword.
    A method that you can invoke without creating the class object. Can be invoked with the class name.
    Static method can't invoke non-static methods.
    For ex. Math, Arrays, Collections have only static methods.
    Classes with only static methods are called Factory Classes.

22.	How can you find a character in a String?
A.	You can use indexOf() method.
    indexOf() method has several overloads. It can take a character or a String.
    Can take an index to start from.
    Returns the index, or -1 if not found.

23.	Method References
A.	Another way to write lambda expression.
    4 kinds of method reference as below:
    a. static method references ex. Math::abs, Integer::max
    b. bound method references ex. System.out::println
    c. unbound method references ex.
    d. constructor method references ex. ArrayList::new
    Method references are to improve the readability. It can be used as per your convenience.

24.	Default methods
A. 	It is a regular method written in an interface.
    Java 7: no default methods.
    Java 8: default methods must be public.
    Java 9: default methods can be private.

25.	What is a JIT?
A.	JIT: Just In Time compiler.
    Class file contains bytecode.
    This bytecode is first interpreted by JVM, which is super slow.
    JIT optimize the bytecode to make fast compilation.

26.	What kind of method can you override?
A.	Instance methods.
    Static methods cannot be overridden.
    Instance method can be overridden unless they are not private, non-final and their class are extended.
    To stop a class being extended, make it final and but you can also make no args constructor as private.

27. What is the signature of a method?
A.	The method name and the method parameters.
    The return type is not part of the signature. Nor the exceptions declaration.

28. What is a marker interface?
A.	An interface with no method that is just here to mark a class.
    Ex. Serializable interface allows the instance of a class to be serialized.
    Ex. Cloneable interface allows the instance of a class to be clonned.

29.	Difference between Collection and Set?
A.	No duplicate in Set and Set extends Collection.
    Collection and Set are interfaces from Collections framework.
    Set extends Collection.
    HashSet implements Set and has implementation of contains() which works superfast.

30.	How does finalize() work?
A.	Deprecated in Java 9.
    finalize() was used to remove that particular object by Garbage Collector.

31. Java 8 new features?
A.	Lambda expressions.
    Updates in Collections(re-written).
    Stream API.
    CompletableFuture API(asynchronous programming model).
    Java 8 was introduced in 2014.

32. Do streams and collections have methods in common?
A.	Yes and No. They do have 1 method which is called and do take same parameter.
    forEach(Consumer) method is used on both stream interface and iterable interface.
    They do the same but not in the same way.
    You can use:
    strings.forEach(System.out::println); -> this avoids the creation of stream object
    strings.stream().forEach(System.out::println);

33. How can you tell that the string is an Anagram of another string?
A.	Sort the letters and compare them. TC = O(N*N)
    Smarter way: map each letter to a prime number. TC = O(N)
    ex. C -> 5, A -> 2, T -> 71 which gives 5 * 2 * 71 = 710
    ex. A -> 2, C -> 5, T -> 71 which gives 2 * 5 * 71 = 710

34.	On what kind of source do you build a stream?
A.	There are many.
    Collections.
    Arrays.
    Lines of a text files.
    Elements of String splitted by regular expressions.
    And many more.

35. What is a groupingBy()?
A.	A collector
    ex. cities.stream().collect(Collectors.groupingBy(City::state));
    Maps each element of stream to a key and binds a list to that key.
    Map<State, List<City>>
    It is called down stream collectors.

36.	Difference between FIFO and LIFO?
A.	FIFO = queue and LIFO = stack.
    2 interfaces to model FIFO and LIFO.
    Queue models FIFO.
    Deque models LIFO.
    Non-concurrent: ArrayDeque.
    ConcurrentLinkedQueue models FIFO thread-safe.
    ConcurrentLinkedDeque models LIFO thread-safe.
    Stack and Vector are deprecated a long ago, so don't use it.

37.	What is the GoF?
A.	The nick name of: Gang of Four
    Design Patterns book which contains 23 design patterns.
    Creational: builder, singleton, factory
    Structural: adapter, proxy, decorator, facade
    Behavioral: iterator, strategy, visitor, template method

38.	How can you create a Comparator?
A.	Just use the factory method of the comparator interface.
    ex. var userComparator = Comparator.comparing(User::lastName).thenComparing(User::firstName).reversed();
    ex. var userComparatorWithNulls = Comparator.nullsLast(userComparator);
    Comparator interface has bunch of factory methods to create comparators that compares using one or other fields.

39.	Functional Interfaces before Java 8?
A.	Runnable, Comparator, Iterable, Executor, Comparable.
    Functional Interface is backward compatible and @FunctionalInterface annotation is optional.

40.	How to open a file for writing text?
A.	There is a factory method in files class.
    2 patterns from java.io and java.nio. Use java.nio.
    ex. var writer = Files.newBufferedWriter(path,
                                             StandardCharsets.ISO_8859_2,
                                             StandardOpenOption.CREATE,
                                             StandardOpenOption.APPEND);

41.	Difference between sorted and ordered Collections.
A.	Sorted = from the smallest to the largest.
    Ordered = from the first added to the last(you can access using index).
    Ordered = List, ArrayList
    Sorted = SortedSet, TreeSet

42.	How could you open a file for reading binary data?
A.	There a factory method in the files class.
    ex. Files.newInputStream(path);

43.	How can you print an array on the console?
A.	Arrays.toString(array);
    Or iterate over the elements of an array.
    Or stream API
    ex. var result = Arrays.stream(array).map(Object::toString).collect(joining(",","{","}"));

44.	How does a SortedSet work?
A.	It is a set which keeps its element sorted.
    Set: It doesn't have a duplicate.
    The elements must be Comparable. If not, you can give a Comparator.
    The default implementation is the TreeSet which implements a Red Black tree.

45.	What pattern has been used to create the Java I/O API?
A.	The decorator pattern.
    The decorator pattern is the structural pattern (which is a wrapper).
    Adds features and modify behavior.

46.	Categories of Design Patterns?
A.	Creational, Structural, Behavioral

47.	Count how many times a letter appears in a String?
A.	Need to iterate over a String.
    Use the stream API
    ex. long count = sentence.chars().filter(c -> c == 'char').count();
    ex. sentence.chars().forEach(e -> System.out.println((char) e));

48.	What is a bucket in a Map?
A.	A cell in an array.
    The HashMap class is backed by an array.
    hashCode() method evaluates a hashCode and assign a bucket.
    Several collisions: LinkedList is created to handle the second key-value pair.
    Too many collisions: LinkedList is replaced by Red Black tree.
    When a map is reached to this 75% of utilization, a new hashmap is created and all the elements are copied into it and re-hashing also takes place. To avoid this, choose a map of right size.

49.	What does Synchronized mean?
A.	It is a keyword that prevents more than one thread to execute the given block of code at the same time.
    Synchronization is related with concurrent programming.
    Synchronized can be an independent block or a block inside a method.
    Works with a key, which allows to execute the block.

50.	Difference between a Stream and a Collection?
A.	A collection contains objects. A stream is empty.
    A collection carries objects while a stream is most of the time empty and it connects to a source of data and processes objects lazily.
    If using distinct and sorted on a stream, then it will not be an empty stream.

51.	What is difference between File and Path?
A.	File is a class and Path is an interface.
    Favor Path over File.

52.	Difference between Checked and Unchecked Exceptions?
A.	Need to write special code to handle checked exceptions not for unchecked exceptions.
    All exceptions extend the Exception class.
    Unchecked = extension of RuntimeException.
    Checked = extension of Exception.
    Errors are unchecked exceptions.

53.	What is a Stream?
A.	An object that implements map / filter / reduce pattern.
    Stream consumes elements from a source and perform operations. It processes data in a pipeline where each element is passed to next step.
    Be careful with parallel streams.

54.	What is a hash code of an object?
A.	An integer that represents an object (A mapping of that object to an integer).
    Used to tell if two objects are equal or not in Hashmap.
    If hash code of two objects are equal than must use equals() method to check the objects are equal or not.
    Use IDE to generate hash code.

55. What is an ExecutorService?
A.	An object to run task in another thread.
    ExecutorService is an interface which is a part of java.util.concurrent added in Java 5.
    You get a Future in return.
    Different ways to create. fixedThreadPool, singleThread, cacheThread, etc.

56. What is an Iterator?
A.	An object to iterate over the elements of a Collection.
    Iterator is an interface having 3 methods:
    hasNext(): says that there are more objects to iterate over
    next(): to get next object
    remove():
    Iterator pattern is pattern from the GoF.

57. What are the four Java I/O base classes?
A.	Reader, Writer, InputStream, OutputStream
    These are four abstract classes for reading and writing characters and binary data. You should not use them directly any more.
    Use the factory methods from Files class.
    new bufferedReader for reading.
    new bufferedWriter for writing.
    new inputStream for reading binary data.
    new outputStream for writing binary data.

58. How many objects can you put in a Collection?
A.	It depends on the implementation you have.
    ArrayList is backed by an array: Integer.MAX_VALUE

59. What is the maximum length of a String in Java?
A.	String is backed by an array, so Integer.MAX_VALUE is the limit.
    In Java 9, String implementation has been changed which is called "Compact String" that reduces memory footprint.

60.	How does a Set knows that it already contains an element?
A.	It uses hashCode() and equals() of that object.
       Set stores the elements in a cell of an array and index of that cell is computed from the hashcode of that object.
       set.contains() is very fast.
       Don't forget to override hashCode() method.
       Don't mutate an object once stored in a set as you will not able to find it again.

61. 