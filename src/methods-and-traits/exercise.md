---
minutes: 15
---

# Exercise: Logger Trait

Let's design a simple logging utility, using a trait `Logger` with a `log`
method. Code which might log its progress can then take an `&impl Logger`. In
testing, this might put messages in the test logfile, while in a production
build it would send messages to a log server.

However, the `StderrLogger` given below logs all messages, regardless of
verbosity. Your task is to write a `VerbosityFilter` type that will ignore
messages above a maximum verbosity.

This is a common pattern: a struct wrapping a trait implementation and
implementing that same trait, adding behavior in the process. In the "Generics"
segment, we will see how to make the wrapper generic over the wrapped type.

```rust,compile_fail,editable
{{#include exercise.rs:setup}}

// TODO: Implement the `Logger` trait for `VerbosityFilter`.

{{#include exercise.rs:main}}
```
