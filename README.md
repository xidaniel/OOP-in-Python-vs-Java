# OOP-in-Python-vs-Java
This article compares to Object-Oriented Programming between Python and Java.

reference https://realpython.com/oop-in-python-vs-java/


## Object Attributes
### Java Coding example
   - class name same as file name
   - Only one class can be defined in each file
   - static is to defind class attribute
   - can change private variable through a public method
   - access private attributes using setters and getters
   - this
   - Functions can’t exist outside of a class, and by definition, all Java functions are methods
   
         public class Car {
              private String color;
              private String model;
              private int year;
              
             (private static int wheels;  // It is class variable and share to each class instance.  not recommend)
              
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
   - every is public, except add perfixing two underscore character
   - access to class attributes using Python decorator syntax
   - self
   
         class Car:
         
           (wheels = 0     // It is class variable and share to each class instance. not recommend)
            
            // constructure
            def __init__(self, color, model, year):
                self.color = color
                self.model = model
                self.year = year
                self.__cupholders = 6   // non public instance variable
             
            // method
            def get_color(self):
                return self.color
                
                
 ## Inheritance and Polymorphism
