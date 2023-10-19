-> Collection is  nothing but a group of individual objects as a single entity.

## COLLECTION FRAMEWORK : (1.2)
>> It is an API which contains predefined classes and Interfaces, which can be used to represent group of individual objects as a single
   entity.
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
   The Collections interface has a method called add(Object o). The Map Interface can not have such method cause it stores values in Key-Value pair.

## Iterable :
>> It is an interface which has method called iterator(), which returns a Iterator over the elements of type T.

## Iterator :
>> It is a interface used for iterating over any collection like lists, sets, maps. Iterator only supports Forward Direction Iteration. 
>> Methods : 
            hasNext() : it checks that collection has more elements or not and return true or false according to it.
            next() :  returns the next element in the collection and moves the cursor forwards.
            remove() : it removes the last element from the colection returned by the iterator.

E.g :         Iterator itr = list.iterator();
              `` FORWARD TRAVERSAL ``
              while(itr.hasNext())
              {
                  System.out.print(itr.next() + " ");
              }

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

E.g :         ListIterator i = list.listIterator();
               `` FORWARD TRAVERSAL ``
               while (i.hasNext()) 
               {
                   System.out.print(i.next() + " ");    
               }
                `` REVERSE TRAVERSAL ``
                while (i.hasPrevious())
                {
                    System.out.print(i.previous() + " ");  
                }

## List : (1.2)
          If we want to represent a group of individual elements as a single entity where Duplicates are allowed and Insertion order is preserved then we should go for list.

## Set :  (1.2)
          If we want to represent a group of individual objects as a single entity where Duplicates are not allowed and Insertion Order not preserved then we should go for Set.

## SortedSet : (1.2)
               If we want to represent a group of individual objects as a single entity where Duplicates are not allowed and inse rtion of elements should be according to some sorting order then we should go for SortedSet.

## NavigableSet : (1.6)
                  It is a child interface of SortedSet. It provides some methods for navigation purpose.

## Queue : (1.5)
           if we want to represent a group of individual objects prior to processing then we should go for Queue.

## Map : (1.2)
         If we want to represent a group of indivisual objects as key value pairs then we should go for Map. Both Key and Value are Objects, duplicated keys are not allowed but values can be duplicated.

## SortedMap : (1.2)
                If we want to represent a group of indivisual objects as key value pairs according to some sorting order of Keys then we should go for SortedMap.

## NavigableMap : (1.6)
                   It is a child interface of SortedMap. It provides some methods for navigation purpose.


