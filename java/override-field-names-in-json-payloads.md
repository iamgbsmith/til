# Override Field Names In JSON Payloads

__Category: Java__

Jackson will attempt to map the payload field to corresponding member variables of the same name in the target class when serialising and deserialising JSON payloads.

Assume a JSON payload of:

```json
{
    "orgId": "14CAB554-86B",
    "ac": "13321245"
}
```

You can override this as follows:

```java
/**
 * Wrapper class example.
 */
public class LicenseRegistration {

    @JsonProperty(value = "orgId")
    private String organisationId;

    @JsonProperty(value = "ac")
    private String accessCode;

}
```
