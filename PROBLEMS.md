# Two-hour Programming Checkpoint

**Date:** Friday, 9 October 2026  
**Duration:** 120 minutes  
**Exercises:** 19  
**Languages:** Any programming language

Complete the exercises below and follow [README.md](README.md) to submit your work.

## Common rules

- Implement each exercise as a callable function or method. The suggested names below identify the required behavior; idiomatic names in your language are welcome if you map them in your submission README.
- Inputs and expected results describe function calls, rather than a specific console input format.
- Arrays must preserve the order shown. Boolean results mean your language's native Boolean values. String results must match the specified spelling and capitalization.
- For exercises 2, 3, and 7, round the returned numeric results to two decimal places. Trailing zeros are optional for numeric values: `212` and `212.00` represent the same result. If you display these results as text, show two decimal places. Tests will avoid exact halfway rounding cases.
- Assume inputs satisfy each exercise's constraints; input validation is not required.
- Each function must produce the correct result on repeated calls with different inputs.
- Include runnable tests. [test-cases.json](test-cases.json) contains the complete expected results for all 177 published cases, including the 1000-element case in exercise 15.
- Explain your approach and its time and space complexity for each exercise. State the complexity of the code you actually submit.

## Exercise list

| # | Exercise |
| --- | --- |
| 1 | Swap Two Numbers |
| 2 | Convert Temperature |
| 3 | Simple and Compound Interest |
| 4 | Convert Seconds to Hours, Minutes, and Seconds |
| 5 | Absolute Value Without a Built-in Function |
| 6 | Integer Quotient and Remainder |
| 7 | Area and Perimeter of Shapes |
| 8 | Even or Odd |
| 9 | Positive, Negative, or Zero |
| 10 | Leap Year — One-line Condition |
| 11 | Convert Marks to a Letter Grade |
| 12 | Can Three Sides Form a Triangle? |
| 13 | Vowel or Consonant |
| 14 | Are Three Points Collinear? |
| 15 | Numbers from 1 to n |
| 16 | Multiplication Table |
| 17 | Sum of Even or Odd Numbers |
| 18 | Count Digits in an Integer |
| 19 | Sum of All Divisors of a Number |

## 1. Swap Two Numbers

**Suggested function:** `swapValues(a, b)`

### Task

Given two integers `a` and `b`, return a two-element array `[b, a]`.

### Constraints and required behavior

- Both inputs fit in a signed 32-bit integer: `-2147483648 <= a, b <= 2147483647`.
- The inputs may be negative, zero, or equal.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `a = 5, b = 7` | `[7,5]` |
| `a = -3, b = 9` | `[9,-3]` |
| `a = 0, b = 12` | `[12,0]` |
| `a = 8, b = 8` | `[8,8]` |
| `a = -5, b = -2` | `[-2,-5]` |
| `a = -2147483648, b = 2147483647` | `[2147483647,-2147483648]` |

For `a = 5` and `b = 7`, the value from `b` comes first and the value from `a` comes second.

## 2. Convert Temperature

**Suggested function:** `convertTemperature(temp, scale)`

### Task

Given a temperature `temp` and its current scale `scale`, return the temperature in the other scale, rounded to two decimal places.

- If `scale = "C"`, use `F = temp * 9 / 5 + 32`.
- If `scale = "F"`, use `C = (temp - 32) * 5 / 9`.

### Constraints and required behavior

- `temp` is a finite real number.
- `scale` is exactly `"C"` or `"F"`.
- Decimal arithmetic is required; fractional parts must not be lost.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `temp = 100, scale = "C"` | `212.00` |
| `temp = 32, scale = "F"` | `0.00` |
| `temp = 0, scale = "C"` | `32.00` |
| `temp = -40, scale = "C"` | `-40.00` |
| `temp = -40, scale = "F"` | `-40.00` |
| `temp = 98.6, scale = "F"` | `37.00` |
| `temp = 37.5, scale = "C"` | `99.50` |
| `temp = 75, scale = "F"` | `23.89` |

For `temp = 75` and `scale = "F"`, the Celsius result is approximately 23.8889, which rounds to 23.89.

## 3. Simple and Compound Interest

**Suggested function:** `calculateInterest(principal, rate, time)`

### Task

Return `[simpleInterest, compoundInterest]` for a starting `principal`, an annual percentage `rate`, and an integer number of years `time`.

Use these formulas:

- `simpleInterest = principal * rate * time / 100`
- `compoundInterest = principal * (1 + rate / 100)^time - principal`

Interest is compounded annually. Return the interest earned, and round each result to two decimal places.

### Constraints and required behavior

- `principal > 0` and `rate >= 0`; both may be real numbers.
- `time >= 0` and is an integer.
- `^` in the mathematical formula means exponentiation; use the appropriate operation in your language.
- Checkpoint inputs will be small enough for the resulting amounts to be representable.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `principal = 1000, rate = 5, time = 2` | `[100.00, 102.50]` |
| `principal = 10000, rate = 12, time = 2` | `[2400.00, 2544.00]` |
| `principal = 500, rate = 0, time = 3` | `[0.00, 0.00]` |
| `principal = 1000, rate = 5, time = 0` | `[0.00, 0.00]` |
| `principal = 2000, rate = 10, time = 1` | `[200.00, 200.00]` |
| `principal = 1500, rate = 4, time = 3` | `[180.00, 187.30]` |
| `principal = 2500, rate = 7.5, time = 2` | `[375.00, 389.06]` |

For `principal = 1000`, `rate = 5`, and `time = 2`, simple interest is 100.00 and compound interest is 102.50.

## 4. Convert Seconds to Hours, Minutes, and Seconds

**Suggested function:** `convertSeconds(totalSeconds)`

### Task

Given a non-negative integer `totalSeconds`, return `[hours, minutes, seconds]`.

Use whole hours, then the remaining whole minutes, then the remaining seconds. Hours represent elapsed time and may be greater than 23.

### Constraints and required behavior

- For this checkpoint, `0 <= totalSeconds <= 2147483647`.
- The returned minutes and seconds must each be between 0 and 59.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `totalSeconds = 3661` | `[1,1,1]` |
| `totalSeconds = 86399` | `[23,59,59]` |
| `totalSeconds = 0` | `[0,0,0]` |
| `totalSeconds = 59` | `[0,0,59]` |
| `totalSeconds = 60` | `[0,1,0]` |
| `totalSeconds = 3599` | `[0,59,59]` |
| `totalSeconds = 3600` | `[1,0,0]` |
| `totalSeconds = 90061` | `[25,1,1]` |
| `totalSeconds = 2147483647` | `[596523,14,7]` |

For 90061 seconds, the result is `[25, 1, 1]`; do not wrap the hours after a day.

## 5. Absolute Value Without a Built-in Function

**Suggested function:** `absoluteValue(n)`

### Task

Given an integer `n`, return its absolute value without using a built-in absolute-value function such as `abs`, `Math.abs`, or `fabs`.

### Constraints and required behavior

- `-2147483648 <= n <= 2147483647`.
- The result is non-negative.
- The result for the smallest input is 2147483648, which exceeds a signed 32-bit integer.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = -5` | `5` |
| `n = 42` | `42` |
| `n = 0` | `0` |
| `n = -1` | `1` |
| `n = 1` | `1` |
| `n = -2147483648` | `2147483648` |
| `n = 2147483647` | `2147483647` |

For `n = -5`, return 5. For `n = 0`, return 0.

## 6. Integer Quotient and Remainder

**Suggested function:** `divideWithRemainder(dividend, divisor)`

### Task

Given two integers, return `[quotient, remainder]` satisfying:

`dividend = divisor * quotient + remainder`

For this checkpoint, integer division truncates toward zero: discard the fractional part of the quotient. The nonzero remainder has the same sign as the dividend, and its absolute value is smaller than the absolute value of the divisor.

### Constraints and required behavior

- `divisor != 0`.
- Both inputs are in the signed 32-bit integer range.
- The quotient for `dividend = -2147483648` and `divisor = -1` is 2147483648, so the returned type must support it.
- Use the checkpoint's division convention even if your language's default integer division behaves differently.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `dividend = 17, divisor = 5` | `[3,2]` |
| `dividend = 3, divisor = 8` | `[0,3]` |
| `dividend = 20, divisor = 4` | `[5,0]` |
| `dividend = 0, divisor = 7` | `[0,0]` |
| `dividend = -17, divisor = 5` | `[-3,-2]` |
| `dividend = 17, divisor = -5` | `[-3,2]` |
| `dividend = -17, divisor = -5` | `[3,-2]` |
| `dividend = -3, divisor = 8` | `[0,-3]` |
| `dividend = -2147483648, divisor = -1` | `[2147483648,0]` |

For `-17 / 5`, the quotient is -3 and the remainder is -2, since `-17 = 5 * (-3) + (-2)`.

## 7. Area and Perimeter of Shapes

**Suggested function:** `areaAndPerimeter(shape, dims)`

### Task

Return `[area, perimeter]` for the requested shape, with each result rounded to two decimal places.

| Shape | Dimensions | Area | Perimeter |
| --- | --- | --- | --- |
| `"rectangle"` | `[length, width]` | `length * width` | `2 * (length + width)` |
| `"square"` | `[side]` | `side * side` | `4 * side` |
| `"circle"` | `[radius]` | `PI * radius * radius` | `2 * PI * radius` |
| `"triangle"` | `[a, b, c]` | `sqrt(s * (s - a) * (s - b) * (s - c))` | `a + b + c` |

For a triangle, `s = (a + b + c) / 2`. Use `PI = 3.14159`.

### Constraints and required behavior

- `shape` is one of the four listed lowercase strings.
- Dimensions are positive real numbers and have the correct length for the selected shape.
- Triangle inputs always describe a valid triangle.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `shape = "rectangle", dims = [4,3]` | `[12.00, 14.00]` |
| `shape = "rectangle", dims = [2.5,4]` | `[10.00, 13.00]` |
| `shape = "square", dims = [5]` | `[25.00, 20.00]` |
| `shape = "square", dims = [1.5]` | `[2.25, 6.00]` |
| `shape = "circle", dims = [1]` | `[3.14, 6.28]` |
| `shape = "circle", dims = [2]` | `[12.57, 12.57]` |
| `shape = "triangle", dims = [3,4,5]` | `[6.00, 12.00]` |
| `shape = "triangle", dims = [5,5,6]` | `[12.00, 16.00]` |
| `shape = "triangle", dims = [2,2,2]` | `[1.73, 6.00]` |

For a triangle with sides 3, 4, and 5, the area is 6.00 and the perimeter is 12.00.

## 8. Even or Odd

**Suggested function:** `evenOrOdd(n)`

### Task

Return `"Even"` if the integer `n` is divisible by 2; otherwise return `"Odd"`.

### Constraints and required behavior

- `n` is in the signed 32-bit integer range.
- The exact capitalization of the returned string matters.
- Zero is even.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 4` | `"Even"` |
| `n = -3` | `"Odd"` |
| `n = 0` | `"Even"` |
| `n = 1` | `"Odd"` |
| `n = -4` | `"Even"` |
| `n = -1` | `"Odd"` |
| `n = 2147483647` | `"Odd"` |
| `n = -2147483648` | `"Even"` |

Negative numbers follow the same rule: -4 is even, while -3 is odd.

## 9. Positive, Negative, or Zero

**Suggested function:** `classifyNumber(n)`

### Task

Return `"Positive"` if `n > 0`, `"Negative"` if `n < 0`, or `"Zero"` if `n = 0`.

### Constraints and required behavior

- `n` is an integer in the signed 32-bit range.
- Return exactly one of the three strings with the capitalization shown.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 5` | `"Positive"` |
| `n = 0` | `"Zero"` |
| `n = -5` | `"Negative"` |
| `n = 1` | `"Positive"` |
| `n = -1` | `"Negative"` |
| `n = 2147483647` | `"Positive"` |
| `n = -2147483648` | `"Negative"` |

Zero has its own classification; it is neither positive nor negative.

## 10. Leap Year — One-line Condition

**Suggested function:** `isLeapYear(year)`

### Task

Return `true` if the positive integer `year` is a leap year; otherwise return `false`.

A year divisible by 4 is a leap year, except that a year divisible by 100 is a leap year only if it is also divisible by 400.

### Constraints and required behavior

- `year` is a positive integer.
- Write the leap-year decision as a single Boolean expression on one line. Function declarations, braces, and test code may occupy additional lines.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `year = 2000` | `true` |
| `year = 1900` | `false` |
| `year = 2024` | `true` |
| `year = 2023` | `false` |
| `year = 2100` | `false` |
| `year = 2400` | `true` |
| `year = 4` | `true` |
| `year = 100` | `false` |
| `year = 400` | `true` |

2000 is a leap year because it is divisible by 400. 1900 is not, even though it is divisible by 4.

## 11. Convert Marks to a Letter Grade

**Suggested function:** `letterGrade(marks)`

### Task

Return the grade for integer `marks` using the following bands:

| Marks | Grade |
| --- | --- |
| 90–100 | `"A"` |
| 80–89 | `"B"` |
| 70–79 | `"C"` |
| 60–69 | `"D"` |
| 0–59 | `"F"` |

### Constraints and required behavior

- `0 <= marks <= 100`.
- Return an uppercase one-letter string.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `marks = 95` | `"A"` |
| `marks = 72` | `"C"` |
| `marks = 100` | `"A"` |
| `marks = 90` | `"A"` |
| `marks = 89` | `"B"` |
| `marks = 80` | `"B"` |
| `marks = 79` | `"C"` |
| `marks = 70` | `"C"` |
| `marks = 69` | `"D"` |
| `marks = 60` | `"D"` |
| `marks = 59` | `"F"` |
| `marks = 0` | `"F"` |

A mark of 90 belongs to A; a mark of 89 belongs to B. Test both sides of every boundary.

## 12. Can Three Sides Form a Triangle?

**Suggested function:** `isValidTriangle(a, b, c)`

### Task

Given three positive side lengths, return `true` if they can form a triangle with nonzero area; otherwise return `false`.

Equality at a triangle-inequality boundary does not form a valid triangle.

### Constraints and required behavior

- `a`, `b`, and `c` are positive real numbers.
- The side lengths can arrive in any order.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `a = 3, b = 4, c = 5` | `true` |
| `a = 1, b = 1, c = 2` | `false` |
| `a = 2, b = 2, c = 2` | `true` |
| `a = 2, b = 3, c = 6` | `false` |
| `a = 10, b = 2, c = 3` | `false` |
| `a = 3, b = 10, c = 2` | `false` |
| `a = 2, b = 3, c = 4` | `true` |
| `a = 1.5, b = 2.5, c = 3` | `true` |

Sides 1, 1, and 2 lie at the boundary and cannot enclose a triangle with nonzero area.

## 13. Vowel or Consonant

**Suggested function:** `vowelOrConsonant(ch)`

### Task

Given a single English alphabet letter `ch`, return `"Vowel"` if it is a, e, i, o, or u in either case. Return `"Consonant"` otherwise.

### Constraints and required behavior

- `ch` contains exactly one letter from `a`–`z` or `A`–`Z`.
- Return the exact strings shown.
- For this checkpoint, y is a consonant.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `ch = "a"` | `"Vowel"` |
| `ch = "Q"` | `"Consonant"` |
| `ch = "E"` | `"Vowel"` |
| `ch = "i"` | `"Vowel"` |
| `ch = "O"` | `"Vowel"` |
| `ch = "u"` | `"Vowel"` |
| `ch = "b"` | `"Consonant"` |
| `ch = "Z"` | `"Consonant"` |
| `ch = "y"` | `"Consonant"` |

Case does not change the classification: both e and E are vowels.

## 14. Are Three Points Collinear?

**Suggested function:** `areCollinear(x1, y1, x2, y2, x3, y3)`

### Task

Return `true` if the three points `(x1, y1)`, `(x2, y2)`, and `(x3, y3)` all lie on a single straight line. Otherwise return `false`.

### Constraints and required behavior

- Every coordinate is an integer in the signed 32-bit range.
- Horizontal and vertical lines are valid straight lines.
- Repeated points are allowed. Three points with two or more identical points are collinear.
- Arithmetic must remain correct for the full input range; intermediate values can exceed a signed 64-bit integer.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `x1 = 1, y1 = 1, x2 = 2, y2 = 2, x3 = 3, y3 = 3` | `true` |
| `x1 = 1, y1 = 1, x2 = 2, y2 = 2, x3 = 3, y3 = 5` | `false` |
| `x1 = 2, y1 = 1, x2 = 2, y2 = 4, x3 = 2, y3 = -3` | `true` |
| `x1 = 0, y1 = 5, x2 = 3, y2 = 5, x3 = -2, y3 = 5` | `true` |
| `x1 = -1, y1 = -1, x2 = 0, y2 = 0, x3 = 2, y3 = 2` | `true` |
| `x1 = 0, y1 = 0, x2 = 0, y2 = 0, x3 = 5, y3 = 7` | `true` |
| `x1 = 1, y1 = 1, x2 = 1, y2 = 1, x3 = 1, y3 = 1` | `true` |
| `x1 = -2147483648, y1 = -2147483648, x2 = 0, y2 = 0, x3 = 2147483647, y3 = 2147483647` | `true` |
| `x1 = -2147483648, y1 = -2147483648, x2 = 2147483647, y2 = -2147483648, x3 = -2147483648, y3 = 2147483647` | `false` |

The points `(2, 1)`, `(2, 4)`, and `(2, -3)` lie on the vertical line x = 2.

## 15. Numbers from 1 to n

**Suggested function:** `numbersFromOne(n)`

### Task

Return an array containing every integer from 1 through `n`, in increasing order.

### Constraints and required behavior

- `1 <= n <= 1000`.
- The result contains exactly `n` elements, starts with 1, and ends with `n`.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 5` | `[1,2,3,4,5]` |
| `n = 3` | `[1,2,3]` |
| `n = 1` | `[1]` |
| `n = 2` | `[1,2]` |
| `n = 8` | `[1,2,3,4,5,6,7,8]` |
| `n = 10` | `[1,2,3,4,5,6,7,8,9,10]` |

For `n = 1`, return `[1]`. Also test `n = 1000`: it must produce 1000 values in order, ending with 1000.

## 16. Multiplication Table

**Suggested function:** `multiplicationTable(n)`

### Task

Return an array of ten integers: the products from `n * 1` through `n * 10`, in order.

### Constraints and required behavior

- `-1000 <= n <= 1000`.
- The result always contains exactly ten elements.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 5` | `[5,10,15,20,25,30,35,40,45,50]` |
| `n = 7` | `[7,14,21,28,35,42,49,56,63,70]` |
| `n = 0` | `[0,0,0,0,0,0,0,0,0,0]` |
| `n = 1` | `[1,2,3,4,5,6,7,8,9,10]` |
| `n = -3` | `[-3,-6,-9,-12,-15,-18,-21,-24,-27,-30]` |
| `n = 1000` | `[1000,2000,3000,4000,5000,6000,7000,8000,9000,10000]` |
| `n = -1000` | `[-1000,-2000,-3000,-4000,-5000,-6000,-7000,-8000,-9000,-10000]` |

For `n = -3`, the first product is -3 and the tenth product is -30.

## 17. Sum of Even or Odd Numbers

**Suggested function:** `sumByParity(n, parity)`

### Task

Return the sum of all integers of the requested `parity` in the inclusive range from 1 through `n`.

If there are no matching numbers, return 0.

### Constraints and required behavior

- `0 <= n <= 10000`.
- `parity` is exactly `"even"` or `"odd"`.
- When `n = 0`, the range is empty.
- The sum fits in a signed 32-bit integer for this range.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 10, parity = "even"` | `30` |
| `n = 9, parity = "odd"` | `25` |
| `n = 0, parity = "even"` | `0` |
| `n = 0, parity = "odd"` | `0` |
| `n = 1, parity = "even"` | `0` |
| `n = 1, parity = "odd"` | `1` |
| `n = 2, parity = "even"` | `2` |
| `n = 5, parity = "even"` | `6` |
| `n = 5, parity = "odd"` | `9` |
| `n = 10000, parity = "even"` | `25005000` |
| `n = 10000, parity = "odd"` | `25000000` |

For `n = 10` and `parity = "even"`, add 2, 4, 6, 8, and 10 to obtain 30.

## 18. Count Digits in an Integer

**Suggested function:** `countDigits(n)`

### Task

Return the number of decimal digits in the absolute value of integer `n`.

The minus sign does not count as a digit. The number 0 has exactly one digit.

### Constraints and required behavior

- `-2147483648 <= n <= 2147483647`.
- Internal and trailing zeros count as digits.
- Handle both ends of the signed 32-bit range correctly.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 12345` | `5` |
| `n = -789` | `3` |
| `n = 0` | `1` |
| `n = 1` | `1` |
| `n = -1` | `1` |
| `n = 9` | `1` |
| `n = -9` | `1` |
| `n = 10` | `2` |
| `n = -10` | `2` |
| `n = 99` | `2` |
| `n = 100` | `3` |
| `n = -100` | `3` |
| `n = 1000` | `4` |
| `n = 10001` | `5` |
| `n = 999999999` | `9` |
| `n = 1000000000` | `10` |
| `n = 2147483647` | `10` |
| `n = -2147483648` | `10` |

For `n = -789`, count the three digits of 789. For `n = 1000`, all four digits count.

## 19. Sum of All Divisors of a Number

**Suggested function:** `sumDivisors(n)`

### Task

Return the sum of all positive divisors of positive integer `n`, including 1 and `n` itself.

A positive integer `d` is a divisor when `n` is divisible by `d` with no remainder. Count each divisor exactly once.

### Constraints and required behavior

- `1 <= n <= 1000000`.
- For `n = 1`, the only divisor is 1.
- The result fits in a signed 32-bit integer at this range.
- Use a 64-bit accumulator in languages with fixed-width integers. Languages with arbitrary-precision integers may use their normal integer type.

### Examples and test cases

| Input | Expected result |
| --- | --- |
| `n = 12` | `28` |
| `n = 6` | `12` |
| `n = 1` | `1` |
| `n = 2` | `3` |
| `n = 3` | `4` |
| `n = 4` | `7` |
| `n = 7` | `8` |
| `n = 9` | `13` |
| `n = 16` | `31` |
| `n = 28` | `56` |
| `n = 36` | `91` |
| `n = 49` | `57` |
| `n = 60` | `168` |
| `n = 97` | `98` |
| `n = 100` | `217` |
| `n = 999983` | `999984` |
| `n = 1000000` | `2480437` |

For `n = 12`, the divisors are 1, 2, 3, 4, 6, and 12, whose sum is 28. For `n = 36`, the sum is 91; divisor 6 is counted once.

## Final checks

1. Run every published test case and add any extra cases you need.
2. Check boundaries, zero where allowed, negative inputs where allowed, and repeated calls.
3. Confirm the two special restrictions: exercise 5 uses no built-in absolute-value function, and exercise 10 uses a one-line Boolean decision.
4. Check that someone else can run your source and tests using only the instructions in your submission README.
5. Push your final work and submit before the 120-minute deadline.

Published examples do not cover every valid input. Review your code against the full constraints.

