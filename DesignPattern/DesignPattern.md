# Design Pattern

- [Design Pattern](#design-pattern)
  - [Creational Patterns](#creational-patterns)
    - [Factory - Class create multiple Object](#factory---class-create-multiple-object)
    - [Builder - Class helper create single Object](#builder---class-helper-create-single-object)
    - [Singleton - A class has only a single instance](#singleton---a-class-has-only-a-single-instance)
  - [Behavioural Patterns](#behavioural-patterns)
    - [Observer / PubSub - Listen notifying change of Object](#observer--pubsub---listen-notifying-change-of-object)
    - [Iterator - Objects that traverse collections](#iterator---objects-that-traverse-collections)
    - [Strategy - Same method in different Class, had different handle](#strategy---same-method-in-different-class-had-different-handle)
  - [Structural Patterns](#structural-patterns)
    - [Facade - Class like extention, Util, Helper](#facade---class-like-extention-util-helper)
    - [Adapter - Inject a Object into other Object, to Re-use it without create again](#adapter---inject-a-object-into-other-object-to-re-use-it-without-create-again)
    - [Abstract Factory: Creates an instance of several families of classes](#abstract-factory-creates-an-instance-of-several-families-of-classes)
    - [Composite: Call 1 func of Parent + Child Class.](#composite-call-1-func-of-parent--child-class)
    - [Decorator: Extend Class from Interface, Abstract class](#decorator-extend-class-from-interface-abstract-class)
- [Reference](#reference)


## Creational Patterns

### Factory - Class create multiple Object

```python
class Burger:
    def __init__(self, ingredients):
        self.ingredients = ingredients

    def print(self):
        print(self.ingredients)

class BurgerFactory:
    
    def createCheeseBurger(self):
        ingredients = ["bun", "cheese", "beef-patty"]
        return Burger(ingredients)
    
    def createDeluxeCheeseBurger(self):
        ingredients = ["bun", "tomatoe", "lettuce", "cheese", "beef-patty"]
        return Burger(ingredients)

    def createVeganBurger(self):
        ingredients = ["bun", "special-sauce", "veggie-patty"]
        return Burger(ingredients)

burgerFactory = BurgerFactory()
burgerFactory.createCheeseBurger().print()
burgerFactory.createDeluxeCheeseBurger().print()
burgerFactory.createVeganBurger().print()

# OUTPUT: ['bun', 'cheese', 'beef-patty'] ['bun', 'tomatoe', 'lettuce', 'cheese', 'beef-patty'] ['bun', 'special-sauce', 'veggie-patty']
```

### Builder - Class helper create single Object

```python
class Burger:
    def __init__(self):
        self.buns = None
        self.patty = None
        self.cheese = None

    def setBuns(self, bunStyle):
        self.buns = bunStyle
    
    def setPatty(self, pattyStyle):
        self.patty = pattyStyle
    
    def setCheese(self, cheeseStyle):
        self.cheese = cheeseStyle

class BurgerBuilder:
    def __init__(self):
        self.burger = Burger()

    def addBuns(self, bunStyle):
        self.burger.setBuns(bunStyle)
        return self
    
    def addPatty(self, pattyStyle):
        self.burger.setPatty(pattyStyle)
        return self
    
    def addCheese(self, cheeseStyle):
        self.burger.setCheese(cheeseStyle)
        return self  

    def build(self):
        return self.burger

# --------------------------
burger = BurgerBuilder() \
            .addBuns("sesame") \
            .addPatty("fish-patty") \
            .addCheese("swiss cheese") \
            .build()
```

### Singleton - A class has only a single instance

```python
class ApplicationState:
    instance = None

    def __init__(self):
        self.isLoggedIn = False

    @staticmethod
    def getAppState():
        if not ApplicationState.instance:  
            ApplicationState.instance = ApplicationState()
        return ApplicationState.instance

# --------------------------
appState1 = ApplicationState.getAppState()
print(appState1.isLoggedIn)

appState2 = ApplicationState.getAppState()
appState1.isLoggedIn = True

print(appState1.isLoggedIn)
print(appState2.isLoggedIn)

# OUTPUT: False True True
```

## Behavioural Patterns

### Observer / PubSub - Listen notifying change of Object

- It's common for different components of an app to respond to events or state changes, but how can we communicate these events?
The Observer pattern is a popular solution. We have a Subject (aka Publisher) which will be the source of events. And we could have multiple Observers (aka Subscribers) which will recieve events from the Subject in realtime.
- Listen change of Stage or Event

```python
class YoutubeChannel:
    def __init__(self, name):
        self.name = name

		# Store data 
        self.subscribers = []	

	# Send data
    def subscribe(self, sub):
        self.subscribers.append(sub)
    
	# Receive new data
    def notify(self, event):
        for sub in self.subscribers:
            sub.sendNotification(self.name, event)

# --------------------------
from abc import ABC, abstractmethod

class YoutubeSubscriber(ABC):
    @abstractmethod
    def sendNotification(self, event):
        pass

class YoutubeUser(YoutubeSubscriber):
    def __init__(self, name):
        self.name = name
    
    def sendNotification(self, channel, event):
        print(f"User {self.name} received notification from {channel}: {event}")

# --------------------------
channel = YoutubeChannel("neetcode")

channel.subscribe(YoutubeUser("sub1"))
channel.subscribe(YoutubeUser("sub2"))
channel.subscribe(YoutubeUser("sub3"))

channel.notify("A new video released")

# OUTPUT: 
# User sub1 received notification from neetcode: A new video released 
# User sub2 received notification from neetcode: A new video released 
# User sub3 received notification from neetcode: A new video released
```

### Iterator - Objects that traverse collections

```java
Iterator iterator = list.createIterator();

while(iterator.hasNext()){
    System.out.println(iterator.next());
}

// OUTPUT: 1 2 3
```

### Strategy - Same method in different Class, had different handle

- A Class may have different behaviour, or invoke a different method based on something we define (i.e. a Strategy). For example, we can filter an array by removing positive values; or we could filter it by removing all odd values. These are two filtering strategies we could implement, but we could add many more.

```python
# Different Filter every Class
from abc import ABC, abstractmethod

class FilterStrategy(ABC):

    @abstractmethod
    def removeValue(self, val):
        pass

class RemoveNegativeStrategy(FilterStrategy):

    def removeValue(self, val):
        return val < 0 

class RemoveOddStrategy(FilterStrategy):

    def removeValue(self, val):
        return abs(val) % 2

# --------------------------
class Values:
    def __init__(self, vals):
        self.vals = vals
    
    def filter(self, strategy):
        res = []
        for n in self.vals:
            if not strategy.removeValue(n):
                res.append(n)
        return res

values = Values([-7, -4, -1, 0, 2, 6, 9])

print(values.filter(RemoveNegativeStrategy())) # Output: [0, 2, 6, 9]
print(values.filter(RemoveOddStrategy()))	# Output: [-4, 0, 2, 6]
```

## Structural Patterns

### Facade - Class like extention, Util, Helper

- wrapper class contain function, like extention

```python
# Python arrays are dynamic by default, but this is an example of resizing.
class Array:
    def __init__(self):
        self.capacity = 2
        self.length = 0
        self.arr = [0] * 2 # Array of capacity = 2

    # Insert n in the last position of the array
    def pushback(self, n):
        if self.length == self.capacity:
            self.resize()
            
        # insert at next empty position
        self.arr[self.length] = n
        self.length += 1

    def resize(self):
        # Create new array of double capacity
        self.capacity = 2 * self.capacity
        newArr = [0] * self.capacity 
        
        # Copy elements to newArr
        for i in range(self.length):
            newArr[i] = self.arr[i]
        self.arr = newArr
        
    # Remove the last element in the array
    def popback(self):
        if self.length > 0:
            self.length -= 1 
```

### Adapter - Inject a Object into other Object, to Re-use it without create again

- Adapters allow incompatible objects to be used together. Following the Open-Closed principle, we can extend class behaviour without modifying the class itself.
- Example: If a MicroUsbCable class is initially incompatible with UsbPort, we can create a wrapper class (i.e. an Adapter), which makes them compatible. In this case, a MicroToUsbAdapter makes them compatible, similar to how we use adapters in the real-world.

```python
class UsbCable:
    def __init__(self):
        self.isPlugged = False
    
    def plugUsb(self):
        self.isPlugged = True

class UsbPort:
    def __init__(self):
        self.portAvailable = True
    
    def plug(self, usb):
        if self.portAvailable:
            usb.plugUsb()
            self.portAvailable = False

# UsbCables can plug directly into Usb ports
usbCable = UsbCable()
usbPort1 = UsbPort()
usbPort1.plug(usbCable)

class MicroUsbCable:
    def __init__(self):
        self.isPlugged = False
    
    def plugMicroUsb(self):
        self.isPlugged = True

class MicroToUsbAdapter(UsbCable):
    def __init__(self, microUsbCable):
        self.microUsbCable = microUsbCable
        self.microUsbCable.plugMicroUsb()

    # can override UsbCable.plugUsb() if needed

# MicroUsbCables can plug into Usb ports via an adapter
microToUsbAdapter = MicroToUsbAdapter(MicroUsbCable())
usbPort2 = UsbPort()
usbPort2.plug(microToUsbAdapter)
```

### Abstract Factory: Creates an instance of several families of classes

### Composite: Call 1 func of Parent + Child Class.

-  A tree structure of simple and composite objects

```java
public abstract class TaskItem {
  public abstract double getTime();
}

public class Task extends TaskItem {
  String name;
  double time;
  // Constructor, getter và setter
  // ...
  @Override
  public double getTime() {
    return time;
  }
}

public class Project extends TaskItem {
  String name;
  ArrayList<TaskItem> subTasks = new ArrayList<>();
  // Constructor, getter và setter
  // ...
  @Override
  public double getTime() {
    double time = 0;
    for (TaskItem task : subTasks) {
      time += task.getTime();
    }
    return time;
  }
  public void addTask(TaskItem taskItem) {
    subTasks.add(taskItem);
  }
  public void removeTask(TaskItem taskItem) {
    subTasks.remove(taskItem);
  }
}


// -----------------------------
Task task1 = new Task("Task 1", 50);
Task task2 = new Task("Task 2", 34);
Task task3 = new Task("Task 3", 65);
Task task4 = new Task("Task 4", 23);

ArrayList<TaskItem> subTasks = new ArrayList<>();
subTasks.add(task1);
subTasks.add(task2);

Project project1 = new Project("Project 1", subTasks);

subTasks = new ArrayList<>();
subTasks.add(task3);
subTasks.add(task4);

Project project2 = new Project("Project 2", subTasks);

ArrayList<TaskItem> projects = new ArrayList<>();
projects.add(project1);
projects.add(project2);


// Calculate Time of All Project

/* mainProject {
    project1 {
        task1,
        task2
    }
    project2 {
        task3,
        task4
    }
 }
*/
Project mainProject = new Project("Main Project", projects);
System.out.println("Total time for Main Project: " + mainProject.getTime());
```

### Decorator: Extend Class from Interface, Abstract class

---

# Reference

- https://neetcode.io/courses/lessons/8-design-patterns
- https://viblo.asia/p/composite-design-pattern-tro-thu-dac-luc-cua-developers-Qbq5QBk3KD8