## Difference between Library and Framework :
>> Libraries provide developers with predefined functions and classes to make their work easier and boost the development process. Framework, on the other hand, is like the foundation upon which developers build applications for specific platforms.

## What is the difference between Authentication and Authorization ?
>> Authentication : 
- Authentication is the process of verifying the identity of a user or a device . It answers the question, "Who are you?"
- Authentication is typically achieved through the presentation of credentials, such as usernames and passwords.
- The goal of authentication is to confirm that the entity trying to access a system or resource is indeed the entity it claims to be.
- Once authentication is successful, the system can trust that the user or entity is who they claim to be, but it doesn't necessarily grant access to specific resources or actions.

>> Authorization :
- Authorization is the process of determining what actions or resources an authenticated user, device, or system entity is allowed to access. It answers the question, "What are you allowed to do?"
- It involves checking the permissions associated with an authenticated identity and comparing them to the permissions required for a particular action or resource.

## What is difference between Encode and Encryption ?
>> Encode:

- Encoding is a process of converting data from one format to another. It doesn't involve making the data secret or secure; it's primarily about representation.
- Encoding is about changing the representation of data, often for compatibility or readability purposes
- Encoding is typically reversible, meaning you can decode the encoded data to get back the original data.
- Examples of encoding include URL encoding (e.g., converting spaces to "%20")

>> Encryption:

- Encryption is about making data secure and confidential by converting it into an unreadable format to protect it from unauthorized access,  that can be reversed only with the appropriate key or method.
- The primary purpose of encryption is to ensure data confidentiality and security.
- Examples of encryption include encrypting files with a password, using HTTPS to secure data transmitted over the internet.

## What is JWT ?
>>  "JWT stands for JSON Web Token. It is a compact and self-contained way to represent information between two parties in a secure manner. JWTs are commonly used for authentication and authorization in web applications. They consist of three parts: a header, a payload, and a signature. The header typically specifies the type of token and the signing algorithm used, while the payload contains claims or data. JWTs are digitally signed, ensuring their integrity, and can be used to verify the identity of the sender. They are often used for single sign-on (SSO) and secure data exchange between services in a distributed system."

>> JWT are stateless, it means that JWT does not rely on the server to maintain any session state for authentication and authorization purposes. In other words, every piece of information needed to verify and process a JWT is contained within the token itself.
>> Stateless authentication with JWTs is highly scalable because any server in a cluster can independently verify the token's authenticity without needing to communicate with other servers or a central session store.

## Statically Typed and Dynamically Typed :
>> Statically Typed Languages:
  In statically typed languages, variable types are determined at compile-time, which means that the type of a variable is known and checked by the compiler before the program is run. This provides the following advantages:

  Type Safety: Statically typed languages catch type-related errors at compile-time, reducing the likelihood of runtime errors caused by type mismatches.

  Performance: Because the types are known at compile-time, the compiler can often optimize the code more aggressively, leading to potentially faster execution.

  Examples of statically typed languages include C, C++, Java, and Rust. In these languages, you typically need to declare the type of a variable explicitly, like int x; or String name;.

>> Dynamically Typed Languages:

  In dynamically typed languages, variable types are determined at runtime. This means that you don't need to specify the type of a variable when declaring it, and the type of a variable can change during the program's execution. This provides the following advantages and challenges:

  Flexibility: Dynamically typed languages allow for more flexible and concise code since you don't have to declare types explicitly.

  Ease of Use: They are often considered more beginner-friendly because you can work with variables without worrying about their types.

  Runtime Errors: However, type-related errors might only surface at runtime, making debugging potentially more challenging.

  Examples of dynamically typed languages include Python, JavaScript, Ruby, and PHP. In these languages, you can simply write x = 5 without specifying the type.

## Implicit Type Coercion in JS :
>> String Coercion :
```
    String coercion takes place while using the ‘ + ‘ operator. When a number is added to a string, the number type is always converted to the string type. and then concatination happens.
```
```js
        var x = 3;
        var y = "3";
        x + y // Returns "33" 
```

```
    Type coercion also takes place when using the ‘ - ‘ operator, but the difference while using ‘ - ‘ operator is that, a string is converted to a number and then subtraction takes place.
```
```js
        var x = 3;
        var y = "3";
        x - y    //Returns 0 since the variable y (string type) is converted to a number type
```

>> Boolean Coercion :
```
    Truthy values are those which will be converted (coerced) to true. Falsy values are those which will be converted to false.
    All values except false, 0, 0n, -0, “”, null, undefined, and NaN are truthy values.
```
```js
        var x = 0;
        var y = 23;
        if(x) { console.log(x) }   // The code inside this block will not run since the value of x is 0(Falsy)
        if(y) { console.log(y) }    // The code inside this block will run since the value of y is 23 (Truthy)
```

>> Logical Operators :
```
    Logical operators in javascript, unlike operators in other programming languages, do not return true or false. They always return one of the operands.
    
    OR ( | | ) operator - If the first value is truthy, then the first value is returned. Otherwise, always the second value gets returned.
    
    AND ( && ) operator - If both the values are truthy, always the second value is returned. If the first value is falsy then the first value is returned or if the second value is falsy then the second value is returned.

```
## Here's how the == operator works in JavaScript:

- If the two operands have the same data type, JavaScript performs a strict equality comparison, which checks if they have the same value.

- If the two operands have different data types, JavaScript will attempt to coerce one or both of them to a common data type before making the comparison.

- If one operand is a primitive value (string, number, boolean), and the other is an object, JavaScript will attempt to convert the object to a primitive value using the valueOf() and toString() methods of the object.

- If one operand is null and the other is undefined, they are considered equal.

- If one operand is a number and the other is a string, JavaScript will try to convert the string to a number and then perform the comparison.
