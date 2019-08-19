# The Ternary Expression and Logic

## Learning Goals

* Identify the Ternary Expression

## Introduction

As conversationalists with computers, we've come so far so fast! We're able to
construct complex _expressions_ and store their _evaluations_ in _variables_.
We can also retrieve those stored values from the variables through the
_variable lookup expression_. We can even assign the results of complex
arithmetic expressions into those variables.

But our expressions have always followed a single track: _evaluate_ this one
single expression, or line of thought. It's like a world of absolute certainty
in every statement: "My outfit today: rain boots" or "My outfit today: sun
hat." Real-life sometimes needs to vary based on a test of some sort. **IF**
it's raining: rain boots **OTHERWISE**: sun hat." This means that _complexity_
is entering our expressions, but we _need_ that complexity so that we can
document our problem-solving strategies in code.

We will now learn how to write an expression that expresses "conditional
thinking" or "if-then" logic. It's called **The ternary expression**. It's an
expression that can return one of two values, based on the truth-status of its
first expression.

## Identify the Ternary Expression

The ternary expression looks like this:

![Ternary Graphic](https://curriculum-content.s3.amazonaws.com/programming-univbasics/the-ternary-expression-and-logic/Image_90_TernarysSyntaxPOP.png)

Or, in Ruby:

```ruby
boolean_conditional_value ? "thing_to_return_if_true" : "thing_to_return_if_false"
```

If the expression in the first position evaluates to anything except `nil` or
`false`, then the return value of the ternary expression is whatever is in
Position 2; here, `"thing_to_return_if_true"`. If the expression in Position 1
returns `nil` or `false`, whatever is in Position 3 is returned; here,
`"thing_to_return_if_false"`.

> **NOTE**: Programmers don't use the terms "Position 1" or "Position 2" in
> daily use (although they might be smart to adopt a standard!). We're using
> those only to help communicate about the parts of a ternary expression

Something that a lot of new programmers miss is that this "something `?`
something `:` something" _expression_ is an _expression_ it **has** a return
value ***and can be assigned to a variable***!

Here's an example to try out in IRB:

```ruby
likely_to_rain = true
garment = likely_to_rain ? "rain boots" : "sun hat"
garment #=> "rain boots"
```

As you see above, the return value of the ternary expression is assigned to
`garment`.  You can use the _variable lookup expression_ to verify that the
value of `garment` is `"rain boots"`.

In IRB, try changing the variable `likely_to_rain` with the _assignment
expression_ from `true` to `false`. Then run the ternary expression again. The
value of `garment` should become `sun hat`.

We now have the ability to express conditional logic in our _expressions_.
You should try writing several ternary expressions yourself in IRB to make sure
you've gotten the hang of things.

> **LEARNING TIP**: Developers learn their craft by making slight experiments
> to given code: be sure you're adopting that habit now.

### Moving Beyond Boolean

Keep in mind that the first term in a ternary statement can also be an
expression that returns a Boolean value of `true` or `false`. It _does not_
have to be the exact `true` or `false` value.  Instead, in the first slot can
be an expression that returns a truth value that is calculated by an
_expression_. We'll provide two simple examples here and go into a lot more
detail in the next lesson.

From arithmetic, recall this statement: `2 > 1` which expresses is the quantity
`2` "greater than" `1`?  Try putting this _expression_ into IRB: does IRB
confirm that it `evaluates` to `true`? It should! That's what we mean by
_calculated_ truth value. Based on the evaluation of an expression, Ruby
returned a `true` or `false` value that could be used in the ternary
expression.

Try updating your original IRB code

```ruby
garment = 2 > 1 ? "rain boots" : "sun hat"
garment #=> "rain boots"
```

This logic makes `garment` `"rain boots"` again. Try swapping `>` for `<`, is
that what you expected? That's a second operator for calculating truth: instead
of greater-than (`>`), we used less-than (`<`).  These operators are known as
_comparison operators_. Comparison operators return `true` or `false`. We'll
meet the whole family of them in the next lesson. 

**The important thing to take away is that you can always swap a literal `true`
or `false` for an expression that returns `true` or `false`.**

Even more amazing, we can swap out the simple `String`s we've used in Positions
2 and 3 of our first ternary with expressions as well.

```ruby
top = 2
bottom = 1
problem_count = 99
lucky_number = (top > bottom) ? ( 3 + 1 ) : ( problem_count / 3 )
lucky_number #=> ??? (Test it out yourself!)
```

What's the value of `lucky_number`? Step through the expressions to make you
understand what happens step by step.

> **STYLE TIP**: To make reading the expressions in the ternary statement's
> positions clear, we wrap them in `()`. It's done for readability and to
> prevent accidental order of operations bugs.

## Conclusion

The ternary expression is where our expression-writing starts to make a leap
upward in complexity. But if we bear in mind that it's always an expression
that, itself, contains three "inner" expressions, we'll be able to keep moving
forward comfortably.

> **NOTE**: Those familiar with programming languages might be wondering, why
> not use `if/else` statements. We'll work our way up to them, but for now
> realize that expressions can provide conditional power (and in one line!).
