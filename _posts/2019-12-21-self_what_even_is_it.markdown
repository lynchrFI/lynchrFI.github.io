---
layout: post
title:      "Self, what even is it?"
date:       2019-12-22 01:08:05 +0000
permalink:  self_what_even_is_it
---


**What is self?**

What is self? Self in Ruby is the object currently in context  – the object that is receiving the current message. To explain: a method call in Ruby is actually the sending of a message to a receiver.  

```
class Name
   puts "Self is #{self}"
end
```

```
Self is: Name
```

The result is that, directly inside the context of a class definition, self is equivalent to the class in which it was defined, Name, in this case. In fact, in this context, the keyword self can be thought of as a substitute for the actual class name. Instead of using self here, we could use Name, and Ruby would treat it the exact same.


**What is self inside of an instance method?**

In the code below, make is an instance method. It belongs to the object we created via Car.new. So self points to that object.

```
class Car
  def make
    self
  end
end

c = Car.new
c.make == c # => true
```

**What is self inside of a class method?**

For this example, reflect is a class method of Car. With class methods, the class itself "owns" the method. self points to the class.

```
class Car
  def self.make
    self
  end
end

Car.make == Car # => true
```

Classes are treated as objects in Ruby. So this behavior isn't that different from the instance method behavior we saw in the first example.

