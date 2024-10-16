# Activity-25-SOLID-PRINCIPLES-in-Angular

# Understanding SOLID Principles and Their Application in Angular

## Introduction
In software development, maintaining clean, maintainable, and scalable code is critical. The SOLID principles provide a set of guidelines to make software designs more understandable, flexible, and maintainable. This document outlines each of the SOLID principles and their application in Angular.

## What Are the SOLID Principles?

### 1. Single Responsibility Principle (SRP)
**Definition**: A class should have one, and only one, reason to change.

**Example**:
```typescript
@Component({
  selector: 'app-user-profile',
  templateUrl: './user-profile.component.html',
})
export class UserProfileComponent {
  constructor(private userService: UserService) {}

  getUserInfo(userId: string) {
    // Fetch user information
  }
}


Use Case: The UserProfileComponent handles displaying user profiles, while UserService manages data interactions.







2. Open/Closed Principle (OCP)
Definition: Software entities should be open for extension but closed for modification.

Example:
abstract class Notification {
  abstract send(message: string): void;
}

class EmailNotification extends Notification {
  send(message: string) {
    // Send email
  }
}

class SMSNotification extends Notification {
  send(message: string) {
    // Send SMS
  }
}

Use Case: New notification methods can be added without changing existing classes.






3. Liskov Substitution Principle (LSP)
Definition: Subtypes must be substitutable for their base types.

Example:
class Car {
  start() { return 'Engine starts'; }
}

class Tesla extends Car {
  start() { return 'Tesla engine starts silently'; }
}

function startCar(car: Car) {
  console.log(car.start());
}

Use Case: Various car types can be passed to functions expecting a base car type.





4. Interface Segregation Principle (ISP)
Definition: No client should be forced to depend on methods it does not use.

Example:
interface Printer {
  print();
}

interface Scanner {
  scan();
}

class MultiFunctionDevice implements Printer, Scanner {
  print() {
    // Implementation
  }
  scan() {
    // Implementation
  }
}


Use Case: Smaller interfaces allow clients to implement only what they require.







5. Dependency Inversion Principle (DIP)
Definition: High-level modules should not depend on low-level modules.

Example:
@Injectable({
  providedIn: 'root',
})
export class UserService {
  constructor(private apiService: ApiService) {}
  
  getUser() {
    return this.apiService.fetchUser();
  }
}

Use Case: Services rely on abstractions, enabling easier testing and flexibility.
