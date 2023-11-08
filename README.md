##Object-oriented programming (OOP)
is a method of structuring a program by bundling related properties and behaviors into individual objects. In this tutorial, you’ll learn the basics of object-oriented programming in Python.

Conceptually, objects are like the components of a system. Think of a program as a factory assembly line of sorts. At each step of the assembly line, a system component processes some material, ultimately transforming raw material into a finished product.

An object contains data, like the raw or preprocessed materials at each step on an assembly line. In addition, the object contains behavior, like the action that each assembly line component performs.

In this tutorial, you’ll learn how to:
 -Define a class, which is like a blueprint for creating an object
 -Use classes to create new objects
 -Model systems with class inheritance

 What Is Object-Oriented Programming in Python?
Object-oriented programming is a programming paradigm that provides a means of structuring programs so that properties and behaviors are bundled into individual objects.

For example, an object could represent a person with properties like a name, age, and address and behaviors such as walking, talking, breathing, and running. Or it could represent an email with properties like a recipient list, subject, and body and behaviors like adding attachments and sending.

Put another way, object-oriented programming is an approach for modeling concrete, real-world things, like cars, as well as relations between things, like companies and employees or students and teachers. OOP models real-world entities as software objects that have some data associated with them and can perform certain operations.
The key takeaway is that objects are at the center of object-oriented programming in Python. In other programming paradigms, objects only represent the data. In OOP, they additionally inform the overall structure of the program.
How Do You Define a Class in Python?
In Python, you define a class by using the class keyword followed by a name and a colon. Then you use .__init__() to declare which attributes each instance of the class should have:

    class Employee:
    def __init__(self, name, age):
        self.name =  name
        self.age = age

But what does all of that mean? And why do you even need classes in the first place? Take a step back and consider using built-in, primitive data structures as an alternative.

Primitive data structures—like numbers, strings, and lists—are designed to represent straightforward pieces of information, such as the cost of an apple, the name of a poem, or your favorite colors, respectively. What if you want to represent something more complex?

For example, you might want to track employees in an organization. You need to store some basic information about each employee, such as their name, age, position, and the year they started working.

One way to do this is to represent each employee as a list:

