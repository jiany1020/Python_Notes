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

## Problems Curious about in PA#1

**Q1 : why in this code a = 37?**
```
def _hash(self, key):
        a = 37
        m = self._capacity
        hash_value = 0
        for i in range(len(key)):
            hash_value = (hash_value * a + ord(key[i])) % m
        return hash_value
```

ChatGPT:
The choice of a = 37 in your hash function is part of the design of a specific type of hash function known as a polynomial rolling hash function. In this context, a is a constant that is used as a multiplier in the calculation of the hash value for a string. The reason for choosing a particular value like 37 involves a balance of efficiency and distribution.

Here's why a value like 37 is chosen:

1. Prime Number: It's common to choose a prime number in hash functions because it tends to provide a good distribution of hash values for keys. Prime numbers are less likely to produce regular patterns that could lead to clustering in the hash table, which in turn reduces the likelihood of collisions.
