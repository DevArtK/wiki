# Practical Uses of Java 8 Streams; Creation, Parallel Execution

## Stream Creation

There are many ways to create a stream instance of different sources.

Once created, the instance **will not modify its source**, therefore allowing
the creation of multiple instances from a single source


## Empty Stream


```java
Stream<String> emptyStream = Stream.empty();
```

Often used is the ```empty()``` method upon creation to avoid returning a *null* for
streams with no element :

```java
public Stream<String> streamOf(List<String> list) {
    return list == null || list.isEmpty() : Stream.empty() : list.stream();
}
```


## Stream of Collection

We can also create a stream of any type of *Collection (Collection, List, Set)*

```java
Collection<String> collection = Arrays.asList("A", "B", "C");
Stream<String> collectionStream = collection.stream();
```


## Stream of Array

An array can also be the source of a stream :

```java
Stream<String> arrStream = Stream.of("A", "B", "C");
```

Or create a stream out of an existing array or of part of an array :

```java
String[] arr = new String[]{"1", "2", "3", "4"};

Stream<String> wholeArr = Arrays.stream(arr);
Stream<String> partArr = Arrays.stream(arr, 1, 3);
```


## Stream.build()

When builder is used, the desired type should be additionally specified in the
right part of the statement, otherwise ```build()``` method will create an
instance of the Stream<Object>

```java
Stream<String> streamBuilder =
Stream.<String>builder().add("a").add("b").add("c").build();
```



## Stream.generate()

The ```generate()``` method accepts a ```Supplier<T>``` for element generation.

As the resulting stream is infinite, the developer should specify the desired
size, or the ```generate()``` method will work until it reaches the memory limit
:

```java
Stream<String> streamGen = Stream.generate(() -> "element").limit(10);
```



## Stream.iterate()
