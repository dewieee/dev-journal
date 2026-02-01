# SOLID Principles

Enhancements to software design that make the code more maintainable & scalable.

### Single Responsibility Principle (SRP)

"A class should only have one reason to change"

**Core idea:** Each class has one purpose

``` js
// Class for baking bread
class BreadBaker {
    bakeBread() {
        console.log("Baking high-quality bread...");
    }
}

// Class for managing inventory
class InventoryManager {
    manageInventory() {
        console.log("Managing inventory...");
    }
}

// Class for ordering supplies
class SupplyOrder {
    orderSupplies() {
        console.log("Ordering supplies...");
    }
}
```
___

### Open/Closed Principle 

"Software entities (classes, modules, functions etc.) should be open for extension, but closed for modification"

**Core idea:** You should be able to extend a class without modifying it

``` js
// Base class for payment processing
class PaymentProcessor {
    processPayment(amount) { // Pure virtual function
        throw new Error("processPayment must be implemented");
    }
}

// Credit card payment processor
class CreditCardPaymentProcessor extends PaymentProcessor {
    processPayment(amount) {
        console.log(`Processing credit card payment of $${amount}`);
    }
}
```
___

### Liskov Substitution Principle (LSP)

"Objects of derived classes should be able to replace objects of the base class without affecting the correctness of the program"

**Core idea:** Derived classes shouldn't override or modify the behaviour of the base class in a way that will break the functionality. 

___

### Interface Segregation Principle (ISP)

"No client should be forced to depend on methods it does not use"

**Core idea:** Create specific, client-focused interfaces rather than large, monolithic ones.

**Implementation:** Create interfaces tailored to needs of clients that implement them.

``` js
interface EmailNotificationProvider {
    void sendEmail();
}

interface SMSNotificationProvider {
    void sendSMS();
}
```

### Dependency Inversion Principle (DIP)

"High-level & low-level modules should depend on abstractions rather than concrete implementations."

**Core idea:** Create specific, client-focused interfaces rather than large, monolithic ones.

**Implementation:** Use dependency injection, inversion of control containers & abstractions to separate high-level/low-level components.

**Benefits:** Greater flexibility, easier testing, reduced coupling.

``` js
interface NotificationProvider {
    void sendNotification();
}

class EmailNotificationProvider implements NotificationProvider {
    public void sendNotification() {
        // Send an email
    }
}

class SMSNotificationProvider implements NotificationProvider {
    public void sendNotification() {
        // Send an SMS
    }
}

class NotificationService {
    private NotificationProvider provider;

    public NotificationService(NotificationProvider provider) {
        this.provider = provider;
    }

    public void sendNotification() {
        provider.sendNotification();
    }
}
```

### Sources:
- [Medium](https://medium.com/@thecodebean/solid-principle-roadmap-to-software-development-9979031b7c3c)
- [Geeks for Geeks](https://www.geeksforgeeks.org/system-design/solid-principle-in-programming-understand-with-real-life-examples/)