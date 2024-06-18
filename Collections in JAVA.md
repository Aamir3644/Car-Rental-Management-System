-> Collection is  nothing but a group of individual objects as a single entity.

## COLLECTION FRAMEWORK : (1.2)
>> It is an API which contains predefined classes and Interfaces, which can be used to represent group of individual objects as a single entity.
## COLLECTION (interface) :
>> It is the root interface (present in java.util package) of all the collection objects.
## COLLECTIONS (utility class) :
>> It is the utility class which contains only static methods for sorting, searching, etc. which is present in java.util package.

## Advantages Of Collection Framework :
>> Type Safety : The use of Generics in Collection Framework enhances type safety. so type related error will be resolved at
                 compile time only rather than runtime.
>> Dynamic Sizing : Most Collections resize themselves After certain limit size. so this Dynamic sizing gives us better memory
                    utilization.
>> Standard Algorithms : The collection framework has standard algorithm implementations like searching, sorting, iterating,    
                         which can be applied to various collections.So there is no need to write the code for this types of algorithms.
>> Concurrent Collections : The framework offers concurrent collections that allows safe manipulation by multiple threads.

## Why Map Interface does not extend Collection Interface ? 
>> So the one line answer to this will be " Because they are incompatible "
   The Collection interface has a method called add(Object o). The Map Interface can not have such method cause it stores values in Key-Value pair.

## Iterable :
>> It is an interface which has method called iterator(), which returns a Iterator over the elements of type T.

## Iterator :
>> It is a interface used for iterating over any collection like lists, sets, maps. Iterator only supports Forward Direction Iteration. 
>> Methods : 
            hasNext() : it checks that collection has more elements or not and return true or false according to it.
            next() :  returns the next element in the collection and moves the cursor forwards.
            remove() : it removes the last element from the colection returned by the iterator.

>> E.g :         
```java
               Iterator itr = list.iterator();
              // FORWARD TRAVERSAL
              while(itr.hasNext())
              {
                  System.out.print(itr.next() + " ");
              }
```

## ListIterator :
>> It is an subinterface of Iterator. It allows iteration in both forward and reverse direction within a list.
>> Methods :
            next() and hasNext() : same as Iterator
            hasPrevious() : it checks that collection has more elements when traversing in reverse direction and return true or
                            false according to it.
            previous() : returns the previous element in the list and moves the cursor backwards.
            nextIndex() : return the index of element that would be returned by subsequent call to next().
            previousNext() : return the index of element that would be returned by subsequent call to previous().
            set() : replaces the last element that was returned by next() or previous() 
            add() : adds the specified element in the list
            remove() : removes the last element that was returned by next() or previous().

>> E.g :         
```java
               ListIterator i = list.listIterator();
               // FORWARD TRAVERSAL
               while (i.hasNext()) 
               {
                   System.out.print(i.next() + " ");    
               }
               // REVERSE TRAVERSAL
                while (i.hasPrevious())
                {
                    System.out.print(i.previous() + " ");  
                }
```

## Fail-fast  vs  Fail-safe :
>> If state of collection is changed while iterating over that collection using a iterator then it fails and gives
   ConcurrentModificationException. then that iterator is said to be fail-fast iterator.

>> If iterator allows you to modify the underlying collection while iterating over that collection, then that iterator is said
   to be fail-safe iterator.
   e.g : CopyOnWriteArrayList, ConcurrentHashMap, etc.
   Internally what happens is a clone of that collection is made and iteration is done over that cloned collection and if we try to modify the collection then modification happens on that cloned collection and no Exception is thrown.

## Enumeration :
                 Used for traversing Vector
> Methods : boolean hasMoreElements()
            E nextElement()

## Synchronized and Unsynchronized Collections :
>> The Legacy collections like Vector, Stack, Hashtable, Properties were synchronized but there performance were low.
   After Java 1.2 all collections that came were unsynchronized.
   Collection classes can be made Synchronized by the use of Collections class methods. 
   e.g : syncList = Collections.synchronizedList
         syncMap = Collections.synchronizedMap
         syncSet = Collections.synchronizedSet

## List : (1.2)
>>        If we want to represent a group of individual elements as a single entity where Duplicates are allowed and Insertion
          order is preserved then we should go for list.

## Set :  (1.2)
>>        If we want to represent a group of individual objects as a single entity where Duplicates are not allowed and 
          Insertion Order not preserved then we should go for Set.

## SortedSet : (1.2)
>>         If we want to represent a group of individual objects as a single entity where Duplicates are not allowed and
           insertion of elements should be according to some sorting order then we should go for SortedSet.

## NavigableSet : (1.6)
>>         It is a child interface of SortedSet. It provides some methods for navigation purpose.

## Queue : (1.5)
>>          if we want to represent a group of individual objects prior to processing then we should go for Queue.
            Add and Delete can be done from different ends (front and rear)
>> Methods :  add()  -> add the element in queue and return true on success and throws IllegalStateException if no space is 
                        available.
              poll() -> returns the head element of the queue and removes it from queue or returns null if queue is empty
              peek() -> return head element of the queue but does not remove it or returns null if queue is empty
              remove() -> returns and removes head element
              offer() -> inserts given element in queue and does return true on success
              element() -> returns head of queue but does not remove it

## Deque :
>>         Add and Delete can be done from both the ends


## Map : (1.2)
>>       If we want to represent a group of indivisual objects as key value pairs then we should go for Map. Both Key and Value 
         are Objects, duplicated keys are not allowed but values can be duplicated.

## SortedMap : (1.2)
>>       If we want to represent a group of indivisual objects as key value pairs according to some sorting order of
         Keys then we should go for SortedMap.

## NavigableMap : (1.6)
>>                 It is a child interface of SortedMap. It provides some methods for navigation purpose.

## ArrayList :
>>             ArrayList is a implementation class of List interface. The ArrayList is internally a dynamically growable array.
               When we initialize an arraylist, its initial capacity would be 10. when we try to add 11th element in list, its capacity will get increased by 50% of initial capacity ( i.e 10+5 = 15 ). Internally what happens is new arraylist is created with new capacity and old arraylist is copied into it and then the reference of our old arraylist will now point towards new arraylist.

## LinkedList :
>>              Internally LinkedList is doubly linked list.
                Elements can be traversed using Iterator, ListIterator, or using index
                Inherited from List and Deque Interface.

## Vector : (1.0)
>>           Vector is a Legacy Collection Class. Internally Vector is a Dynamically growable array. Default capacity of vector 
             is 10 and when we try to add 11th element, capacity will get increased by its existing capacity (i.e 20)
             Vector has a method named elements() which returns Enumeration Object for traversing over a vector.
                

## Stack : (1.0)
>>          Stack is Legacy Collection Class, Inherited from Vector Class. 
            Synchronized but Slow performance
>> Methods :    push()   -> adds element into the stack   
                pop()    -> removes element from top of the stack and returns that element as return value of this function
                peek()   -> returns top element from stack but does not remove it
                empty()  -> checks if stack is empty or not and return boolean according to it
                search() -> searches the given element and return its position (numbered from 1 to n)            

## Priority Queue :
>>                  In Priority Queue, the order of insertion may or may not be same as the order of popping or printing of     
                    elements.
>>                  Default Initial Capacity of PriorityQueue is 11. 
>>                  The elements are popped according to priority and Priority is decided according to 2 Scenarios :

                    1) Natural Order : if you don't provide custom comparator while creating PriorityQueue then it is popped according to its natural ordering i.e ascending. The elements with low integer values will have higher priority.
                    
                    2) Custom Comparator : If we give custom comparator when creating PriorityQueue. This comparator decides the priority of elements. e.g :

```java 
PriorityQueue<Integer> pq = new PriorityQueue<>((a,b)-> b - a); // Descending Order
```   

## ArrayDeque :
>>              Internally, ArrayDeque is dynamically growable array.

## HashSet :
>>           Underlying Data Structure is Hash Table.
             Default Initial Capacity Of HashSet is 16.
             Duplicates are not allowed         
             add() method return type is boolean, so if try to insert duplicate value, it will not give error. It will return False.
             Insertion order is  not maintained. The printing order is not predictable, depends on internal hashing mechanism.
             It allows null but only one null value.
             Due to the Hashing technique, Hashset is good for searching operation.

## LinkedHashSet :
>>           It uses combination of Hashtable and LinkedList.
             Duplicates are not allowed.
             Maintains the insertion order, provides predictable iteration order.
             
## TreeSet :
>>           Duplicates are not allowed
             It keeps the elements in sorted. If we don't give Comparator specifically to define sorting order, elements gets stored in natural order.

## HashMap :
>>           Internally used Hash Table.
             It stores elements in Key-Value pairs.
             Duplicate Keys are not allowed.
             Only one null key is allowed.

>> map.put(1,"A");   =>    At first, the key is converted into hashcode integer value using hashcode(). 
                           Then, hashcode is converted into index of array (table) of buckets, generally using % operator.
                           According to index, it is inserted into appropriate bucket and if hash collision happens i.e if multiple Key-Value pairs exist already in that bucket, then LinkedList or Tree is used handle that according to that implementation.

>> map.get(1);       =>    At first, key is converted into hashcode integer value using hashcode().
                           Then, hashcode is converted into index of array (table) of buckets, generally using % operator.
                           Then, HashMap looks into calculated index. If only one Key-Vaue is there, then directly it will compare your given key with stored key with equals() method.
                           If multiple Key-Value Pairs are in the bucket, the  hashmap iterates and compares every Key with given Key with equals() method.
                           When a key in bucket matches the given key, then associated value is returned.

>> HashMap Iteration using EntrySet : 
   The entrySet() method returns a set of key-value pairs (entries) in the HashMap.

```java 
         HashMap<Integer,String> map = new HashMap<>();
         map.put(1,"A");
         map.put(2,"B");
         map.put(3,"C");

         // Here Map.Entry<Integer,String> represents the each key-value pair
         for(Map.Entry<Integer,String> entry : map.entrySet())
         {
            Integer key = entry.getKey();
            String value = entry.getValue();
            System.out.println(key+" "+value);
         }
```
>> Hashmap Iteration using KeySet :
   The keySet() method returns a set of keys from the Hashmap.

```java
         HashMap<Integer,String> map = new HashMap<>();
         map.put(1,"A");
         map.put(2,"B");
         map.put(3,"C");

         // Here Integer represents the type of each key, thats why are writing Integer not Set<Integer> in the loop
         for(Integer key : map.keySet())
         {
            String value = map.get(key);
            System.out.println(key+" "+value);
         }
```

## LinkedHashMap :
>>           It uses combination of hashtable and LinkedList.
             Insertion order is maintained.
         
## HashTable :
>>          Hashtable is old and synchronized version of HashMap. It has performance issues cause of synchronization.
            It does not guarantee specific order for key-value pair.



