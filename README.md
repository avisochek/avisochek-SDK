# LOTR SDK

The LOTR SDK is a python SDK for retrieving book titles, movie titles, characters and quotes related to the Lord of the Rings Trilogy. It is built as a client to [the one API](https://the-one-api.dev), which provides data on the lord of the rings.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the requests library and the LOTR SDK.

```bash
pip install requests
pip install avisochek-sdk
```
You will also need an API key from the one API, which you can get by signing up [here](https://the-one-api.dev/sign-up).

## Usage

```python
from LOTR.lotr import LOTR
from pprint import PrettyPrinter
pp = PrettyPrinter()

# initialize a client
lotr = LOTR(`<your API Key>`)

# Get a list of books.
list_of_books = lotr.get_book_info()
print("Lord Of The Rings Books:")
pp.pprint(list_of_books)

# Get a list of movies.
list_of_movies = lotr.get_movie_info()
print("Lord Of The Rings Movies:")
pp.pprint(list_of_movies)

# Get a list of characters.
list_of_characters = lotr.get_character_info()
print("10 Characters From Lord of the Rings:")
pp.pprint(list_of_characters[0:10])

movie_id = list_of_movies[6]["_id"]
movie_name = list_of_movies[6]["name"]
# Get a list of quotes from a particular movie
# (only works for lord of the rings trilogy for now)
quotes_from_movie = lotr.get_quotes_from_movie(movie_id)
print(f"10 Quotes From {movie_name}:")
pp.pprint(quotes_from_movie[0:10])

# Get a list of quotes from a particular character
quotes_from_frodo = lotr.get_quotes_from_character("5cd99d4bde30eff6ebccfc15")
print("10 Quotes From Frodo Baggins:")
pp.pprint(quotes_from_frodo[0:10])

book_id = list_of_books[0]["_id"]
book_name = list_of_books[0]["name"]
# Get a list of chapters from the first book
book_chapters = lotr.get_book_chapters(book_id)
print(f"Chapters From {book_name}:")
pp.pprint(book_chapters)

```

## License
[MIT](https://choosealicense.com/licenses/mit/)