# 2 - Common Prefix Length

Given a string, split the string into two substrings at every possible point. The rightmost substring is a suffix. The beginning of the string is the prefix. Determine the lengths of the common prefix between each suffix and the original string. Sum and return the lengths of the common prefixes. Return an array where each element i is the sum for string `i`.

Example

Consider the only string in the array inputs = `['abcabcd']`. Each suffix is compared to the original string

| Remove to leave Suffix | Suffix    | Common Prefix | Length |
|------------------------|-----------|---------------|--------|
| ''                     | 'abcabcd' | 'abcabcd'     | 7      |
| 'a'                    | 'bcabcd'  | ''            | 0      |
| 'ab'                   | 'cabdc'   | ''            | 0      |
| 'abc'                  | 'abcd'    | 'abc'         | 3      |
| 'abca'                 | 'bcd'     | ''            | 0      |
| 'abcab'                | 'cd'      | ''            | 0      |
| 'abcabc'               | 'd'       | ''            | 0      |


```
The sum is 7 + 0 + 0 + 3 + 0 + 0 + 0 = 10.
```

## Function Description
Complete the function commonPrefix as presented below:

```python
# Complete the 'commonPrefix' function below.
# The function is expected to return an INTEGER_ARRAY.
# The function accepts STRING_ARRAY inputs as parameter.

def commonPrefix(s: [str]):
    # Write your code here
        result = []

    if len(s)==0:
        return 0

    for arr in s:
        n = len(arr)
        Z = [0 for i in range(n)]
        L, R, k = 0, 0, 0

        # [L, R] make a window which matches
        # with prefix of arr
        for i in range(n):
            # if i>R nothing matches so we will
            # calculate Z[i] using naive way.

            if i > R:
                L, R = i, i


                while R < n and arr[R - L] == arr[R]:
                    R += 1
                Z[i] = R - L
                R -= 1
            else:

                # k = i-L so k corresponds to number
                # which matches in [L, R] interval.
                k = i - L

                # if Z[k] is less than remaining interval
                # then Z[i] will be equal to Z[k].
                # For example, str = "ababab", i = 3, R = 5
                # and L = 2
                if Z[k] < R - i + 1:
                    Z[i] = Z[k]
                else:
                    L = i
                    while R < n and arr[R - L] == arr[R]:
                        R += 1
                    Z[i] = R - L
                    R -= 1
        total = n
        #
        # # summation of the Z-values
        for i in range(n):
            total += Z[i]
        result.append(total)
    return result
```

