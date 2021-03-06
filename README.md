# Clean Code - Handbook of Agile Software Craftsmanship
This is my summary of the Clean Code - Handbook of Agile Software Craftsmanship by Robert C. Martin.
Contributions: Issues, comments and pull requests are super welcome 😃
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->
# Table of Contents
- [Chapter 1. Introduction](#Chapter-1-introduction)
- [Chapter 2. Meaningful Names](#Chapter-2-meaningful-names)
- [Chapter 3. Functions](#Chapter-3-functions)
<!-- /TOC -->
# Chapter 1. Introduction
- This Book is about good programming. It's about how to write good code, and how to transform bad code into good code.
- The code represents the detail of the requirements and the details cannot be ignored or abstracted. We may create languages that are closer to the requirements. We can create tools that help us parse and assemble those requirements into formal structures. But we will never eliminate necessary precision.
- Procrastination cleaning your code may be a trap to LeBlanc's Law.
	- Later equals never.
- As the mess builds, the productivity of the team continues to decrease, asymptotically approaching zero.
- It’s not enough to write the code well. The code has to be kept clean over time. We have all seen code rot and degrade as time passes. So we must take an active role in preventing this degradation.
- Each experimented programmer has his/her own definition of clean code, but something is clear, a clean code is a code that you can read easily. The clean code is code that has been taken care of.
# Chapter 2. Meaningful Names
- Since names are scattered eveywhere in the programming environment, we should take some time to create meaningful names.
- **Use intention-revealing names**
	- Any name should answer the following three questions:
		- Why it exists?
		- What it does?
		- How it is used?
	- Example of bad naming: `int d; elapsed time in days`
	- Examples of good naming:
		- `int elapsedTimeInDays;`
		- `int fileAgeInDays;`
	- A code should be explicit in meaning not implicit as well as simple in structure.
- **Avoid disinformation**
	- Programmers must avoid leaving fast clues that obscure the meaning of code.
	- We should avoid words whose entrenched meanings vary from our intended meaning.
	- Spelling similar concepts similarly is information.
		- Using inconsistent spellings is disinforamtion.
- **Make meaningful distinctions**
	- If names must be different, then they should also mean something different.
		- For example, naming a variable arbitary name in order not to confilct with reserved word.
- **Use pronounceable names**
	- Programming is a social activity, so you should use names which can be pronouncead easily without making you an idiot.
- **Use searchable names**
	- Longer names trump shorter ones, and any searchable name trumps a constant in code.
	- The length of a name should correspond to the size of its scope.
- **Avoid encoding**
	- Encoding type or scope information into names simply adds an extra burden of deciphering.
	- Encoded names are seldom pronounceable and are easy to mis-type. An example of this, is the use of the Hungarian Notation or the use of member prefixes.
- **Avoid mental mapping**
	- Readers shouldn't have to mentally translate your names into other names they already know.
	- One difference between a smart programmer and a professional programmer is that the professional understands that clarity is king. Professionals use their powers for good and write code that others can understand.
	- Classes and objects should have noun or noun phrase names like Customer, WikiPage, Account, and AddressParser. Avoid words like Manager,Processor, Data, or Info in the name of a class. A class name should not be a verb.
	- Methods should have verb or verb phrase names like postPayment, deletePage or save. Accessors, mutators, and predicates should be named for their value and prefixed with get, set, and is according to the javabean standard.
	- When constructors are overloaded, use static factory methods with names that describe the arguments. For example:
		- `Complex fulcrumPoint = Complex.FromRealNumber(23.0);`
		- Is generally better than
		- `Complex fulcrumPoint = new Complex(23.0);`
- **Don't be cute**
	- Choose clarity over enterainment value.
	- Say what you mean. Mean what you say.
- **Pick one word per concept**
	- A consistent lexicon is a great boon to the programmers who must use you code.
- **Don't pun**
	- Avoid using the same word for two purposes.
	- Using the same term for two different ideas is a pun.
	- Example: in a class use `add` for create a new value by adding or concatenating two existing values and in another class use add for put a simple parameter in a collection, it's a better options use a name like `insert` or `append` instead.
- **Use solution domain names**
	- Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth.
- **Use Problem Domain Names** 
	- When there is no “programmer-eese” for what you’re doing, use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means.
- **Add meaningful context**
	- There are a few names which are meaningful in and of themselves—most are not. Instead, you need to place names in context for your reader by enclosing them in well-named classes, functions, or namespaces. When all else fails, then prefixing the name may be necessary as a last resort.
- **Don’t add gratuitous context**
	- In an imaginary application called “Gas Station Deluxe,” it is a bad idea to prefix every class with GSD. Example: GSDAccountAddress.
	- Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary.
# Chapter 3. Functions
- Functions are the first line of organization in any program.
- The first rule of functions is that they should be small.
- The blocks within if statements, else statements, while statements, and so on should be one line long.
- Functions should not be large enough to hold nested structures.
- The indent level of a function should not be greater than one or two to increse readability.
- Functions should do one thing. They should do it well. They should do it only.
- The reason we write functions is to decompose a larger concept into a set of steps at the next level of abstraction.
- Another way to know that a function is doing more than “one thing” is if you can extract another function from it with a name that is not merely a restatement of its implementation.
- Functions that do one thing cannot be reasonably divided into sections.
- Mixing levels of abstraction within a function is always confusing.
- Stepdown rule: We want every function to be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions.
- Making the code read like a top-down set of TO paragraphs is an effective technique for keeping the abstraction level consistent.
- It’s hard to make a small switch statement.
- Even a switch statement with only two cases is larger than I’d like a single block or function to be.
- It’s also hard to make a switch statement that does one thing. By their nature, switch statements always do N things.
- Unfortunately we can’t always avoid switch statements, but we can make sure that each switch statement is buried in a low-level class and is never repeated.
- We do this, of course, with polymorphism.
- 

> You know you are working on clean code when each routine turns out to
> be pretty much what you expected
- Half the battle to achieving that principle is choosing good names for small functions that do one thing. The smaller and more focused a function is, the easier it is to choose a descriptive name.
- Choosing descriptive names will clarify the design of the module in your mind and help you to improve it. It is not at all uncommon that hunting for a good name results in a favorable restructuring of the code.

