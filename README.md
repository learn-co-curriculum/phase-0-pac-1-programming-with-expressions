# The Ternary Expression and Logic

## Learning Goals

* Identify the Ternary Expression

## Introduction

As conversationalists with computers, we've come so far so fast!

We now want to learn how to write an expression that expresses "conditional
thinking" or "if-then" logic. Oh and lets drop some hot gossip:

***Tons of programmers never learn to use this expression that you're about to
learn &mdash; they're afraid of it***

We're about to learn **the ternary expression** which is an expression that can
provide one of two values, based on the truth (or "Boolean value" of a third
value)

>**NOTE** "Ternary" is Latin for "3 per." The previous paragraph shows three
>values being involved in the statement. Let's get to know our friend the
>ternary statement.

## Identify the Ternary Expression

The ternary statement is an _expression_ just like all the other expressions
we've already met. It looks like this:

```ruby
# Position 1                # Position 2                # Position 3
boolean_conditional_value ? "thing_to_return_if_true" : "thing_to_return_if_false"
```

If the expression (_constant expression_ with a Boolean value, _assignment
expression_,  etc.) is a `true` value, then the return value of the expression
is "thing_to_return_if_false". If it is `false`, "thing_to_return_if_false` is
returned.

Here's an example to try out:

```ruby
likely_to_rain = true
garment = likely_to_rain ? "galoshes" : "sun hat"
```

As you see the return value of the ternary expression is assigned to `garment`.
You can use the _variable lookup expression_ to verify that the value of
`garment` is `"galoshes"`.

Try changing the variable with the _assignment expression_ from `true` to
false. Then run the ternary expression again. The value of `garment` should
become `sun hat`.

Amazingly, in expression we now have the ability to understand conditional
logic.

### Moving Beyond Boolean

Keep in mind that the first term in a ternary statement can also be an
expression. It does not have to be `true` or `false` (_constant expressions_)
it can be _calculated_ truth; truth calculated by an _expression_.

Recall arithmetic, recall this statement: `2 > 1` is `2` "greater than" 1?  Try
putting this _expression_ into IRB: does IRB confirm that it `evaluates` to
`true`?

Try updating your original IRB code

```ruby
garment = 2 > 1 ? "galoshes" : "sun hat"
```

This logic makes `garment` `"galoshes"` again. Try swapping `>` for `<`, is
that what you expected?

You've now met two _comparison operators_. Comparison operators return `true`
or `false`. We'll meet the whole family of them in the next lesson. You can
always swap a "literal constant value" for "an expression that returns a value"
in programming. Thus since comparison operations return `true` or `false`, we
can use one of those expressions in Position 1 of our ternary statement.

Even more awamzing, we can swap out the simple `String`s we've used in
Positions 2 and 3 of our ternary with expressions as well.

```ruby
top = 2
bottom = 1
problem_count = 99
lucky_number = (top > bottom) ? ( 3 + 1 ) : ( problem_count / 3 ))
```

What's the value of `lucky_number`? Step through the expressions to make you
understand what happens step by step.

> **STYLE TIP**: To keep reading the expressions in the ternary statement's
> positions clear, we wrap them in `()`. It's done for readability and to
> prevent accidental order of operations bugs.

## What Provides Truth?

Obviously, given the ternary's power to express conditionals, it's really
helpful to know which operators express `true` and `false`. In our next lesson
we'll give a list of Boolean operators.

## Conclusion

It's an amazing moment when a child moves from mere _variable lookup_ and
_variable assignment_ to start surfacing the ability to reason between
hypothetical if-then outcomes. **IF** I touch the stove, I will get hurt;
**ELSE** I shall stay unhurt. **IF** I sass grandma, I will get a time-out;
**ELSE** I can eat ice cream. We've now gained the ability to express
conditional logic to Ruby!

> **NOTE**: Those familiar with programming languages might be wondering, why not use
`if/else` statements. In most programming languages `if / else` statements are
**statements** not **expressions**. **Statements** _do not_ always have a
return value, but **expressions** always do. This entire module is about
working with **expressions**. Fear not, though, we'll give the full list of
conditional **statements** in an upcoming module.

## Resources
