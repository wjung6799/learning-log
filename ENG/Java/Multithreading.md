# Multithreading

https://www.youtube.com/watch?v=r_MbozD32eo


## Two ways of doing multithreading

1. Extending Thread
2. Implement Runnable


If you implement runnable, all you have to do is override implementation of run method. However you would have to feed runnable object inside a thread.

If you extend thread, you don't have to create an instance of thread in order to run your method.

However since multiple interface is allowed in runnalbe, you can have an advantage of implementing different classes even inheritance!
