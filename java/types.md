## Types of Variables in Java

In Java, variables are categorized into two main groups based on the type of data they can hold:

### 1. Primitive Types (8 built-in types)
These store simple values directly.

| Type      | Size    | Example Range / Values                     |
|-----------|---------|--------------------------------------------|
| `byte`    | 1 byte  | -128 to 127                                |
| `short`   | 2 bytes | -32,768 to 32,767                          |
| `int`     | 4 bytes | -2³¹ to 2³¹–1 (most common integer)        |
| `long`    | 8 bytes | -2⁶³ to 2⁶³–1 (needs `L` suffix: `100L`)  |
| `float`   | 4 bytes | fractional numbers (needs `f`: `3.14f`)   |
| `double`  | 8 bytes | double precision (default for decimals)    |
| `char`    | 2 bytes | single character: `'A'`, `'7'`             |
| `boolean` | 1 bit   | `true` or `false`                          |

**Example:**
```java
int age = 25;
double price = 19.99;
boolean isRaining = false;
char grade = 'A';
```

### 2. Reference Types
These store **references** (memory addresses) to objects. They include:
- **Classes** (e.g., `String`, `Scanner`, custom classes)
- **Interfaces**
- **Arrays** (e.g., `int[] numbers = new int[5];`)
- **Enums**

**Example:**
```java
String name = "Alice";          // String is a class
int[] scores = {90, 85, 88};    // array
List<String> list = new ArrayList<>(); // interface reference
```

> **Note:** Besides data types, variables can also be classified by **scope**:
> - **Local variables** (declared inside methods)
> - **Instance variables** (inside a class, but outside methods – belong to an object)
> - **Static variables** (belong to the class itself, declared with `static`)

---

## How to Run a Simple `main` Function

The `main` method is the entry point of any Java application. Its signature **must** be:

```java
public static void main(String[] args) {
    // your code here
}
```

- `public` – accessible from anywhere
- `static` – called without creating an object
- `void` – returns nothing
- `String[] args` – command-line arguments

### Step-by-Step Execution (using terminal/command line)

1. **Write the code** in a file named `HelloWorld.java`:
   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }
   ```

2. **Compile** it with `javac`:
   ```bash
   javac HelloWorld.java
   ```
   This produces `HelloWorld.class` (bytecode).

3. **Run** it with `java`:
   ```bash
   java HelloWorld
   ```
   Output: `Hello, World!`

> **Note:** Do not add `.java` or `.class` when running – only the class name.

### Using an IDE (IntelliJ, Eclipse, VS Code)
- Create a new Java project and a class.
- Write the `main` method as above.
- Click the "Run" button (or right-click → Run).

### Example with a variable and output:
```java
public class Demo {
    public static void main(String[] args) {
        int number = 42;
        String message = "The answer is: ";
        System.out.println(message + number);
    }
}
```
Output: `The answer is: 42`
