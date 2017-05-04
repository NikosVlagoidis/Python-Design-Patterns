# Python-Design-Patterns
## Creational Patterns

#### Factory

Factory encapsulates object creation. That is, Factory is an object specializing in creating other objects. The Factory pattern is useful, especially when you're not sure about what type of objects you'll be needing eventually in your system. Another possibility is the situation in which your application needs to decide on what class to use at run time. Here is a scenario we'll be using in our coding exercise.

Your pet shop was only selling dogs but now you need to sell cats, too. Therefore, your system needs to be able to handle cats as well as dogs. Your system's supposed to show how each of the pets you sell speak.

#### Abstract Factory

Abstract Factory is especially useful when a client expects to receive a family of related objects at a given time, but don't have to know which family it is until run time. Here is the scenario we'll be using. We'll first build a pet factory whose concrete factories include Dog factory and Cat factory. Both dog and cat factories produce related products such as dog food and cat food.

At least in theory our solution, Abstract Factory, consists of Abstract factory, Concrete factory, Abstract product, and Concrete product. For the Abstract factory we use pet factory in our example. For concrete factory we use dog factory and cat factory in our example. And finally for the concrete product we'll be creating the dog, which is a pet, and the dog food, and also cat and the cat food.

We implement our Abstract Factory without using inheritance, mainly because Python is a dynamically typed language and therefore does not require abstract classes. Abstract Factory is related to factory method and the concrete factories are often singletons.

#### Singleton

Abstract Factory is especially useful when a client expects to receive a family of related objects at a given time, but don't have to know which family it is until run time. Here is the scenario we'll be using. We'll first build a pet factory whose concrete factories include Dog factory and Cat factory. Both dog and cat factories produce related products such as dog food and cat food.

At least in theory our solution, Abstract Factory, consists of Abstract factory, Concrete factory, Abstract product, and Concrete product. For the Abstract factory we use pet factory in our example. For concrete factory we use dog factory and cat factory in our example. And finally for the concrete product we'll be creating the dog, which is a pet, and the dog food, and also cat and the cat food.

We implement our Abstract Factory without using inheritance, mainly because Python is a dynamically typed language and therefore does not require abstract classes. Abstract Factory is related to factory method and the concrete factories are often singletons.

#### Builder

Builder is a solution to an Anti-Pattern called Telescoping Constructor. An Anti-Pattern is the opposite of the best practice. The Telescoping Constructor Anti-Pattern occurs when a software developer attempts to build a complex object using an excessive number of constructors. The Builder pattern is trying to solve this problem. Think of a scenario, in which you're trying to build a car. This requires various car parts to be first constructed individually and then assembled.

The Builder pattern brings an order to this chaotic process to remove this unnecessary complexity in building a complex object. The Builder partitions the process of building a complex object into the four different roles. The first role is Director, and Director is in charge of actually building a product using the builder object. Then, the builder class provides all the necessary interfaces required in building an object. We call this an Abstract Builder, because there will be a Concrete Builder inheriting from this Abstract Builder.

The Concrete Builder class inherits from the Builder class and actually implements the details of the interfaces of the Builder class, for a specific type of a product. And the product represents an object being built. The Builder Pattern does not rely on polymorphism, unlike Factory and Abstract Factory. The focus of the Builder Pattern is rather on reducing the complexity of building a complex object through a divide and conquer strategy.

#### Protoype
Prototype clones objects according to a prototypical instance. Prototype is especially useful when creating many identical objects individually. So this could be very expensive. And cloning could be a good alternative instead of creating individual objects one at a time. Let's assume that we are building a car. We can mass produce cars if the cars have the same color and the same options.

So in this case, you can simply clone the objects instead of creating the individual objects one at a time. So the solution in this case consists of creating a prototypical instance first and then simply cloning it whenever you need a replica. One of the patterns related to the prototype pattern is abstract factory.

## Structural Patterns

#### Prototype

Prototype clones objects according to a prototypical instance. Prototype is especially useful when creating many identical objects individually. So this could be very expensive. And cloning could be a good alternative instead of creating individual objects one at a time. Let's assume that we are building a car. We can mass produce cars if the cars have the same color and the same options.

So in this case, you can simply clone the objects instead of creating the individual objects one at a time. So the solution in this case consists of creating a prototypical instance first and then simply cloning it whenever you need a replica. One of the patterns related to the prototype pattern is abstract factory.

#### Proxy

Proxy becomes handy when creating an object that is very resource intensive. The problem we need to solve here is to postpone our object creation as long as possible, due to the resource intensive nature of the object we're creating. Therefore, there is a need for a placeholder which will in turn create the object if its creation is absolutely necessary. So here is our scenario. So in our scenario, we create this instance of the Producer class only when he's available, because only a fixed number of Producer objects can exist at a given time.

Our Proxy in this case is an artist who is checking to see if the Producer becomes available for a guest. In the Proxy design pattern clients interact with a Proxy object most of the time until the resource intensive object becomes available. Therefore, the Proxy object is in charge of creating the resource intensive objects. Adapter and Decorator are related to the Proxy design pattern.

#### Adapter

Adapter converts the interface of a class into another one a client is expecting. This time our problem is that the interfaces are incompatible between a client and a server. In our scenario, we have Korean and British objects which have different method names for speaking. Instead, the client would like to use a uniform interface that is the speak method. Our solution is the use of the adapter pattern that translates the method names in between the client and the server code.

Bridges and decorators are related to the adapter pattern.

#### Composite

The composite design pattern maintains a tree data structure to represent part-whole relationships. Here we like to build a recursive tree data structure so that an element of the tree can have its own sub-elements. An example of this problem is creating menu and submenu items. The submenu items can have their own sub-submenu items. So our coding challenge is to display menu and submenu items using this composite design pattern.

Our solution consists of three major elements. The first one is component, the second one is child, and the third one is composite. The component element is an abstract class. A concrete class called child inherits from this component class. And then we have another concrete class called composite, which is also inheriting from the component class. Finally, our composite class maintains child objects by adding and removing them to a tree data structure.

Decorator, iterator, and visitor are related to the composite design pattern.

#### Bridge

The bridge pattern helps untangle an unnecessary complicated class hierarchy, especially when implementation specific classes are mixed together with implementation-indendent classes. So our problem here is that there are two parallel or orthogonal abstractions. One is implementation-specific, and the other one is implementation-independent.

And our scenario involves this implementation-independent circle abstraction and implementation-dependent circle abstraction. The implementation-dependent circle abstraction involves how to draw a circle, and implementation-independent circle abstraction involves how to define the properties of a circle and scale it. The key to our solution is not trying to abstract both implementation-specific and implementation-independent classes in a single class hierarchy.

The abstract factory and adaptor patterns are the related patterns to this rich design pattern.

## Behavioral Patterns

#### Observer

Observer establishes a one-to-many relationship between a subject and multiple observers. Our problem here is that a subject object need to be monitored, and other observer objects need to be notified when there is a change in the subject. In our scenario we need to be able keep track of core temperatures of reactors at a power plant. When there is a change in the core temperature registered observers need to be notified.

For our solution we need an abstract class called subject, which has interfaces that allow the operations, such as attaching, an observer detaching, an observer and notifying observers. We also need concrete subject classes inheriting from the abstracts subject class. Singleton is related to the observer design pattern.

#### Visitor

The Visitor design pattern allows adding new features to an existing class hierarchy without changing it. It is sometimes necessary to add new operations dynamically to existing classes with minimal changes. For our scenario, we present a House class. Visitors in this scenario include HVAC specialist and Electrician. HVAC specialist in our scenario is Visitor type 1 and Electrician is Visitor type 2.

The visitor pattern represents new operations to be performed on the various elements of an existing class hierarchy. Visitors can also provide operations on a composite object.

#### Iterator

The iterator pattern allows a client to have sequential access to the elements of an aggregate object without exposing its underlying structure. The problem is that some programmers overcrowd the traversal interfaces of an aggregate object for every possible way of iteration. We'll be building our own iterator that takes advantage of a built-in Python iterator called zip(). The iterator iterates through a list of German counting words.

It will iterate only up to a certain point based on a client input. An iterator isolates access and traversal features from an aggregate object. It also provides an interface for accessing the elements of an aggregate object. An iterator keeps track of the objects being traversed. One of the recommended solutions is to make the aggregate object create an iterator for a client. The composite design pattern is related to the iterator pattern.
```python
def count_to(count):
	"""Our iterator implementation"""
	
	#Our list
	numbers_in_german = ["eins", "zwei", "drei", "vier", "funf"]

	#Our built-in iterator
	#Creates a tuple such as (1, "eins")
	iterator = zip(range(count), numbers_in_german)
	
	#Iterate through our iterable list
	#Extract the German numbers
	#Put them in a generator called number
	for position, number in iterator:
		
		#Returns a 'generator' containing numbers in German
		yield number 

#Let's test the generator returned by our iterator
for num in count_to(3):
	print("{}".format(num))

for num in count_to(4):
	print("{}".format(num))
	
```

#### Strategy

The Strategy pattern offers a family of interchangeable algorithms to a client. The problem we often see is that there is a need for dynamically changing the behavior of an object. So we offer our Strategy class with its default behavior. When there is a need, we provide another variation of the Strategy class by dynamically replacing its default method with a new one.

Python allows adding methods dynamically by importing the types module.

#### Chain of responsibility 

Chain of Responsibility opens up various possibilities of processing for a given request. The Chain of Responsibility pattern decouples the request and its processing. Our given problem is that many different types of processing needs to be done depending on what the request is. In our scenario, we receive an integer value and then we use different handlers to find out its range. As our solution, we used Abstract Handler that stores a Successor who will handle a request if it is not handled at the current handler.

then Concrete Handlers check if they can handle the request. If they can, they handle it and return a true value indicating that the request was handled. Composite is related to the Chain of Responsibility design pattern.
