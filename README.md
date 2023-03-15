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
        
        
   5.getter and setter 
   
                    class Person {
                  constructor(name, age) {
                    this._name = name;
                    this._age = age;
                  }

                  get name() {
                    return this._name.toUpperCase();
                  }

                  set age(value) {
                    if (value < 0 || value > 120) {
                      console.log("Invalid age");
                      return;
                    }
                    this._age = value;
                  }

                  get age() {
                    return this._age;
                  }
                }

                const person = new Person("John Doe", 30);
                console.log(person.name); // output: "JOHN DOE"
                person.age = 40;
                console.log(person.age); // output: 40
                person.age = 150; // output: "Invalid age"
                
                
6.static


                    class Circle {
                  constructor(radius) {
                    this.radius = radius;
                  }

                  get diameter() {
                    return this.radius * 2;
                  }

                  get circumference() {
                    return this.radius * 2 * Math.PI;
                  }

                  get area() {
                    return Math.PI * this.radius ** 2;
                  }

                  static createFromDiameter(diameter) {
                    return new Circle(diameter / 2);
                  }
                }

                const circle = new Circle(5);
                console.log(circle.area); // output: 78.53981633974483

                const circleFromDiameter = Circle.createFromDiameter(10);
                console.log(circleFromDiameter.radius); // output: 5
                console.log(circleFromDiameter.area); // output: 78.53981633974483


