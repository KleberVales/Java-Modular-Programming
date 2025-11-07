# 🐾 Java Modular Programming Example — `zoo.animal.feeding`

This project demonstrates how to **create, compile, run, and package** a simple modular Java program using the **Java Platform Module System (JPMS)** — introduced in Java 9.

It’s inspired by the *OCP Java 21 Study Guide* example for the module **`zoo.animal.feeding`**, which serves as a foundation module for other modules in a modular system.

---

## 📁 Project Structure

```text

zoo.animal.feeding/
│
├── zoo/
│ └── animal/
│ └── feeding/
│ └── Task.java
│
└── module-info.java

```


**Additional directory used for packaging:**

mods/ ← stores the compiled and packaged module (JAR)


---

## 🧩 Module Definition

The `module-info.java` file defines the module:

```java
module zoo.animal.feeding {
}

```

Key notes:

* module-info.java must be located in the root directory of the module.
* The module name follows package naming rules (e.g., uses dots . but no dashes -).
* The keyword module replaces class, interface, or enum.,

## 🧠 Source Code Example

Task.java
```java

package zoo.animal.feeding;

public class Task {
    public static void main(String... args) {
        System.out.println("All fed!");
    }
}


```

This simple class prints a line to confirm the program ran successfully.

## ⚙️ Compiling the Module

Use the javac command to compile your module:

```bash

javac --module-path mods -d feeding \
feeding/zoo/animal/feeding/*.java feeding/module-info.java


```

## 📋 Important Options (Exam Tip)

| Purpose                   | Short Form  | Long Form              |
| ------------------------- | ----------- | ---------------------- |
| Directory for class files | `-d <dir>`  | n/a                    |
| Module path               | `-p <path>` | `--module-path <path>` |

Alternative valid forms:

```bash

javac -p mods -d feeding feeding/zoo/animal/feeding/*.java feeding/module-info.java
javac -p mods -d feeding feeding/zoo/animal/feeding/Task.java feeding/module-info.java

```

## ▶️ Running the Module

Once compiled, you can run the program directly:

```bash

java --module-path feeding --module zoo.animal.feeding/zoo.animal.feeding.Task


```

or using the shorthand options:

```bash

java -p feeding -m zoo.animal.feeding/zoo.animal.feeding.Task

```


