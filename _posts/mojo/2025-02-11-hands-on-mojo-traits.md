---
layout: post
title: Hands On Mojo Traits 1
date: 2025-02-11
modifiedDate: 2025-02-11
tags: [mojo, mojolang, trait, traits]
category: Mojo Article
---

Understanding [Mojo traits](https://docs.modular.com/mojo/manual/traits) (struct) is critical to being able to read Mojo Standard Library documentation.
We will try to keep our exploration of structs as shallow as possible so we can jump right in to writing compilable code. The goal is to provide enough understanding of Mojo structures to enable reading of documentation.
<!--more-->

This article entry is based on [Hands On Mojo Structures](/mojo%20article/2025/02/10/hands-on-mojo-structures.html) video.

Mojo traits are roughly analogous to Java interfaces.  They are a blueprint that a method or a function can use as a contract.  Unlike Java
interfaces, traits can be defined and will match already existing structures.

For our first code example we will use the already existing [Writable trait](https://docs.modular.com/mojo/stdlib/utils/write/Writable/).
In the below code we add the "write_to" method as defined by the documentaton (link above).  This allows us to reduce the number of print
statments needed.

{% highlight mojo linenos %}
@value
struct Person:
    var name: String
    var eyeColor: String
    var heightInches: Float16

    fn write_to[W: Writer](self, mut writer: W):
        writer.write(self.name, " ", self.eyeColor, " ", self.heightInches)

fn main():
    bob = Person("Bob", "Brown", 70.5)
    bob.name = "Ralph"
    print(bob)
{% endhighlight %}

* Line 7-8 contains the method write_to as defined by the Writable trait.
* Line 13 replaces three print statements with a single print statement.  It will print the text "Ralph Brown 70.5".
