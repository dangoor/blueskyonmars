---
title: Python dictionaries are not the same as instances
author: Kevin Dangoor
type: post
date: 2007-06-13T00:29:50+00:00
url: /2007/06/12/python-dictionaries-are-not-the-same-as-instances/
categories:
  - Python

---
Yes, yes, I know that Python dictionaries _are_ instances of the dict class. Something that I have noticed through the years and in a variety of bits of code is that many people will use a dictionary where they should really be using an instance. Many of the people that do this likely came from PHP4, Perl or even C where classes are either non-existent or are a little uncomfortable to use.

Dictionaries are great if you need to pass around a few values in one limited place in a larger system. Custom class instances are much better, though, if you have some data that is going to be used in many places in your code.

This is not a rant about â€œyou should be doing OO designâ€. As weâ€™ll see in a moment, Iâ€™m not even writing about OO design. Iâ€™m advocating using custom class instances instead of plain dictionaries because Python is a class-based object oriented language. That means that the language specifically provides benefits to people using classes.

First, I should make it clear what exactly Iâ€™m talking about. Iâ€™ll use the simple example of a person. A person could be represented with a dictionary:

    kev = dict(first_name="Kevin", last_name="Dangoor", address="1600 Pennsylvania Avenue")
    

A person can also be represented by a class:

    class Person(object):
        def __init__(self, first_name, last_name, address):
            self.first_name = first_name
            self.last_name = last_name
            self.address = address
    
    kev = Person("Kevin", "Dangoor", "1600 Pennsylvania Avenue")
    

Some people would probably jump out and say that the second example is a lot more verbose and doesnâ€™t let you store whatever data values you want as you can in the first example. The thing is that you only define the Person class once. The instantiation of a Person is just as easy as the instantiation of a dict. And, if you want to make the class smaller and support an unlimited number of attributes, you could do this if you really want:

    class Person(object):
        def __init__(self, **kw):
            self.__dict__.update(kw)
    

When you use an instance of Person rather than the dictionary, you get several benefits:

## 1. Lazily computed values. {#1_lazily_computed_values}

If you want to add `full_name` to Person, you just do this:

    class Person(object):
        def __init__(self, **kw):
            self.__dict__.update(kw)
    
        @property
        def full_name(self):
            return self.first_name + " " + self.last_name
    
    kev = Person(first_name="Kevin", last_name="Dangoor")
    kev.full_name
    

Just like that, every Person instance now has a `full_name` property. To do the same with a dictionary would require adding `full_name` to the dict manually.

## 2. Backwards compatibility. {#2_backwards_compatibility}

Python properties allow you to override attribute-style access with a method call. Letâ€™s say that our Person class changed to maintain a `full_name` instead of separate first and last names. We could still make `first_name` work, though:

    class Person(object):
        def __init__(self, full_name):
            self.full_name = full_name
    
        @property
        def first_name(self):
            # warning... no error checking!
            return self.full_name.split(" ")[0]
    
    kev = Person(full_name="Kevin Dangoor")
    kev.first_name
    

If you are creating a given data structure in many different spots in your program, this can be a problem if youâ€™re using a dictionary and need to add a new key/value pair. With a class, you can just do this:

    class Person(object):
        age = None
    

And now, everywhere a Person is used you know youâ€™re not going to get an AttributeError for person.age. If you use dictionaries everywhere, youâ€™ll get a KeyError if you try to access â€˜ageâ€™ on a dictionary created by older code.

## 3. Deprecations. {#3_deprecations}

Even better than just providing backwards compatibility is to issue a deprecation warning so that you can clean up uses of the old style.

    import warnings
    
    class Person(object):
        def __init__(self, full_name):
            self.full_name = full_name
    
        @property
        def first_name(self):
            warnings.warn("Use full_name or else!", DeprecationWarning)
            return self.full_name.split(" ")[0]
    
    kev = Person(full_name="Kevin Dangoor")
    kev.first_name
    

## 4. You can add behavior. {#4_you_can_add_behavior}

Unlike my other points here, this one is an OO design thingâ€¦ Thereâ€™s not much difference between

    hire(person)
    

and

    person.hire()
    

For many types of behaviors, though, I think itâ€™s handy to have the behavior on the object youâ€™re trying to act on. This potentially saves you from extra imports. Consider this case:

    "foo bar".split()
    
    import string
    string.split("foo bar")
    

These two are equivalent, but you donâ€™t need to import string or have the â€˜stringâ€™ name muddying up your module namespace.

## 5. Less typing. {#5_less_typing}

This is not a good reason for a choosing a programming technique, but it is a fact:

    person["first_name"]
    

is more typing than

    person.first_name
    

## 6. Higher level features. {#6_higher_level_features}

Custom class instances have the advantages I note above, just using them as basic data containers. Classes also offer inheritance and metaclasses which allow you to share attributes and behavior in a way that a plain dictionary canâ€™t. Classes also give you operator overloading, customizable attribute access and the ability to customize the str and repr forms of the objects.

* * *Thereâ€™s really very little downside to using custom classes and quite a few benefits, particularly if youâ€™ve got a system thatâ€™s going to grow. If you tend to reach for dictionaries whenever you need to store some data, you might consider whipping up a quick class instead.</p>