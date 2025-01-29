Static Code : https://www.programiz.com/online-compiler/5ds72LcoOhS1p

### **Difference Between Class Method and Object Method in Java**

In Java, methods can be categorized into **class methods (static methods)** and **object methods (instance methods)**. The key difference between them lies in how they are called and what they operate on.

---

### **1. Class Method (Static Method)**
- Defined using the `static` keyword.
- Belongs to the class rather than any specific object.
- Can be called without creating an instance of the class.
- Cannot access instance variables or instance methods directly.
- Mostly used for utility or helper functions.

#### **Example of a Static Method**
```java
class MathUtils {
    // Static method
    static int add(int a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        // Calling a static method using the class name
        int sum = MathUtils.add(5, 10);
        System.out.println("Sum: " + sum);
    }
}
```
**Output:**
```
Sum: 15
```
📌 **Key Point:** `MathUtils.add(5, 10)` is called without creating an instance of `MathUtils`.

---

### **2. Object Method (Instance Method)**
- Does **not** use the `static` keyword.
- Belongs to a specific object of the class.
- Can access instance variables and other instance methods.
- Requires an instance (object) of the class to be called.

#### **Example of an Instance Method**
```java
class Person {
    String name;

    // Constructor
    Person(String name) {
        this.name = name;
    }

    // Instance method
    void introduce() {
        System.out.println("Hello, my name is " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating an object of Person
        Person p1 = new Person("Dhiraj");
        
        // Calling an instance method
        p1.introduce();
    }
}
```
**Output:**
```
Hello, my name is Dhiraj
```
📌 **Key Point:** The method `introduce()` is called on an **object** (`p1`), not the class itself.

---

### **Key Differences in Tabular Form**

| Feature          | Class Method (Static) | Object Method (Instance) |
|-----------------|----------------------|-------------------------|
| **Keyword Used** | `static` | No `static` keyword |
| **Belongs To** | Class | Object |
| **Called Using** | Class name | Object of the class |
| **Can Access Instance Variables?** | ❌ No | ✅ Yes |
| **Can Access Other Static Methods?** | ✅ Yes | ✅ Yes |
| **Can Access Instance Methods?** | ❌ No | ✅ Yes |
| **Requires Object Creation?** | ❌ No | ✅ Yes |
| **Example Use Cases** | Utility methods (e.g., `Math.max()`) | Object behavior (e.g., `p1.introduce()`) |

---

### **Combined Example Demonstrating Both**
```java
class Example {
    int instanceVar = 10; // Instance variable
    
    // Static method (Class method)
    static void staticMethod() {
        System.out.println("Static method called.");
        
        // Cannot access instanceVar directly (Uncommenting below will cause an error)
        // System.out.println("Instance Variable: " + instanceVar); 
    }
    
    // Instance method (Object method)
    void instanceMethod() {
        System.out.println("Instance method called.");
        System.out.println("Instance Variable: " + instanceVar);
    }
}

public class Main {
    public static void main(String[] args) {
        // Calling static method
        Example.staticMethod();

        // Creating an object
        Example obj = new Example();
        
        // Calling instance method
        obj.instanceMethod();
    }
}
```
**Output:**
```
Static method called.
Instance method called.
Instance Variable: 10
```

---

### **When to Use What?**
✅ **Use Static Methods When:**
- The method does not depend on instance variables.
- You need utility/helper methods (e.g., `Math.sqrt()`).

✅ **Use Instance Methods When:**
- The method manipulates or depends on instance variables.
- Each object should have its own behavior.

Would you like more examples or clarifications? 🚀
