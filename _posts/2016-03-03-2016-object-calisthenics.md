---
layout: post
title: Object Calisthenics 
tags: [PHP, programming]
---

Last week Wednesday evening (24-02) i went to a meetup at the developers.nl homebase. That night some interesting topics where covered about the SOLID programming principles. Afterwards i spoke a guy (forgot his name -_-) and he told me about **Object Calisthenics**.

I had never heard of it and after some reading i found it important enough to write a post about it ^^ .

So basically object calisthenics describes a set of guidelines which can be applied during programming.  
Applying these rules should result in *better* software. Oh boy... did that sound good :) .

After seeing an [interesting talk](https://www.youtube.com/watch?v=H2AvoAzbGOE) of [Rafael Dohms](https://twitter.com/rdohms) (slides found [here](http://www.slideshare.net/rdohms/your-code-sucks-lets-fix-it-15471808)) about this topic I decided to make a short summary here.

# OC #1  
*Only one indention*  

A method should only have one level of indentation.
If your method has more than one level of indentation it is probably doing *more than one* thing.

# OC #2
*Do not use the "else" keyword*  

The else keyword clutters the true (happy) flow of your code.  
Martin Fowler wrote about this too in his book Refactoring where he calls this refactoring [Replace Nested Conditional With Guard Clauses](http://refactoring.com/catalog/replaceNestedConditionalWithGuardClauses.html).

# OC #3
*Wrap primitive types and strings*  

While this rule is more applicable for Java-ish kind of languages it also applies to PHP when there is more behaviour in the game. A key benefit in PHP is that it gives the ability to type-hint on the wrapper object (which is impossible with scalars < PHP 7.x).

# OC #4
*One -> per line*  

This rule suggest that if there is more then one -> (dot in Java) per line, there might be a encapsulation issue in your model.  

It has a strong relationship with the [Law of Demeter](http://c2.com/cgi/wiki/LawOfDemeter?LawOfDemeter) (LoD):
> Only talk to your immediate friends

LoD rules:

- Your method can call other methods in its class directly.
- Your method can call methods on its own fields directly (but not on the fields fields).
- When your method takes parameters, your method can call methods on those parameters directly.
- When your method creates local objects, that method can call methods on the local objects.

# OC #5
*Do not abbreviate*  

Just don't do it period.  
The cause of abbreviation might have to do with the fact that a function or method is doing too much.

# OC #6  
*Keep your classes small*  

Rule of thumb:

- 200 lines per class (including comments/docblocks)
- 15-20 lines per method (if more the method is probably doing too much)
- 10 methods per class

# OC #7
*Use first class collections*  

I think this is more applicable to Java-ish languages but it can have its benefits for PHP as well.
If you have a collection of any type, put them in a separate class/type. This way you can put all the behaviour which belongs to the collection in its own type without cluttering it with other irrelevant logic.

# OC #8
*Do not use accessors (getters/setters)*

Dropped for PHP.

