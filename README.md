# C-sharp-notes

This is a c# notes from the microsoft tutorials

## Datatypes :

- There are many types of datatypes in C# for now we are g0ing to learn about only basics.

1. char

```cs
char a = 'v';
```

2. int

```cs
int i = 8;
```

3. decimal :

```cs
Console.WriteLine(12.3m);
```

> note:You can use either a lower-case m or upper-case M as the literal suffix for a decimal. 4. boolean :

```cs
bool b = true;
```

5. string:

```cs
string s = "Vishal";
```

## Variable name rules and conventions

A software developer once famously said "The hardest part of software development is naming things." Not only does the name of a variable have to follow certain syntax rules, it should also be used to make the code more human-readable and understandable. That's a lot to ask of one line of code!

Here's a few important considerations about variable names:

Variable names can contain alphanumeric characters and the underscore character. Special characters like the hash symbol # (also known as the number symbol or pound symbol) or dollar symbol $ are not allowed.
Variable names must begin with an alphabetical letter or an underscore, not a number. Developers use the underscore for a special purpose, so try to not use that for now.
Variable names must not be a C# keyword. For example, you cannot use the following variable declarations: decimal decimal; or string string;.
Variable names are case-sensitive, meaning that string Value; and string value; are two different variables.
Variable names should use camel case, which is a style of writing that uses a lower-case letter at the beginning of the first word and an upper-case letter at the beginning of each subsequent word. For example: string thisIsCamelCase;.
Variable names should be descriptive and meaningful in your application. Choose a name for your variable that represents the kind of data it will hold.
Variable names should be one or more entire words appended together. Don't use contractions because the name of the variable (and therefore, its purpose) may be unclear to others who are reading your code.
Variable names shouldn't include the data type of the variable. You might see some advice to use a style like string strValue;. That advice is no longer current.
The example string firstName; follows all of these rules and conventions, assuming I want to use this variable to store data that represents someone's first name.

Variable name examples
Here's a few examples of variable declarations using the data types we learned about previously.

```cs
C#

Copy
char userOption;

int gameScore;

decimal particlesPerMillion;

bool processedCustomer;
```

## What are implicitly typed local variables?

1. var :

- You can only use the var keyword if the variable is initialized.
- It's important to understand that the var keyword is dependent on the value you use to initialize the variable. If you try to use the var keyword without initializing the variable, you'll receive an error when you attempt to compile your code.

## Perform basic string formatting in C#

### Character Escape Sequences ("\back slash") :

- To handle that situation, use the \" escape sequence.

```c#
Console.WriteLine("Hello \"World\"!");
```

If you run the code above, you would see the following output.

Output

```c#
Hello "World"!
```

- What if you need to use the backslash for other purposes, like to display a file path?

```C#
Console.WriteLine("c:\source\repos");
```

- Unfortunately, C# reserves the backslash for escape sequences, so if you run the code, the compiler will display the following error.

Output

```cs
(1,22): error CS1009: Unrecognized escape sequence
```

- The problem is the sequence \s. The \r doesn't produce an error because it is a valid escape sequence for a carriage return. However, it's unlikely that you would want to use a carriage return in this context.

- To solve the problem, you use the \\ to display a single backslash.

```C#
|Console.WriteLine("c:\\source\\repos");
```

- Escaping the back slash character produces the output you intended.

Output

```cs
c:\source\repos
```

## Escape character in C# :

- We can escape the special meaning of any character using `"\"`.

## Verbatim String Literal `"@"`:

- We can use this with any number of space and tabs without using any escape character in the String.

## Unicode Escape Characters `"\u"` :

- We use this to get the character using the unicode value `\u`
  using this we can add four character code. and get the values.

## Exercise - String Interpolation `"$"`:

- We can do the string concat using

```cs
string firstName = "Bob";
string greeting = "Hello";
Console.WriteLine($"{greeting} {firstName}!");
```

## Combine verbatim literals and string interpolation. :

- We can combine them and make use of them and they will be useful to work with

```cs
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");
```

## namespace :

- This is used to manage the code and avoid the name collisions.

## System.Random :

```cs
Random dice = new Random();
int roll = dice.Next(1, 7);
Console.WriteLine(roll);
```

## Stateful versus stateless methods :

- In computing, state describes the condition of the execution environment at a specific moment in time. As your code executes line by line, values are stored in variables. At any moment during execution, the current state of the application is the collection of all values stored in memory.

Some methods don't rely on the current state of the application to work properly. In other words, stateless methods are implemented so that they can work without referencing or changing any values already stored in memory. Stateless methods are also known as static methods.

For example, the Console.WriteLine() method doesn't rely on any values stored in memory. It performs its function and finishes without impacting the state of the application in any way.

Other methods, however, must have access to the state of the application to work properly. In other words, stateful methods are built in such a way that they rely on values stored in memory by previous lines of code that have already executed. Or they modify the state of the application by updating values or storing new values in memory. They're also known as instance methods.

Stateful (instance) methods keep track of their state in fields, which are variables defined on the class. Each new instance of the class gets its own copy of those fields in which to store state.

A single class can support both stateful and stateless methods. However, when you need to call stateful methods, you must first create an instance of the class so that the method can access state.

## Conversion of the data :

- Use a helper method on the data type
- Use a helper method on the variable
- Use the Convert class' methods

* `ToString()` - to convert values to the string.
* `Parse()` - to convert from string to the `int` value.

## Using Convert class :

- `TryParse()` - this is a method from the `Convert` class
- `ToInt32()` - this convert from string to the int.

## Array :

- `Sort()`
- `Reverse()`
- `Clear()`
- `Resize()`
- `ToCharArray()`
- `Join()` -

```cs
string value = "abc123";
char[] valueArray = value.ToCharArray();
Array.Reverse(valueArray);
// string result = new string(valueArray);
string result = String.Join(",", valueArray);
Console.WriteLine(result);
```

- `Split()`

## String :

Here are most important takeaways from this unit about string formatting:

You can use composite formatting or string interpolation to format strings.
With composite formatting, you use a string template containing one or more replacement tokens in the form {0}. You also supply a list of arguments that are matched with the replacement tokens based on their order. Composite formatting works when using string.Format() or Console.WriteLine().
With string interpolation, you use a string template containing the variable names you want replaced surrounded by curly braces. Use the $ directive before the string template to indicate you want the string to be interpolated.
Format currency using a :C specifier.
Format numbers using a :N specifier. Control the precision (number of values after the decimal point) using a number after the :N like {myNumber:N3}.
Formatting currency and numbers depends on the end user's culture, a five character code that includes the user's country and language (per the settings on their computer).

Methods that either add blank spaces for formatting purposes (PadLeft(), PadRight())

Methods that either compare two strings or facilitate comparison (Trim(), TrimStart(), TrimEnd(), GetHashcode(), the Length property)

Methods that help you determine what's inside of a string, or even retrieve just a part of the string (Contains(), StartsWith(), EndsWith(), Substring())

Methods that change the content of the string by replacing, inserting, or removing parts (Replace(), Insert(), Remove())

Methods that turn a string into an array of strings or characters (Split(), ToCharArray())

- `IndexOf()` and `Substring()` `IndexOfAny()`
