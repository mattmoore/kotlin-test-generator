# Pattern Matching

The goal of this Arrow Meta plugin is to support pattern matching in Kotlin, similar to [Scala](https://docs.scala-lang.org/tour/pattern-matching.html) and [Haskell](http://learnyouahaskell.com/syntax-in-functions).

A [KEEP](https://github.com/Kotlin/KEEP/pull/213) for pattern matching was submitted. I don't know how long it will take to get this proposal accepted and implemented. Subsequently, since I've been wanting to see how easy it would be to add pattern matching via Arrow Meta, I decided to start work on that.

## State of this Project

I have just begun this project on May 8, 2020. I have yet to see just how far I can get using the latest version of Arrow Meta (1.3.61 as of this time).

Currently, I have a very simple example where `_` matching works for simple types. Of course, this is not very useful. There are problems with constructor-style matching on values vs types that I have yet to come up with a working solution for.

The bottom line is this is a research plugin and should not be used for production any time soon.

Also worth noting, Java has a [pending proposal](https://cr.openjdk.java.net/~briangoetz/amber/pattern-match.html) to add pattern matching, which might make any attempts at this in Kotlin difficult to support when the Java compiler finally supports it. Use this plugin at your own peril.

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

when {
    pair is Pair<Int, Int> && y.second == 2 -> //...
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

## Contributions

I welcome contributions! If you'd like to help contribute code, please feel free to open a PR!
