# Pattern Matching

The goal of this Arrow Meta plugin is to support pattern matching in Kotlin.

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
