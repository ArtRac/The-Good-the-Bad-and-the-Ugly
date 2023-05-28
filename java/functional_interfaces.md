Interfejsy funkcyjne zostały wprowadzone do Javy 8 w ramach nowego pakietu java.util.function.  
Dzielą się na cztery podstawowe kategorie, których skrótowe opisy można zdefiniować w następujący sposób:

`Function <T, R>` – przyjmuje dowolny obiekt i zwraca dowolny obiekt (T, R),  
`Consumer <T>` – przyjmuje dowolny obiekt, ale nic nie zwraca (T, void),  
`Supplier <T>` – nic nie przyjmuje, ale zwraca dowolny obiekt (void, T),  
`Predicate <T>` – przyjmuje dowolny obiekt, ale zwraca boolean (T, boolean),  

I wiele innych na [docs.oracle.com](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)
  
---
##### Własny intefejs funkcyjny.  
```java
public interface Item {     

    String getDescription();
} 

public class Start {     

    public static void main(String[] args) {
    
        Item item = () -> "This is description for MovieItem";
        String description = item.getDescription();
        System.out.println(description);
    }  
}      
```
  
---
##### Interfejs Predicate:

Interfejs Predicate jest częścią pakietu java.util.function i reprezentuje funkcję, która przyjmuje argument i zwraca wartość typu boolean.
Posiada metodę test(T t), która sprawdza warunek na podstawie dostarczonego argumentu i zwraca wartość logiczną (true/false).
Przykład użycia:

```java
Predicate<Integer> isPositive = num -> num > 0;

boolean result = isPositive.test(5);
System.out.println(result);  // true
```
##### Interfejs Comparator:

Interfejs Comparator jest częścią pakietu java.util i jest używany do porównywania obiektów.
Posiada metodę compare(T o1, T o2), która porównuje dwa obiekty i zwraca wartość całkowitą reprezentującą wynik porównania.
Przykład użycia:

```java
Comparator<Integer> comparator = (num1, num2) -> num1.compareTo(num2);

int result = comparator.compare(5, 10);
System.out.println(result);  // -1 (num1 < num2)
```

Interfejsy Predicate i Comparator są często używane w Javie do sprawdzania warunków lub porównywania obiektów.
Dzięki nim można wygodnie przekazać funkcje do metod, które wymagają takiego typu funkcji jako argumentu, 
np. filtrowania kolekcji lub sortowania elementów.
