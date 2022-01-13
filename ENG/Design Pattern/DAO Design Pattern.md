# DAO Design Pattern

Dao Stands for Data Access Object. It is used to separate the data persistence logic in a separate layer.

Data Persistence involves saving data in a non-volatile storage system so that the data's value can be retrieved reliably later.

Using this we don't have to know where the data is retrieved.
This acquires separation of logic

When designing DAO pattern, we have following components on which our design depends
- The model which is transferred from one layer to the other
- The interfaces which provides a flexible design
- The interface implemetation which is a concrete implementation of the persistence logic

![image](https://user-images.githubusercontent.com/41399709/149393699-c1719b85-0069-4340-b97c-cce8201a404c.png)

```

package com.journaldev.model;

public class Books {

    private int isbn;
    private String bookName;

    public Books() {
    }

    public Books(int isbn, String bookName) {
        this.isbn = isbn;
        this.bookName = bookName;
    }

    // getter setter methods
}
```

```
package com.journaldev.dao;

import com.journaldev.model.Books;

import java.util.List;

public interface BookDao {

    List<Books> getAllBooks();
    Books getBookByIsbn(int isbn);
    void saveBook(Books book);
    void deleteBook(Books book);
}
```

```

package com.journaldev.daoimpl;

import com.journaldev.dao.BookDao;
import com.journaldev.model.Books;

import java.util.ArrayList;
import java.util.List;

public class BookDaoImpl implements BookDao {

    //list is working as a database
    private List<Books> books;

    public BookDaoImpl() {
        books = new ArrayList<>();
        books.add(new Books(1, "Java"));
        books.add(new Books(2, "Python"));
        books.add(new Books(3, "Android"));
    }

    @Override
    public List<Books> getAllBooks() {
        return books;
    }

    @Override
    public Books getBookByIsbn(int isbn) {
        return books.get(isbn);
    }

    @Override
    public void saveBook(Books book) {
        books.add(book);
    }

    @Override
    public void deleteBook(Books book) {
        books.remove(book);
    }
}
```
