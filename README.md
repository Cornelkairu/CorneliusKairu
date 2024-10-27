# CorneliusKairu
"""
Question 1:
Write a query  that will display the results below (Note: Some columns might  be  renamed but use the column names above). It should only show 2020 data and order by drivers points.

SELECT c.circuit_location AS location, rs.grid, d.driver_number AS position,rs.fastest_lap, rs.points, d.driver_name, r.race_name, rs.race_time AS time, YEAR(r.race_date) AS year, cs.team AS team_name, r.race_date AS date
FROM circuits c
LEFT JOIN races r
ON c.circuitid = r.circuitid
LEFT JOIN results rs
ON r.raceid = rs.raceid
LEFT JOIN drivers d
ON d.driverid = rs.driverid
LEFT JOIN constructors cs
ON rs.constructorid = cs.constructorid
WHERE YEAR(r.race_date) = 2020
ORDER BY rs.points

# Python script to check if a word is a palindrome.
"""
Question 2:
Write a Python function that checks whether a word or phrase is palindrome or
not.
Note: A palindrome is word, phrase, or sequence that reads the same
backward as forward, e.g., madam,kayak,racecar, or a phrase "nurses run"
"""


def check_palindrome(word):
  """
  - If it is a palindrome, it returns true, otherwise, false.
  - Using recursion.
  """
  if word == "" or len(word) == 1:
    return True

  if word[0] != word[-1]:
    return False

  return check_palindrome(word[1:-1])


print(check_palindrome("racecar"))  # returns true
print(check_palindrome_v2("hello"))  # returns false

"""
Question 3:
- Write a Python function to check whether a string is pangram or not. (Assume
the string passed in does not have any punctuation)
Note: Pangrams are words or sentences containing every letter of the
alphabet at least once. For example: "The quick brown fox jumps over the
lazy dog"
"""


def check_pangram(string: str) -> bool:
  # use a set to store unique characters of the given string
  letters = set(string.replace(" ", "").lower())
  return len(letters) >= 26


print(
  check_pangram("The quick brown fox jps over the lazy dog"))  # returns False

"""
Question 4:
-Write a program that takes an integer as input and returns an integer with
reversed digit ordering.
Examples:
For input 500, the program should return 5.
For input -56, the program should return -65.
For input -90, the program should return -9.
For input 91, the program should return 19.
"""


def reverse_digits(num: int) -> int:
  # Convert the number to a string and reverse it
  reversed_str = str(num)[::-1]
  # If the number is negative, add a '-' sign to the beginning
  if reversed_str[-1] == "-":
    reversed_str = "-" + reversed_str[:-1]
    return int(reversed_str)
  else:
    return int(reversed_str)

print(reverse_digits(56) #returns 65
"""
Question 5:
Write a program that accepts a string as input, capitalizes the first letter of each
word in the string, and then returns the result string.
Examples:
"hi"=> returns "Hi"
"i love programming"=> returns "I Love Programming"
"""


def capitalize_str(input_string):
  # Split the input string into words
  words = input_string.split()
  res = ""
  for word in words:
    # Capitalize the first letter of each word
    res += word.capitalize() + " "
    print(res)
  return res.rstrip()


print(capitalize_str("hi man hello how are you"))


