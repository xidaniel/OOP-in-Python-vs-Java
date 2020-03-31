# OOP-in-Python-vs-Java
This article compares to Object-Oriented Programming between Python and Java.

[Reference](https://realpython.com/oop-in-python-vs-java/)


## Object Attributes
### Java Coding example
   - class name is same as file name
   - Only one class can be defined in each file
   - static is use to defind class attribute not object
   - Through a public method to change private object variable
   - access private attributes using setters and getters
   - this: when a parameter name is same as a class variable
   - Functions can’t exist outside of a class, and by definition, all Java functions are methods
   
         public class Car {
              private String color;
              private String model;
              private int year;
              
             (private static int wheels;)  // It is class variable and share to each class instance.  not recommend)
              
              // constructure 
              public Car(String color, String model, int year) {
                  this.color = color;
                  this.model = model;
                  this.year = year;
              }
              
              //method
              public String getColor() {
                  return color;
              }
          }
          
 ### Python coding example
   - can declare a class anywhere, in any file, at any time
   - save this calss in the file car.py
   - everything is public, except for add perfixing two underscore character
   - access to class attributes using Python decorator syntax
   - self
   
         class Car:
         
           (wheels = 0)     // It is class variable and share to each class instance. not recommend
            
            // constructure
            def __init__(self, color, model, year):
                self.color = color
                self.model = model
                self.year = year
                self.__cupholders = 6   // non public instance variable
             
            // method
            def get_color(self):
                return self.color
                
____________________________________________________________________________________________________________________________
 ## Inheritance and Polymorphism
 ### Java codeing example
   - Java only supports single inheritance, which means classes in Java can inherit data and behavior from only a single parent class
   - Java objects can inherit behavior from many different interfaces
   - Interfaces provide a group of related methods an object must implement, and allow multiple child classes to behave similarly
   - Interfaces only define the methods—they cannot define instance data or implementation details
   - Each class and interface needs to live in its own file

         public class Vehicle {

             private String color;
             private String model;
             
             // constructure
             public Vehicle(String color, String model) {
                 this.color = color;
                 this.model = model;
             }
             // method
             public String getColor() {
                 return color;
             }

             public String getModel() {
                 return model;
             }
         }
         
         public interface Device {
             int getVoltage();
          }
          
         public class Car extends Vehicle implements Device {

             private int voltage;
             private int year;

             public Car(String color, String model, int year) {
                 super(color, model);    // super private color and private model
                 this.year = year;
                 this.voltage = 12;
             }

             @Override  interface method
             public int getVoltage() {
                 return voltage;
             }

             public int getYear() {
                 return year;
             }
         }
      
      
 ### Python coding example
   - Python supports multiple inheritance, or creating classes that inherit behavior from more than one parent class
   
         class Vehicle:
          def __init__(self, color, model):
              self.color = color
              self.model = model

         class Device:
             def __init__(self):
                 self._voltage = 12

         class Car(Vehicle, Device):
             def __init__(self, color, model, year):
                 Vehicle.__init__(self, color, model)
                 Device.__init__(self)
                 self.year = year

             @property
             def voltage(self):
                 return self._voltage

             @voltage.setter
             def voltage(self, volts):
                 print("Warning: this can cause problems!")
                 self._voltage = volts

             @voltage.deleter
             def voltage(self):
                 print("Warning: the radio will stop working!")
                 del self._voltage
                 
_____________________________________________________________________________________________________

## Types and Polymorphism
