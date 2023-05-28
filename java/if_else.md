### good
```java
if (value == null)
{
   value = newValue
}
```

### better
```java
value = (value != null) ? value : newValue;

//1. Gdy nie powinna być null.
var result = Objects.requireNonNull(value);
//2. Gdy ma prawo być null.
//IF-ELSE
var result = Optional.ofNullable(value).orElse(defaultValue));
//IF
Optional.ofNullable(input).ifPresent(v -> println(v));
//lub
Optional.ofNullable(input).ifPresent(Sysyem.out::println);
//---------------------------------
StringUtils.isBlank(null)      = true
StringUtils.isBlank("")        = true  
StringUtils.isBlank(" ")       = true  
StringUtils.isBlank("bob")     = false  

StringUtils.isEmpty(null)      = true
StringUtils.isEmpty("")        = true  
StringUtils.isEmpty(" ")       = false  
StringUtils.isEmpty("bob")     = false  

StringUtils.isNotEmpty(String param)
//----------------------------------------------------
Objects.nonNull(Object obj)
Objects.isNull(Object obj)

```
---

### good
```java
if (value != null)
{
   value.doSomething();
}
```
### better ?
```java
Optional.ofNullable(value).ifPresent(value::doSomething);
```
---
Under construction
### ugly
### better

Ciekawa konstrukcja !!!!
```java
return divBy3 && divBy5 ? "FizzBuzz"
    : divBy3 ? "Fizz"
    : divBy5 ? "Buzz"
    : String.valueOf(i);
```

```java
import java.util.HashMap;
import java.util.Map;
import java.util.function.Supplier;

public class Main {
    public static void main(String[] args) {
        Map<Integer, Supplier<String>> mapa = new HashMap<>();
        mapa.put(1, () -> "Wartość dla przypadku 1");
        mapa.put(2, () -> "Wartość dla przypadku 2");
        mapa.put(3, () -> "Wartość dla przypadku 3");

        int zmienna = 2; // Przykładowa wartość zmiennej

        if (mapa.containsKey(zmienna)) {
            String value = mapa.get(zmienna).get();
            System.out.println(value);
        } else {
            System.out.println("Wartość dla pozostałych przypadków");
        }
    }
}
```
