
Introduction to Maps
In C#, the Dictionary<TKey, TValue> class represents a collection of keys and values. Each key must be unique,
and each key maps to exactly one value. Dictionaries are implemented using hash tables, providing average time
complexity of O(1) for operations like insertion, deletion, and lookup.

Creating a Dictionary
To create a dictionary in C#, you need to specify the types for the keys and values. Here's an example
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Dictionary<string, int> ageDictionary = new Dictionary<string, int>();

        ageDictionary.Add("Alice", 30);
        ageDictionary.Add("Bob", 25);
        ageDictionary.Add("Charlie", 35);

        int aliceAge = ageDictionary["Alice"];
        Console.WriteLine("Alice's Age: " + aliceAge);
    }
}
Accessing Values
To access a value, use the key inside square brackets:
int bobAge = ageDictionary["Bob"];
Console.WriteLine("Bob's Age: " + bobAge);

Removing Elements
Use the Remove method to remove a key-value pair from the dictionary:
ageDictionary.Remove("Alice");

Iterating Through a Dictionary
foreach (KeyValuePair<string, int> entry in ageDictionary)
{
    Console.WriteLine(entry.Key + ": " + entry.Value);
}

You can iterate through a dictionary using a foreach loop:
foreach (KeyValuePair<string, int> entry in ageDictionary)
{
    Console.WriteLine(entry.Key + ": " + entry.Value);
}

Conclusion
In this tutorial, you learned the basics of using dictionaries in C#. Dictionaries are powerful data structures that allow for efficient
data manipulation using key-value pairs. By understanding how to create, add, access, check, remove, and iterate through dictionaries,
you can leverage their capabilities to solve various programming problems efficiently.

For further reading and more advanced usage, consider exploring the official Microsoft documentation on Dictionaries in C#.

Feel free to reach out if you have any questions or need additional help!
