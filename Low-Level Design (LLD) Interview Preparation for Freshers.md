# Low-Level Design (LLD) Interview Preparation for Freshers

## 1. LLD Fundamentals and Requirement Clarification — High Priority

1. What is Low-Level Design, and what does it describe about a software system?
2. How does Low-Level Design differ from High-Level Design?
3. How is object-oriented design different from simply writing classes?
4. What should you clarify before starting an LLD interview problem?
5. How do functional requirements differ from non-functional requirements?
6. How would you identify the main actors and use cases in a problem statement?
7. How would you decide which features belong in the initial scope?
8. How would you identify important business rules and constraints?
9. How would you move from requirements to classes, relationships, and methods?
10. How would you explain your assumptions and design decisions to an interviewer?

## 2. Object-Oriented Programming Fundamentals — High Priority

1. What are encapsulation, abstraction, inheritance, and polymorphism?
2. How does encapsulation help an object maintain a valid state?
3. How does abstraction differ from encapsulation?
4. How would you model a bank account so that its balance cannot be changed arbitrarily?
5. What is the difference between method overloading and method overriding?
6. How does compile-time polymorphism differ from runtime polymorphism?
7. How does an interface differ from an abstract class?
8. When would you choose an interface, an abstract class, or a concrete class?
9. What is the difference between an “is-a” relationship and a “has-a” relationship?
10. Why can excessive inheritance make a design difficult to change?
11. What does “favor composition over inheritance” mean?
12. How would you choose between inheritance and composition when adding different payment methods?

## 3. Classes, Responsibilities, and Relationships — High Priority

1. How do you identify classes from a set of requirements?
2. How do you distinguish an entity from a service or a value object?
3. How do you decide which class should own a particular behavior?
4. What is the difference between association, aggregation, and composition?
5. How would you represent one-to-one, one-to-many, and many-to-many relationships in code?
6. What are cohesion and coupling?
7. Why are high cohesion and low coupling desirable?
8. What is a “god class,” and how would you break one into smaller responsibilities?
9. Why can exposing mutable collections through getters cause problems?
10. When should a relationship be one-directional instead of bidirectional?
11. How would you decide whether two objects are equal by identity or by value?
12. How would you prevent an object from being created in an invalid state?

## 4. SOLID Principles — High Priority

1. What are the five SOLID principles?
2. What does the Single Responsibility Principle mean?
3. How would you refactor a class that calculates invoices, saves them, and emails them?
4. What does the Open/Closed Principle mean?
5. How would you support new discount rules without repeatedly modifying an existing checkout class?
6. What does the Liskov Substitution Principle require from a subtype?
7. Why can a subclass that rejects behavior supported by its parent violate substitutability?
8. What does the Interface Segregation Principle mean?
9. How would you redesign an interface that forces some implementations to provide unsupported methods?
10. What does the Dependency Inversion Principle mean?
11. How does dependency inversion differ from dependency injection?
12. When can applying SOLID too aggressively introduce unnecessary complexity?

## 5. UML and Communicating a Design — Medium Priority

1. What is a UML class diagram, and what should it communicate?
2. How do you represent classes, interfaces, attributes, and methods in a class diagram?
3. How do you show inheritance, interface implementation, association, and composition?
4. What does multiplicity mean in a class relationship?
5. What is a sequence diagram, and when is it useful?
6. How would you show the interactions involved in booking an appointment?
7. What is a state diagram, and when is it more useful than a class diagram?
8. How would you keep a design diagram readable without including every implementation detail?

## 6. Method Contracts and Object State — High Priority

1. How do you design a method signature that clearly expresses its purpose?
2. What are preconditions, postconditions, and invariants?
3. How would you decide whether a method should return a value, return an optional result, or throw an exception?
4. Why can methods with many boolean parameters be difficult to understand?
5. When should related parameters be grouped into a separate object?
6. How do immutable objects differ from mutable objects?
7. When would you use an enum instead of strings to represent a fixed set of values?
8. How would you model valid and invalid transitions between order states?
9. How would you prevent a cancelled booking from being marked as completed?
10. Why should operations such as `withdraw()` or `cancel()` often be preferred over unrestricted setters?
11. How would you make a cancellation operation safe to call more than once?

## 7. Essential Design Patterns — High Priority

1. What is a design pattern, and how does it differ from an algorithm?
2. What problem does the Strategy pattern solve?
3. How would you use Strategy to support different pricing or payment behaviors?
4. How does a simple factory differ from the Factory Method pattern?
5. When is a Builder useful compared with a constructor?
6. What problem does the Observer pattern solve?
7. How would you notify multiple subscribers when an order changes status?
8. What problem does the Adapter pattern solve?
9. How would you integrate a third-party payment interface that differs from your application’s interface?
10. How does the Decorator pattern add behavior without creating many subclasses?
11. What problem does the State pattern solve, and when would an enum with conditional logic be sufficient?
12. What are the drawbacks of Singleton, particularly for testing and shared mutable state?
13. How would you decide whether a pattern improves a design or adds unnecessary abstraction?

## 8. Collections and Data Structures in Design — High Priority

1. How would you choose between a list, set, map, queue, and priority queue?
2. How would you store objects that need frequent lookup by a unique ID?
3. How would you maintain uniqueness while preserving insertion order?
4. How would you represent a waiting list that serves requests in arrival order?
5. How would you represent requests that must be processed by priority?
6. Why can mutable objects be problematic as hash-map keys?
7. In Java, what relationship must hold between `equals()` and `hashCode()`?
8. How would you keep multiple in-memory indexes consistent when an object changes?
9. How would you choose a data structure for checking time-slot conflicts?
10. How would you explain the time and space trade-offs of your chosen collections?

## 9. Layering, Persistence, and External Dependencies — Medium Priority

1. What responsibilities belong in a controller, service, domain object, and repository?
2. How would you prevent business logic from becoming tightly coupled to a database?
3. What is a repository interface, and why might you provide an in-memory implementation?
4. How does a Data Transfer Object (DTO) differ from a domain object?
5. Where should input validation and business-rule validation happen?
6. How would you inject a payment gateway or notification provider into a service?
7. How would you replace an external dependency with a fake implementation during testing?
8. Where would you place a transaction boundary for an operation that updates multiple records?
9. How would you handle a notification failure after a booking has already been saved?
10. How would you keep database and framework details from dominating a small LLD solution?

## 10. Error Handling and Testability — High Priority

1. How would you distinguish invalid input, a business-rule violation, and an infrastructure failure?
2. When would you create a custom exception?
3. How would you report “seat unavailable” differently from “database connection failed”?
4. How would you ensure a failed operation does not leave an object partially updated?
5. How does constructor injection make a class easier to test?
6. How would you test behavior that depends on the current time?
7. How would you test behavior that depends on randomness, such as rolling dice?
8. What edge cases would you test for a booking or payment operation?
9. How would you test that invalid state transitions are rejected?
10. How would you test an interface’s implementations against the same expected contract?

## 11. Basic Concurrency in LLD — Medium Priority

1. What is a race condition in an object-oriented application?
2. What can happen if two threads book the same available seat simultaneously?
3. Why is a separate “check availability, then book” sequence unsafe?
4. What does it mean for an operation to be atomic?
5. When would synchronization or a lock be needed around shared state?
6. Why does using a thread-safe collection not automatically make a multi-step operation thread-safe?
7. How can immutable objects simplify concurrent code?
8. Why should you avoid holding a lock while making a slow external API call?
9. Why might an in-process lock be insufficient when several application instances share a database?
10. How would you keep concurrency handling proportional to the requirements of a fresher-level design problem?

## 12. Beginner LLD Practice Problems — High Priority

### 12.1 Library Management System

1. How would you model books, physical book copies, members, and loans?
2. How would you support borrowing and returning a specific copy?
3. How would you enforce borrowing limits and prevent an unavailable copy from being issued?
4. How would you add a replaceable overdue-fee calculation policy?

### 12.2 Parking Lot

1. How would you model vehicles, parking spots, floors, tickets, and payments?
2. How would you assign a suitable spot to an incoming vehicle?
3. How would you separate spot allocation from parking-fee calculation?
4. How would you prevent a spot from being assigned to two active tickets?

### 12.3 Tic-Tac-Toe

1. How would you model the board, players, moves, and game status?
2. How would you validate a move and enforce player turns?
3. How would you detect a win or a draw?
4. How would you support a configurable board size and winning rule?

### 12.4 Vending Machine

1. How would you model products, inventory, money, and machine states?
2. How would you handle product selection, payment, and dispensing?
3. How would you handle insufficient payment, unavailable products, or unavailable change?
4. How would you support cancellation and refunds before dispensing?

### 12.5 Doctor Appointment Booking

1. How would you model doctors, patients, available slots, and appointments?
2. How would you support booking for either the account holder or a family member?
3. How would you prevent overlapping active bookings for a doctor?
4. How would you handle cancellation and rescheduling while preserving valid appointment states?

## 13. Intermediate LLD Practice Problems — Medium Priority

### 13.1 Expense Sharing System

1. How would you model users, groups, expenses, and shares?
2. How would you support equal, exact-amount, and percentage-based splits?
3. How would you validate that individual shares match the total expense?
4. How would you represent balances and record settlements without losing expense history?

### 13.2 Elevator System

1. How would you model elevators, floors, internal selections, and external requests?
2. How would you separate elevator movement from request-assignment logic?
3. How would you handle several pending requests?
4. How would you make the scheduling policy replaceable?

### 13.3 Movie Ticket Booking

1. How would you distinguish a movie, theatre, screen, show, and seat?
2. How would you represent seat availability separately for each show?
3. How would you temporarily hold seats and expire unpaid reservations?
4. How would you handle payment failure or a payment result that arrives after a hold expires?

### 13.4 Shopping Cart and Checkout

1. How would you model products, cart items, orders, and payments?
2. How would you support different discount rules?
3. How would you handle changes in product price or stock between adding an item and checking out?
4. How would you prevent repeated checkout requests from creating duplicate orders?

## 14. Common Design Follow-Up Questions — High Priority

1. Why did you choose these classes and assign these responsibilities?
2. Which business rules does your design enforce, and where?
3. What assumptions does your design make?
4. Which parts are likely to change, and how would your design accommodate them?
5. Can any class, interface, or abstraction be removed without harming the design?
6. How would you add a new behavior without changing unrelated classes?
7. What are the main failure cases and edge cases?
8. How would you demonstrate the main use case with a short runnable example?
9. What are the time and space complexities of the main operations?
10. What would need to change if the data moved from memory to a database?
11. What would need to change if multiple users performed the same operation concurrently?
12. What would you implement first if the interview time were limited?

## 15. Optional Advanced Topics — Low Priority

1. When would Command, Chain of Responsibility, or Abstract Factory be useful?
2. What are domain aggregates, and how do aggregate boundaries protect invariants?
3. How would you design an in-memory LRU cache?
4. How would you design an in-memory rate limiter?
5. How would you support retries without repeating a payment or another irreversible operation?
6. How can optimistic version checks prevent conflicting updates?
7. When might an event-driven design help separate responsibilities?
8. What additional complexity do distributed locks introduce compared with local locks?

## Must-Prepare Checklist

- [ ] LLD vs HLD.
- [ ] Requirement clarification, scope, and assumptions.
- [ ] Actors, use cases, and business rules.
- [ ] Encapsulation, abstraction, inheritance, and polymorphism.
- [ ] Interfaces vs abstract classes.
- [ ] Composition vs inheritance.
- [ ] Class responsibilities and object relationships.
- [ ] Entities vs value objects vs services.
- [ ] High cohesion and low coupling.
- [ ] SOLID principles with practical examples.
- [ ] Basic class, sequence, and state diagrams.
- [ ] Clear method contracts and object invariants.
- [ ] Immutability and controlled state transitions.
- [ ] Strategy, factories, Builder, Observer, and Adapter.
- [ ] Basic Decorator and State patterns.
- [ ] Singleton drawbacks.
- [ ] Collection choices and operation complexity.
- [ ] `equals()` and `hashCode()` in Java.
- [ ] Separation of domain logic and external dependencies.
- [ ] Dependency injection and testable design.
- [ ] Validation, exceptions, and partial-failure handling.
- [ ] Race conditions and atomic booking operations.
- [ ] Library Management System.
- [ ] Parking Lot.
- [ ] Tic-Tac-Toe.
- [ ] Vending Machine.
- [ ] Doctor Appointment Booking.
- [ ] At least one intermediate design problem.
- [ ] A runnable demonstration of the main use case.
- [ ] Explaining design trade-offs and handling requirement changes.
