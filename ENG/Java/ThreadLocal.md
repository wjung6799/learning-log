# ThreadLocal

ThreadLocal is a construct that allows us to store fields in eac thread.

## API

The TheadLocal construct allows us to store data that will be **accessible only by a specific thread**.

Let's say that we want to have an *Integer* value that will be bundled with the specific thread

```java
ThreadLocal<Integer> threadLocalValue = new ThreadLocal<>();
```

Next, we can use get or set.

```java
threadLocalValue.set(1);
Integer result = threadLocalValue.get();
```
