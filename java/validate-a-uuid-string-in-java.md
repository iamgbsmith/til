# Validate A UUID String In Java

__Category: Java__

You can validate a UUID string is in the correct format with the following Java code.

```java
import java.util.regex.Pattern;

public class UUIDValidator {

    private final static Pattern UUID_REGEX_PATTERN = Pattern.compile("^[{]?[0-9a-fA-F]{8}-([0-9a-fA-F]{4}-){3}[0-9a-fA-F]{12}[}]?$");

    public static boolean isValidUUID(String uuid) {
        if (uuid == null) {
            return false;
        }
        return UUID_REGEX_PATTERN.matcher(uuid).matches();
    }

}
```
