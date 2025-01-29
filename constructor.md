# **Constructor in Java**

## **Definition**
A **constructor** in Java is a **special method** that is automatically called when an object of a class is created. It has the **same name** as the class and **does not have a return type (not even `void`)**.

---

## **Why Use a Constructor?**
✅ **Initialize Objects** – It assigns initial values to instance variables.  
✅ **Ensures Object Setup** – Makes sure an object is properly initialized before use.  
✅ **Reduces Redundancy** – Avoids the need to call setter methods manually after object creation.  

---

## **Types of Constructors in Java**
1. **Default Constructor (No-Argument Constructor)**
2. **Parameterized Constructor**
3. **Copy Constructor (Manually Created in Java)**

---

## **1. Default Constructor (No-Argument Constructor)**
A **default constructor** is a constructor that takes **no arguments** and initializes instance variables with **default values**.

### **Example**
```java
class Car {
    String model;
    int year;

    // Default Constructor
    public Car() {
        model = "Unknown";
        year = 2024;
    }

    // Method to display values
    public void display() {
        System.out.println("Car Model: " + model);
        System.out.println("Manufacturing Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // Constructor is automatically called
        myCar.display();
    }
}
```
### **Output**
```
Car Model: Unknown
Manufacturing Year: 2024
```

### **Explanation**
- The **default constructor** initializes `model` as `"Unknown"` and `year` as `2024`.
- When `new Car();` is called, the constructor runs automatically.
- The `display()` method prints the values.

---

## **2. Parameterized Constructor**
A **parameterized constructor** allows passing values while creating an object.

### **Example**
```java
class Car {
    String model;
    int year;

    // Parameterized Constructor
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    public void display() {
        System.out.println("Car Model: " + model);
        System.out.println("Manufacturing Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar1 = new Car("Tesla Model X", 2023);
        Car myCar2 = new Car("Ford Mustang", 2022);

        myCar1.display();
        myCar2.display();
    }
}
```
### **Output**
```
Car Model: Tesla Model X
Manufacturing Year: 2023
Car Model: Ford Mustang
Manufacturing Year: 2022
```

### **Explanation**
- The **constructor takes parameters** (`model` and `year`).
- When `new Car("Tesla Model X", 2023);` is called, values are assigned dynamically.
- This avoids the need for setter methods after object creation.

---

## **3. Copy Constructor (Manually Created in Java)**
Java **does not have a built-in copy constructor**, but you can create one manually.

### **Example**
```java
class Car {
    String model;
    int year;

    // Parameterized Constructor
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // Copy Constructor
    public Car(Car otherCar) {
        this.model = otherCar.model;
        this.year = otherCar.year;
    }

    public void display() {
        System.out.println("Car Model: " + model);
        System.out.println("Manufacturing Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car car1 = new Car("BMW X5", 2022); // Original object
        Car car2 = new Car(car1); // Copy constructor is called

        car1.display();
        car2.display();
    }
}
```
### **Output**
```
Car Model: BMW X5
Manufacturing Year: 2022
Car Model: BMW X5
Manufacturing Year: 2022
```

### **Explanation**
- The **copy constructor** takes another object as a parameter and copies its values.
- This is useful when we want to duplicate an object.

---

## **Real-Life Example: Bank Account**
In real life, when you **open a bank account**, the bank assigns:
- A **default account balance (like ₹1000)**
- An **account number**
- A **customer name**

### **Java Implementation**
```java
class BankAccount {
    String accountHolder;
    int accountNumber;
    double balance;

    // Parameterized Constructor
    public BankAccount(String accountHolder, int accountNumber, double balance) {
        this.accountHolder = accountHolder;
        this.accountNumber = accountNumber;
        this.balance = balance;
    }

    // Display account details
    public void displayAccount() {
        System.out.println("Account Holder: " + accountHolder);
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Balance: ₹" + balance);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a new account
        BankAccount account1 = new BankAccount("Dhiraj Kumar", 12345678, 5000.0);
        
        // Displaying account details
        account1.displayAccount();
    }
}
```
### **Output**
```
Account Holder: Dhiraj Kumar
Account Number: 12345678
Balance: ₹5000.0
```

---

## **Key Differences: Constructor vs. Method**
| Feature | Constructor | Method |
|---------|------------|--------|
| **Purpose** | Initializes an object | Performs actions on an object |
| **Return Type** | No return type (not even `void`) | Can have a return type |
| **Name** | Same as class name | Any valid name |
| **Called Automatically?** | ✅ Yes, when an object is created | ❌ No, must be called manually |
| **Can be Overloaded?** | ✅ Yes | ✅ Yes |

---

## **Conclusion**
✔ **Constructors are special methods** used to initialize objects.  
✔ They **eliminate the need for setter methods** after object creation.  
✔ Java provides **default, parameterized, and copy constructors**.  
✔ Constructors **cannot have a return type** and run **automatically** when an object is created.  

---

### **Would you like me to explain constructor chaining (calling one constructor from another)?** 🚀
