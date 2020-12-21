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
