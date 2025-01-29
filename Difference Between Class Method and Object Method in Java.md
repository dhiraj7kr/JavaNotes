Static Code : https://www.programiz.com/online-compiler/5ds72LcoOhS1p
Object Method code: https://www.programiz.com/online-compiler/1786W8fzoOf5L

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


### **Object Method (Instance Method) in Java**  

#### **Definition:**  
An **object method (instance method)** is a method that belongs to an **instance (object) of a class**. It does not use the `static` keyword and can access both **instance variables** and **other instance methods** of the same object.  

---

### **Key Characteristics of Instance Methods**
1. **Requires Object Creation** – You must create an object of the class to call an instance method.  
2. **Can Access Instance Variables** – Since it belongs to an object, it can access and modify the instance variables.  
3. **Can Call Other Instance Methods** – It can call other instance methods of the same class.  
4. **Cannot Be Called Using Class Name** – Unlike static methods, instance methods cannot be called directly using the class name.  

---

### **Example: Understanding Instance Methods in Java**
```java
class Person {
    // Instance variable
    String name;

    // Constructor (used to initialize the object)
    Person(String name) {
        this.name = name;
    }

    // Instance Method (Object Method)
    void introduce() {
        System.out.println("Hello, my name is " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating an object of the class
        Person p1 = new Person("Dhiraj");
        Person p2 = new Person("Kumar");

        // Calling instance methods on the objects
        p1.introduce();
        p2.introduce();
    }
}
```
**Output:**
```
Hello, my name is Dhiraj
Hello, my name is Kumar
```
### **Explanation of the Example**
1. **Instance Variable**: The `name` variable belongs to each `Person` object.  
2. **Constructor**: The constructor initializes the `name` when an object is created.  
3. **Instance Method `introduce()`**: This method prints the name of the person.  
4. **Calling the Method**:  
   - `p1.introduce();` → Calls the method on `p1`, so it prints "Hello, my name is Dhiraj".  
   - `p2.introduce();` → Calls the method on `p2`, so it prints "Hello, my name is Kumar".  

---

### **Types of Instance Methods**
Instance methods can be further classified into three categories:

#### **1. Accessor Method (Getter)**
- Used to retrieve the value of an instance variable.
- It does not modify the value.

```java
class Car {
    private String model;

    // Constructor
    Car(String model) {
        this.model = model;
    }

    // Getter Method (Accessor)
    String getModel() {
        return model;
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Tesla Model X");
        System.out.println("Car Model: " + myCar.getModel());
    }
}
```
**Output:**
```
Car Model: Tesla Model X
```

---

#### **2. Mutator Method (Setter)**
- Used to modify the value of an instance variable.

```java
class Car {
    private String model;

    // Constructor
    Car(String model) {
        this.model = model;
    }

    // Setter Method (Mutator)
    void setModel(String newModel) {
        model = newModel;
    }

    void display() {
        System.out.println("Car Model: " + model);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Tesla Model X");
        myCar.display();

        // Modifying the instance variable using a setter method
        myCar.setModel("Tesla Model S");
        myCar.display();
    }
}
```
**Output:**
```
Car Model: Tesla Model X
Car Model: Tesla Model S
```

---

#### **3. Helper Method**
- Used internally within the class to perform some calculations or logic.

```java
class Rectangle {
    int length, width;

    // Constructor
    Rectangle(int length, int width) {
        this.length = length;
        this.width = width;
    }

    // Helper Method (Calculates Area)
    int calculateArea() {
        return length * width;
    }

    // Instance Method (Calls Helper Method)
    void displayArea() {
        System.out.println("Area: " + calculateArea());
    }
}

public class Main {
    public static void main(String[] args) {
        Rectangle rect = new Rectangle(5, 10);
        rect.displayArea();
    }
}
```
**Output:**
```
Area: 50
```

---

### **Key Differences Between Instance Methods and Static Methods**
| Feature            | Instance Method | Static Method |
|--------------------|----------------|--------------|
| **Belongs To** | Object (instance) | Class |
| **Requires Object Creation?** | ✅ Yes | ❌ No |
| **Can Access Instance Variables?** | ✅ Yes | ❌ No |
| **Can Access Static Variables?** | ✅ Yes | ✅ Yes |
| **Called Using** | Object reference | Class name |
| **Example Usage** | Behavior of an object (e.g., `introduce()`) | Utility functions (e.g., `Math.max()`) |

---

### **When to Use Instance Methods?**
✅ When the method **depends on object-specific data** (instance variables).  
✅ When the method **needs to modify object properties**.  
✅ When you need **separate behavior for each object**.

---

### **Conclusion**
- **Instance methods** are tied to individual objects and can access instance variables.  
- They are widely used for defining **object behaviors**.  
- Unlike static methods, they **require an object to be invoked**.  


