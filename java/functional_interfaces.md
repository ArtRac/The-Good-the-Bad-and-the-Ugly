Interfejsy funkcyjne zostały wprowadzone do Javy 8 w ramach nowego pakietu java.util.function.  
Dzielą się na cztery podstawowe kategorie, których skrótowe opisy można zdefiniować w następujący sposób:

**Supplier** - nie przyjmuje żadnego obiektu na wejściu, ale zwraca obiekt (dostawca)  
**Consumer** - przyjmuje obiekt na wejściu, ale niczego nie zwraca (konsumer)  
**Predicate** - przyjmuje obiekt na wejściu i zwraca wartość PRAWDA lub FAŁSZ (predykat)  
**Function** - przyjmuje obiekt na wejściu i zwraca obiekt na wyjściu (funkcja) 

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
