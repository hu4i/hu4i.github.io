---
title: "Haskell Note"
date: 2023-04-10T08:49:08+08:00
draft: true
---

Chapter 1: [http://learnyouahaskell.com/starting-out](http://learnyouahaskell.com/starting-out)

- The name of a function can’t begin with uppercase letters
- When a function doesn't take any parameters, we usually say it's a *definition*
 (or a *name)*
- ghci
  - :l xxx.hs  (load haskell source code)
  - :r   (reload all)
- List
  - List operations
    - Operator ++ (append)is not efficient, while : (cons) operator is.
    - Operator !! is used as indexing
    - Lists can be compared if the stuff they contain can be compared. They are compared in lexicographical order.
    - List operations that return element: head, tail, last, init. be careful not to use them on empty lists
    - Calculation on list: length, null, maximum, minimum, sum, product, elem
    - List operations that return list: take, drop, cycle, repeat
  - range ..
  - list comprehension [ output | predicates ]
- Tuple
  - there is no singleton tuple
  - Operation on pair: fst, snd
  - zip: combine two lists into list of pairs

Chapter2 [Types and Typeclasses](http://learnyouahaskell.com/types-and-typeclasses)

- ghci
  - :t express (calculate the type)
  - If a function is comprised only of special characters (like +,-,*,==), it's considered an infix function by default. If we want to examine its type, pass it to another function or call it as a prefix function, we have to surround it in parentheses.
- :: is used as type declaration
- common types
  - Int (efficient)
  - Integer
  - Float
  - Double
  - Bool
  - Char
  - () (the type of () is () and the only value of () is ())
- type variable (type is written in capital case) is in lower case
- type class
  - => class constraint
  - type classes
    - Eq
      - function compare returns Ordering (a type of which values can be GT, LT, EQ)
    - Ord
    - Show
      - function show takes a type belongs to Show
    - Read
      - function read takes a string and returns a type belongs to Read
    - Enum
      - members are sequentially ordered types
    - Bounded
      - members have an upper and a lower bound.
      - **minBound and maxBound are polymorphic constants**
    - Num
      - Its members have the property of being able to act like numbers.
    - Integral
    - Floating
- :: can be used as type annotations

## Chapter3 **[Syntax in Functions](http://learnyouahaskell.com/syntax-in-functions)**

- Pattern Matching
  - When defining functions, you can define separate function bodies for different patterns.
  - the order of the catch-all pattern is matter
    - edge condition first
  - wildcard: `_` or `any-unused-name`
  - bind pattern to name: `name@pattern`, eg `nonEmptyList@(x::xs)`

    ```Haskell
    bmiTell :: (RealFloat a) => a -> String  
    bmiTell bmi  
    | bmi <= 18.5 = "You're underweight, you emo, you!"  
    | bmi <= 25.0 = "You're supposedly normal. Pffft, I bet you're ugly!"  
    | bmi <= 30.0 = "You're fat! Lose some weight, fatty!"  
    | otherwise   = "You're a whale, congratulations!"  
    ```
