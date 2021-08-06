# Check If A String Value Is Numeric

__Category: Java__

You can check if a string value is numeric using the following method:

```java  
public boolean isNumeric(final String input) {
    if (input == null || input.length() == 0) {
        return false;
    }
    return input.chars().allMatch(Character::isDigit);
}
```
