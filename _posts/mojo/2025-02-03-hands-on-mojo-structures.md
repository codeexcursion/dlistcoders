---
layout: post
title: Hands On Mojo Structures 
date: 2025-02-10
modifiedDate: 2025-02-10
tags: [mojo, mojolang, structure, structures, trait, traits]
category: Mojo Article
---

Understanding [Mojo structure](https://docs.modular.com/mojo/manual/structs) (struct) is critical to being able to read Mojo Standard Library documentation.
We will try to keep our exploration of structs as shallow as possible so we can jump right in to writing compilable code. The goal is to provide enough understanding
of Mojo structures to enable reading of documentation.
<!--more-->

If you need help installing Mojo you can watch our [Mojo Lang Install](https://rumble.com/v60lhj2-mojo-lang-install-d-list-coders.html?e9s=src_v1_ucp) video.

Mojo structs are loosely analogous to Java classes.  They do not support inheritance.  [Mojo Structs Class Comparison](https://docs.modular.com/mojo/manual/structs#structs-compared-to-classes).
We are going to focus only on struct basic ability to hold data.  

>All values in Mojo have an associated data type. Most of the types are nominal types, defined by a struct. These types are nominal (or "named") because type equality is determined by the type's name, not its structure.
> [Mojo Manual](https://docs.modular.com/mojo/manual/types)

For day to day use you can think of all data types in Mojo as structures.  Boolean, String and numeric types are all structures.
Boolean and numeric types are aliases of the [DType](https://docs.modular.com/mojo/stdlib/builtin/dtype/DType/) struct.

Before we begin read and writing example code we need to briefly discuss [Mojo Decorators](https://docs.modular.com/mojo/manual/decorators/).
A decorator is code that executes during compilation of the code.  The @value decorator we use below adds all the necessary boiler plate methods
a struct needs for compilation.

{% highlight shell %}
  $ netstat -gn
{% endhighlight %}

* Line 1 contains the @value decorator which modifies the Person struct during compilation.
* Line 2 begins the definition of the Person structure.
* Lines 3-5 defines the three fields of our struct and their data types.
* Line 7 defines our main function that is the entry point for our small program.
* Line 8 implicity creates a variable of type Person and assigns values to each of the fields.
* Line 9 changes the value of name from "Bob" to "Ralph"
* Line 10 will print the text "Ralph"
* Line 11 will print the text "Brown"
* Line 12 will print the text "70.5"
