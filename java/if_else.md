good
```java
if (value == null)
{
   value = newValue
}
```
better
```java
value = (value == null) ? newValue : value;
```
```java
value = Optional.ofNullable(value).orElse(newValue);
```
---

good
```java
if (value != null)
{
   value.doSomething();
}
```
better
```java
Optional.ofNullable(value).ifPresent(value::doSomething);
```
