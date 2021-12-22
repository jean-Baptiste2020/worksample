> # Explanation of "Ruby's" self and its use

## What is self?

You may have heard people say that everything in Ruby is an object. If that's true it means that every piece of code you write "belongs" to some object.

- [ ] self is a special variable that points to the object that "owns" the currently executing code. Ruby uses self everwhere:

    > For instance variables: @myvar
    
    > For method and constant lookup
    
    > When defining methods, classes and modules.

In theory, self is pretty obvious. But in practice, it's easy for tricky situations to pop up. That's why I wrote this post.

## Examples of self

We're going to step through several examples now. If the first ones seem too basic for you, just keep reading. They get more advanced.
Inside of an instance method

- [ ] In the code below, reflect is an instance method. It belongs to the object we created via Ghost.new. So self points to that object.

```
class Ghost
  def reflect
    self
  end
end

g = Ghost.new
g.reflect == g # => true
```

Inside of a class method

- [ ] For this example, reflect is a class method of Ghost. With class methods, the class itself "owns" the method. self points to the class.

```
class Ghost
  def self.reflect
    self
  end
end

Ghost.reflect == Ghost # => true
```

- [ ] It works the same with "class" methods inside of modules. For example:

```
module Ghost
  def self.reflect
    self
  end
end 
Ghost.reflect == Ghost # => true
```

Remember, classes and modules are treated as objects in Ruby. So this behavior isn't that different from the instance method behavior we saw in the first example.
Inside of a class or module definition

One feature of Ruby that makes it such a good fit for frameworks like Rails is that you can execute arbitrary code inside class and module definitions. When you put code inside of a class/module definition, it runs just like any other Ruby code. The only real difference is the value of self.

- [ ] As you can see below, self points to the class or module that's in the process of being defined.

```
class Ghost
  self == Ghost # => true
end 

module Mummy
  self == Mummy # => true
end 
```

Inside mixin methods

Mixed-in methods behave just like "normal" instance or class methods when it comes to self. This makes sense. Otherwise the mixin wouldn't be able to interact with the class you mixed it into.
Instance methods

- [ ] Even though the reflect method was defined in the module, its self is the instance of the class it was mixed into.

```
module Reflection
  def reflect
    self
  end
end 

class Ghost
  include Reflection
end

g = Ghost.new
g.reflect == g # => true
```

Class methods

- [ ] When we extend a class to mix in class methods, self behaves exactly like it does in normal class methods.

```
module Reflection
  def reflect
    self
  end
end 

class Ghost
  extend Reflection
end

Ghost.reflect == Ghost # => true
```

Inside the metaclass

- [ ] Chances are you've seen this popular shortcut for defining lots of class methods at once.

```
class Ghost
  class << self 
    def method1
    end

    def method2
    end
  end
end
```

The class << foo syntax is actually pretty interesting. It lets you access an object's metaclass - which is also called the "singleton class" or "eigenclass." I plan on covering metaclasses more deeply in a future post. But for now, you just need to know that the metaclass is where Ruby stores methods that are unique to a specific object.

- [ ] If you access self from inside the class << foo block, you get the metaclass.

```
class << "test"
  puts self.inspect
end

# => #<Class:#<String:0x007f8de283bd88>
```

Outside of any class

- [ ] If you're running code outside of any class, Ruby still provides self. It points to "main", which is an instance of Object:

```
puts self.inspect # => main
```
