# Java Tutorial

## ✅ 1. JVM (Java Virtual Machine)

💡 The engine that runs Java programs.

### What it does:

* Converts bytecode (.class) into machine code
* Ensures platform independence
* Handles memory management, GC, and security

### Key Points:

* Platform-dependent (OS-specific)
* Runs `.class` files, not `.java`

---

## ✅ 2. JRE (Java Runtime Environment)

💡 Required to run Java programs.

### Includes:

* JVM
* Core libraries
* Supporting files

### Does NOT include:

* Java compiler (javac) or development tools

Use case: Running Java applications

---

## ✅ 3. JDK (Java Development Kit)

💡 Required to develop Java programs.

### Includes:

* JRE
* JVM
* Development tools: `javac`, `javadoc`, `jdb`, etc.

Use case: Writing, compiling, and debugging code

---

## 🔁 JDK-JRE-JVM Relationship Diagram

```
JDK
 ├── JRE
 │    ├── JVM
 │    └── Libraries
 └── Tools (javac, javadoc, etc.)
```

### 🔍 Summary Table

| Component | Stands For               | Purpose                | Contains        |
| --------- | ------------------------ | ---------------------- | --------------- |
| JVM       | Java Virtual Machine     | Runs bytecode          | -               |
| JRE       | Java Runtime Environment | Runs Java applications | JVM + Libraries |
| JDK       | Java Development Kit     | Develop Java apps      | JRE + Dev Tools |

---

## ✅ Control Flow of a Java Program

1. You write a `.java` file
2. Compile with `javac` → `.class` file
3. `.class` is passed to JVM
4. JVM interprets or JIT-compiles it
5. Runs as machine code on OS

```
.java → javac → .class → JVM → Machine Code → Run
```

---

## ✅ What is JIT (Just-In-Time Compiler)?

* Part of JVM
* Converts hot bytecode into machine code at runtime

### Benefits:

* Faster performance for long-running apps
* Avoids repeated interpretation

---

## ✅ Basic Java Program Template

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Breakdown:

* `public` – accessible anywhere
* `static` – doesn't require object (Means the method belongs to the class itself, not an object.)
* `void` – returns nothing
* `main` – entry point (Method Name)
* `String[] args` – command-line arguments

---

## ✅ `System.out.println("...");`

* `System` – built-in class
* `out` – static field (PrintStream)
* `println` – prints text + newline

### Example:

```java
System.out.println("Java is fun!");
```

---

## ✅ Java Data Types

### 1. Primitive Data Types

| Type    | Size    | Description                | Example           |
| ------- | ------- | -------------------------- | ----------------- |
| byte    | 1 byte  | -128 to 127                | byte b = 100;     |
| short   | 2 bytes | Whole numbers              | short s = 1000;   |
| int     | 4 bytes | Default integer            | int x = 50000;    |
| long    | 8 bytes | Large integers             | long l = 100000L; |
| float   | 4 bytes | Single-precision float     | float f = 5.75f;  |
| double  | 8 bytes | Double-precision float     | double d = 19.99; |
| char    | 2 bytes | Single character (Unicode) | char c = 'A';     |
| boolean | 1 bit   | true or false              | boolean b = true; |

### 2. Non-Primitive (Reference) Data Types

| Type      | Description                    | Example                        |
| --------- | ------------------------------ | ------------------------------ |
| String    | Sequence of characters         | String name = "John";          |
| Array     | Collection of elements         | int\[] arr = {1,2,3};          |
| Class     | Blueprint for objects          | MyClass obj = new MyClass();   |
| Interface | Contract a class can implement | Runnable r = new MyRunnable(); |
| Enum      | Fixed set of constants         | enum Day { MON, TUE }          |

---

## ✅ Interface as a Data Type

* Interfaces **are** reference types in Java
* Can be used as variable types, return types, and parameters

### Example:

```java
interface Animal {
    void sound();
}
class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }
}
public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound(); // Output: Bark
    }
}
```

---

## ✅ Enum in Java

### Definition:

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}
```

### Usage:

```java
enum Day { MON, TUE, WED, THU, FRI, SAT, SUN }

Day today = Day.SAT;
if (today == Day.SAT || today == Day.SUN) {
    System.out.println("It's weekend!");
} else {
    System.out.println("It's a weekday.");
}
```

### Advanced Enum:

```java
enum Level {
    LOW, MEDIUM, HIGH;
    public void showLevel() {
        System.out.println("Level is: " + this);
    }
}
```

---

## ✅ Type Casting

### 1. Widening (Implicit)

```java
int a = 10;
double b = a; // Output: 10.0
```

### 2. Narrowing (Explicit)

```java
double x = 9.78;
int y = (int) x; // Output: 9
```

### Summary:

| Type      | Description             | Example                         |
| --------- | ----------------------- | ------------------------------- |
| Widening  | Implicit, safe          | int i = 10; double d = i;       |
| Narrowing | Explicit, may lose data | double d = 9.8; int i = (int)d; |

---

## ✅ String & Char Conversion

### String → int

```java
String str = "123";
int num = Integer.parseInt(str);
```

### char → int

```java
char c = 'A';
int code = c; // or (int) c
```

### int → char

```java
int i = 65;
char ch = (char) i; // Output: 'A'
```

---

## ✅ Array to String

### Primitive Arrays:

```java
int[] nums = {1, 2, 3};
System.out.println(Arrays.toString(nums));
```

### String Arrays:

```java
String[] arr = {"Hello", "World"};
System.out.println(String.join(" ", arr));
```

---

## ✅ char to String

```java
char ch = 'A';
String s1 = String.valueOf(ch);
String s2 = ch + "";
String s3 = Character.toString(ch);
```

---

## ✅ Convert Integer to Binary

### Built-in:

```java
int num = 10;
String binary = Integer.toBinaryString(num); // Output: "1010"
```

### Manual:

```java
while (num > 0) {
    binary = (num % 2) + binary;
    num = num / 2;
}
```

### 8-bit Binary:

```java
String binary = String.format("%8s", Integer.toBinaryString(5)).replace(' ', '0');
```

---

## ✅ println() vs printf()

| Feature    | println()               | printf()                      |
| ---------- | ----------------------- | ----------------------------- |
| Purpose    | Simple print w/ newline | Formatted output              |
| Formatting | No                      | Yes (e.g. %d, %s, %f)         |
| Newline    | Adds newline            | Needs `\n` or `%n` explicitly |

### Examples:

```java
System.out.println("Value is: " + a);
System.out.printf("Value is: %d\n", a);
```
## ✅ Java Strings & Their Methods

### 🔹 What is a String in Java?

A `String` is a sequence of characters.

* Strings are **immutable**, meaning once created, they cannot be changed.
* Defined in the `java.lang` package.

---

### 🔹 Declaring Strings

```java
String s1 = "Hello";                    // Using string literal
String s2 = new String("World");       // Using new keyword
```

---

### 🔹 Commonly Used String Methods

| Method                     | Description                                   | Example                                  |
| -------------------------- | --------------------------------------------- | ---------------------------------------- |
| `length()`                 | Returns number of characters                  | `s.length()` → `5`                       |
| `charAt(int index)`        | Character at specific index                   | `s.charAt(1)` → `'e'`                    |
| `substring(beginIndex)`    | Substring from index to end                   | `s.substring(2)` → "llo"                 |
| `substring(beg, end)`      | Substring from begin to end-1                 | `s.substring(0, 2)` → "He"               |
| `equals(String)`           | Compares two strings                          | `s1.equals(s2)`                          |
| `equalsIgnoreCase(String)` | Case-insensitive comparison                   | `s1.equalsIgnoreCase("hello")`           |
| `compareTo(String)`        | Lexicographical comparison                    | `s1.compareTo("Hi")`                     |
| `toLowerCase()`            | Converts string to lowercase                  | `"Java".toLowerCase()` → "java"          |
| `toUpperCase()`            | Converts string to uppercase                  | `"java".toUpperCase()` → "JAVA"          |
| `trim()`                   | Removes leading/trailing spaces               | `" Hello ".trim()` → "Hello"             |
| `contains(String)`         | Checks if string contains substring           | `s.contains("el")` → `true`              |
| `replace(a, b)`            | Replaces characters or substrings             | `s.replace("l", "x")` → "Hexxo"          |
| `split(String)`            | Splits string into array by regex/delimiter   | `"a,b,c".split(",")` → `["a", "b", "c"]` |
| `indexOf(String)`          | Index of first occurrence                     | `s.indexOf("l")` → `2`                   |
| `lastIndexOf(String)`      | Index of last occurrence                      | `s.lastIndexOf("l")` → `3`               |
| `isEmpty()`                | Checks if string is empty                     | `"".isEmpty()` → `true`                  |
| `startsWith(String)`       | Checks if string starts with specified prefix | `s.startsWith("He")` → `true`            |
| `endsWith(String)`         | Checks if string ends with specified suffix   | `s.endsWith("lo")` → `true`              |

---

### 🔹 String Concatenation

```java
String a = "Java";
String b = "Rocks";
String c = a + " " + b;  // Output: Java Rocks
```

---

### 🔹 Using `==` vs `.equals()` for String Comparison

| Operator/Method | Compares            | Returns true if                      | Use Case                                 |
| --------------- | ------------------- | ------------------------------------ | ---------------------------------------- |
| `==`            | References (memory) | Both references point to same object | Use only when comparing memory addresses |
| `.equals()`     | Content             | Actual string contents are equal     | Preferred for string value comparison    |

#### 🔸 Example:

```java
String s1 = "Hello";
String s2 = "Hello";
String s3 = new String("Hello");

System.out.println(s1 == s2);       // true (same literal pool reference)
System.out.println(s1 == s3);       // false (different object)
System.out.println(s1.equals(s3));  // true (same content)
```

✅ Use `.equals()` when comparing values of strings.

---

### 🔹 String Literals vs `new String()`

```java
String s2 = "Hello";                   // String literal
String s3 = new String("Hello");      // Using new keyword
```

* **String literals** are stored in the **String pool** (shared in memory).
* When you use `new`, Java creates a **new object in heap memory**, even if the content is the same.

#### 🔸 Comparison:

```java
String s2 = "Hello";
String s3 = new String("Hello");

System.out.println(s2 == s3);       // false (different memory)
System.out.println(s2.equals(s3));  // true (same content)
```

✅ Prefer string literals unless object duplication is required.

---

### 🔹 Mutable Alternatives

#### ✅ StringBuilder (Not thread-safe, faster)

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb); // Output: Hello World
```

#### ✅ StringBuffer (Thread-safe version)

```java
StringBuffer sb = new StringBuffer("Hi");
sb.append(" there");
System.out.println(sb); // Output: Hi there
```

---

## ✅ StringBuilder vs StringBuffer in Java

### 🔹 Why Not Use String for Modifications?

* `String` is immutable in Java.
* Every time you modify a `String`, a new object is created in memory.
* This is inefficient when you need frequent changes (like in loops or concatenations).

---

### ✅ StringBuilder

* **Mutable**: You can modify contents without creating new objects.
* **Not Thread-Safe**: No synchronization; not safe in multi-threaded environments.
* **Faster** than `StringBuffer` due to lack of synchronization.
* **Recommended for single-threaded programs.**

#### 🔸 Example:

```java
StringBuilder sb = new StringBuilder("Java");
sb.append(" is");
sb.append(" awesome");
System.out.println(sb);  // Output: Java is awesome
```

#### 🔸 Common Methods:

| Method                     | Description                            |
| -------------------------- | -------------------------------------- |
| `append(String)`           | Adds string to the end                 |
| `insert(int, str)`         | Inserts string at specified index      |
| `delete(start, end)`       | Deletes characters from start to end-1 |
| `reverse()`                | Reverses the string                    |
| `replace(start, end, str)` | Replaces part of the string            |
| `toString()`               | Converts StringBuilder to String       |

---

### ✅ StringBuffer

* **Mutable** and **Thread-Safe**: Methods are synchronized.
* **Slower** than `StringBuilder` due to synchronization overhead.
* **Recommended for multi-threaded applications** where multiple threads modify the same string.

#### 🔸 Example:

```java
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");
System.out.println(sb);  // Output: Hello World
```

---

### 🔍 String vs StringBuilder vs StringBuffer

| Feature     | String           | StringBuilder        | StringBuffer        |
| ----------- | ---------------- | -------------------- | ------------------- |
| Mutable     | ❌ (Immutable)    | ✅ (Mutable)          | ✅ (Mutable)         |
| Thread-Safe | ✅ (Immutable)    | ❌                    | ✅                   |
| Performance | Slow for changes | Fastest (no lock)    | Slower (with lock)  |
| Use Case    | Read-only data   | Single-threaded mods | Multi-threaded mods |

---

### 🧠 Tip:

If you're repeatedly modifying strings (e.g., in loops or data processing), prefer:

* `StringBuilder` for speed
* `StringBuffer` for thread safety
