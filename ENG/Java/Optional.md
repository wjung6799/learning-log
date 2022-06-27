# Optional

## Overview

The purpose of the class is to provide a type-level solution for representing optional values instead of null.

https://www.baeldung.com/java-optional


The reason

```java

if (optional.isPresent())
{

}
else
{

}

```

looks similar to null check and we insist using Optional is because this is to let the users know that null can be returned.


Instead of using get() of Optional, use OrElse()
