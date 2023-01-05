# Software Questions

I have listed some software technical questions that were asked in my interviews at Tesla, Amazon, and Google below.

## Questions from SWE interviews

Similar or even identical questions can be found on LeetCode.

- Parse string into dictionary
- Move all elements of a certain value in a list to the end
- Ping pong (simple multithreading)
- OOP (inheritance)
- Find the maximum MaximaCount out of all the categories in `categories`
    - `categories` is a string
    - The MaximaCount of character `c` representing a category in `categories` is the number indices `i` such that the
      frequency of `c` is maximum in the prefix of the string up to the index `i`
- Check similar passwords
    - `newPasswords` and `oldPasswords` are lists of strings
    - Return a list where the `i`th element is `"YES"` if `newPasswords[i]` and `oldPasswords[i]` are similar, else `"NO"`
        - Passwords are similar if there exists a set of characters in the new password that can be incremented by 1
          (e.g., `"z"` -> `"a`", `"a"` -> `"b"`) to make the old password a subsequence
            - Subsequence: a sequence that can be derived from the given sequence by deleting 0 or more elements without
              changing the order of the remaining elements
- Remove ancestors of a tree starting from the leaf nodes, removing newly created leaf nodes first
- Remove ancestors of a tree starting from the leaf nodes, removing newly created leaf nodes last
- [Stock price fluctuation](https://leetcode.com/problems/stock-price-fluctuation/)
- Given an equation as a string, calculate the final result
    - E.g., `"add(5,mul(2,pow(5,2)))"` -> `55.0`

## Questions from hardware & embedded interviews

- Multiply numbers up to 100 digits long
- Alphabetically sort a string
- Check, set, clear, and toggle a bit
- Polymorphism
    - See [40+ OOPs Interview Questions and Answers](https://www.interviewbit.com/oops-interview-questions/)
- Python questions
    - Datatypes
    - List vs array
    - Performance advantage of Numpy
- C/C++ questions
    - See [Top Embedded C Interview Questions](https://www.interviewbit.com/embedded-c-interview-questions/)

--8<-- "includes/abbreviations.md"
