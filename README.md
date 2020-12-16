# Programming with Expressions

## Learning Goals

* Identify the Ternary Expression
* Write a program with conditional logic using expressions

## Introduction

You've traveled quite a road! You started, from a conversational perspective,
mute and unable to interact, and now you can converse with JavaScript.

As conversationalists with computers, we are now able to construct complex,
sophisticated _expressions_. But so far our expressions have followed a single
track: _evaluate_ this one single expression, or line of thought. It's like a
world of absolute certainty in every statement: "My outfit today: rain boots" or
"My outfit today: sun hat." In real life, however, we sometimes need to base our
decisions on a test of some sort. "**IF** it's raining: rain boots... **OTHERWISE**:
sun hat." This means that _complexity_ is entering our expressions; we _need_
that complexity so that we can express our problem-solving strategies in code.

We will now learn how to write an expression that expresses "conditional
thinking" or "if-then" logic. It's called **The ternary expression**. It's an
expression that takes a Boolean value or expression and returns one of two
values, depending on the truth-status of that first expression.

## Identify the Ternary Expression

The ternary expression looks like this:

![Ternary Graphic](https://curriculum-content.s3.amazonaws.com/phase-0/programming-with-expressions/ternary.jpg)

Or, in code:

```js
booleanExpression ? "thingToReturnIfTrue" : "thingToReturnIfFalse"
```

If the expression in the first position evaluates to a truthy value, then the
return value of the ternary expression is whatever is in the second position;
here, `"thingToReturnIfTrue"`. If the expression in the first position is
falsey, however, whatever is in the last position is returned; here,
`"thingToReturnIfFalse"`.

Let's try an example:

<iframe height="400px" width="100%" src="https://repl.it/@LizBurton/SweetNativeQuadrant?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

The expression in the first position evaluates to `true`, so the ternary
expression returns the value after the question mark, "rain boots". Try
changing the variable `likelyToRain` with the _assignment expression_ from
`true` to `false`. Then run the ternary expression again. The return value of
our ternary expression should now be `sun hat`.

We now have the ability to express conditional logic. You should try writing
several ternary expressions yourself in the REPL to make sure you've gotten the
hang of things.

> **LEARNING TIP**: Developers learn their craft by making slight experiments to given code: be sure you're adopting that habit now.

### Moving Beyond Boolean Values

Above we had a variable, `likelyToRain`, in which the literal Boolean value
`true` was stored and we used that as our Boolean expression in our ternary. But
we can, in fact, use _any_ Boolean expression, not just literal Boolean values.
Specifically, we can use the comparison operators and logical operators that we
learned about in the previous lessons to construct our expression.

Let's look at an example:

<iframe height="400px" width="100%" src="https://repl.it/@LizBurton/RashUnconsciousSigns?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Here we see we can make a decision based on a _comparison_. _If_ the chance of
rain is greater than 30%, we know we should take our rain boots; _otherwise_
we'll grab our sun hat. Try different values for `rainPercentage` and see what
happens.

With this understanding of ternary expressions, we are now ready to write a
program using expressions.

## Write a Program with Conditional Logic Using Expressions

Guess what? We've already done this! [According to Wikipedia](https://en.wikipedia.org/wiki/Computer_program), a program is "a collection of instructions that can be
executed by a computer to perform a specific task." The ternary (set of
instructions) we looked at above is an _expression_ that performs the task
of _evaluating a condition_ and, based on the results, _returning a value_.
But of course we can expand on this, making our conditions more sophisticated
and our return values more informative:

<iframe height="400px" width="100%" src="https://repl.it/@LizBurton/HungryWealthyVertex?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Now we have three variables and we're using them not only to construct ternary
expressions but also to output a more informative message. Try experimenting
with the values of the variables and see how it affects the return value.

Let's take a closer look at the code:

```js
//Input values: we could easily imagine asking a user for these values.
const name = "Byron the Poodle";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

`Hello, ${name}, with a rain chance of ${probabilityOfRain * 100}% and a temperature of ${temperatureInC}C we recommend that you ` + (rainPercentage > 0.3 ? "take an umbrella" : "enjoy this rain-free day") + `${temperatureInC >= 26 ? ' and watch out for heatstroke.' : ' and bask in this fine weather.'}`;
```

Although this code works &mdash; JavaScript knows what we want it to do &mdash;
that doesn't make it good code. Recall that programming is _conversation_, not
just with the JavaScript engine but _also_ with other programmers or ourselves
in the future. How easy is it to read the line of code that defines our return
value? How much work does it take to figure out how it works? Writing good code
means writing code that not only works but is also as clean and readable as we
can make it.

Let's do some _refactoring_.

We have learned that, in assigning values to variables, we can use constant
values:

```js
const name = "Byron the Poodle";
```

Or values evaluated from an expression:

```js
const rainPercentage = 0.2 * 100;
```

We can also include variables as part of the evaluated expression:

```js
const rainPercentage = probabilityOfRain * 100;
```

In fact, ***you can assign virtually any _expression_ as the value of a
variable***, including _comparison_ expressions. So to start, let's use our new
`rainPercentage` variable and also create a couple of appropriately named
variables to store the conditions we're checking in our ternary statements. The
condition `rainPercentage > 0.3` is basically checking whether it's likely to
rain, while the condition `temperatureInC >= 26` is checking whether it's hot
enough that we should stay out of the sun. Once we've created the variables we
can then use them in our ternary statements:

```js
const name = "Byron the Poodle";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

const likelyToRain = probabilityOfRain > 0.3;
const sunIsDangerous = temperatureInC >= 26;
const rainPercentage = probabilityOfRain * 100;

`Hello, ${name}, with a rain chance of ${rainPercentage}% and a temperature of ${temperatureInC}C we recommend that you ` + (likelyToRain ? "take an umbrella" : "enjoy this rain-free day") + `${sunIsDangerous ? ' and watch out for heatstroke!' : ' and bask in this fine weather.'}`
```

This is already a bit easier to read: we've moved the math and some of the logic
out of our return value; we've also used meaningful variable names that make it
clearer how we're using our conditions and, by extension, what the ternary
expressions are doing. But we can do better.

We mentioned above that we can assign virtually any expression as the value of a
variable; this includes _ternary expressions_:

```js
const rainAdvice = likelyToRain ? "take an umbrella" : "enjoy this rain-free day";
const sunAdvice = sunIsDangerous ? "and watch out for heatstroke" : "and bask in this fine weather"
```

A ternary expression returns a value, just like any other expression; the value
it returns is what is assigned to the variable.

Let's update our code, implementing this improvement:

```js
const name = "Byron the Poodle"
const probabilityOfRain = 0.2;
const temperatureInC = 26;

const likelyToRain = probabilityOfRain > 0.3;
const sunIsDangerous = temperatureInC >= 26;
const rainPercentage = probabilityOfRain * 100;

const rainAdvice = likelyToRain ? "take an umbrella" : "enjoy this rain-free day";
const sunAdvice = sunIsDangerous ? " and watch out for heatstroke" : " and bask in this fine weather";

`Hello, ${name}, with a rain chance of ${rainPercentage}% and a temperature of ${temperatureInC}C we recommend that you ` + rainAdvice + sunAdvice;
```

Much better! But there are still some improvements we can make. For one thing,
it looks a little strange that we're using both interpolation and the `+`
operator; let's fix that. And, while we're at it, we can take the " and" and the
punctuation out of the `sunAdvice` ternary and incorporate them into our return
value instead. This not only improves the readability of our return message, it
also makes our code more flexible: if we decide to reverse the order of
`rainAdvice` and `sunAdvice` in our message, or to add a third piece of advice,
we don't need to go back and edit the values returned by the ternary.

Once we've done all that, the code defining our return value is much easier to
read: it no longer includes a jumble of mathematical, comparison, and ternary
expressions. Furthermore, by using meangingful variable names, we've made it
clear what the final message will consist of:

<iframe height="400px" width="100%" src="https://repl.it/@LizBurton/BitterTeemingAbandonware?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

Nice!

One final note before we move on. In the example above, we used simple `String`s
as the return values in our ternary expressions. But we can use any data type
here &mdash; numbers, Booleans, objects, etc. And, of course, we can also use
more complex expressions. Let's look at an example:

```js
const first = 2;
const second = 1;
const problemCount = 99;
const luckyNumber = (first > second) ? ( (problemCount - 1) / 2 ) : ( problemCount / 3 );
luckyNumber; //=> ??? (Test it out yourself!)
```

What's the value of `luckyNumber`? Step through the expressions to make sure you
understand what happens step by step.

> **STYLE TIP**: To make reading the expressions in each of the ternary statement's positions easier, we wrap them in `()`. It is not required: it's done for readability and to prevent accidental order of operations bugs.

The ternary expression enables us to make a leap upward in the complexity of our
expression-writing. An important thing to remember is that a ternary is an
expression that, itself, is made up of three "inner" expressions.

> **NOTE**: Those familiar with programming languages might be wondering, why not use `if/else` statements. We'll work our way up to them, but for now we have the ability to implement simple conditional decisions in one line of code!

## Conclusion

Congratulations, you've learned the art of conversing with JavaScript at a basic
level. You should be proud of this accomplishment. Learning any programming
language generally follows these same steps. It's a proven general structure for
finding your bearings in a programming language. Feel free to return to it.

As you build code in future lessons, be sure to try to make tiny changes and
make sure the code still works. Flatiron School has learned that the students
who are most successful in our programs are those who make the most "small hops"
away from the given content to make the content their own. Programmers usually
call this "playing with the code." Try swapping out a conditional expression,
nesting a ternary within a ternary, turning a conditional from < to <=, etc. As
you move on, make sure you continue to play with all the skills you've learned
so far. If you need help making those "small hops" be sure to work with your
community via Slack. You won't regret the investment.

By the way, doing this exact work is how most programmers orient themselves to a
new language. Having the skill of getting started in a new language is a rocket
booster for your career.

But to take your skills to the next level, you need to learn a new type of
construction: a statement. Unlike an expression which always returns a value,
statements are used to help choose which expressions to evaluate or to do
repetitive tasks. That's Programming as Conversation Part II: Statements. Take a
virtual high-five from us! You've come a long way!

## Resources

* MDN
  * [Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
