# Checked Exception vs Unchecked Exception

Exception is an unwanted or unexpected event and there are two tpes of exceptions.

## 1. Checked exception

Checked exceptions are checked at compile time. If some code within a method throws a checked exception then the method must either handle the exception or it must specify the exception using the throws key word.

A fully chekced exception is a checked exception where all its child classes are also chekced, like IOException, InterruptedException. A partially checked exception is a checked exception where osf of its child classes are unchekced like Exception.

Basically in a nutshell, with checked exception misplaced it does not compile


## 2. Unchecked Exception

Unchekced Exceptions are not handled by compiler but it is handled in runtime thus RuntimeException.
