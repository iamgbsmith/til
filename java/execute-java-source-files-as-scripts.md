# Execute Java Source Files As Scripts

__Category: Java__

The `java` command can be used to run a single class file without requiring manual compilation making it suitable for simple scripting purposes.

Add a shebang line as the first entry in the file to resolve to the location of the `java` executable followed by `--source` and the Java version the code was written for. The filename can use any extension.

For example:

```java
#!/path/to/bin/java --source 18

import java.time.format.DateTimeFormatter;  
import java.time.LocalDateTime;   

public class DoSomething {

    public static void main(String[] args) {
        DateTimeFormatter dtf = DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss");  
        LocalDateTime now = LocalDateTime.now();  
        System.out.println(dtf.format(now));  
    }
}
```

Update the file permission using `chmod +x` to make it executable then run it.
