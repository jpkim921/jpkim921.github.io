---
layout: post
title:      "Arrays in Ruby"
date:       2018-11-15 03:45:21 +0000
permalink:  arrays_in_ruby
---



One of the most important (IMO) part of programming. After finishing a couple of projects, I realized that the use of Arrays in programming is all over the place. Even if it's not something that you coded yourself, Ruby might return something in an array as a default or a library or gem that you're using might return an array. Either way at some point you will most likely end up with an array and you're going to have to know how to use the returned array.

Arrays can be though of as a list, but organized by the index of it's elements. It can be used to "hold" all kinds of objects. You'll read what an element and an index is just a little further down.


## Creating an Array

There are a few ways to create arrays but the simplest way is to use the literal notation using square brackets, `[]`.

```Ruby
[] # empty array holding nothing
arr = [] # save it to a variable
```

An array can contain nothing, or anything, separated by a comma: integers, strings, methods, other arrays, etc.

```Ruby
[] # empyt array
[1,2,3,4,5] # array of integers
["cat", "hat","rat", "bat"] # array of strings


def puts_hello # method
  puts "hello"
end

var = "It can hold a variable."

arr = [1,"a",2,"b", var, puts_hello]
```

## Parts of an Array

All items within an array is called an element and every element has a corresponding index. The index starts from 0 and counts up by 1 for every additional element going left to right.

```Ruby
arr = ["cat", "hat","rat", "bat"] # arr has 4 total elements
index of "cat" is 0.
index of "hat" is 1.
index of "rat" is 2.
index of "bat" is 3.
```

Just have to note and keep in mind, that because it starts from 0, the last element's index will be `your_array.length - 1`.

```Ruby
arr = ["cat", "hat","rat", "bat"] # arr has 4 total elements

index_of_last_element = arr.length - 1 # => 3
```

You can also go backwards through an array from the end to the beginning (right to left). However, in this case the index starts at -1 and counts down to `your_array.length * -1.`

```Ruby
arr = ["cat", "hat","rat", "bat"] # arr has 4 total elements
index of "bat" is -1.
index of "rat" is -2.
index of "hat" is -3.
index of "cat" is -4.
```
```Ruby
arr = ["cat", "hat","rat", "bat"] # arr has 4 total elements

index_of_first_element = arr.length * -1 # => -4
```

## Accessing Elements

To access an array, just put an element's index inside of a square bracket.

```Ruby
arr = ["cat", "hat","rat", "bat"]

puts arr[0] # => cat
puts arr[1] # => hat
puts arr[2] # => rat
puts arr[3] # => bat
```

If you try to access an element that doesn't exist, you will get the default answer of `nil`.

```Ruby
arr = ["cat", "hat","rat", "bat"]

arr[0] # => cat
arr[-4] # => cat

arr[9] # => nil
arr[5463] # => nil
```

Hopefully it didn't seem like a lot but recognizing arrays and knowing how to access it's elements are going to help a lot.


In the next part, we will go over manipulating and using arrays.

