# Interfaces vs Abstract Classes

There are a few key differences that separate an abstract class and an interface, and these key differences can have an effect on which you would want to use in different situations. I outline a few of these differences below:

#### Differences with Inheritance Rules

One main difference between interfaces and classes in general is that any given class *can implement **multiple** interfaces*, however can *only extend **one** class / abstract class*.

This is an important distinction. Given the specific project you are working on and the way you want to organize and design your interfaces and classes, this might be a deciding factor for whether you must use an interface, or if you can also use an abstract class. 

#### Differences in Access Modifiers

Access modifiers are also a key differentiator between interfaces. If you recall, you **cannot** use access modifiers (like `public`, `private`, etc.) on methods in an interface! Doing so would be invalid and cause a syntax error in IntelliJ.

However, since abstract classes are *classes*, you **can** use access modifiers in abstract classes! There might be cases where you want to force a subclass to "declare" a method with a certain access modifier, and in this case, you would need to use an abstract method over an interface.

#### Differences in Class "Fields"

Another major difference here is with *fields*. If you recall, you cannot create fields in an interface. In interfaces, you can *only* declare *constants* -- no fields! Therefore, it is up to the implementing class to define which fields are needed based on the methods defined in the interface. 

A great example of this is in `a01-sushi` with the `IngredientPortion` interface. As you probably noticed, an `IngredientPortion` needs to keep track of two things -- the *ingredient*, and the  *amount* of that ingredient. These two things make up a portion. However, if you take a look at the `IngredientPortion` interface, you notice that these fields are not written in for you. When creating `IngredientPortionImpl`, you had to do this yourself.

Fields however *can* exist as part of abstract classes. So, if it was necessary in your code that you wanted to specify which fields should be used to a subclass, it might be beneficial to use an abstract class rather than an interface.

#### Instantiation

Another key thing to remember is that, like interfaces, abstract classes **cannot** be instantiated directly. Abstract methods are, by design, incomplete! They require some other subclass to extend it and finish declaring the necessary abstract methods, thus adding all of the necessary functionality. This is also true with interfaces, as interfaces also cannot be instantiated.

The difference here, however, is that abstract classes ***can still have a constructor!*** Abstract classes cannot be instantiated directly, but a lot of the functionality for constructing the object can be written out. Then, the subclass can easily use `super()` to access this functionality in the abstract superclass.

If you recall, interfaces do not have constructors. It is up to the subclasses to define these from scratch.

#### Putting it All Together

I want to provide a short example showcasing some of these concepts. Say we want to implement two classes, `Cat` and `Dog`, that share similar functionality. Below are two valid ways to do this -- one with an *interface*, and one with an *abstract class*. Seeing how the code is structured here might help you see the benefits and drawbacks of each implementation.


**With an `Animal` Interface:**

Link to the **interface** example on GitHub [here](https://github.com/comp301unc/piazza-examples/blob/main/interface-vs-abstract-class/interface-example.md)!

**With an `Animal` Abstract Class:**

Link to the **abstract class** example on GitHub [here](https://github.com/comp301unc/piazza-examples/blob/main/interface-vs-abstract-class/abstract-class-example.md)!

If you actually try to compare both implementations in IntelliJ, you will see the outputs are **indentical!** However, one (interface method) allows for more *flexibility* in the subclasses `Dog` and `Cat`, while the other (abstract class method) moves a lot of the functionality to `Animal` and makes `Dog` and `Cat` significantly shorter.

#### TL;DR - Differences Summary

- A subclass can implement multiple interfaces, while a subclass can only extend a single abstract class.
- Abstract classes allow for the use of access modifiers (`public`, `private`, etc.), while interfaces do not.
- Abstract classes can include fields and constructors, while interfaces cannot.
-  Both interfaces and abstract classes cannot be instantiated directly.

#### Extra Reading

- Check out some official Java documentation from Oracle of abstract methods and classes [here](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html).
- Read more about abstract classes on W3Schools [here](https://www.w3schools.com/java/java_abstract.asp)

I hope that this helps anyone who wants to know more about the differences between interfaces and abstract classes! This content is covered in the **abstraction** lecture and in the slides, however I think it is good to have a bit of a supplement so that you have a very solid understanding of the differences between abstract classes and interfaces. This distinction can be difficult to understand at first without many examples, so I also recommend experimenting in IntelliJ -- create some sample interfaces and classes, just as I did with `Animal`, `Dog`, and `Cat`, and play around with them! See what works, what gives an error, and how these different components interact. Experiencing these things hands-on will make them a lot more easier to understand than just memorizing definitions.
