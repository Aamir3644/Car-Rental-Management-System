## String Palindrome Checking in generic way :
- I have solved this coding problem using two-pointer approach
```java
        public class practice{

            static boolean PalindromeChecker(String str)
            {
                // Following Regex gives all characters which are not alphabets & numbers and replaceAll() methods removes them with empty string
                str = str.replaceAll("[^a-zA-Z0-9]","").toLowerCase() ;
                int left = 0 ;
                int right = str.length()-1 ;

                while(left < right)
                {
                    if(str.charAt(left) != str.charAt(right))
                    {
                        return false;
                    } 
                    left++ ;
                    right-- ;
                }
                return true;
            }

            public static void main(String[] args){
                
                String str = "aamir" ;

                if(PalindromeChecker(str))
                {
                    System.out.println("It is a Palindrome...");
                }
                else
                {
                    System.out.println("It is not a Palindrome...");	
                }
            }
        }      
```

## String Palindrome Checking with help of StringBuffer Class :
- I have solved this coding problem by converting String into StringBuffer and using StringBuffer helper methods
```java
        public class practice{

            static boolean PalindromeChecker(String str)
            {
                StringBuffer stfu = new StringBuffer(str);
                String rev = stfu.reverse().toString() ;
                if(str.equals(rev))
                {
                    return true;
                }
                return false;
            }

            public static void main(String[] args){
                
                String str = "nitin" ;

                if(PalindromeChecker(str))
                {
                    System.out.println("It is a Palindrome...");
                }
                else
                {
                    System.out.println("It is not a Palindrome...");	
                }
            }
        }
```

## How to find out frequency of each character in a String :
```java
        import java.util.* ;

        public class CharacterFrequency{

            static void frequencyCalculator(String str){
                HashMap<Character,Integer> map = new HashMap<>();


                char[] arr = str.toLowerCase().toCharArray();

                for(int i=0 ; i<arr.length ; i++)
                {
                    if(map.containsKey(arr[i]))
                    {
                        map.put(arr[i],map.get(arr[i])+1);
                    }
                    else
                    {
                        map.put(arr[i],1);
                    }
                }
                System.out.println(map);
            }

            public static void main(String[] args){
                String str = "Karnataka";
                frequencyCalculator(str);
            }
        }
```

## Number Palindrome Checking in generic way :
- We can also solve this problem if we convert the number into string and then convert that string into StringBuffer and after that using reverse() method of StringBuffer class, we can get the reverse of that number and find that number is palindrome or not.
```java
    public class ReverseNumber {

        public static void main(String[] args) {
            
            int number  = 1234;
            int original = number;
            int reverse = 0;
            int remainder = 0;

            while(number != 0){
                remainder = number % 10 ;
                reverse = reverse * 10 + remainder;
                number = number/10 ;
            }
            
            if(original == reverse)
            {
                System.out.println("The number is Palindrome...");
            }
            else
            {
                System.out.println("The number is not Palindrome...");
            }
        }
    }
```