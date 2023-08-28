# Count Words In A String

__Category: Python__

You can use the `split()` function to count words in a string. 

The following method will strip whitespace from the start and end of a string, tokenize a string based on the space character, and return the length of the list which is the number of words.

```python
def count_words(string):
    word_count = (len(string.strip().split(" ")))
    print("Word count", word_count)
    return word_count
```
