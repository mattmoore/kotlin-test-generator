# Pattern Matching

The goal of this Arrow Meta plugin is to support pattern matching in Kotlin, similar to [Scala](https://docs.scala-lang.org/tour/pattern-matching.html) and [Haskell](http://learnyouahaskell.com/syntax-in-functions).

A [KEEP](https://github.com/Kotlin/KEEP/pull/213) for pattern matching was submitted. I don't know how long it will take to get this proposal accepted and implemented. Subsequently, since I've been wanting to see how easy it would be to add pattern matching via Arrow Meta, I decided to start work on that.

## What is Pattern Matching?

_Before:_

```kotlin
val x = 1

when (x) {
    42 -> //...
    is Any -> //...
}
```

_After:_

```kotlin
val x = 1

when (x) {
    2 -> //...
    is _ -> //...
}
```

## With Tuples

_Before:_

```kotlin
val pair = Pair(1, 2)

when (pair) {
    is Pair<Int, Int> -> //...
}
```

_After:_

```kotlin
val pair = Pair(1, 2)

when (pair) {
    is Pair(_, 2) -> //...
}
```

## Run from the command line

```shell
cd pattern-matching
./gradlew clean :use-plugin:shadowJar
```
