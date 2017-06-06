# Collection Summary
 In Python, a protocol is a set of operations or methods that a type must support if it is to implement that protocol. Protocols needn't be defined in the source code as separate interfaces or base classes as they would in an anomaly typed language such as C# or Java. It's sufficient to simply have an object provide functioning implementations of those operations. We can organize the different collections we've encountered in Python according to which protocols they support. Support for protocol demands specific behavior from a type.

## Collection protocols
| Protocol | Implementing Collections|
| ------------- |:-------------:|
|Container | str, list, range, tuple, bytes, set, dict|
|Sized | str, list, range, tuple, bytes, set, dict|
|Iterable | str, list, range, tuple, bytes, set, dict|
|Sequence | str, list, range, tuple, bytes, set, dict|
|Mutable Sequence| list|
|Mutable Set|set|
|Mutable Mapping| dict|

## Protocols
To implement a protocol, objects must support certain operations.
- The container protocol requires that membership testing using the in and not in operators be supported.
- The size protocol requires that the number of elements in a collection can be determined by passing the collection to the built-in len function
- Iterable Protocol can produce an iterator with iter(s)
- The sequence protocol requires that items can be retrieved using square brackets with an integer index, that items can be searched for with the index method, that items can be counted with the count method, and that a reversed copy of the sequence can be produced with the reversed built-in function
