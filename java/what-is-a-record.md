# What Is A Record

__Category: Java__

A record is an immutable Java object that can be used for DTOs, value objects, and API responses. Records are alternatives to POJO classes and make it easier to work with data by reducing boilerplate code. Records provide a constructor, getters, and toString methods.

## Record objects

Assume a product object. Define a record for a product as follows:

```java
public record Product(UUID id, String sku, String description, BigDecimal price) { }
```

Instantiate the product object as follows:

```java
Product product = new Product(UUID.randomUUID(), "abc-1423132", "Giant TCR Advanced Disc 2 Pro Compact Road Bike", BigDecimal(4049.10));
```

Records can define custom constructors. For example, you can define a compact constructor which ignores all arguments, including the parentheses. Assignment of  fields happens automatically.

```java
public record Product(UUID id, String sku, String description, BigDecimal price) {

      public Product {
          if (price < 0) {
              throw new IllegalArgumentException("Price must be greater than zero.");
          }
     }
}
```

## Generic Records

You can also define generic record objects. For example:

```java
public record Pair<K, V>(K key, V value) {}
```

Instantiate as follows:

```java
Pair<String, Integer> pair = new Pair<>("abcd-1234", 94729857983);
```

__Note:__ Records were a preview feature in Java 14 and finalised in Java 17.
