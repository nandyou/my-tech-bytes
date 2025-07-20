**ACID principle**


The **ACID principle** in database systems stands for:

* **A**tomicity – Transactions are all-or-nothing. Either all operations succeed, or none do.
* **C**onsistency – The database remains in a valid state before and after the transaction.
* **I**solation – Concurrent transactions don’t interfere with each other.
* **D**urability – Once a transaction is committed, it stays even after a crash.

It's used to ensure reliable and secure transaction processing in databases.


---

 **SOLID principles** with simple **examples**:


### **S – Single Responsibility Principle**

**One class → One job**

✅ **Example**:

```python
class InvoicePrinter:
    def print_invoice(self, invoice):
        print(invoice.details)
```

*This class only handles printing, not calculating or saving.*

---

### **O – Open/Closed Principle**

**Open for extension, closed for modification**

✅ **Example**:

```python
class Shape:
    def area(self):
        pass

class Circle(Shape):
    def area(self):
        return 3.14 * r * r
```

*Add new shapes by extending, without changing existing code.*

---

### **L – Liskov Substitution Principle**

**Subclasses must replace base classes without errors**

✅ **Example**:

```python
def print_area(shape: Shape):
    print(shape.area())

# Works with Circle or Rectangle
print_area(Circle())
```

*Any `Shape` subclass must work with `print_area` function.*

---

### **I – Interface Segregation Principle**

**Don’t force classes to implement unused methods**

✅ **Example**:

```python
class Printable:
    def print(self): pass

class Scannable:
    def scan(self): pass

class Printer(Printable):
    def print(self): print("Printing...")

# Not forced to implement scan
```

---

### **D – Dependency Inversion Principle**

**Depend on abstractions, not concretes**

✅ **Example**:

```python
class Database:
    def save(self, data): pass

class MySQLDatabase(Database):
    def save(self, data): print("Saved to MySQL")

class App:
    def __init__(self, db: Database):
        self.db = db

    def save_data(self, data):
        self.db.save(data)
```

*App works with any `Database`, not just MySQL.*

---


**top 5 Java design patterns**

### **1. Singleton Pattern**

**Ensures only one instance of a class exists.**

✅ **Use Case**: Logging, configuration, DB connection.

```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {} // private constructor

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

---

### **2. Factory Pattern**

**Creates objects without exposing creation logic.**

✅ **Use Case**: Creating objects based on conditions (e.g., shape, user roles).

```java
public interface Shape {
    void draw();
}

public class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

public class ShapeFactory {
    public Shape getShape(String type) {
        if (type.equalsIgnoreCase("circle")) {
            return new Circle();
        }
        return null;
    }
}
```

---

### **3. Observer Pattern**

**One-to-many dependency: when one object changes, others are notified.**

✅ **Use Case**: Event handling (UI buttons, notifications).

```java
interface Observer {
    void update(String message);
}

class Subscriber implements Observer {
    public void update(String message) {
        System.out.println("Received: " + message);
    }
}

class Publisher {
    List<Observer> observers = new ArrayList<>();

    public void addObserver(Observer o) {
        observers.add(o);
    }

    public void notifyObservers(String msg) {
        for (Observer o : observers) {
            o.update(msg);
        }
    }
}
```

---

### **4. Strategy Pattern**

**Defines a family of algorithms and makes them interchangeable.**

✅ **Use Case**: Sorting, compression, payment methods.

```java
interface PaymentStrategy {
    void pay(int amount);
}

class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid $" + amount + " via Credit Card");
    }
}

class ShoppingCart {
    private PaymentStrategy payment;

    public void setPaymentStrategy(PaymentStrategy payment) {
        this.payment = payment;
    }

    public void checkout(int amount) {
        payment.pay(amount);
    }
}
```

---

### **5. Decorator Pattern**

**Adds behavior to objects dynamically.**

✅ **Use Case**: Add features to UI components, I/O streams.

```java
interface Coffee {
    String getDescription();
}

class BasicCoffee implements Coffee {
    public String getDescription() {
        return "Basic Coffee";
    }
}

class MilkDecorator implements Coffee {
    private Coffee coffee;

    public MilkDecorator(Coffee coffee) {
        this.coffee = coffee;
    }

    public String getDescription() {
        return coffee.getDescription() + ", Milk";
    }
}
```

---

