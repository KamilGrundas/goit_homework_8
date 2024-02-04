
# Homework #8

## Part I.
Initial Data:

We have a json file with authors and their properties: date and place of birth, a brief description of their biography. Content of the file `authors.json`.

```json
[
  {
    "fullname": "Albert Einstein",
    "born_date": "March 14, 1879",
    "born_location": "in Ulm, Germany",
    "description": "In 1879, Albert Einstein was born in Ulm, Germany. He completed his Ph.D. at the University of Zurich by 1909. His 1905 paper explaining the photoelectric effect, the basis of electronics, earned him the Nobel Prize in 1921. His first paper on Special Relativity Theory, also published in 1905, changed the world. After the rise of the Nazi party, Einstein made Princeton his permanent home, becoming a U.S. citizen in 1940. Einstein, a pacifist during World War I, stayed a firm proponent...
  },
  {
    "fullname": "Steve Martin",
    "born_date": "August 14, 1945",
    "born_location": "in Waco, Texas, The United States",
    "description": "Stephen Glenn "Steve" Martin is an American actor, comedian, writer, playwright, producer, musician, and composer. He was raised in Southern California in a Baptist family, where his early influences were working at Disneyland and Knott's Berry Farm and working magic and comedy acts at these and other smaller venues in the area. His ascent to fame picked up when he became a writer for the Smothers Brothers Comedy Hour, and later became a frequent guest on the Tonight Show.In the 197...
  }
]
```

We also have the following json file with quotes from these authors. Content of the file `quotes.json`.

```json
[
  {
    "tags": [
      "change",
      "deep-thoughts",
      "thinking",
      "world"
    ],
    "author": "Albert Einstein",
    "quote": "“The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”"
  },
  {
    "tags": [
      "inspirational",
      "life",
      "live",
      "miracle",
      "miracles"
    ],
    "author": "Albert Einstein",
    "quote": "“There are only two ways to live your life. One is as though nothing is a miracle. The other is as though everything is a miracle.”"
  },
  {
    "tags": [
      "adulthood",
      "success",
      "value"
    ],
    "author": "Albert Einstein",
    "quote": "“Try not to become a man of success. Rather become a man of value.”"
  },
  {
    "tags": [
      "humor",
      "obvious",
      "simile"
    ],
    "author": "Steve Martin",
    "quote": "“A day without sunshine is like, you know, night.”"
  }
]
```

Execution Procedure:

1. Create an Atlas MongoDB database.
2. Using Mongoengine ODM, create models to store data from these files in `authors` and `quotes` collections.
3. When saving quotes (`quotes`), the author field in the document should not be a string value but a Reference fields, in which the ObjectID from the `authors` collection is stored.
4. Write scripts to upload the json files to the cloud database.
5. Implement a script to search for quotes by tag, author's surname, or set of tags. The script runs in an infinite loop and uses a simple `input` statement accepts commands in the following format command: value.
   Example:

   - `name: Steve Martin` — find and return a list of all quotes by author Steve Martin;
   - `tag:life` — find and return a list of quotes for the tag life;
   - `tags:life,live` — find and return a list of quotes that contain the tags life or live (no space between the tags life, live);
   - `exit` — close the script;

Search results should only be displayed in utf-8 format;
