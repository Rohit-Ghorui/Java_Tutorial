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

Let me know if you'd like this styled as a real README with badges, or uploaded to GitHub!
