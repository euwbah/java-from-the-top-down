#Java From The Top Down

[TOC]

#####Preface (tl;dr)

It begins with a common educational concept. Basics first, then move on. This concept is especially prevalent in the education systems of USA, South Korea and a majority of South East Asian countries (including Singapore). Consensus has it that this is the most _logical_ way to transfer knowledge.

However, this methodology also presents its inhibitions. It is diminished in a fundamental area of the learning process: causation. Learning from the bottom-up will _look as if_, from the perspective of the educator, 'bottom-up' per se. However, for the student, the quantity of misidentified and misunderstood concepts are legion. 

This psuedo-book/tutorial does not prove to be the _only_ way to learn, but it always helps to give **another option**, and this (hopefully) will be that other option.

#####How to read this psuedo-book:

Every part of this 'book' is based on, and will explain, a block of code, and not the other way around. This means that the natural human learning process of experiencing first, then learning, will be utilised. This also means that it will be a little less organized compared to a standard book. 

Whenever you are lost, go back and look at **THE CODE:** first, then continue from where you still had your bearings.

#Chapter `null`: terminology

Herein lies some words you should be familiar with. **DO NOT READ THIS SECTION. Only read it when a link in the book redirects you to a definition.** Please go back up to the [Table of Contents](#java-from-the-top-down) and click the next chapter.

###1: Syntax

####Define Syntax
>Syntax, simply put, is the grammar of Java.

#####Sentence Structure
Very much like other languages, it has a **sentence structure**, and **punctuation**, and **prepositions**.

As an example, let's take a look at the English **sentence structure**:
```sequence
You->fish.: eat
```
> You eat fish.
> #####Subject, Verb, Object:: You, Eat, Fish

Now let's look at **Java's** sentence structure:

```sequence
System.out.println->("Welcome");:
```
> `System.out.println("Welcome");`
> #####Verb, Object

In fact, it is even **simpler** than English's. You **don't even need** to specify the Subject.

#####_'Punctuation'_
However, Java has much, much more '_punctuation marks_' than in English.

But beware: Don't get **tricked** into thinking that all the '_punctuation marks_' you see in **Java** code play the same role as punctuation marks do in **English**. You may replace a 'single quote' with a "double quote" in English, but doing the same in Java would only _call disaster upon yourself._ 

The only two _punctuation marks_  from Java that can **almost** resemble English are:

- The semicolon **;** ~ which acts like a full stop which separates sentences ([statements](#statement))
- The comma **,** ~ which acts like a comma. Separating distinct **expressions** in a sentence.

----

####Syntax terms

#####Expressions

Now you may be thinking: what on Earth is an **expression**?

> An expression evaluates to a single value

And still, you're just as confused.

Let's look at this Mathematical **expression**:

$$\frac {-\beta}{ \alpha}$$

And now, let's look at this Mathematical _equation_:

$$\Sigma \; roots = \frac {-\beta}{\alpha}$$

The difference is that for the **expression**, the entire thing is still technically **one** value -- meaning that if $\alpha$ was 3 and $\beta$ was 4, you would get a **single** value (which is $-\frac{4}{3}$).

However, for the _equation_, the _entire_ thing will not evaluate to a _single value_ even if you knew what are the sum of the roots. What kind of value will $3 = 5$ have? You definitely can't do $4 + (3 = 5)$ for sure!

--------------

Now observe this sentence:
> I like trains, but I like muffins too.

How many expressions are there in that sentence?
**Two**

Similarly, in Java - one _sentence_ can have multiple **expressions**, like this one:

```java 8
JOptionPane.showInputDialog(null, "Hi", "Bye", JOptionPane.MESSAGE_DIALOG);
```

Now, how many expressions are there in _**that**_ [statement](#statement)?

**Five.** Surprise, surprise.

The entire 'sentence' is one expression -- `JOptionPane.showInputDialog(...` evaluates to a [String](#string)

Within that 'sentence' itself contains four more expressions. Remember, anything that evaluates to a **single value** is an expression.  So that means, `null`, `"Hi"`, `"Bye"`, and `JOptionPane.MESSAGE_DIALOG` are expressions on their own.

But there's also something special about the first three --- they don't just evaluate to single values, but they **are** the single values! These types of values are called [literals](#literals) and you can click on that to find out more.

Besides the semicolon and the comma, most of the remaining 'punctuation marks' should perhaps be more similar to how **prepositions** are in English. Things like 'on', 'of', 'in', 'at', 'within', 'therein', 'notwithstanding', and a lot more.


#####Statement
A statement is a 'sentence' in Java.
This is the simplest statement:
```java
;
```

Yes. A semicolon. It does nothing but it is - still a statement...

One line can also have multiple statements like this:
```java
;;;
```

*But why would you want to do that?*

------

#####Complex statements:

Java also has more complex statements that can contain other statements.

This is a statement that contains three other pointless statements:

```java 8
{
	;
	;
	;
}
```

Note how the { } statement didn't need a semicolon to end it.

> In Java, this statement is called a **code-block**.

Here is another important statement that contains other statements:

```java
if (true) {
	;
	;
}
```

This is called an **if-statement**. You can see the syntax of the [if-statement here](#if-statement)

####Bracket thingies

> What are thooooosee???

There are four types of brackets that Java uses, each with it's own specific purpose.

#####(Parenthesis)

These `()` are _parenthesis_. Most probably you would have been referring to them as 'brackets' for the duration of your existence. Oh well.

Parenthesis are used for three rather different things in Java:

1. They are used as brackets as in a Mathematical [expression](#expressions) --- e.g:
	
	```java
	3 * (2 + 7)
	```
2. They are _always_ used in Java [structures](#syntax-and-flow-of-java-structures) --- e.g:

	```java
	while (true) {...
	if (true) {....
	for (int x = 0; x < 10; x++) {....
	switch (x) {.....
	```
3. They are used to group the [parameters]() of a [method](#method) like how you give the value of $x$ in this lovely quadratic function:
	$$
	f(x) = (x + 1) ^ 2\\~\\\
	\begin{align} let \, x = 3, \\\
	 \therefore f(3) &= (3 + 1) ^ 2\\\
	&= 4 ^ 2\\\
	&= 16 \end{align}$$

	Or in Java,
	```java
	System.out.println("hello");
	```
	Where `System.out.println` is your $f$, and `("hello")` is your $(x)$.

#####{Braces}

These `{}` are _braces_. They are sometimes called 'curly brackets' but I'm pretty sure 'braces' sounds much less cheesy.

They have two different uses:

1. They surround a [code block](#complex-statements)
2. They surround a list of values for declaring lists of things (as in an [array] declaration, or sometimes an [enumeration]) --- e.g:

	```java
	int[] intArray = new int[] {1, 2, 3, 5, 8, 13};
	```

#####[Brackets]

Now these `[]` things are _really_ called brackets. But just to be as precise as possible, you can call them **square brackets**.

They have two uses, both related to [arrays]:

1. They're used to set the length (a.k.a. size) of an [array]

	```java
	int[] iWant5Numbers = new int[5];
	```
2. They're used to retrieve a specific item from the array. However, be very cautious about the [zero-index](#zero-index) rule in programming!

	```java
	iWant5Numbers[2] = 3//Sets the third number to 3
	iWant5Numbers[0] = 1//Sets the first number to 1
	
	//This will display 4, because 3 + 1 = 4
	System.out.println(iWant5Numbers[2] + iWant5Numbers[0]);
	```

#####&lt;Chevrons>
Chevrons `<>`, also known as **angle brackets** are the most rarely used brackets in Java. (Don't even bother reading this if you haven't done Java for at least a month)

These mystical creatures only have one very mystical and rather complex use.

Chevrons are used to denote the type of a type --- which means --- to denote which type of object an object works with. Kinda hard to define that, but here's an example:

```java
ArrayList<String> strings = new ArrayList<String>();
strings.add("Hello ");
strings.add("world!");
System.out.println(strings.get(0));//outputs "Hello "

ArrayList<Integer> ints = new ArrayList<Integer>();
ints.add(1);
ints.add(3);
System.out.println(ints.get(1) + 4);//outputs "7"
```

An `ArrayList` is an example of a type that works with a type.

Notice how the same method `add()` and `get(int index)` can be used to add to, and retrieve different types of objects from the `ArrayList`. For the `ArrayList<String>`, you can only add and get `String` objects to it, and similarly, for the `ArrayList<Integer>`, you can only add and get `Integer` objects to it.

###2. Programming Terms

You will see these same terminology used in most programming languages. It's like a programmers' _lingua franca_ kinda' thing.

####Condition
A **condition** refers to a [boolean](#boolean) value that is used to [select which path should the code follow](#syntax-and-flow-of-java-structures).

Perhaps the most basic usage would be the [if-statement](#if-statement)

####Parameter
A **parameter** is always **passed** to a [**method**](#method).

####Function
A function is a block of code which has a name to it.
Functions have three purposes:

1. To simply run code
2. To operate on values and data it is given, if any.
3. To [return](#return) a value

You may be thinking -- why do functions need to exist then? When I type code, am I not doing what is listed above?

The whole idea of functions is to reduce the time spent typing the same code over and over again. For example, if I want to let the user type in 3 numbers and display the sum of the three, I need to do this:

```java
import javax.swing.JOptionPane;

public class SoManyLinesOfCode {
	public static void main(String[] args) {
		int num1 = Integer.parseInt(JOptionPane.showInputDialog("Enter number 1"));
		int num2 = Integer.parseInt(JOptionPane.showInputDialog("Enter number 2"));
		int num3 = Integer.parseInt(JOptionPane.showInputDialog("Enter number 3"));
		JOptionPane.showMessageDialog(null, "The sum of the three numbers is: " + (num1 + num2 + num3));
	}
}
```

Whereas, if I make use of a function to give me the numbers the user typed instead of re-typing `Integer.parseInt(JOptionPane.showI......`over again, it will look much nicer:

```java
public class CleanerCode {
	public static void main(String[] args) {
		int num1 = get("number 1");
		int num2 = get("number 2");
		int num3 = get("number 3");
		JOptionPane.showMessageDialog(null, "The sum of the three numbers is: " + (num1 + num2 + num3));
	}
	
	public static int get(String s) {
		return Integer.valueOf(JOptionPane.showInputDialog("Enter " + s));
	}
}
```

####Zero-Index
**Lists and Arrays in Java start counting from 0, instead of 1**

In English, you say:
> 3 is the 3<sup>rd</sup> number from the list {1, 2, 3, 4, 5}

But in Java, you say:
> 3 has the index of 2 in the list {1, 2, 3, 4, 5}

Or in code:

```java
int[] from1To5 = new int[] {1, 2, 3, 4, 5};
boolean thisWillBeTrue = from1To5[2] == 3;//True
boolean thisIsNotCorrect = from1To5[3] == 3;//False
```

This is because arrays and lists are **zero-indexed**. So even though 1 is the 1<sup>st</sup> number from the list, that very same number has an index of `0`, because the **index starts counting from 0**.

####Return
In programming, you use the word 'return' the same way you use the phrase 'gives you' or 'evaluates to be'.

Using this code as an example --
```java
int x = 3;
double y = Math.pow(x, 2);
```
You verbalize it as:
> Math.pow(x, 2) **returns** the value of 9.

Most of the time, this word is used to describe the final result of a [function](#function) like this:
> The function `addOne(int x)` **returns** the value of x plus one

In fact, the word is attributed to [functions](#function) so much that java has made the word `return` a [keyword](#keywords) to mean exactly what it means.

```java
public int addOne(int x) {
	return x + 1;
}
```

However, programmers also use this term casually to say things like:
> 3 * 4 **returns** 12
> this method **returns** an [integer](#int)

to just mean *'equals'* or *'gives you'*.

###3. Java Terms
####Native Class
Native Classes are the [objects] which come with Java itself. You don't need to declare or assign them to anything, you just use them. A good example would be this [method](#method):
```java
System.out.println("Hi");
```
All you did was use that method, and it displayed something. No one cares how, and nobody cares why.

####Method
A **method** is just a _fancy_ [OOP](#1-define-oop) way of saying ['function'](#function)

####Type class
(a.k.a. 'class' or 'type')
Think of type classes the same way you would think of Pokémon **types** or character **classes** in RPGs.

*Fire type, Mage class, Archer type, Dark type, Paladin class.*
They all represent the type of the character -- which determines what abilities the character has, and what are the characters' attributes (such as **Max HP**, **Mana cap**, **Attack speed**).

Similarly, the type class of a value (or [Object](#object) as you would say in Java) determines what kind of value it is.

For example -- a integer value belongs to the `Integer` class, and it has the ability to be added, subtracted, etc...; and some text belongs to the `String` class, and it has the ability to be [concatenated](#concatenation), split, etc...

#Chapter I : define Java

> This chapter will teach you how to understand the mentality behind Java code. If you wish to start with something more practical and less mind-liquifying instead, go to Chapter II, but remember to come back when you feel ready :P

**THE CODE:**⧸⧸the code first, then continue from where you still had your bearings.

##Chapter `null`: terminology

Herein lies some words you should be familiar with. You don't really need to read them now though - when a fancy word comes up, they will be linked here.

#####

##Chapter I : define Java
⧸⧸
```java 8
System.out.println("Welcome to Java!");
```

If you were to ask a fellow coder what would be the first thing that comes to your mind when you see the word "Java", it would mean either one of two things:

- Coffee
- OOP

Coffee is really important. Coffee is love - coffee is life. Especially if ⧸⧸you're⧸⧸that person is⧸⧸ a software engineer. But let's look at the ⧸⧸second attribute.


###1:⧸⧸other one.


####1:⧸⧸ define OOP

> "OOP stands for Object Oriented Programming".

 (The above statement would have been undoubtedly reiterated over nine thousand and one times across a wide span of "Learn-it-yourself Java" books.)

_Everything_ in Java is revolving around **Objects**. As a matter of fact, the only thing differentiating OOP languages and Mathematics is the concept of **Objects**.

> Everything in Java is an 'object' as to how everything ⧸⧸is a 'thing'

So variables are objects, values are objects, even the type of an object itself is an object. Even the lines and statements of code **itself** can be objects (albeit a very complex one). **Everything** is an object.

#####this is how you understand the [code](#chapter-i-define-java):

`System.out.println`

```sequence
participant System
participant out
participant println
out->System: Belongs to
println->out: Belongs to
```

> **NEW SYNTAX: Possession operator**
(Click [Syntax](#1-syntax) if you don't know what 'syntax' means)

> The **possession operator** is that dot '.' between 'System' and 'out', and the very same dot between 'out' and 'println'. This dot is the equivalent of the apostrophe S ('s) after a word, or the Chinese particle 的, or the Japanese particle の. 

Putting into context,

`System.out.println` simply means: _System's out's println_ -- which is a [native](#native-java) [method](#method) which displays text on a [console](https://en.wikipedia.org/wiki/Console_application).

`println` belongs to `out`, that belongs to `System`. 

###2: _What_ is Java?

**THE CODE:**

```java 8 
while (true) {
  System.out.println("Welcome");
}
```
> if you hadn't known already, the above code will spam you with "Welcome" forever

**Everything in Java can be classified into five main roles:**

- [Literals](#literals)
- [Keywords](#keywords)
- [Syntax](#1-syntax)
- Standard Native Java
- User-defined Java

Now let's analyze [the code](#2-what-is-java) and see which categories can be found inside.


##### [`while`](#while):
>This is a [keyword](#keywords). Keywords are very important. You'll know why later. They usually either alter the 'flow' of the program (like this `while` loop), or used as [Syntax](#1-syntax) itself. 

##### **`(`** opening [parenthesis](#parenthesis):
>This is part of the [syntax](#1-syntax) of the [`while`](#while) loop. The while loop needs a [condition](#condition) to operate.

##### [`true`](#boolean-literal):
>This is a [boolean](#boolean-literal) [literal](#literals). Literals represent values as-is. For example, the value `true` is simply equal to `true`. There's nothing else that `true` is made of. 

##### **`)`** closing [parenthesis](#parenthesis):
>This is also [syntax](#1-syntax). It closes the [opening parenthesis](#opening-parenthesis) you saw earlier.

##### **{** opening [braces](#braces):
>This is [syntax](#1-syntax) denoting the start of a [code block](#complex-statements), which is where multiple [statements](#statement) of code is grouped together so it can be executed as if it were one statement.

##### `System.out.println`:
>This is standard native Java. `System`, `out`, and `println` are already defined by Java. There's nothing special to it other than the fact that it exists the moment you install Java. 
>
> If you were to type `asdf.derp.potato` however, you will be getting an error because it _doesn't exist_. You will need to define it _painstakingly_ and _manually_. But if you eventually decide to define it, then good for you, because that's what you call User-Defined Java.

##### **(** opening [parenthesis](#parenthesis):
> Once again, syntax. Click on the link to find out what it's for

#####`"Welcome"`:
> This is a different type if [literal](#literals) called a [String literal]

##### **)** closing [parenthesis](#parenthesis):
> Surrounds the literal `"Welcome"`. Again, syntax.

#####`;` semicolon:
> Syntax again. All [simple statements](#statement) must end with a semicolon.

#####`}` closing [braces](#braces):
> Syntax --- What is opened must be closed. This syntax will group everything that is within the opening and closing braces as a single statement to execute every time the [while loop](#while) loops.

-----

#Chapter II: Start writing Java

Java is, put in the most respectful manner possible, a beast. But like all beasts, there is always an entrance where everything starts.

In Java, that entrance is known as
```java
public static void main(String[] args) {
	
}
```

&lt;dramatic music plays>

 It is also often referred to as the program's _entry point._ [Statements](#statements) will start executing from this very place.

Now it's good to know a few things about this 'entry point' first:

1. This is usually called a "main method". `main` is the name of the method. A method (a.k.a function) is just a [block of code](#complex-statements) which has a name. You will learn more about this 'method' thing later on.

2. You must always, always have `public static void`. These are [modifier keywords], but it is not important to know what they do.

3. It must always be called `main`. There's a reason why it's called the `main` method.

4. `String[] args` must always be there. This is because, when you run any program, you can choose to run it in default mode, or you can run it in some special modes. When running in a 'special mode', `args` will contain a list of 'settings' that you will use in your code if you want it to have an effect on your program. Not that you will _actually_ use it though...

Now that we know where to start writing the program, let's write some code!

...

Or _not._

----

##1. How to create a .java file.

Before you can start adding lines to the `main()` method, we need to find out where to put this. All Java source code are in .java files, and there are three things to take note of when creating these Java files.

1. All the source code will be in a folder marked as source by the IDE. If you're using NetBeans IDE, you can find where by going to File > Project Properties > Sources > Source Package Folders. The path of the source code file will usually be `projectName/src`. 

2. The path of the code file must be reflected in the source. This means that if the file is in `projectName/src/hello/welcome/to/sparta`, the first line of code **must** be
	```java
	package hello.welcome.to.sparta;
	```
	Note that projectName and src is not within that line of the code, because they are already configured in step 1.

3. Every .java code file must have a [`public`] [`class`] (you'll know what that is soon). Also, this `public class` **must** have the same name as the .java file. That means, if your code file is called DerpityHerp.java, your class must be defined like this:
	```java
	public class DerpityHerp {
	
	}
	```

---

Putting all of this together, if you want to start writing some code in a file called `ThisIsSparta.java`, and that file can be found in `.../Spartacus/src/welcome/to/sparta`, you will need to do this:

```java
package welcome.to.sparta;

public class ThisIsSparta {
	public static void main(String[] args) {
	}
}
```

Simple enough.

----
##2. Start writing some spartan code
Now that we can create a very medieval sounding .java file, let's start by displaying a very classic line indeed.

**THE CODE:**
```java 8
package welcome.to.sparta;

public class ThisIsSparta {
	public static void main(String[] args) {
		System.out.println("THIS. IS. SPARTAAA!!");
	}
}
```

####What it does

The console displays

```text
THIS. IS. SPARTAAA!!
```

(If you had already read Chapter 1, there shouldn't be anything here that surprises you, but just in case you haven't -- [click here](#1-define-oop).)

####Things to take note:

- `"THIS. IS. SPARTAAA!!"` is called a [String Literal](#string-literal)
- `System.out.println(....` is a [native](#native-java) [function](#function) that displays a [String](#string) in a console, which in this case, is the [String literal](#string-literal) mentioned above.
- `;` is a **semicolon** and it is **very important**. All basic statements in Java must end with a semicolon. Find out what it does [here](#punctuation).

-----
###3. More drama plz
Yes, yes I heard you.

**THE CODE:**
```java
package welcome.to.sparta;

public class ThisIsSparta {
	public static void main(String[] args) {
		System.out.print("THIS. ");
		Thread.sleep(1000);
		System.out.print("IS. ");
		Thread.sleep(1000);
		System.out.print("SPARTA");
		Thread.sleep(100);
		System.out.print("A");
		Thread.sleep(100);
		System.out.print("A");
		Thread.sleep(100);
		System.out.print("!");
		Thread.sleep(100);
		System.out.print("!");
	}
}
```

####What it does:
The console starts out showing
```text
THIS. 
```
and 1 second later
```text
THIS. IS.
```
and 2 seconds later:
```text
THIS. IS. SPARTA
```
followed by a stream of `A` and `!` and ends up looking like this:
```text
THIS. IS. SPARTAAA!!
```

####Things to take note:
- The code uses `System.out.print(..` instead of `System.out.println(..`. The difference is that `println` first displays the [String](#string) parameter in the console, then it moves to the next line, or in typing terms, 'presses the enter key'. Whereas, `print` just displays the string on the same line.
In that respect, `System.out.println(string)` is the same as doing `System.out.print(string + "\n")` because `"\n"` is Java's way of 'pressing the enter key'. (Click [here](#string-literal) if you want to find out why)
- `Thread.sleep(long milliseconds)` lets you pause the program for the given number of milliseconds.
- The program flows downwards, not the other way around. Also, each line won't be executed at the same time. (I know this is common sense, but this is a **really** important thing to note)
- Once again, the beloved `;` must be placed at the end of every single-line statement.

----

###4. Going deeper

Now that you know how to get stuff showing up on your console, it's time dig a little deeper into what is _really_ going on.

Let's talk about `System.out.println()`...

Go ahead, type `System.out.printl` in NetBeans or IntelliJ IDEA -- purposely leave out the last `n`, and press `Ctrl` - `Space` to show up the auto-complete thingamajig. Now look at the autocomplete dialog box. You should see something like

> System.out.println()
> System.out.println(**Object** x)
> System.out.println(**String** x)
> System.out.println(**boolean** x)
> System.out.println(**char** x)
> System.out.println(**char[]** x)
> System.out.println(**double** x)
> System.out.println(**int** x)
> System.out.println(**long** x)

Now -- you may be wondering... Why on Earth are there so many `System.out.println`s?!

Let me explain --
Each one of those `System.out.println`s are called **method overloads**. A [**method**](#method) is just some code that has a name. So for example, instead of writing 1000 lines of code over and over again, you can save it with a name of your preference, and use that name to run that 1000 lines of code. We'll go through this in detail eventually.

But let's look at **overloads**

Notice how we used `System.out.println` like this earlier on?
```java
System.out.println("THIS. IS. SPARTAAA!!");
```

If you haven't known already, `"THIS. IS. SPARTAAA!!"` is a [String literal](#string-literal) -- which means that it is a `String` [type](#type-class) value. Notice how this fulfills one of the many `System.out.println`s listed above --- particularly this:

> System.out.println(**String** x)

This means that we are substituting the value of the String type `"THIS. IS. SPARTAAA!!"` as `String x` which is one of the method overloads listed when `ctrl`-`space` was pressed.

By looking the other overloads, `System.out.println` can also accept not just a `String` [type](#type-class), but many others, like an [int](#int) that can be provided by an [int literal](#int-literal):

```java
System.out.println(1337);
```

Or even a [boolean](#boolean) that can be supplied by a [boolean literal](#boolean-literal):

```java
System.out.println(false);
```

However, don't think that all functions can take any and every [type](#type-class) of value like how `System.out.println` does!

If you were to do this:

```java
Thread.sleep("hello");
```

There would definitely be an **error** -- and you'll know why when you press `ctrl`-`space` after typing `Thread.sl`. If everything is working well, you should see something like:

> Thread.sleep(**long** millis)
> Thread.sleep(**long** millis, **int** nano)

A [long](#long) is a type of integer. Supplying a [`String`](#string) when `Thread.sleep` requires you to give it a `long` will only result in an error that looks something like this:

> Error: (line, column) java: incompatible types: java.lang.String cannot be converted to long

Which is really self-explanatory when you think about it -- `Thread.sleep` can only take a **`long`**, not a String!

However, if you are observant enough, you would also notice that **another method overload** exists for `Thread.sleep`. This time, instead of seeing just one input value -- there are two! One for milliseconds and another for nanoseconds. In order to use this method overload, you have to make sure you give `Thread.sleep` two separate values like this:

```java
Thread.sleep(0, 1);
```

This will set `long millis` as 0, and `int nano` as 1. 
As you can see, the comma separates the two values, so that Java knows you're giving `Thread.sleep` two values, not one. 

Note that both [`long`](#long) and [`int`](#int) share the same [literal](#literals) -- which is the [integer literal](#int-literal), and so even though they are both different [types](#type-class), you can key them in the same way and Java will automatically sort it out for you.

------

###In summary --

In this chapter, you've learned how to

1. Type out the `main` function -- where the program starts
2. Create a `.java` source code file
3. Name your class correctly -- Same name as the code file
4. Use `System.out.print` and `System.out.println`
5. Hit `ctrl`-`space` when you are in doubt.
6. Read the auto-complete dialog that appears when you hit `ctrl`-`space` and make use of it to see what [types](#type-class) of values you need to give a [method](#method)

#Chapter 2:

# Appendix

##Keywords

Keywords have a special place in Java --- It would be impossible to write a program in Java without using a keyword. 

They have many different uses; some of them are used to define a variable of a [primitive type](#primitive-types), some of them alter the [flow of the program](#syntax-and-flow-of-java-structures), and some of them are used to create and expand Java itself (trust me we won't be going into that anytime soon).

Anyways, here is an exhaustively exhausting list of keywords for your variable-naming pleasure.

#####Primitive type keywords
These keywords are used to define variables

[`boolean`](#boolean)

[`byte`](#byte)

----

##Literals

Literals are values that are what they are. It's like how 1 equals 1 -- yes means yes; there's no explanation to it, and they are just themselves, and they are not made up of anything simpler. Most literals are [Primitive values](#primitive-types), and the only exception is the [String](#string).

####[Boolean](#boolean) Literal
There are only two values. `true` for true, and `false` for false.
```java
boolean yep = true;
boolean nuhp = false;
```

####[Char](#char) Literal
If you want to _literally_ put in a character, use single quotes:
```java
char A = 'A'
```
Note that chars can also be defined _figuratively_ by type-casting numbers into chars:
```java
char alsoA = (char) 65
```
You can see which number relates to which char in an [ASCII Table](http://www.asciitable.com/)

####[Int](#int) Literal
The integer's literal format can be used for [bytes](#byte), [shorts](#short), [ints](#int), and [longs](#long).

An integer literal is simply just a number without a decimal point -- as in:

```java
int x = 13379001;
byte y = 34;
```

However, **don't think that negative integers are still considered literals!** This may sound very counter-intuitive, but there are no such things as 'negative-number literals' in Java. Instead, they are regarded as [expressions](#expressions).

The negative number `-1337` is actually made up of two different parts, the [unary] [negation operator] `-`, and the integer literal `1337` -- hence it is an expression instead, not a single value literal.

**If you really want to,** there are also more quirky and nerdy ways to punch in a number in Java. (It's ok if you don't understand the following section)

For **octal**  numbers in **base 8**, put a `0` in front of the number. Because this is in base 8, you only have 8 digits -- so that means you can only use the digits
`0 1 2 3 4 5 6 7`

```java
int _10 = 012;//This is 10 in decimal aka what you count with
```

For **binary** numbers, which is **base 2**, put a `0b` in front of the number. Once again, you only have 2 digits that you can use, `0` and `1`.

```java
int thisIsAlso10 = 0b1010;
```

And for **hexadecimal** numbers -- **base 16**, prefix  `0x` to the start of the number. You have 16 digits to choose from -- `0 1 2 3 4 5 6 7 8 9 a b c d e f`.

```java
int thisIsAnother10 = 0xA;
```

####[Floating point](#float) literal
A floating point literal is used for [floats](#float) and [doubles](#double). It just means 'number with a decimal point'.

Very simply put, the only thing that separates a floating point literal from an integer literal is the decimal point.

However, there is something you must note -- **if you want your number to be a float, you have to suffix an `f` to the end of the number. If not, that number will be, by default, a double. ** Also, if for whatever reason you want to **ensure** yourself that the number is a double, you can add a `d` behind the number.

```java
float x = 0.13f;//Good
float y = 0.13;//Bad. 0.13 is a double, but y must be a float.

double z = 0.13d//Good, but the d is not necessary
double a = 0.13f//Bad.
```

Sometimes, you need a double or float without a decimal point, but you don't want it to be read as an [`int`](#int) either -- such as in this case:

```java
double wrong3Over5 = 3 / 5;//This is 0! I want it to be 0.6!!
```

This 'issue' arises because if you operate with two [ints](#int) you get an int, no matter what. And because an int cannot have decimal places, anything after the decimal places gets cut off, not even rounded up. In order to solve this, either one, or both, of the numbers must be a double or float. 

```java
double correctThreeFifth = 3.0 / 5;
double anotherCorrectThreeFifth = 3 / 5d;

float threeFifthFloat = 3.0f / 5;
```

Another thing to take note -- **If one or both of the values are a float, the result wil be a float, and vice versa, if one or both of the values are a double, the result will be a double. But what happens when you do this?**

```java
float threeFifthError = 3d / 5f;
```

You get an error. You cannot combine doubles with floats.

Also, there are also other ways that you can make a double or a float:

```java
double d = .3;//This is 0.3 as a double
double e = 153.;//This is 153 as a double
float f = .3f;//This is 0.3 as a float
float g = 153.f;//this is 153 as a float

double h = 1337d//This is 1337 as a double
float i = 1337f//This is 1337 as a float
int j = 1337//If you leave out the d or f, it becomes an int
```

And you can also make use of the standard scientific form to make double and float literals:

```java
double x = 1e6//This is 1 million as a double
float y = 1e6f//This is 1 million as a float
double z = 1e-9//This is 1 billionth, or 0.000,000,001 as a double
float a = 1e-9//Same thing as a float
double b = 1.35e2//This is a pointless way to make 135 as a double
double c = 135d//This is a smarter way
```

####String
A String is the only non-[primitive type](#primitive-types) in Java to have a literal form -- and for this reason, many confuse Strings to be a Java primitive type, when it actually isn't.

String literals are very simple to create -- all you have to do is enclose some text within double quotes like this:
```java
"This is a String!"
```

However, if you want to key in special characters, quotation marks like new lines or other weird characters not from the English language, you can't simply add them in like this:

```java
"Hello! I said, "Hi!".
π♪"
```

You will end up with lots of horrific errors and red squiggly lines.

Instead, it should look something like this:
```java
"Hello! I said, \"Hi!\".\n\u0225\u0525"
```

To get special characters, you need to use escape sequences. "Escape" meaning that you escape normal Java [Syntax](#syntax). A good example of this would be the in the double quotes here:

```java
"It went \"BOOM!\""//It went "BOOM!"
```

Because you have to start and end a string with these `"` double quotes, putting a double quote within the String itself would be impossible, because it would mean the the String literal has finished. In order to overcome this, the escape sequence `\"` is used to tell the String literal reading machine to not stop the string there -- but continue on and treat `\"` as `"` which would be impossible to type in a String if not for the escape sequence.

#####Escape sequences

Here is an exhaustive list of escape sequences:

- `"\n"`: New line

	```java
	"A\nB" becomes
	A
	B
	```
- `"\t"`: Tab

	```java
	"A\tB" becomes
	A	B
	```
- `"\b"`: Backspace

	```java
	"A\bB" becomes
	B
	```
- `"\r"`: Carriage Return (hardly used)
	Moves the 'cursor' back to the start of the line and overwrites any existing characters from there.

	```java
	"Abcdef\refg" becomes
	efgdef ('efg' overwrites the first three characters 'Abc')
	```
- `"\f"`: Formfeed (also hardly used)
	Goes to the next page
	
	```java
	"A\fB" becomes
	A
	(next page)
	B
	```
- `"\'"`: Single quote character
	Mostly used for escaping the single quote char

	```java
	char singleQuote = '\'';
	```
- `"\""`: Double quote character

	```java
	"And his name was \"JOHN CENAAAA!!!!\"" becomes
	And his name was "JOHN CENAAAA!!!!"
	```
- `"\\"`: Backslash escape
	Because the backslash is already used to denote an escape sequence - keying in a backslash would require an escaping of the escape character.

----

##Primitive Types

Primitive [types](#type-class) are the most basic and fundamental types to Java. They cannot be simplified any further, nor do they contain any other values besides themselves. Think of these as how you would think of sub-atomic particles. All other [types](#type-class) are -- in it's most simplified and reduced form -- primitive types.

#####Boolean
A `boolean` can only hold two different values.
[`true`](#boolean-literal): meaning that an [expression](#expressions) holds true
[`false`](#boolean-literal): meaning that an [expression](#expressions) is not true

```java
boolean nope = (3 == 5);//this will be false, 3 is not 5
boolean yep = (3 < 5);//this will be true, 3 is less than 5
```

#####Byte
A `byte` is any integer from -128 to 127, or mathematically speaking,
$$range(-2^7, 2^7-1)$$
It's literal format is the same as the [int literal](#int-literal)

#####Short
A `short` is any integer from -32,768 to 32,767, or
$$range(-2^{15}, 2^{15} - 1)$$
It's literal format is the same as the [int literal](#int-literal)

#####Char
A `char` is essentially a [`short`](#short), but the range is shifted such that the lowest number is 0. This means that a char can have a value from 0 to 65,535. Most of the time though, you won't be using `char`s this way, and you would use the [single quote to denote a `char` literal](#char-literal).

#####Int
An `int` is any integer from --2,147,483,648 to 2,147,483,647, or
$$range(-2^{31}, 2^{31} - 1)$$
It's literal is simply a [number without a decimal point](#int-literal)

#####Long
A `long` is any integer from –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807, or
$$range(-2^{63}, 2^{63} - 1)$$
It's literal format is the same as the [int literal](#int-literal)

#####Float
A `float` is a decimal number that can be accurately used from about $-3.4\times10^{38}$ to $3.4\times10^{38}$. However, it gets less accurate the larger the number. This is because floats (and [doubles](#double)) uses the standard scientific form to express numbers, that is:
$$x \times 10^n; where\; 1 \le x \lt 10$$

and due to the limitations of a float -- 23 bits of significand (that is $x$) and 8 bits of exponant (that is $n$),

> The minimum value of x is limited to the smallest binary increment, which is `0b0000 0000 0000 0000 0000 001` (as many binary digits as the significand), and the range of the exponant is from $-2^{e-1}$ to $2^{e-1} - 1$ where $e$ is the exponant.

and put in the most simple way, the number of decimal places the value $x$, which is called the _significand_, can have is limited. This means that you can have a really small number that is accurate to many decimal places, or you can have a really huge number and hundreds and thousands will get punted off in every direction every time you try adding or subtracting with that value

It's literal format is the [floating point literal](#floating-point-literal), which is the same as a [double's](#double)

#####Double
A `double` is a decimal number that can be accurately used from about $-1.7\times10^{308}$ to $1.7\times10^{308}$. It works the same way as a [float](#float) -- and gets less accurate the greater the magnitude of the number, just that it has an significand consisting of 52 bits, and an exponent of 11 bits. (See [float](#float) to find out what that means)

It has the same literal format as the [float](#float), which is the [floating point literal](#floating-point-literal)

#####Not String!
A `String` is **not** a Primitive Type - contrary to what you would expect. To see more about Strings, click [here](#string).

##Useful Java classes
Here are some pre-loaded classes that you will use a lot in your adventures with Java...

###String
The `String` class, or more precisely, `java.lang.String`, is simply put, [char](#char)acters strung together in one line to form text. 

It is commonly mistaken as a [Primitive Type](#primitive-types) because it has it's own [literal](#string-literal). However, do not get confused -- Strings are more than just a primitive type as even String literals carry their own [methods](#method) like these:

```java
String[] upperCaseWords = "Hello World!".toUpperCase().split(" ");
```

####Concatenation

There are many things you can do with a String, but most important is String concatenation -- meaning 'Joining two strings together' which can be done in two ways:

```java
//The addition method
String derpherp = "derp" + "herp"

//The String.concat() method
String another_derpherp = "derp".concat("herp");
```

The difference is that if you use the `.concat()` method, the value you want to join to the end of the String **must** be a String -- whereas if you use the `+` operator, you can do this:

```java
String whatIs3Times5 = "3 * 5 = " + (3 * 5);
```

and Java will automatically turn (3 * 5) into a String using the `String.valueOf()` method.

Be very careful when you do String concatenation -- as all the `+` operators have the same precedence (see [Order of Operations]), it is operated from left to right. Doing this:

```java
System.out.println(3 + 5 + " is 35");
```

will give you
> 8 is 35

Because the [integers](#int) 3 and 5 are added first - to give 8, then the number 8 is converted into a String because `" is 35"` is a String which concatenates to (is added to the end of) the number 8.

####List of String methods

----

## Syntax and flow of Java structures 
### Loops 
#### While
```java 8 
//Syntax:
while (condition::boolean) {code block}

//E.g.:
int x = 5;
while (x > 0) {
	System.out.println(x--);
}
```

```flow
st=>start: Start
end=>end: End
cond=>condition: Is condition true?
sub=>subroutine: Execute statements

st->cond
cond(yes, right)->sub(right)->cond
cond(no)->end
```

###Selections
####If-statement

---

##Operators

Java operations can do either one, or both of the following actions:

1. Return a new value
2. Change a value

For example, the assignment operator `=` changes a value

```java
int x = 1;
x = 2;//x is changed to 2
```
The addition operator `+` returns a new value

###Order of Operations
As to how the 'BODMAS' rule applies to mathematics, a much more comprehensive '⧸⧸in real life is a 'thing'

That is all you have to know about _objects_

#####how to [read the code](#charpter-i-define-java)

`System.out.println`

```sequence
participant System
participant out
participant println
out->System: Belongs to
println->out: Belongs to
```

> NEW (SYNTAX)[]:

####2: _What_ is Java?

Java is made up of the following things⧸⧸