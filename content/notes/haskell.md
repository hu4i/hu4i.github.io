---
title: "Haskell Notes"
date: 2023-04-10T08:49:08+08:00
summary: "Just some notes, nothing interesting."
draft: false
tags: ["haskell"]
---

This note is basically a pruned copy of Miran Lipovača's book named [*Learn You a Haskell for Great Good!*](http://learnyouahaskell.com/) under [Creative Commons Attribution-Noncommercial-Share Alike 3.0 Unported License](http://creativecommons.org/licenses/by-nc-sa/3.0/). I copied too much so I have to mention this :D.

I have tried Coq, Rust and OCaml before, therefore I only record something I don't know or I don't familiar here.

## Chapter 2 Starting Out

The [link](http://learnyouahaskell.com/starting-out) to this chapter.

An interactive interface: ghci

- `ghci>:l xxx.hs`  (load haskell source code)
- `ghci>:r`   (reload all)

### Basics

Logical operators:

```haskell
ghci> True && False  
False  
ghci> True && True  
True  
ghci> False || True  
True   
ghci> not False  
True
```

Testing for equality:

```haskell
ghci> 5 == 5
True
ghci> 5 /= 4  
True
```

Function definition:

```haskell
doubleMe x = x + x
doubleUs x y = doubleMe x + doubleMe y 
doubleSmallNumber x = if x > 100  
                        then x  
                        else x*2 
conanO'Brien = "It's a-me, Conan O'Brien!"
```

{{< admonition warning "Warning" true>}}

- The name of a function can’t begin with uppercase letters
- `if ... then ...` is an expression, so `else` is mandatory.

{{< /admonition >}}

{{< admonition info "Info" false >}}
When a function doesn't take any parameters, we usually say it's a definition (or a name).
{{< /admonition >}}

### List

```haskell
ghci> let lostNumbers = [4,8,15,16,23,42] 
ghci> lostNumbers  
[4,8,15,16,23,42]
```

Append `++` and cons `:`:

```haskell
ghci> [1,2,3,4] ++ [9,10,11,12]
[1,2,3,4,9,10,11,12]
ghci > 5:[1,2,3,4,5]
[5,1,2,3,4,5]
ghci> 'A':" SMALL CAT"  
"A SMALL CAT"
```

Indexing:

```haskell
ghci> "Steve Buscemi" !! 6  
'B'  
ghci> [9.4,33.2,96.2,11.2,23.25] !! 1  
33.2 
```

Lists can be compared if the stuff they contain can be compared. They are compared in lexicographical order.

```haskell
ghci> [3,2,1] > [2,1,0]  
True  
ghci> [3,2,1] > [2,10,100]  
True  
ghci> [3,4,2] > [3,4]  
True  
ghci> [3,4,2] > [2,4]  
True  
ghci> [3,4,2] == [3,4,2]  
True
```

Functions involving tuple:

- `head`, `tail`, `last`, `init`:

  ```haskell
  ghci> head [5,4,3,2,1]  
  5   
  ghci> last [5,4,3,2,1]  
  1   
  ghci> init [5,4,3,2,1]  
  [5,4,3,2]   
  ghci> tail [5,4,3,2,1]  
  [4,3,2,1]  
  ```

- `take`, `drop`, `elem`:

  ```haskell
  ghci> take 3 [5,4,3,2,1]  
  [5,4,3]
  ghci> take 0 [6,6,6]  
  []
  ghci> drop 3 [8,4,2,1,5,6]  
  [1,5,6]  
  ghci> drop 0 [1,2,3,4]  
  [1,2,3,4]
  ghci> 4 `elem` [3,4,5,6]  
  True  
  ghci> 10 `elem` [3,4,5,6]  
  False
  ```

- `length`, `null`, `maximum`, `minimum`, `sum`, `product`...

Range:

- Finite range:

  ```haskell
  ghci> [1..20]  
  [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]  
  ghci> ['a'..'z']  
  "abcdefghijklmnopqrstuvwxyz
  ```

- Infinite range: `[1..]`

- Function produce infinite list:

  `repeat` and `cycle`

  ```haskell
  ghci> take 10 (cycle [1,2,3])  
  [1,2,3,1,2,3,1,2,3,1]
  ghci> take 10 (repeat 5)  
  [5,5,5,5,5,5,5,5,5,5]
  ```

### list comprehension

```haskell
ghci> [x*2 | x <- [1..10]]  
[2,4,6,8,10,12,14,16,18,20] 

ghci> [x*2 | x <- [1..10], x*2 >= 12]  
[12,14,16,18,20] 

ghci> [ x*y | x <- [2,5,10], y <- [8,10,11], x*y > 50]  
[55,80,100,110]
```

### Tuple

Unlike a list, a tuple can contain a combination of several types:

```haskell
(8,11)
("Wow", False)
```

{{< admonition note "Note" false >}}
There is no singleton tuple.
{{< /admonition >}}

Functions involving tuple: `fst`, `snd`, `zip`:

```haskell
ghci> fst (8,11)  
8  
ghci> fst ("Wow", False)  
"Wow"  

ghci> snd (8,11)  
11  
ghci> snd ("Wow", False)  
False  

ghci> zip [1,2,3,4,5] [5,5,5,5,5]  
[(1,5),(2,5),(3,5),(4,5),(5,5)]  
ghci> zip [1 .. 5] ["one", "two", "three", "four", "five"]  
[(1,"one"),(2,"two"),(3,"three"),(4,"four"),(5,"five")]
```

## Chapter 3 Types and Typeclasses

The [link](http://learnyouahaskell.com/types-and-typeclasses) to this chapter.

Check type in ghci:

- Calculate type: `ghci>:t expression`
- If a function is comprised only of special characters (like +,-,*,==), it's considered an infix function by default. If we want to examine its type, pass it to another function or call it as a prefix function, we have to surround it in parentheses, eg: `ghci>:t (+)`
- `::` is used as type declaration or describe an expression's type.
- `[Sometype]` has the type: list of `Sometype`

  ```haskell
  ghci> :t 'a'  
  'a' :: Char  
  ghci> :t True  
  True :: Bool  
  ghci> :t "HELLO!"  
  "HELLO!" :: [Char] 
  ```

Explicit type declaration:

```haskell
removeNonUppercase :: [Char] -> [Char]  
removeNonUppercase st = [ c | c <- st, c `elem` ['A'..'Z']]
```

Common types:

- `Int` (efficient), bounded
- `Integer`, not boundded
- `Float`
- `Double`
- `Bool`
- `Char`
- `()` (the type of () is () and the only value of () is ())

### Type variable

Type variable (type is written in capital case) is in lower case, functions that have type variables are called polymorphic functions:

```haskell
ghci> :t head  
head :: [a] -> a

ghci> :t fst  
fst :: (a, b) -> a
```

### Type classes

Check the type signature of the `==` function:

```haskell
ghci> :t (==)  
(==) :: (Eq a) => a -> a -> Bool
```

Everything before the `=>` symbol is called a class constraint. The type signature above means: the equality function takes any two values that are of the same type and returns a `Bool`. The type of those two values must be a member of the `Eq` class (this was the class constraint).

Some basic type classes:

- `Eq` is used for types that support equality testing
- `Ord` is for types that have an ordering.

  `Ord` covers all the standard comparing functions such as `>`, `<`, `>=` and `<=`.

  (`Ordering` is a type (not a type class) that can be `GT`, `LT` or `EQ`, meaning greater than, lesser than and equal, respectively. )

- `Show` is for types can be presented as strings

  function `show :: Show a => a -> String` takes a value of the type belongs to Show and returns the string representation of the value
  
- `Read` is sort of the opposite type class of `Show`
  
  function `read :: Read a => String -> a` takes a string and returns a value of a type belongs to Read

  but the return type of `read` is not determined, so we need type annotations:

  ```haskell
  ghci> read "5" :: Int  
  5  
  ghci> read "5" :: Float  
  5.0  
  ghci> (read "5" :: Float) * 4  
  20.0  
  ghci> read "[1,2,3,4]" :: [Int]  
  [1,2,3,4]
  ```

- `Enum` members are sequentially ordered types — they can be enumerated

  The main advantage of the Enum type class is that we can use its types in list ranges.

  They also have defined successors and predecesors, which you can get with the `succ` and `pred` functions.

  Types in this class: `(),` `Bool`, `Char`, `Ordering`, `Int`, `Integer`, `Float` and `Double`.

  ```haskell
  ghci> ['a'..'e']  
  "abcde"  
  ghci> [LT .. GT]  
  [LT,EQ,GT]  
  ghci> [3 .. 5]  
  [3,4,5]  
  ghci> succ 'B'  
  'C'  
  ```

- `Bounded` members have an upper and a lower bound.

  `minBound` and `maxBound` are polymorphic constants:

  ```haskell
  ghci> minBound :: Int  
  -2147483648  
  ghci> maxBound :: Char  
  '\1114111'  
  ghci> maxBound :: Bool  
  True  
  ghci> minBound :: Bool  
  False
  ``

- `Num` is a numeric typeclass.
  
  Its members have the property of being able to act like numbers.

  It appears that whole numbers are also polymorphic constants:

  ```haskell
  ghci> 20 :: Int  
  20  
  ghci> 20 :: Integer  
  20  
  ghci> 20 :: Float  
  20.0  
  ghci> 20 :: Double  
  20.0  
  ```

  To join `Num`, a type must already be friends with `Show` and `Eq`.

- `Integral` is also a numeric typeclass. But it includes only integral (whole) numbers. In this typeclass are `Int` and `Integer`.

- `Floating` includes only floating point numbers, so `Float` and `Double`.

A useful unction for dealing with numbers is `fromIntegral`.

- It has a type declaration of `fromIntegral :: (Num b, Integral a) => a -> b`.
- It takes an integral number and turns it into a more general number.

## Chapter3 Syntax in Functions

[Link](http://learnyouahaskell.com/syntax-in-functions)

### Pattern Mathcing

When defining functions, you can define separate function bodies for different patterns:

```haskell
factorial :: (Integral a) => a -> a  
factorial 0 = 1  
factorial n = n * factorial (n - 1)  
```

{{< admonition warning "Warning" true >}}
The **order** of the catch-all pattern is matter, you should always put edge condition first.
{{< /admonition >}}

Wildcard: `_`

```haskell
first :: (a, b, c) -> a  
first (x, _, _) = x 
```

Bind pattern to name: `name@pattern`

```haskell
capital :: String -> String  
capital "" = "Empty string, whoops!"  
capital all@(x:xs) = "The first letter of " ++ all ++ " is " ++ [x] 
```

### Guard

Guards are a way of testing whether some property of a value (or several of them) are true or false:

```haskell
max' :: (Ord a) => a -> a -> a  
max' a b   
    | a > b     = a  
    | otherwise = b  
```

or

```haskell
max' :: (Ord a) => a -> a -> a  
max' a b | a > b = a | otherwise = b  
```

or

```haskell
max' :: (Ord a) => a -> a -> a
a `max'` b
    | a > b = a
    | otherwise = b
```

### where

Keyword `where` is used to reduce duplication by using `where` bindings:

```haskell
bmiTell :: (RealFloat a) => a -> a -> String
bmiTell weight height
    | bmi <= skinny = "You're underweight, you emo, you!"
    | bmi <= normal = "You're supposedly normal. Pffft, I bet you're ugly!"
    | bmi <= fat    = "You're fat! Lose some weight, fatty!"
    | otherwise     = "You're a whale, congratulations!"
    where bmi = weight / height ^ 2
          skinny = 18.5
          normal = 25.0
          fat = 30.0
```

can also use `where` bindings to pattern match:

```haskell
...
where bmi = weight / height ^ 2
      (skinny, normal, fat) = (18.5, 25.0, 30.0)
```

another example:

```haskell
initials :: String -> String -> String  
initials firstname lastname = [f] ++ ". " ++ [l] ++ "."
    where (f:_) = firstname
          (l:_) = lastname
```

it can also be used in definitions of functions:

```haskell
calcBmis :: (RealFloat a) => [(a, a)] -> [a]  
calcBmis xs = [bmi w h | (w, h) <- xs]  
    where bmi weight height = weight / height ^ 2  
```

{{< admonition note "Note" false >}}
`where` bindings can also be nested. It's a common idiom to make a function and define some helper function in its `where` clause and then to give those functions helper functions as well, each with its own where clause.
{{< /admonition >}}

{{< admonition warning "Warning" true >}}
Notice that all the names of `where` bindings should be aligned at a single column.
{{< /admonition >}}

### let expresion

{{< admonition note "Note" false >}}

- `where` bindings are a syntactic construct that let you bind to variables at the end of a function and the whole function can see them, including all the guards.
- `Let` bindings let you bind to variables anywhere and are expressions themselves, but are very local, so they don't span across guards.
- **The difference** is that `let` bindings are expressions themselves. `where` bindings are just syntactic constructs.
  
{{< /admonition >}}

The form is `let <bindings> in <expression>`. The names that you define in the let part are accessible to the expression after the in part:

```haskell
cylinder :: (RealFloat a) => a -> a -> a  
cylinder r h = 
    let sideArea = 2 * pi * r * h  
        topArea = pi * r ^ 2  
    in  sideArea + 2 * topArea 
```

{{< admonition warning "Warning" true >}}
Notice that all the names of `let` bindings should be aligned at a single column.
If can't, separate them with semicolons.
{{< /admonition >}}

It can be used inside a list comprehension:

```haskell
calcBmis :: (RealFloat a) => [(a, a)] -> [a]
calcBmis xs = [bmi | (w, h) <- xs, let bmi = w / h ^ 2, bmi >= 25.0]
```

{{< admonition warning "Warning" true >}}
We can't use the `bmi` name in the `(w, h) <- xs` part because it's defined prior to the let binding.
{{< /admonition >}}

{{< admonition note "Note" false >}}
We omitted the `in` part of the let binding when we used them in list comprehensions because the visibility of the names is already predefined there. However, we could use a let `in` binding in a predicate and the names defined would only be visible to that predicate. The `in` part can also be omitted when defining functions and constants directly in GHCi. If we do that, then the names will be visible throughout the entire interactive session.
{{< /admonition >}}

### case expression

The syntax for case expressions is:

```haskell
case expression of pattern -> result
                   pattern -> result
                   pattern -> result
                   ..
```

Example:

```haskell
describeList :: [a] -> String  
describeList xs = "The list is " ++ case xs of [] -> "empty."  
                                               [x] -> "a singleton list."   
                                               xs -> "a longer list."  
```

{{< admonition note "Note" false >}}
Pattern matching on parameters in function definitions! Well, that's actually just syntactic sugar for case expressions:

```haskell
head' :: [a] -> a  
head' [] = error "No head for empty lists!"  
head' (x:_) = x  
```

is

```haskell
head' :: [a] -> a  
head' xs = case xs of [] -> error "No head for empty lists!"
                      (x:_) -> x
```

{{< /admonition >}}

{{< admonition note "Note" false>}}

Because pattern matching in function definitions is syntactic sugar for case expressions, we could have also defined this like so:

```haskell
describeList :: [a] -> String  
describeList xs = "The list is " ++ what xs  
    where what [] = "empty."  
          what [x] = "a singleton list."  
          what xs = "a longer list."  
```

{{< /admonition >}}

## Chapter5 Recursion

[Link](http://learnyouahaskell.com/recursion)

Unlike imperative languages, functional languages do computations by declaring what something is instead of declaring how you get it.

Example:

```haskell
maximum' :: (Ord a) => [a] -> a  
maximum' [] = error "maximum of empty list"  
maximum' [x] = x  
maximum' (x:xs) = max x (maximum' xs)
```

and:

```haskell
replicate' :: (Num i, Ord i) => i -> a -> [a]
replicate' n x
    | n <= 0    = []  
    | otherwise = x:replicate' (n-1) x
```

{{< admonition note "Note" false >}}
`Num` is not a subclass of `Ord`. That means that what constitutes for a number doesn't really have to adhere to an ordering. So that's why we have to specify both the `Num` and `Ord` class constraints when doing addition or subtraction and also comparison.
{{< /admonition >}}

and:

```haskell
take' :: (Num i, Ord i) => i -> [a] -> [a]  
take' n _  
    | n <= 0   = []  
take' _ []     = []  
take' n (x:xs) = x : take' (n-1) xs  
```

{{< admonition note "Note" false >}}
Notice that we use a guard, but without an otherwise part. That means that if n turns out to be more than 0, the matching will fall through to the next pattern.
{{< /admonition >}}

and typically:

### Quick Sort

```haskell
quicksort :: (Ord a) => [a] -> [a]  
quicksort [] = []  
quicksort (x:xs) =   
    let smallerSorted = quicksort [a | a <- xs, a <= x]  
        biggerSorted = quicksort [a | a <- xs, a > x]  
    in  smallerSorted ++ [x] ++ biggerSorted 
```

## Chapter 6 Higher Order Functions

Haskell functions can take functions as parameters and return functions as return values. A function that does either of those is called a higher order function.

### Curried functions

Every function in Haskell officially only takes one parameter.

Infix functions can also be partially applied by using sections. To section an infix function, simply surround it with parentheses and only supply a parameter on one side:

```haskell
divideByTen :: (Floating a) => a -> a  
divideByTen = (/10)  
```

and

```haskell
isUpperAlphanum :: Char -> Bool  
isUpperAlphanum = (`elem` ['A'..'Z'])  
```

except

{{< admonition warning "Warning" true>}}

The only special thing about sections is using `-`. `(-4)` means minius 4. You should use `subtract` instead: `(subtract 4)`

{{< /admonition >}}

### Laziness

`filter` is a function that takes a predicate (a predicate is a function that tells whether something is true or not, so in our case, a function that returns a boolean value) and a list and then returns the list of elements that satisfy the predicate. The type signature and implementation go like this:

```haskell
filter :: (a -> Bool) -> [a] -> [a]  
filter _ [] = []  
filter p (x:xs)   
    | p x       = x : filter p xs  
    | otherwise = filter p xs  
```

Let's find the largest number under 100,000 that's divisible by 3829:

```haskell
largestDivisible :: (Integral a) => a  
largestDivisible = head (filter p [100000,99999..])  
    where p x = x `mod` 3829 == 0
```

Although the filtered list `[100000,99999..]` is infinite, but due to the call-by-name evaluation strategy, we won't filter the numbers smaller than the largest number divisible by 3829 and therefore we only end up using the head of the filtered list.

Another example of laziness: next up, we're going to find the sum of all odd squares that are smaller than 10,000:

```haskell
sum (takeWhile (<10000) (filter odd (map (^2) [1..])))
```

`takeWhile` takes a predicate and a list and then goes from the beginning of the list and returns its elements while the predicate holds true.

My example (chain here is the Collatz sequence):

```haskell
chain :: (Integral a) => a -> [a]
chain 1 = [1]
chain n
    | even n = n : chain (n `div` 2)
    | odd n  = n : chain (n * 3 + 1)

chains :: [[Integer]]
chains = map chain [1..]

firstNChains :: Integral a => Int -> [[a]]
firstNChains n = take n (map chain [1..])

firstNLengthMChains :: Int -> Int -> [[Integer]]
firstNLengthMChains n m = take n (filter isThatLong chains)
    where isThatLong xs = length xs == m

lengthsOfFirstNChains :: Int -> [Int]
lengthsOfFirstNChains n = map length (firstNChains n)

qSort :: Ord a => [a] -> [a]
qSort [] = []
qSort [x] = [x]
qSort (x:xs) = 
    let smallerPart = filter (<=x) xs
        biggerPart  = filter (>x) xs
    in
        qSort smallerPart ++ [x] ++ qSort biggerPart

orderedLengthsOfFirstNChains :: Int -> [Int]
orderedLengthsOfFirstNChains n = qSort (lengthsOfFirstNChains n)
```

### Lambdas

Lambdas are basically anonymous functions that are used because we need some functions only once. Normally, we make a lambda with the sole purpose of passing it to a higher-order function. Its form: `\param1 param2 .. -> functionbody`.

- Example:

  You can change this code:

  ```haskell
  numLongChains :: Int  
  numLongChains = length (filter isLong (map chain [1..100]))  
      where isLong xs = length xs > 15 
  ```

  to

  ```haskell
  numLongChains :: Int  
  numLongChains = length (filter (\xs -> length xs > 15) (map chain [1..100]))
  ```

- Pattern matching in lambdas:

  ```haskell
  map (\(a,b) -> a + b) [(1,2),(3,5),(6,3),(2,6),(2,5)]
  ```

  {{< admonition warning "Warning" ture>}}
  Although like normal functions, you can pattern match in lambdas. The only difference is that you can't define several patterns for one parameter, like making a `[]` and a `(x:xs)` pattern for the same parameter and then having values fall through. If a pattern matching fails in a lambda, a runtime error occurs, so be careful when pattern matching in lambdas!
  {{< /admonition>}}

- Currying a function:
  
  From:

  ```haskell
  addThree :: (Num a) => a -> a -> a -> a  
  addThree x y z = x + y + z  
  ```

  To:

  ```haskell
  addThree :: (Num a) => a -> a -> a -> a  
  addThree = \x -> \y -> \z -> x + y + z
  ```

### Fold

Folds can be used to implement any function where you traverse a list once, element by element, and then return something based on that. Whenever you want to traverse a list to return something, chances are you want a fold.

{{< admonition note "Note" false >}}
See the McCann's [answer](https://stackoverflow.com/questions/3082324/foldl-versus-foldr-behavior-with-infinite-lists/3085516#3085516) about the difference between `foldl` and `foldr`:

Consider folding a list of `n` values `[x1, x2, x3, x4 ... xn ]` with some function `f` and accumulator `acc`:

- `foldl` is `f ( ... (f (f (f (f acc x1) x2) x3) x4) ...) xn`
- `foldr` is `f x1 (f x2 (f x3 (f x4 ... (f xn acc) ... )))`

{{< /admonition>}}

- Example:

  An implementation of `sum`:

  ```haskell
  sum' :: (Num a) => [a] -> a  
  sum' xs = foldl (\acc x -> acc + x) 0 xs
  ```

  or

  ```haskell
  sum' :: (Num a) => [a] -> a  
  sum' = foldl (+) 0 
  ```

- Another Example:

  Two different implementations of `elem` by using `foldl` or `foldr`:

  ```Haskell
  elem'l :: (Eq a) => a -> [a] -> Bool
  elem'l y = foldl (\acc x -> (x == y) || acc) False

  elem'r :: (Eq a) => a -> [a] -> Bool
  elem'r y = foldr (\x acc -> (x == y) || acc) False
  ```

  But `foldl` can't be used on infinite list, but sometimes `foldr` can. Try to evaluate `elem'r 3 [1..]` and `elem'l 3 [1..]`. See [why](https://stackoverflow.com/questions/3082324/foldl-versus-foldr-behavior-with-infinite-lists/3085516#3085516).

The `foldl1` and `foldr1` functions work much like `foldl` and ``foldr`, only you don't need to provide them with an explicit starting value. They assume the first (or last) element of the list to be the starting value and then start the fold with the element next to it. They assume the first (or last) element of the list to be the starting value and then start the fold with the element next to it.

- Examples

  ```haskell
  maximum' :: (Ord a) => [a] -> a  
  maximum' = foldr1 (\x acc -> if x > acc then x else acc)  
    
  reverse' :: [a] -> [a]  
  reverse' = foldl (\acc x -> x : acc) []  
    
  product' :: (Num a) => [a] -> a  
  product' = foldr1 (*)  
    
  filter' :: (a -> Bool) -> [a] -> [a]  
  filter' p = foldr (\x acc -> if p x then x : acc else acc) []  
    
  head' :: [a] -> a  
  head' = foldr1 (\x _ -> x)  
    
  last' :: [a] -> a  
  last' = foldl1 (\_ x -> x)  
  ```

  {{< admonition info "Info" false >}}
  If you use hLint, it will suggest you change the definition of `maximum'` to `maximu` (that is: `maximum' = maximum`). How smart!
  {{< /admonition >}}

The `scanl` and `scanr` are like `foldl` and `foldr`, only they report all the intermediate accumulator states in the form of a list. (Similarly for `scanl1` and `scanr1`)

- Exmaple

  How many elements does it take for the sum of the roots of all natural numbers to exceed 1000?

  ```haskell
  sqrtSums :: Int  
  sqrtSums = length (takeWhile (<1000) (scanl1 (+) (map sqrt [1..]))) + 1
  ```

### Function application with `$`

It's definition:

```haskell
($) :: (a -> b) -> a -> b  
f $ x = f x 
```

Whereas normal function application (putting a space between two things) has a really high precedence, the `$` function has the lowest precedence. Function application with a space is left-associative (so `f a b c` is the same as `((f a) b) c)`), function application with `$` is right-associative.

We can use it to get rid of parentheses:

- Exmple
  
  - `sum (map sqrt [1..130])` is the same as `sum $ map sqrt [1..130]`

  - `sum (filter (> 10) (map (*2) [2..10]))` is the same as `sum $ filter (> 10) $ map (*2) [2..10]` (Because `f (g (z x))` is the same as `f $ g $ z x`)

But apart from getting rid of parentheses, $ means that function application can be treated just like another function. That way, we can, for instance, map function application over a list of functions.

- Example

  `map ($ 3) [(4+), (10*), (^2), sqrt]`

### Function composition

It's definition:

```haskell
(.) :: (b -> c) -> (a -> b) -> a -> c  
f . g = \x -> f (g x)  
```

- Example1:

  ```haskell
  map (\xs -> negate (sum (tail xs))) [[1..5],[3..6],[1..7]]
  ```

  and further:

  ```haskell
  map (negate . sum . tail) [[1..5],[3..6],[1..7]]
  ```

- Example with `$`:

  ```haskell
  replicate 100 (product (map (*3) (zipWith max [1,2,3,4,5] [4,5,6,7,8])))
  ```

  to

  ```haskell
  replicate 100 . product . map (*3) . zipWith max [1,2,3,4,5] $ [4,5,6,7,8]
  ```

### Point free style

Point free style (also called the pointless style:

- Example

  From

  ```haskell
  sum' :: (Num a) => [a] -> a     
  sum' xs = foldl (+) 0 xs 
  ```

  to

  ```haskell
  sum' :: (Num a) => [a] -> a     
  sum' = foldl (+) 0
  ```

- Example2

  From

  ```haskell
  fn x = ceiling (negate (tan (cos (max 50 x))))
  ```

  to

  ```haskell
  fn = ceiling . negate . tan . cos . max 50
  ```

### Using let to make code more readable

- Exmaple

  Find the sum of all odd squares that are smaller than 10,000

  ```haskell
  oddSquareSum :: Integer  
  oddSquareSum = sum (takeWhile (<10000) (filter odd (map (^2) [1..])))
  ```

  The `.` version:
  
  ```haskell
  oddSquareSum :: Integer  
  oddSquareSum = sum . takeWhile (<10000) . filter odd . map (^2) $ [1..]  
  ```

  The `let` binding version:

  ```haskell
  oddSquareSum :: Integer  
  oddSquareSum =   
      let oddSquares = filter odd $ map (^2) [1..]  
          belowLimit = takeWhile (<10000) oddSquares  
      in  sum belowLimit
  ```

## Chapter 7 Modules

### Loading modules

- Import module:

  ```haskell
  import Data.List
  ```

  In ghci: `ghci> :m + Data.List Data.Map Data.Set`
- Import seleced functions:
  
  ```haskell
  import Data.List (nub, sort)
  ```

- Import module except for some function(s): ``
  
  ```haskell
  import Data.List hiding (nub)
  ```

- Import moudle in the way you have to type full name for conficting function
  
  ```haskell
  import qualified Data.Map
  ```

  (For example, you need to type `Data.Map.filter` for `filter` in `Data.Map`, and type `filter` for the oringal `filter`)

- Import module with a designated name:

  ```haskell
  import qualified Data.Map as M
  ```

  (For example, call `filter` in `Data.Map` as `M.filter`)

### Useful modules

- [Data.List](http://learnyouahaskell.com/modules#data-list)
- [Data.Char](http://learnyouahaskell.com/modules#data-char)
- [Data.Map](http://learnyouahaskell.com/modules#data-map)
- [Data.Set](http://learnyouahaskell.com/modules#data-set)

### Making our own modules

Single module:

- Example:

  We start by creating a file called `Geometry.hs` and in this file we specify the functions that it exports and after that, we can start writing the functions:

  ```haskell
  module Geometry  
  ( sphereVolume  
  , sphereArea  
  , cubeVolume  
  , cubeArea  
  , cuboidArea  
  , cuboidVolume  
  ) where  
    
  sphereVolume :: Float -> Float  
  sphereVolume radius = (4.0 / 3.0) * pi * (radius ^ 3)  
    
  sphereArea :: Float -> Float  
  sphereArea radius = 4 * pi * (radius ^ 2)  
    
  cubeVolume :: Float -> Float  
  cubeVolume side = cuboidVolume side side side  
    
  cubeArea :: Float -> Float  
  cubeArea side = cuboidArea side side side  
    
  cuboidVolume :: Float -> Float -> Float -> Float  
  cuboidVolume a b c = rectangleArea a b * c  
    
  cuboidArea :: Float -> Float -> Float -> Float  
  cuboidArea a b c = rectangleArea a b * 2 + rectangleArea a c * 2 + rectangleArea c b * 2  
    
  rectangleArea :: Float -> Float -> Float  
  rectangleArea a b = a * b 
  ```

Module with sub-modules:

- Example:

  First, make a folder called `Geometry`.

  Second, in that folder, create three fiels: `Sphere.hs`, `Cuboid.hs`, and `Cube.hs`.

  In file `Sphere.hs`:

  ```haskell
    module Geometry.Sphere  
  ( volume  
  , area  
  ) where  
    
  volume :: Float -> Float  
  volume radius = (4.0 / 3.0) * pi * (radius ^ 3)  
    
  area :: Float -> Float  
  area radius = 4 * pi * (radius ^ 2)
  ```
