#Java From The Top Down

[TOC]

#####Preface (tl;dr)

It begins with a common educational concept. Basics first, then move on. This concept is especially prevalent in the education systems of USA, South Korea and a majority of South East Asian countries (including Singapore). Consensus has it that this is the most _logical_ way to transfer knowledge.

However, this methodology also presents its inhibitions. It is diminished in a fundamental area of the learning process: causation. Learning from the bottom-up will _look as if_, from the perspective of the educator, 'bottom-up' per se. However, for the student, the quantity of misidentified and misunderstood concepts are legion. 

This psuedo-book/tutorial does not prove to be the _only_ way to learn, but it always helps to give **another option**, and this (hopefully) will be that other option.

#####How to read this psuedo-book:

Every part of this 'book' is based on, and will explain, a block of code, and not the other way around. This means that the natural human learning process of experiencing first, then learning, will be utilised. This also means that it will be a little less organized compared to a standard book. 

Whenever you are lost, go back and look at **THE CODE:** first, then continue from where you still had your bearings.

##Chapter `null`: terminology

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

####Condition
A **condition** refers to a [boolean](#boolean) value that is used to [select which path should the code follow](#syntax-and-flow-of-java-structures).

Perhaps the most basic usage would be the [if-statement](#if-statement)

####Parameter
A **parameter** is always **passed** to a [**method**](#method).

####Method
A **method** is just a _fancy_ [OOP](#1-define-oop) way of saying ['function']

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

##Chapter I : define Java

> This chapter will teach you how to understand the mentality behind Java code. If you wish to start with something more practical and less mind-liquifying instead, go to Chapter II, but remember to come back when you feel ready :P

**THE CODE:**
```java 8
System.out.println("Welcome to Java!");
```

If you were to ask a fellow coder what would be the first thing that comes to your mind when you see the word "Java", it would mean either one of two things:

- Coffee
- OOP

Coffee is really important. Coffee is love - coffee is life. Especially if you're a software engineer. But let's look at the second attribute.


###1: define OOP

> "OOP stands for Object Oriented Programming".

 (The above statement would have been undoubtedly reiterated over nine thousand and one times across a wide span of "Learn-it-yourself Java" books.)

_Everything_ in Java is revolving around **Objects**. As a matter of fact, the only thing differentiating OOP languages and Mathematics is the concept of **Objects**.

> Everything in Java is an 'object' as to how everything is a 'thing'

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

`System.out.println` simply means: _System's out's println_.

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

#Chapter II: How to start writing Java

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

4. `String[] args` must always be there. This is because, when you run any program, you can choose to run it in default mode, or you can run it in some special modes. When running in a 'special mode', `args` will contain a list of 'settings' that you must use in your code so that it will have an effect on your program. Not that you will _actually_ use it though...

# Appendix

##Keywords

Keywords have a special place in Java --- It would be impossible to write a program in Java without using a keyword. 

They have many different uses; some of them are used to define a variable of a [primitive type](#primitive-types), some of them alter the [flow of the program](#syntax-and-flow-of-java-structures), and some of them are used to create and expand Java itself (trust me we won't be going into that anytime soon).

Anyways, here is an exhaustively exhausting list of keywords for your variable-naming pleasure.

#####Primitive type keywords
These keywords are used to define variables

[`boolean`](#boolean)

[`byte`](#byte)

##Literals

#####Boolean Literal
There are only two values. `true` for true, and `false` for false.

#####Char Literal
If you want to _literally_ put in a character, use single quotes:
```java
char A = 'A'
```
Note that chars can also be defined _figuratively_ by type-casting numbers into chars:
```java
char alsoA = (char) 65
```
You can see which number relates to which char in an [ASCII Table](http://www.asciitable.com/)

##Primitive Types

#####Boolean
A `boolean` can only hold two different values.
`true`: meaning that an [expression](#expressions) holds true
`false`: meaning that an [expression](#expressions) is not true

```java
boolean nope = (3 == 5);//this will be false, 3 is not 5
boolean yep = (3 < 5);//this will be true, 3 is less than 5
```

#####Byte
A `byte` is any number from -128 to 127, or mathematically speaking,
$$range(-2^7, 2^7-1)$$

#####Short
A `short` is any number from -32,768 to 32,767, or
$$range(-2^{15}, 2^{15} - 1)$$

#####Char
A `char` is essentially a [`short`](#short), but the range is shifted such that the lowest number is 0. This means that a char can have a value from 0 to 65,535. Most of the time though, you won't be using `char`s this way, and you would use the [single quote to denote a `char` literal](#char-literal).

 
## Syntax and flow of Java structures 
### Loops 
#### While
```java 8 
while (condition::boolean) {
  //statements 
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