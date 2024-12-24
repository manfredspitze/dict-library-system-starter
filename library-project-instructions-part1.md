## Python Dictionaries: Library Project (Part 1)

### Overview

In this project, you'll learn how to use a dictionary to create a small library system for managing book data.
    details = library[isbn]
    print(f"Book found: {details['title']} by {details['author']} ({details['year']})")
Your library system will use:

- functions
- `if-else` statements
- a `main( )` function
- a `while` loop that displays a simple menu


### Your Dictionary

- At the top of your script, define an empty dictionary named `library`


### The `add_book( )` Function

- Takes four parameters:
    - `isbn`
    - `title`
    - `author`
    - `year`
- To the function body, use triple quotes to add a **docstring** that summarizes what the function does:

```python
def add_book(isbn, title, author, year):
    """Add a book to the library."""
```
- Then tell Python you want the `isbn` key to use a dictionary as its corresponding value:
```python
library['isbn'] = {
        'title': title,
        'author': author,
        'year': year
    }
```

- Lastly, build an `f-string` that confirms the book was added to the `library` dictionary:
```python
print(f"Book '{title}' added to the library.")
```
---

### The `view_books( )` Function

- This function takes no parameters
- Add a **docstring** to the function that says: `"""View all books in the library."""`
- Use the Python `len( )` function and an `if-else` statement to check if the libary is empty
    - If the library is empty, print a message to that effect
    - Otherwise, use a `for` loop and the dictionary `items ( )` method to loop through all the data for each book in the library:

    ```python
    else:
        # isbn is the key in the key-value pair
        # details represents the value in the key-value pair
        for isbn, details in library.items():
            print(f"ISBN: {isbn}")
            print(f"  Title: {details['title']}")
            print(f"  Author: {details['author']}")
            print(f"  Year: {details['year']}\n")
    ```
---

### The `search_book( )` Function

- Takes one parameter (`isbn`)
- Add a **docstring** to the function that says: `"""Search for a book by ISBN."""`
- Use an `if-else` statement and the `in` operator to search for a specific book in the library by its ISBN:

```python
if isbn in library:
    details = library[isbn]
    print(f"Book found: {details['title']} by {details['author']} ({details['year']})")
else:
    print("Book not found.")
```
---

### The `remove_book( )` Function

- Takes one parameter (`isbn`)
- Add a **docstring** to the function that says: `"""Remove a book from the library by ISBN."""`
- Use an `if-else` statement, the `in` operator, and the `pop( )` method to search by ISBN for a book to remove from the library:
```python
if isbn in library:
    removed_book = library.pop(isbn)
    print(f"Book '{removed_book['title']}' removed from the library.")
else:
    print("Book not found.")
```
---

