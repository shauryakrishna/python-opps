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

    kirk = ["James Kirk", 34, "Captain", 2265]
    spock = ["Spock", 35, "Science Officer", 2254]
    mccoy = ["Leonard McCoy", "Chief Medical Officer", 2266]
    
There are a number of issues with this approach.

First, it can make larger code files more difficult to manage. If you reference kirk[0] several lines away from where you declared the kirk list, will you remember that the element with index 0 is the employee’s name?

Second, it can introduce errors if employees don’t have the same number of elements in their respective lists. In the mccoy list above, the age is missing, so mccoy[1] will return "Chief Medical Officer" instead of Dr. McCoy’s age.
Classes vs Instances#
Classes allow you to create user-defined data structures. Classes define functions called methods, which identify the behaviors and actions that an object created from the class can perform with its data.

In this tutorial, you’ll create a Dog class that stores some information about the characteristics and behaviors that an individual dog can have.

A class is a blueprint for how to define something. It doesn’t actually contain any data. The Dog class specifies that a name and an age are necessary for defining a dog, but it doesn’t contain the name or age of any specific dog.

While the class is the blueprint, an instance is an object that’s built from a class and contains real data. An instance of the Dog class is not a blueprint anymore. It’s an actual dog with a name, like Miles, who’s four years old.

Put another way, a class is like a form or questionnaire. An instance is like a form that you’ve filled out with information. Just like many people can fill out the same form with their own unique information, you can create many instances from a single class.

A great way to make this type of code more manageable and more maintainable is to use classes.
Class Definition
You start all class definitions with the class keyword, then add the name of the class and a colon. Python will consider any code that you indent below the class definition as part of the class’s body.

Here’s an example of a Dog class:

    # dog.py
     class Dog:
     pass

The body of the Dog class consists of a single statement: the pass keyword. Python programmers often use pass as a placeholder indicating where code will eventually go. It allows you to run this code without Python throwing an error.

The Dog class isn’t very interesting right now, so you’ll spruce it up a bit by defining some properties that all Dog objects should have. There are several properties that you can choose from, including name, age, coat color, and breed. To keep the example small in scope, you’ll just use name and age.

You define the properties that all Dog objects must have in a method called .__init__(). Every time you create a new Dog object, .__init__() sets the initial state of the object by assigning the values of the object’s properties. That is, .__init__() initializes each new instance of the class.

You can give .__init__() any number of parameters, but the first parameter will always be a variable called self. When you create a new class instance, then Python automatically passes the instance to the self parameter in .__init__() so that Python can define the new attributes on the object.

Update the Dog class with an .__init__() method that creates .name and .age attributes:

    # dog.py

    class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

        Make sure that you indent the .__init__() method’s signature by four spaces, and the body of the method by eight spaces. This indentation is vitally important. It tells Python that the .__init__() method belongs to the Dog class.

In the body of .__init__(), there are two statements using the self variable:

self.name = name creates an attribute called name and assigns the value of the name parameter to it.
self.age = age creates an attribute called age and assigns the value of the age parameter to it.
Attributes created in .__init__() are called instance attributes. An instance attribute’s value is specific to a particular instance of the class. All Dog objects have a name and an age, but the values for the name and age attributes will vary depending on the Dog instance.

On the other hand, class attributes are attributes that have the same value for all class instances. You can define a class attribute by assigning a value to a variable name outside of .__init__().

For example, the following Dog class has a class attribute called species with the value "Canis familiaris":

    # dog.py

    class Dog:
    species = "Canis familiaris"

    def __init__(self, name, age):
        self.name = name
        self.age = age
You define class attributes directly beneath the first line of the class name and indent them by four spaces. You always need to assign them an initial value. When you create an instance of the class, then Python automatically creates and assigns class attributes to their initial values.

Use class attributes to define properties that should have the same value for every class instance. Use instance attributes for properties that vary from one instance to another.

Now that you have a Dog class, it’s time to create some dogs!
How Do You Instantiate a Class in Python?
Creating a new object from a class is called instantiating a class. You can create a new object by typing the name of the class, followed by opening and closing parentheses:

    >>> class Dog:
    ...     pass
    ...
    >>> Dog()
    <__main__.Dog object at 0x106702d30>\
You first create a new Dog class with no attributes or methods, and then you instantiate the Dog class to create a Dog object.

In the output above, you can see that you now have a new Dog object at 0x106702d30. This funny-looking string of letters and numbers is a memory address that indicates where Python stores the Dog object in your computer’s memory. Note that the address on your screen will be different.

Now instantiate the Dog class a second time to create another Dog object:
  
    >>> Dog()
    <__main__.Dog object at 0x0004ccc90>
The new Dog instance is located at a different memory address. That’s because it’s an entirely new instance and is completely unique from the first Dog object that you created.

To see this another way, type the following:

    >>> a = Dog()
    >>> b = Dog()
    >>> a == b
    False

 In this code, you create two new Dog objects and assign them to the variables a and b. When you compare a and b using the == operator, the result is False. Even though a and b are both instances of the Dog class, they represent two distinct objects in memory.
