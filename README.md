# Python_Notes
## Interfaces
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

It's kind of restriction for those classes wirtten below, which is good for creating a library.
In this example, AbstractClassExample is an abstract base class with an abstract method do_something. ConcreteClassExample is a subclass that implements the do_something method. **You cannot create an instance of AbstractClassExample because it has abstract methods that are not implemented**. Once do_something is implemented in a subclass, you can then create instances of that subclass.

**ABC-Person-Student/Employee (Person class is a subset of ABC class)**

## Groupby
```
import pandas as pd

# Example DataFrame
df = pd.DataFrame({
    'entity_id': [1, 1, 2, 2, 3, 3],
    'reg_description': ['A', 'B', 'A', 'C', 'B', 'C']
})

# Group by 'entity_id'
grouped = df.groupby('entity_id')

# Iterating over each group
for entity_id, group in grouped:
    print(f"Entity ID: {entity_id}")
    print(group, "\n")
```
