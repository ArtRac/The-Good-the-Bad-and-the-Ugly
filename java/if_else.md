### good
```java
if (value == null)
{
   value = newValue
}
```
```java
value = Optional.ofNullable(value).orElse(newValue);
```

### better
```java
value = (value != null) ? value : newValue;
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
