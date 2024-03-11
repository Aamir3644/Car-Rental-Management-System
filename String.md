## String :
>> String are immutable in java. Once they are created they can not be changed. If we try to change a String object (eg: str.concat("aamir")), a new String object will be created.


## StringBuffer :
>> StringBuffer are mutable. means we can perform changes in StringBuffer object once they are created and new object won't be created.


" == " operator always compares references. if only both references pointing towards same object then only it will return true.
" equals() " method : As we know every class is inherited from Object class in java. In Object class, the equals() method is already defined and it is defined for reference comparison. The equals() method is overridden in String class for content comparison and in StringBuffer it stil compares references.

## Why Strings are immutable in Java ?
>> so goal of any programming language is to make effecient use of memory. Its very common for String literals to occupy a lot of space, which can even cause redundancy. So in order to make Java more efficient JVM sets aside a special area in memory called "String Constant Pool". When we create a String Literal, it first checks that this literal is in string pool, if it is present in string pool. The reference will start pointing towards it, and if it is not present it will create a new literal. In the String Pool, more than one references can point towards a Single String Object and it would be bad if one reference changes string value. so thats why strings are immutable.
>> Also, in any application Strings are used for confidential data like password so it would pose a great security threat if Strings are not immutable. Hence Strings are immutable, so its value cannot be changed.