## Readability

Companies and research institutes can have millions of lines of source
code that they have to understand in order to succesfully make changes
to. Therefore it is important that software is as readable as possible
even though its logic might be complex. Therefore you will also be
graded on the readability of your source code even though you probably
will never have to look at it again after you pass this course.

- think carefully about the names you choose

      s = 0             # bad
      sum = 0           # better
      sum_of_grades = 0 # good

- write comments when they are useful 

      width = 25        # assign 25 to width, not useful
      length = math.sqrt( x**2 + y**2 )  # use Pythagoras to compute length, useful

- think about problem decomposition (splitting in different parts)

  Prefer many small functions that each do their own thing over a few
  large functions that do many things. With many functions you can
  give each function a nice name and you can reuse the same function
  elsewhere. The result is a simpler structure that is less complex to
  work with.

      def is_average_grade_above_5(grades):
         sum_of_grades = 0
         for grade in grades:
             sum_of_grades += grade
         average_grade = sum_of_grades / len(grades)
         return average_grade>5

      # bad, does 3 things: compute sum, compute average, test
      #--------------------------------------------------------------
      # good, each function does its own thing and has a nice name
      
      def sum_of_grades(grades): 
         sum_of_grades = 0
         for grade in grades:
             sum_of_grades += grade
         return sum_of_grades

      def average_grade(grades):
         return sum_of_grades(grades) / len(grades)
     
      def is_average_grade_above_5(grades):  # good
         return average_grade(grades) > 5
     
- don't repeat yourself

  Don't copy-past code and change it a bit, instead make a reusable
  function that you can call from different places.

- shorter is generally better

  Don't write functions that already exist. For example Python already
  has a way to compute the sum of numbers so we don't have to write
  sum_of_grades() again, instead search and use already existing
  function sum(). Unless ofcourse the goal of the exercise is to write
  it yourself. Also take some time to think about shortening your code
  after writing it:

      def in_between(x,min,max):  # bad
          result= True
          if x < min:
             result = False
          if x > max:
             result = False
          return result

      def in_between(x,min,max):  # good
          return x >= min and x <= max
