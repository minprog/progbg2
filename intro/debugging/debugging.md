## Debugging

A bug is an error in your code that causes a wrong output with some
specific input. When programs get larger or more complex you often
spend more time finding and fixing bugs than you spend writing new
code even if the bug is caused by a tiny little typo. This is normal
and can be frustrating, but don't let a bug get you all worked
up. Instead write your code carefully (think it through, don't put
thinking off until testing) and try to find bugs early by testing
early and often. After adding every few lines of code make sure your
program still does what you think it does. Because if you don't test
often and a bug appears you will not know where to look for it and you
will likely have to spend more time debugging. 

- print: You can test by temporarily adding print statements to your
code, run it, and analyse the output:

      def sum_of_grades(grades): 
           sum_of_grades = 0
           for grade in grades:
               print("sum_of_grades:", sum_of_grades)  # temporary print
               sum_of_grades += grade
           return sum_of_grades

- debugger: You can also use a debugger to step through your code, to see
how it executes and see how values are changing, for example with 'pgd':

  <https://www.youtube.com/watch?v=ChuU3NlYRLQ>

- test data: Make your own test to more easily test your code. For
  example if you want to count how many times each words occurs in a
  large text then testing with a large text will result in a lot of
  loop iterations and a lot of data that is hard to check. Therefore
  it is a good idea to first test with a your own small text with just
  a few words. That way you can easily check each iteration and know
  what the right output should be. You can incrementally make your
  test set harder as you write more code. Think about what the most
  difficult input to your program would be (possible edge cases?) and
  incrementally add those in your test set.

Debugging is an important skill to develop. Find out what strategy
works for you.
