# Streams

[Streams Basics](Streams/Iterating)
[Streams/Creating Streams](Streams/Creating Streams)

Streams started with Java 8

**Central API**

```Stream<T>```


Should not be confused with Java I/O streams (ex: FileInputStream etc); they
have very little to do with each other

Streams are wrappers around a data source, allowing us to operate with that data
source and making bulk processing convenient and fast

**A stream does not store data, and in that sense, is not a data structure. It
also never modifies the underlying data source**

Streams bring functional programming to Java, and are supported from Java 8 and
on

Advantages of Streams:
- ParallelStreams make it very easy to do multi-thread operations
- Allow you to use Lambda Expressions, which are disposable functions


A Stream pipeline consists of
- a source; where data flows out of
- followed by 0 or more intermediate operations
- terminal operation

**Stream Source**

A Stream of elements

Streams can be created from :
- Collections,
- Lists,
- Sets,
- ints,
- longs,
- doubles,
- arrays,
- lines of a file


**Stream Operations**
Stream operations are either intermediate or terminal

- **Intermediate Operations** : such as :
    - filter
    - map
    - or sort
return a stream so we can chain multiple intermediate operations

- **Terminal Operations** : such as :
    - forEach,
    - collect
    - or reduce
are either void or return a non stream result


### Intermediate Operations



Zero or more intermediate operations are allowed
- Intermediate operations return another Stream which allows you to call
  multiple operations in the form of a query
- Traversal of the Stream does not begin until the Terminal Operation of the
  pipeline is executed
- Order matters for large datasets; filter first, then sort or map
- All stream operations are packaged in java.util.stream.Stream

For very large datasets use ParallelStream to enable multi-threading

Some Intermediate operations include :


|            |            |          |             |
| ---        | ----       | ---      | ---         |
| anyMatch() | distinct() | filter() | findFirst() |
| flatMap()  | map()      | skip()   | sorted()    |
| peek()     | limit()    | skip()   |             |


### Terminal Operations

Only one terminal operation is allowed
- forEach applies the same function to each element
- collect saves the elements into a collection
- other options reduce the stream to a single summary element

|                     |       |       |        |
|---------------------|-------|-------|--------|
| count()             | min() | max() | reduce |
| summaryStatistics() |       |       |        |
