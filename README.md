# class-js

Object-Oriented Programming (OOP) in JavaScript can be structured around the four pillars of OOP:

        1.Encapsulation
        
        2.Inheritance
        
        3.Abstraction 
        
        4.Polymorphism.
        
1. Encapsulation:  

        class BankAccount {
          #balance = 0; // private variable

          deposit(amount) {
            this.#balance += amount;
          }

          withdraw(amount) {
            if (this.#balance >= amount) {
              this.#balance -= amount;
              return amount;
            } else {
              console.log("Insufficient funds!");
            }
          }

          getBalance() {
            return this.#balance;
          }
        }

        const account = new BankAccount();
        account.deposit(1000);
        console.log(account.getBalance()); // output: 1000
        account.withdraw(500);
        console.log(account.getBalance()); // output: 500
        
        
    2.Inheritance:
    
         class Animal {
          constructor(name) {
            this.name = name;
          }

          speak() {
            console.log(`${this.name} makes a noise.`);
          }
        }

        class Dog extends Animal {
          speak() {
            console.log(`${this.name} barks.`);
          }
        }

        const spot = new Dog("Spot");
        spot.speak(); // output: Spot barks.

3. abstraction

        function Shape() {}

        Shape.prototype.draw = function() {
          throw new Error("Cannot call abstract method.");
        }

        class Circle extends Shape {
          draw() {
            console.log("Drawing a circle.");
          }
        }

        const circle = new Circle();
        circle.draw(); // output: Drawing a circle.
        
  4.Polymorphism:
  
  
        class Vehicle {
          start() {
            console.log("Starting vehicle...");
          }
        }

        class Car extends Vehicle {
          start() {
            console.log("Starting car...");
          }
        }

        class Motorcycle extends Vehicle {
          start() {
            console.log("Starting motorcycle...");
          }
        }

        function startVehicle(vehicle) {
          vehicle.start();
        }

        const car = new Car();
        const motorcycle = new Motorcycle();
        startVehicle(car); // output: Starting car...
        startVehicle(motorcycle); // output: Starting motorcycle...

