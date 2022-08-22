# 1 - Alphabet Filter

Given a string consisting of only lowercase characters, create two methods that remove all the consonants or vowels from the given word. They must retain the original order of the characters in the returned strings. 

Example:

s = `"onomatopoeia"`

- The filter_vowels method removes all vowels from s and returns the string `"nmtp"`.
- The filter_consonants method removes all consonants from s and returns the string `"ooaooeia"`.


## Function Description

For a given definition of a class LetterFilter, complete its methods filter_vowels and filter_consonants. The class takes a string in the constructor and stores it to its s attribute. The method filter_vowels must return a new string with all vowels removed from it. Similarly, the method filter_consonants must return a new string with all consonants removed from it.

```python
class LetterFilter:
    def init(self, s):
        self.s = s
    
    def validation(self):
        vowels = [True for st in s if st not in "aeiou"]  
        if ((s.isalpha()==False) | (all(value)==True)):
            return True
        else:
            retrun False

    def filter_vowels(self):
        if validation() == True:
           return ""
        for ch in "aeiou" :     
            if ch in s :
                s = s.replace(ch,"")
        return s

    def filter_consonants(self):
        if validation() == True:
           return ""
        for ch in s :
            if ch not in "aeiou" :
                s = s.replace(ch,"")      
        return s
    
```

## Constraints
The string contains only lowercase letters in the range `ascii[a-z]` The string contains at least one vowel and at least one consonant.


