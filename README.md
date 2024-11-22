# week-5-python-ASSIGNMENT

Assignment 1: Design Your Own Class! 🏗️
Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
Add attributes and methods to bring the class to life!
Use constructors to initialize each object with unique values.
Add an inheritance layer to explore polymorphism or encapsulation.


# Parent class
class Device:
    def __init__(self, brand, model, storage_capacity):
        self.brand = brand
        self.model = model
        self.storage_capacity = storage_capacity  # in GB
    
    def display_info(self):
        print(f"Brand: {self.brand}, Model: {self.model}, Storage: {self.storage_capacity}GB")

# Child class: Smartphone
class Smartphone(Device):
    def __init__(self, brand, model, storage_capacity, battery_percentage):
        # Call the constructor of the parent class
        super().__init__(brand, model, storage_capacity)
        self.battery_percentage = battery_percentage  # in percentage
    
    def charge(self, amount):
        """Charge the phone by a certain percentage."""
        if self.battery_percentage + amount > 100:
            self.battery_percentage = 100
        else:
            self.battery_percentage += amount
        print(f"Charging... Battery is now {self.battery_percentage}%")
    
    def use_storage(self, amount):
        """Use up some storage."""
        if amount > self.storage_capacity:
            print("Not enough storage space!")
        else:
            self.storage_capacity -= amount
            print(f"Used {amount}GB of storage. Remaining storage: {self.storage_capacity}GB.")
    
    def display_info(self):
        super().display_info()  # Show base info
        print(f"Battery: {self.battery_percentage}%")
    
# Create an instance of Smartphone
my_phone = Smartphone("Apple", "iPhone 14", 128, 80)

# Using the methods
my_phone.display_info()
my_phone.charge(15)
my_phone.use_storage(50)


Activity 2: Polymorphism Challenge! 🎭

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).

# Base class
class Vehicle:
    def move(self):
        pass  # Base method, to be overridden in subclasses

# Subclass 1: Car
class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

# Subclass 2: Plane
class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

# Subclass 3: Boat
class Boat(Vehicle):
    def move(self):
        print("Sailing ⛵")

# Subclass 4: Bicycle
class Bicycle(Vehicle):
    def move(self):
        print("Pedaling 🚴")

# Test the polymorphism
def test_vehicle_move(vehicle):
    vehicle.move()  # Calls the appropriate move() based on the object type

# Creating instances of different vehicles
car = Car()
plane = Plane()
boat = Boat()
bicycle = Bicycle()

# Testing polymorphism
test_vehicle_move(car)      # Output: Driving 🚗
test_vehicle_move(plane)    # Output: Flying ✈️
test_vehicle_move(boat)     # Output: Sailing ⛵
test_vehicle_move(bicycle)  # Output: Pedaling 🚴
