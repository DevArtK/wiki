# Iterating Using a Stream

Stream API helps to substitute for, for-each, and while loops

It allows concentrating on operation's logic, but not on the iteration over the
sequence of elements

```java
for (String s : list) {
    if (s.contains("a")) {
        return true;
    }
}
```

Stream equivalent:

```java
boolean ifExists = list.stream().anyMatch(e -> e.contains("a"));
```

## Filtering

The filter() method allows us to pick a stream of elements that satisfy a
predicate.

```java
ArrayList<String> list = new ArrayList<>();
list.add("Monday");
list.add("Tuesday");
list.add("Wednesday");
list.add("Thursday");
list.add("Friday");
list.add("January");
list.add("February");

Stream<String> stream = list.stream().filter(e -> e.contains("d"));
```

## Mapping

To convert elements of a Stream by applying a special function to them and to
collect these new elements into a Stream, use the ```map()``` method
expression to every element of the *initial stream*
```java
// Converts Stream<String> to the Stream<Path> by applying a specific lambda
List<String> uris = new ArrayList<>();
uris.add("C:\\My.txt");

Stream<Path> pathStream uris.stream().map(uri -> Paths.get(uri));
```

```java
// If you have a stream where every element contains its own sequence of elements
// and you want to create a stream of these inner elements, you should use flatMap()

List<Detail> details = new ArrayList<>();
details.add(new Detail());

Stream<String> stream = details.stream().flatMap(d -> d.getParts().stream());
```
In this example, we have a list of elements of type Detail. The *Detail* class
contains a field *parts*, which is a list<String>. With the help of
```flatMap()``` method, every element from the field *parts* will be extracted
and added to the new resulting stream.
After that, the initial *Stream\<Detail>* will be lost.


## Matching

Stream API gives a set of instructions to validate elements of a sequence
according to some predicate.

- anyMatch()
- allMatch()
- nonMatch()

```java
boolean isValid = list.stream().anyMatch(el -> el.contains("h"));       // true
boolean isValidOne = list.stream().allMatch(el -> el.contains("h"));    // false
boolean isValidTwo = list.stream().noneMatch(el -> el.contains("h"));   // false
```

For empty stream, the ```allMatch()``` method with any given predicate will
return true :
```java
Stream.empty().allMatch(Objects::nonNull);  // true
```
- This is a sensible default, as we can't find any element that doesn't satisfy
  the predicate

Similiarly, the ```anyMatch()``` method always returns ```false``` for empty
streams :
```java
Stream.empty().anyMatch(Objects::nonNull);      // false
```


## Reduction

Stream API allows reducing a sequence of elements to some value according to a
specified function with the help of the ```reduce()``` method of the type
```Stream```

This method takes two parameters :
- first: a start vaalue
- second: an accumulator function

```java
List<Integer> integers = Arrays.asList(1, 1, 1);
Integer reduced = integers.stream().reduce(0, (a, b) -> a + b); // result = 3
```


## Collecting

The reduction can also be provided by the ```collect()``` method of type
```Stream```

The operation is very handy in case of converting a stream to a ```Collection```
or ```Map``` and representing a stream in the form of a single string

There is a utility class ```Collectors``` which provides a solution for almost
all typical collecting operations.

```java
List<String> resultList =
    list.stream()
    .map(el ->
        el.toUpperCase())
    .collect(Collectors.toList());
```
