# Programming with Expressions

## Learning Goals

- Use the code window in replit to try out code
- Identify the Ternary Expression
- Write a program with conditional logic using expressions
- Refactor code

## Introduction

You've traveled quite a road! You started, from a conversational perspective,
mute and unable to interact, and now you can converse with JavaScript.

As conversationalists with computers, we are now able to construct complex,
sophisticated _expressions_. But so far our expressions have followed a single
track: _evaluate_ this one single expression, or line of thought. It's like a
world of absolute certainty in every statement: "My outfit today: rain boots" or
"My outfit today: sun hat." In real life, however, we sometimes need to base our
decisions on a test of some sort. "**IF** it's raining: rain boots...
**OTHERWISE**: sun hat." This means that _complexity_ is entering our
expressions; we _need_ that complexity so that we can express our
problem-solving strategies in code.

In this lesson, we will learn how to write an expression that expresses
"conditional thinking" or "if-then" logic. It's called the **ternary
expression**. It's an expression that takes a Boolean value or expression and
returns one of two values, depending on the truth-status of that first
expression. We will also learn how to write a program using conditional
expressions. Before we get to that, though, let's expand our [replit][] skills a
bit.

## Using the Code Window in replit

So far, we've been using the console window in [replit][] and ignoring the code
window. Now we're going to learn how we can use the code window to make it
easier to write, test, and experiment with code. Go ahead and open [replit][].

When you open it, you'll see a single line of code in the code window on the
left side:

```js
console.log('Hello, world!')
```

If you click the "Run" button, you will see the message "Hello, world!" written
out in the console window on the right. You will learn more about using
`console.log()` a bit later in this section. For now, just know that
`console.log()` allows us to write code in the code window and print out results
of that code to the console.

When you pressed "Run", the REPL _evaluated_ the expression inside the
parentheses, and then printed that value out to the console. In this case, there
is a constant expression inside the parentheses, so that value is what is
output. But we can put other types of expressions in the parentheses as well.

For example, try entering the following into the code window, then press "Run".

```js
const sum = 1 + 1;

console.log(sum);
```

You should see the value `2` written to the console.

What do you think will happen if you type the following into the code window and
run it?

```js
console.log(5 * 5);
```

As long as whatever is inside the parentheses _evaluates to a value_ — i.e., as
long as it's an expression — that value will be logged in the console.

So now we know two different ways to check the value of an expression in the
REPL: we can either wrap it in a `console.log()` in the code window and press
"Run", or we can enter it directly in the console window and hit enter.

Note that we could also combine the two approaches. Go ahead and enter this line
of code into the code window and click "Run":

```js
const difference = 10 - 5;
```

Although it doesn't appear that anything happens because nothing is printed to
the console, when we clicked "Run", JavaScript evaluated the arithmetic
expression and stored that value in the variable `difference`. Now type
`difference;` in the _console window_ and hit enter.

**Important**: the evaluation and assignment happen when you click "Run". If you
just paste the code into the code window and then try to check the value of
`difference` in the console, it won't work.

Often, it's inconvenient to type or copy/paste code into the console — if you're
working with a large block of code, for example, or if you want to be able to
make multiple changes. Putting code in the code window makes it easier to
correct errors and try different things.

As you work through the curriculum, we encourage you to use [replit][] to try
out code samples from the lessons and to experiment with your own examples. Now
that you know how to use the code window, you have another tool at your
disposal.

## Identify the Ternary Expression

The ternary expression looks like this:

![Ternary Graphic](https://curriculum-content.s3.amazonaws.com/phase-0/programming-with-expressions/ternary.jpg)

Or, in code:

```js
booleanExpression ? "thingToReturnIfTrue" : "thingToReturnIfFalse";
```

If the expression in the first position evaluates to a truthy value, then the
return value of the ternary expression is whatever is in the second position;
here, `"thingToReturnIfTrue"`. If the expression in the first position is
falsey, however, whatever is in the last position is returned; here,
`"thingToReturnIfFalse"`.

Let's try an example. Go ahead and copy the code below into the _code window_ of
replit. When you click the "Run" button, JavaScript will log the value of
`clothingChoice` to the console.

```js
const likelyToRain = true;
const clothingChoice = likelyToRain ? "rain boots" : "sun hat";

console.log(clothingChoice);
```

The expression in the first position evaluates to `true`, so the ternary
expression returns the value after the question mark, "rain boots". Try changing
the variable `likelyToRain` from `true` to `false` in the code window, then
press "Run" again. The return value of our ternary expression should now be `sun
hat`.

We now have the ability to express conditional logic. You should try writing
several ternary expressions yourself in the REPL to make sure you've gotten the
hang of things.

> **Note**: we will add `console.log()`s to the code samples in this lesson so
> you just need to click "Run" to see the results. If you want to check the
> value of any other expressions or variables, you can either add more
> `console.log()`s to the code window or check the values directly in the
> console. Remember to click "Run"!

> **LEARNING TIP**: Developers learn their craft by making slight experiments to
> given code: be sure you're adopting that habit now.

### Moving Beyond Boolean Values

Above we had a variable, `likelyToRain`, in which the literal Boolean value
`true` was stored and we used that as our Boolean expression in our ternary. But
we can, in fact, use _any_ Boolean expression, not just literal Boolean values.
Specifically, we can use the comparison operators and logical operators that we
learned about in the previous lessons to construct our expression.

Let's look at an example:

```js
const rainPercentage = 0.2;
const clothingChoice = rainPercentage > 0.3 ? "rain boots" : "sun hat";

console.log(clothingChoice);
```

Here we see we can make a decision based on a _comparison_. _If_ the chance of
rain is greater than 30%, we know we should take our rain boots; _otherwise_
we'll grab our sun hat. Try different values for `rainPercentage` and see what
happens.

With this understanding of ternary expressions, we are now ready to write a
program using expressions.

## Write a Program with Conditional Logic Using Expressions

Guess what? We've already done this!
[According to Wikipedia](https://en.wikipedia.org/wiki/Computer_program), a
program is "a collection of instructions that can be executed by a computer to
perform a specific task." The ternary (set of instructions) we looked at above
is an _expression_ that performs the task of _evaluating a condition_ and, based
on the results, _returning a value_. But of course we can expand on this, making
our conditions more sophisticated and our return values more informative:

```js
// Input values: we could easily imagine asking a user for these values.
const name = "Your name here";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

// Create our message
const message = `Hello, ${name}, with a rain chance of ${probabilityOfRain * 100}% and a temperature of ${temperatureInC}C we recommend that you ` + (probabilityOfRain > 0.3 ? "take an umbrella" : "enjoy this rain-free day") +
`${temperatureInC >= 26 ? ' and watch out for heatstroke.' : ' and bask in this fine weather.'}`;

console.log(message);
```

Now we have three variables and we're using them not only to construct ternary
expressions but also to output a more informative message. Try experimenting
with the values of the variables and see how it affects the return value.

Although this code works — JavaScript knows what we want it to do — that doesn't
make it good code. Recall that programming is _conversation_, not just with the
JavaScript engine but _also_ with other programmers or ourselves in the future.
How easy is it to read the line of code that defines our return value? How much
work does it take to figure out how it works? Writing good code means writing
code that not only works but is also as clean and readable as we can make it.

## Refactoring our Code

We have learned that, in assigning values to variables, we can use constant
values:

```js
const name = "Spinach the Shiba";
```

Or values evaluated from an expression:

```js
const rainPercentage = 0.2 * 100;
```

We can also include variables as part of the evaluated expression:

```js
const probabilityOfRain = 0.2;
const rainPercentage = probabilityOfRain * 100;
```

In fact, **_you can assign virtually any *expression* as the value of a
variable_**, including _comparison_ expressions. So to start, let's use our new
`rainPercentage` variable and also create a couple of appropriately named
variables to store the conditions we're checking in our ternary statements. The
condition `probabilityOfRain > 0.3` is basically checking whether it's likely to
rain, while the condition `temperatureInC >= 26` is checking whether it's hot
enough that we should stay out of the sun. Once we've created these variables,
we can then use them instead of including the math in the message, which will
make it a little easier to read:

```js
const name = "Spinach the Shiba";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

const likelyToRain = probabilityOfRain > 0.3;
const sunIsDangerous = temperatureInC >= 26;
const rainPercentage = probabilityOfRain * 100;

const message = `Hello, ${name}, with a rain chance of ${rainPercentage}% and a temperature of ${temperatureInC}C we recommend that you ` +
  (likelyToRain ? "take an umbrella" : "enjoy this rain-free day") +
  `${
    sunIsDangerous
      ? " and watch out for heatstroke!"
      : " and bask in this fine weather."
  }`;

console.log(message);
```

This is already a bit easier to read. We've:

1. moved the math and some of the logic out of our return value
2. used meaningful variable names that make it clearer how we're using our
   conditions and, by extension, what the ternary expressions are doing
3. split out our message onto multiple lines to make it easier to follow the
   logic.

But we can do better.

We mentioned above that we can assign virtually any expression as the value of a
variable; this includes _ternary expressions_.

A ternary expression returns a value, just like any other expression; the value
it returns is what is assigned to the variable. Here's an example:

```js
const advice = raining ? "take an umbrella" : "enjoy this rain-free day";
```

The value assigned to `advice` will be "take an umbrella" if `raining` is
`true`, and "enjoy this rain-free day" otherwise.

Note that we can write ternary expressions on one line, as we did above, or on
multiple lines:

```js
const rainAdvice = likelyToRain
  ? "take an umbrella"
  : "enjoy this rain-free day";
```

Let's create variables to hold the results of our ternary expressions and use
those in our message as well:

```js
const name = "Spinach the Shiba";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

const likelyToRain = probabilityOfRain > 0.3;
const sunIsDangerous = temperatureInC >= 26;
const rainPercentage = probabilityOfRain * 100;

const rainAdvice = likelyToRain
  ? "take an umbrella"
  : "enjoy this rain-free day";
const sunAdvice = sunIsDangerous
  ? " and watch out for heatstroke"
  : " and bask in this fine weather";

const message = `Hello, ${name}, with a rain chance of ${rainPercentage}% and a temperature of ${temperatureInC}C we recommend that you ` + rainAdvice + sunAdvice;

console.log(message);
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
expressions. Furthermore, by using meaningful variable names, we've made it
clear what the final message will consist of.

Be sure to verify that our refactored code still works!

```js
const name = "Spinach the Shiba";
const probabilityOfRain = 0.2;
const temperatureInC = 26;

const likelyToRain = probabilityOfRain > 0.3;
const sunIsDangerous = temperatureInC >= 26;

const rainPercentage = probabilityOfRain * 100;
const rainAdvice = likelyToRain ? "take an umbrella" : "enjoy this rain-free day";
const sunAdvice = sunIsDangerous ? "watch out for heatstroke" : "bask in this fine weather";

const message = `Hello, ${name}, with a rain chance of ${rainPercentage}% and a temperature of ${temperatureInC}C we recommend that you ${rainAdvice} and ${sunAdvice}.`;

console.log(message);
```

Nice!

One final note before we move on. In the example above, we used simple `String`s
as the return values in our ternary expressions. But we can use any data type
here — numbers, Booleans, objects, etc. And, of course, we can also use more
complex expressions. Let's look at an example:

```js
const first = 2;
const second = 1;
const problem = 99;
const luckyNumber = first > second ? (problem - 1) / 2 : problem / 3;
luckyNumber; //=> ??? (Test it out yourself!)
```

What's the value of `luckyNumber`? Step through the expressions to make sure you
understand what happens step by step.

The ternary expression enables us to make a leap upward in the complexity of our
expression-writing. An important thing to remember is that a ternary is an
expression that, itself, is made up of three "inner" expressions.

> **NOTE**: Those familiar with programming languages might be wondering, why
> not use `if/else` statements. We'll work our way up to them, but for now we
> have the ability to implement simple conditional decisions in one line of
> code!

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

- MDN
  - [Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

[replit]: https://replit.com/languages/javascript
