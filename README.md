# String Capitalizer (Java OOP)

This is a simple Java program that demonstrates **Object-Oriented Programming (OOP)** by creating a utility method to capitalize each word in a given string.  

## 📌 Features
- Capitalizes the **first letter** of each word.  
- Converts the **rest of the letters** to lowercase.  
- Handles multiple spaces and empty strings.  

## 🛠️ How It Works
The `StringFormatter` class has a static method `capitalizeWords(String input)` which:
1. Splits the input string into words.  
2. Converts the first character of each word to uppercase.  
3. Converts the remaining characters to lowercase.  
4. Joins the words back into a single string.  

## 💻 Code Example

```java
public class StringFormatter {

    // Method to capitalize each word
    public static String capitalizeWords(String input) {
        if (input == null || input.isEmpty()) {
            return input;
        }

        // Split string into words
        String[] words = input.split("\\s+");
        StringBuilder result = new StringBuilder();

        for (String word : words) {
            if (word.length() > 0) {
                // Capitalize first letter + rest lowercase
                result.append(Character.toUpperCase(word.charAt(0)))
                      .append(word.substring(1).toLowerCase())
                      .append(" ");
            }
        }

        return result.toString().trim(); // remove extra space
    }

    // Main method to test
    public static void main(String[] args) {
        String text = "hello world from java oops";
        System.out.println("Original: " + text);
        System.out.println("Capitalized: " + capitalizeWords(text));
    }
}
