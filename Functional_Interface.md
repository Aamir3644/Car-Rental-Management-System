## Functional Interface :  
```
    Those Interface which has exactly one abstract method.
    Functional interfaces are primarily designed to be used with lambda expressions.
    It can have multiple static and default methods, but it must have precisely one abstract method.This method represents the
    behaviour that can be implemented using lamda expressions.
    When you create an instance of a functional interface using a lambda expression, you're effectively providing an
    implementation for its single abstract method.
```
```
    Note : If you have array or list of user defined class and you try to sort that array or list using Arrays.sort() or 
           Collections.sort() without using comparable and comparator then it will give you compilation error cause it will not
           know on which basis it has to compare these objects. This error does not come up with array or collection that
           contains primitive data.
```
## Comparable :
```
            - compare this object with other object
            - Functional Interface
            - contains only one abstract method named "public int compareTo(T o)" for sorting objects.
            - When using comparable with user defined classes, that class has to implement Comparable interface with specifying
              generic type of that class e.g - Comparable<Employee> (if Employee class want to implement Comparable interface) 
              and you have to override compareTo() method also.
```
>> Example : 

```java
        import java.util.*;

        class Employee implements Comparable<Employee>{
            private int id;
            private String name;
    
            public Employee(int id,String name){
                this.id = id;
                this.name = name;
            }
            
            // Getters and Setters Here...
            
            @Override
            public String toString(){
                return "Employee id - "+id+" name - "+name;
            }
            
            public int compareTo(Employee other){
                return other.id -  this.id;
            }
        }

        public class Main
        {
	        public static void main(String[] args) {
            Employee e1 = new Employee(4,"Aamir");
            Employee e2 = new Employee(2,"Harsh");
            Employee e3 = new Employee(1,"Prajyot");
            Employee e4 = new Employee(3,"Avdhoot");
            
            Employee[] arr = {e1,e2,e3,e4};
            
            Arrays.sort(arr);
            
            System.out.println(Arrays.toString(arr));
	        }
        }

```
## Comparator :
```
        - compare two given objects
        - Functional Interface
        - it has only one abstract Method named " public int compare(T obj1, T obj2) " for sorting objects
```            
        Ways to Use Comparator :
```
        1) Making a Comparator Class implementing Comparator<T> and then creating object of that comparator class and passing
        that object as second parameter to Arrays.sort() or Collections.sort() or any methods that takes comparator as
        argument. 
```
```java

                class IdComparator implements Comparator<Employee>
                {
                @Override
                public int compare(Employee emp1,Employee emp2){
                        return emp1.getId()-emp2.getId() ;
                }      
                }

                public class Main
                {
                        public static void main(String[] args) {
                        
                                Employee[] arr = {e1,e2,e3,e4};
                                
                                IdComparator comp = new IdComparator();
                                
                                Arrays.sort(arr,comp);
                                
                                System.out.println(Arrays.toString(arr));
                        
                        }
                }

```
```
        2) By Passing anonymous object of Comparator Class as a parameter
```
```java
		 Arrays.sort(arr,new IdComparator()); //Anonymous Object
```
```
        3) By assigning Lambda to Comparator reference and then passing comparator object as a parameter
```
```java
        Comparator<Employee> comp = (emp1, emp2)-> emp1.getName().compareTo(emp2.getName());
        Arrays.sort(arr,comp);
```
```
        4) By using anonymous object of anonymous class
```
```java
                Arrays.sort(arr,new Comparator<Employee>(){
		     public int compare(Employee emp1,Employee emp2)
		     {
		         return emp1.getId() - emp2.getId();
		     }
		 });
```
We can make above code concise with the help of lambda
```java
        Arrays.sort(arr,(e1,e2) -> e1.getId - e2.getId); 
        // Java Compiler will able to know that e1 and e2 are of Employee cause, you made arr of Employee[] type.
        // In Lambda Expressions, the compiler performs type inference based on context in which it is used, It is one of the
        // advantages of Lambda.
```

