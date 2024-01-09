# Python_Notes
Here is a simple example of how to use ABCs in Python:

```
from abc import ABC, abstractmethod

class AbstractClassExample(ABC):
    
    @abstractmethod
    def do_something(self):
        pass

class ConcreteClassExample(AbstractClassExample):
    
    def do_something(self):
        return "I'm doing something!"
```

In this example, AbstractClassExample is an abstract base class with an abstract method do_something. ConcreteClassExample is a subclass that implements the do_something method. You cannot create an instance of AbstractClassExample because it has abstract methods that are not implemented. Once do_something is implemented in a subclass, you can then create instances of that subclass.
