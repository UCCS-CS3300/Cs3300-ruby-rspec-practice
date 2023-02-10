# **Ruby Intro**

This homework gives some basic practice in Ruby as well as getting you accustomed to making testing a regular part of your workflow.

Get started by reading Chapter 3 and trying out some of the tutorials listed at the end of this assignment. 

Step one: “learn” Ruby- easy right? No.  Jump in as soon as possible and start trying out Ruby.


## **Learning Goals**

After completing this assignment, you will know how to:

*   Write code that uses basic constructs in the Ruby language, including methods and arguments, conditionals, string and array manipulation, regular expressions, and basic object-oriented programming mechanisms
*   Understand the Ruby project conventions for where code files and test files are located in a project's directory hierarchy
*   Run individual tests or suites of tests using the RSpec unit testing tool
*   Understand the basic syntax of RSpec unit tests and write your own



## **Commit Work Frequently**

Run your current docker container and fork this code. Then clone this code to your docker environment. 

## SECTION 1: RUBY BASICS

------------------------------------------------------------------------------------------------------------


## **Overview**

The repo for this assignment follows a fairly standard Ruby convention for codebases: **the code files are stored in lib/ and the test files are stored in spec/**. (We use the RSpec unit-testing framework)


You SHOULD do your own testing. Test each of the 3 parts separately, or together. The files spec/part[123]_spec.rb contain RSpec tests for each of the three parts. For example, to test your answers to Part 1, say rspec ./spec/part1_spec.rb. rspec with no arguments runs the tests in all the files spec/*_spec.rb. You wil notice you can run the command with -e to run a certain test. For example in part 2: rspec -e '#starts_with_consonant?' spec/part2_spec.rb


*   The line numbers in the RSpec error report will give you guidance as to which tests failed. (You can check the[ RSpec documentation](http://rspec.info) to see how the .rspec file can be used to customize the output format.)

To ensure you have the rspec gem installed, you need bundler and can then run bundle install like so:


```
$ cd Cs3300-ruby-rspec-practice

$ bundle install

$ rspec spec/ for all parts 1 through 3 or rspec spec/part#_spec.rb to run 1 at a time for 1 through 3
```

When the above completes successfully you'll have RSpec installed and can run rspec from the command line to test your code. 

LOOK AT THE TESTS IN THE SPEC FOLDER!! Right now, all tests will fail. Your goal is to make all tests pass once you complete the code. 


# **1. Arrays, Hashes, and Enumerables**

Check the[ Ruby 3.0.x documentation](http://ruby-doc.org) on Array, Hash and Enumerable as they could help tremendously with these exercises!  



1. Define a method sum(array) that takes an array of integers as an argument and returns the sum of its elements. For an empty array it should return zero. Run associated tests via: $ rspec ./spec/part1_spec.rb:5
2. Define a method max_2_sum(array) which takes an array of integers as an argument and returns the sum of its two largest elements. For an empty array it should return zero. For an array with just one element, it should return that element. Run associated tests via: $ rspec ./spec/part1_spec.rb:24
3. Define a method sum_to_n?(array, n) that takes an array of integers and an additional integer, n, as arguments and returns true if any two elements in the array of integers sum to n. sum_to_n?([], n) should return false for any value of n, by definition. Run associated tests via: $ rspec ./spec/part1_spec.rb:43

You can check your progress on the **all** the above by running $ rspec ./spec/part1_spec.rb.


# **2. Strings and Regular Expressions**

Check the documentation on String and Regexp as they could help a lot with these exercises!



1. Define a method hello(name) that takes a string representing a name and returns the string "Hello, " concatenated with the name. Run associated tests via: $ rspec -e '#hello' spec/part2_spec.rb
2. Define a method starts_with_consonant?(s) that takes a string and returns true if it starts with a consonant and false otherwise. (For our purposes, a consonant is any letter other than A, E, I, O, U.) NOTE: be sure it works for both upper and lower case and for nonletters! Run associated tests via: $ rspec -e '#starts_with_consonant?' spec/part2_spec.rb
3. Define a method binary_multiple_of_4?(s) that takes a string and returns true if the string represents a binary number that is a multiple of 4. NOTE: be sure it returns false if the string is not a valid binary number! Run associated tests via: $ rspec -e '#binary_multiple_of_4?' spec/part2_spec.rb

You can check your progress on the all the above by running $ rspec ./spec/part2_spec.rb.


# **3. Object Oriented Basics**

Define a class BookInStock which represents a book with an ISBN number, isbn, and price of the book as a floating-point number, price, as attributes. Run associated tests via: $ rspec -e 'getters and setters' spec/part3_spec.rb

The constructor should accept the ISBN number (a string, since in real life ISBN numbers can begin with zero and can include hyphens) as the first argument and price as second argument, and should raise ArgumentError (one of Ruby's built-in exception types) if the ISBN number is the empty string or if the price is less than or equal to zero. Include the proper getters and setters for these attributes. Run associated tests via: $ rspec -e 'constructor' spec/part3_spec.rb

Include a method price_as_string that returns the price of the book formatted with a leading dollar sign and two decimal places, that is, a price of 20 should format as "$20.00" and a price of 33.8 should format as "$33.80". Run associated tests via: $ rspec -e '#price_as_string' spec/part3_spec.rb

You can check your progress on the all the above by running rspec ./spec/part3_spec.rb.


