---
title : 'Lambda Expressions'
date : 2023-12-18T13:36:54-06:00
draft : false
author: Hu
tags : ["UW-Madiosn", "CS400", "Lambda Expressions"]
categories: ["Courses"]
---

### Lambda Expressions  

One issue with anonymous classes is that if the implementation of your anonymous class is very simple, such as an interface that contains only one method, then the syntax of anonymous classes may seem unwieldy and unclear. In these cases, you're usually trying to pass functionality as an argument to another method, such as what action should be taken when someone clicks a button. Lambda expressions enable you to do this, to treat functionality as method argument, or code as data.   
Anonymous Classes, shows you how to implement a base class without giving it a name. Although this is often more concise than a named class, for classes with only one method, even an anonymous class seems a bit excessive and cumbersome. Lambda expressions let you express instances of single-method classes more compactly.  

**Syntax**  
Syntax: Type variable name = (pass in the parameters here if there are any) -> func body; // this is only one line  
For multiple line: Type variable name = (pass in the parameters here if there are any) -> {func body.................................;  func body line 2; } ;  
Parameter scope of the lambda expression   

A lambda expression consists of the following:

A comma-separated list of formal parameters enclosed in parentheses. The CheckPerson.test method contains one parameter, p, which represents an instance of the Person class.

Note: You can omit the data type of the parameters in a lambda expression. In addition, you can omit the parentheses if there is only one parameter. For example, the following lambda expression is also valid:

p -> p.getGender() == Person.Sex.MALE 
    && p.getAge() >= 18
    && p.getAge() <= 25
The arrow token, ->

A body, which consists of a single expression or a statement block. This example uses the following expression:

p.getGender() == Person.Sex.MALE 
    && p.getAge() >= 18
    && p.getAge() <= 25
If you specify a single expression, then the Java runtime evaluates the expression and then returns its value. Alternatively, you can use a return statement:

p -> {
    return p.getGender() == Person.Sex.MALE
        && p.getAge() >= 18
        && p.getAge() <= 25;
}
A return statement is not an expression; in a lambda expression, you must enclose statements in braces ({}). However, you do not have to enclose a void method invocation in braces. For example, the following is a valid lambda expression:

email -> System.out.println(email)
Note that a lambda expression looks a lot like a method declaration; you can consider lambda expressions as anonymous methods—methods without a name.