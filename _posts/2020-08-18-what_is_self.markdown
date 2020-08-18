---
layout: post
title:      "What is self?"
date:       2020-08-18 19:57:10 +0000
permalink:  what_is_self
---


Self can be a bit abstract to understand when first writting code. In this blog post we will take a look at what is `self` within a class, an instance method, and initialize. One major rule to remember is that `self` will always be dependent on the object or circumstance we are calling it on.

**Self within a Class

Within a class, `self` will generally refer to the parent class itself. If we write:

class Author
     puts "Self is: #{self}"
end

We will get:

"Self is: Author"

Contextually, we could see it as. we are writting a message on behalf of, and as if we were our object Author in this case. Self would mean, or be a replacement for whatever class we are writting. In this case, `self` is equivalent to the parent class, or 'Author'.

**Self within an Instance Method

Self within an instance method is a bit tricky. We cannot call self on an instance method without first creating an instance of a class. Picture it as the class being a cookie mold, an object a cookie, and an instance method some sort of topping on a cookie. We cannot add a topping to a cookie without first having the cookie!

If we add an instance method to our class and create an new instance of that class:


    def name
        puts "Self inside class instance method is: #{self}"
    end

We will get something like this:

Self inside class instance method is: #<Author:0x00000004td45k4>"


**Self within initialization


In Ruby, `initialize` is what we call a constructor method. For the purpose of this blog, we will not get into how initialize works. Yet, it is important to note that by the time your code executes the initialize line, a new instance of that object has already been created. This means that if we have something like this:

class Author

  def initialize
        puts self.class
  end
	
end

Author.new 

Self will return the instance of the Author class, or in this case: `Author`.



