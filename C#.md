## What is C# ?
- C# is a high-level, object-oriented programming language developed by Microsoft for building Windows applications and web services. It's commonly used for developing various types of software.

## What are the differences between value types and reference types in C# ?
- Value types holds the actual data directly within the memory location , while reference types store a reference to the data. 
- Value types include simple types like int, double, etc., and are stored on the stack, while reference types like classes, interfaces, and delegates are stored on the heap.
- When passed as a parameter, value types are passed by value meaning a copy is sent to the method.
- When passed as a parameter, reference types are passed by reference so the changes made in the method will affect the original object.

## Explain the difference between the `==` operator and the `.Equals()` method in C#.
- The `==` operator compares object references, while the `.Equals()` method is used to compare the content or values of objects.

## Explain Delegate
- Delegates in C# is a type that represents references to methods. It works like function pointers which are present in C and C++.
- Delegate always points to a method that matches its specific signature.
```C#
    public class Program
    {
        // Declare a delegate
        public delegate void MyDelegate(string message);

        public static void Main(string[] args)
        {
            // Create an instance of the delegate
            MyDelegate del = new MyDelegate(MethodA);
            
            // Invoke the delegate
            del("Hello from MethodA");
        }

        public void MethodA(string msg)
        {
            Console.WriteLine(msg);
        }
    }
```

## Boxing & Unboxing
- Boxing is the process of converting a value type into a reference type directly. Boxing is implicit.
- Unboxing is the process where reference type is converted back into a value type. Unboxing is explicit.
```C#
        int a = 10;      // a value type
        object o = a;     // boxing
        int b = (int)o;   // unboxing
```

## Difference between Abstract class and interface

- **Abstract Class**
- Abstract classes are those classes which can not be instantiated. They contain both abstract methods and concrete methods.
- A class can only inherit only one class
- It is used when you want to provide a common base class with default behavior that can be overridden.

```C#
        public abstract class Animal
        {
            public abstract void MakeSound(); // Abstract method
        }

        public class Dog : Animal
        {
            public override void MakeSound()
            {
                Console.WriteLine("Bark");
            }
        }
```

- **Interface**
- An interface is a blueprint for a class that defines a set of abstract methods. Any class implementing the interface must provide concrete implementations for those methods.
- A class can implement multiple interfaces.
- From C# 8.0, classes can have interface default methods.

```C#
        public interface IAnimal
        {
            void MakeSound(); // Method signature
        }

        public class Dog : IAnimal
        {
            public void MakeSound()
            {
                Console.WriteLine("Bark");
            }
        }
```

## Method overloading
- A class can have multiple methods with the same name but with different parameter list (number or type of parameters)
```C#
        public class Calculator
        {
            public int Add(int a, int b)
            {
                return a + b;
            }

            public int Add(int a, int b, int c)
            {
                return a + b + c;
            }

            public double Add(double a, double b)
            {
                return a + b;
            }
        }

        var calc = new Calculator();
        Console.WriteLine(calc.Add(2, 3)); // Calls Add(int, int)
        Console.WriteLine(calc.Add(2, 3, 4)); // Calls Add(int, int, int)
        Console.WriteLine(calc.Add(2.5, 3.5)); // Calls Add(double, double)
```
## Method overriding
- A derived class can provide implementation for a method which is already defined in its base class.

```C#
        public class Animal
        {
            public virtual void MakeSound()
            {
                Console.WriteLine("Some generic animal sound");
            }
        }

        public class Dog : Animal
        {
            public override void MakeSound()
            {
                Console.WriteLine("Bark");
            }
        }

        Animal myDog = new Dog();
        myDog.MakeSound(); // Outputs: Bark
```

## Built-in Generic Delegates

(1) `Func` Delegate
- The Func delegate represents a method that can return a value and take one or more parameters.
```C#
        Func<int, int, int> add = (a, b) => a + b;
        int result = add(3, 4);
        Console.WriteLine(result); // Outputs: 7
```

(2) `Action` Delegate
- The Action delegate represents a method that does not return a value and can take zero or more parameters.
```C#
        Action<string> greet = name => Console.WriteLine("Hello, " + name);
        greet("Alice"); // Outputs: Hello, Alice   
```

(3) `Predicate` Delegate
- The Predicate delegate represents a method that takes one parameter and returns a boolean value. It is commonly used for methods that needs to check a condition. 
```C#
        Predicate<int> isEven = num => num % 2 == 0;
        bool result = isEven(4);
        Console.WriteLine(result); // Outputs: True
```

## `using` keyword in C#
- The using keyword helps you include namespaces so you can use the classes and methods without typing the full namespace every time.
- The using keyword is also used to manage resources, such as file handles, database connections, or network connections. It ensures that resources are properly released when they are no longer needed, even if an exception occurs.
