---
layout: page
title:  Testing
---
Another facet of becoming a top ruby and rails developer and developer in general is testing.  From a rails perspective, rails even comes with a built in library for testing.  My usual
approach for learning something up other than looking at random blog entries is to find what I consider to be highly recommended books, and work through them gleaning what
I consider "the good parts" to file away for future and current use.  Other than the old noodle, I will file some way here.

My favorite "work thru" book right now is Everyday Rails Testing wih Rspec   [Everyday Rails Testing with RSpec ] [3] by Aaron Sumner.  I just like his style, that when it
comes to books that is often the deciding factor on whether or not you read pass CHAPTER2.

I have provided links to the other testing books I use also if you are interested.

## Concepts
TDD is the idea and practice of writing your tests BEFORE the code.  After the test has failed, you write the code to make it pass.  It has been seen in practice that this
leads to more modular code with less coupling, and in the long term when refactoring occurs, will improve the overall development time and accuracy.

### What is TDD?
* The classic process
    * create a short test that should run automatically.
    * make sure it fails.
    * write the code to make the code pass.
    * refactor and improve the code
### TDD impact on the design process
* Design impacts with TDD happen in three ways
    * When you decide to create the test, you are making a design decision about what your code does, in terms of functionality.  Where and how to
    write the code are design questions.
    *  When your write the test you are defining the interface between the test and the code, which will also define the API to that code and any other
       parts of your application.
    *  Refactoring - after the test passes, you probably will make changes to improve the code.  This refactoring process is design.

One of the main benefits of this is that you design is improved.  The test code sits between all of the "interfaces" or API's in your code.  When these interfaces are
eventually used in production, the interfaces will have been tested more carefully.

If in the future you change something, and the test breaks, you will suspect the code.  Because you have written the tests first and they have passed.
If you write the tests after the code, then you might more likely suspect the test, or both.

The first approach seems to make more sense.

The tests become the final source of truth for your application vs. the code.

> "I used to think it was a coincidence that tested code and easy-to-change code have similar structures, but I’ve realized the commonality is a
>  direct side effect of building the code in tandem with the tests. In essence, the tests act as a universal client for the entire codebase, guiding all the code to have clean interactions between parts because the tests, acting as a third-party interloper, have to get in between all the parts of the code to work. Metaphorically, compared to code written without tests,
> your code has more surface area and less work happening behind the scenes where it is hard to observe."

--<cite>Noel Rappen/Rails 4 Test Prescriptions </cite> [The RSpec Book ] [1]



### (Buy and support : Book links )
 [Everyday Rails Testing with RSpec ] [3]
 </br>
 [The RSpec Book ] [1]
 </br>
 [Rails 4 Test Prescriptions ] [2]
  </br>

  [1]:  https://pragprog.com/book/achbd/the-rspec-book
  [2]:   https://pragprog.com/book/nrtest2/rails-4-test-prescriptions
  [3]:   https://leanpub.com/everydayrailsrspec



