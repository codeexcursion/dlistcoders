---
layout: post
title: Hands On Generic Parameterization of Functions
date: 2025-02-12
modifiedDate: 2025-02-12
tags: [mojo, mojolang, parameter, function]
category: Mojo Article
---

[Mojo Parameterization](https://docs.modular.com/mojo/manual/parameters/) is part of compile time code generation/modification.  
We will try to keep our exploration of Parameters as shallow as possible so we can jump right in to writing compilable code. The goal is to provide enough understanding of Mojo Parameters to enable reading of documentation.
<!--more-->

You will need a basic understanding of Traits which can be acquired reading [Hands On Mojo Traits](/mojo%20article/2025/02/11/hands-on-mojo-traits.html).

In other programming languages parameter and argument terminology is often used interchangeably.  In Mojo the two are distincly different.
Function arguments are used while the compiled code is running.  Parameters are used while the code is being compiled.

For our code example we will create a function that focus on Parameters and [Generics](https://docs.modular.com/mojo/manual/parameters/#parameters-and-generics).  Generics allow us to write generic code that will interact with multiple data types.  As long as the data type
implements the correct method.  Below we have a contrived example that shows how generics work.  The commented out code will not compile.
You can uncomment it while you are playing with the code to better understand how traits, parameters and generics work.

{% highlight mojo linenos %}
trait WarmBlooded:
    fn is_warm_blooded(self) -> Bool:
        ...

trait ColdBlooded:
    fn is_cold_blooded(self) -> Bool:
        ...

@value
struct Cat:
    var name: String

    fn is_warm_blooded(self) -> Bool:
        return True

@value
struct Turtle:
    var name: String

    fn is_cold_blooded(self) -> Bool:
        return True

fn print_warm_blooded[T: WarmBlooded](warm_blood: T):
    print(warm_blood.is_warm_blooded())

fn print_cold_blooded[T: ColdBlooded](cold_blood: T):
    print(cold_blood.is_cold_blooded())

fn main():
    betsy = Cat("Betsy")
    samuel = Turtle("Samuel")
    print_warm_blooded(betsy)
    #print_cold_blooded(betsy)
    #print_warm_blooded(samuel)
    print_cold_blooded(samuel)
{% endhighlight %}

* Lines 1-3 we define the warm blooded trait.
* Lines 5-7 we define the cold blooded trait.
* Lines 9-14 we define the Cat struct which implements the is_warm_blooded method.
* Lines 16-21 we define the Turtle struct which implements the is_cold_blooded method.
* Lines 23-24 we define a function that only accepts types that implement the warm blooded trait.
* Lines 26-27 we define a function that only accepts types that implement the cold blooded trait.
* Line 30 we instantiate a Cat struct.
* Line 31 we instantiate a Turtle struct.
* Line 32 we run the print_warm_blooded function.
* Line 33 is commented out because it will not compile.  Betsy variable of type Cat does not implement cold blooded trait.
* Line 34 is commented out because it will not compile.  Samuel variable of type Turtle does not implement warm blooded trait.
* Line 35 we run the print_cold_blooded function.
