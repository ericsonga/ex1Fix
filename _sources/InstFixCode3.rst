..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. setup for automatic question numbering.

.. 	qnum::
	:start: 1
	:prefix: 4-3-
	
.. |runbutton| image:: Figures/run-button.png
    :height: 20px
    :align: top
    :alt: run button
    
.. |pass| image:: Figures/pass.png
    :height: 20px
    :align: top
    :alt: pass
    
.. |fail| image:: Figures/fail.png
    :height: 20px
    :align: top
    :alt: fail
    
.. |start| image:: Figures/start.png
    :height: 24px
    :align: top
    :alt: start
    
.. |finish| image:: Figures/finishExam.png
    :height: 24px
    :align: top
    :alt: finishExam
    
.. |right| image:: Figures/rightArrow.png
    :height: 24px
    :align: top
    :alt: right arrow for next page

Example 3: Find the Average of a List of Values
--------------------------------------------------
      
Another common thing to do with a list of values is find the average.  To do this create a variable to hold the sum and initialize it to 0.  Then loop through all the indices in the list and add the value at the current index to the sum.  Remember that you can't divide by 0, so if the length of the list is 0 then return 0, otherwise return the sum divided by the number of items in the list (the length of the list). 

Examples
========

For example ``getAverage([50, 60, 70])`` should return 60 and ``getAverage([])`` should return 0.

Run Code
=========

Click the |runbutton| button to run the tests that check that this code is working correctly.  All tests should print |pass| since this is correct code.  Scroll down to try to solve the practice problem below.

.. activecode:: Get_Average
   :nocodelens:

   # define the function
   def getAverage(numList):
   
       # init sum 
       sum = 0  
      
       # loop through indicies
       for index in range(len(numList)):
       
           # get value at index
           value = numList[index]
      
           # add value to sum
           sum = sum + value
    
       # prevent a divide by zero
       if len(numList) == 0:
             return 0 
             
       # return the average
       return sum / len(numList)
           
   =====
      
   # code to test the getAverage function
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testOne(self):
           self.assertEqual(getAverage([50, 60, 70]), 60.0, "Test of getAverage[50, 60, 70])");
           self.assertEqual(getAverage([]), 0, "Test of getAverage([])");
           self.assertEqual(getAverage([75, 60, 80, 95]), 77.5, "Test of getAverage([75, 60, 80, 95])");
           self.assertEqual(getAverage([10,20,30,40,90]), 38.0, "Test of getAverage([10, 20, 30, 40, 90])");
           self.assertEqual(getAverage([4]), 4.0, "Test of getAverage([4])");

   myTests().main()
   
Practice 3: Find the Average Dropping the Lowest Value
-----------------------------------------------------------

The following code should find the average of a list of numbers except for the lowest value, but it contains errors.  To find the average of all but the lowest value first check if the length of the list is less than or equal to one and if so return 0 to prevent a divide by zero error.  Otherwise create a variable to hold the sum and initialize it to 0. Create another variable to hold the lowest value found so far and initialize it to the first value in the list. Next loop through all the indices in the list and add the value at the current index to the sum.  Also check if the current value is less than the saved lowest value found so far and if it is set the lowest value to the current value.  Return the sum minus the lowest value divided by the number of values in the list minus one.

.. note ::
   
    Remember that you should set the initial lowest to the first value that you are processing, not zero.  
    
Examples
========

For example ``getAverageDropLowest([50, 10, 50])`` should return 50 since dropping the lowest value (10) results in a sum of 100 and dividing 100 by 2 yields 50.  The call ``getAverageDropLowest([10])`` should return 0 since there is only one value in the list.   

Fix Code Here
==============

Fix the errors so that all the tests print |pass| when you click the |runbutton| button.  The error messages and test results are displayed below the code. 

Click on the |start| button below when you are ready to try to order this code.  You will have up to 10 minutes to try to solve it.  Click the |runbutton| button to check your solution.  Click on the |finish| button when you have solved this problem or wish to move on without solving it.

.. timed:: get_average_drop_lowest_fix_timed
   :timelimit: 10
   :noresult:
   :nofeedback:
   :fullwidth:
   
   .. activecode:: Get_Average_Drop_Lowest_Fix

      # Fix the getAverageDropLowest function that calculates
      # the average of a list of numbers, but also drops the 
      # lowest value in the list from the average calculation
      def getAverageDropLowest(numList):
      
          # if no values, return 0
          if len(numList) <= 1:
              return 0
   
          # init sum and lowest
          sum = 0
          lowest = 0 

          # loop through the indices
          for index in range(numList):

              # add value to sum
              value = numList[index]
              sum = sum + value
    
              # if new lowest
              if lowest < value: 

                  # reset lowest
                  value = lowest 

          # return average (drop lowest)
          return (sum - lowest) / (len(numList) - 1)
              
      ====
             
      # code to test the getAverageDropLowest function
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(getAverageDropLowest([50, 10, 50]),50, "Test of getAverageDropLowest([50, 10, 50])");
              self.assertEqual(getAverageDropLowest([10]), 0, "Test of getAverageDropLowest([10])");
              self.assertEqual(getAverageDropLowest([]), 0, "Test of getAverageDropLowest([])");
              self.assertEqual(getAverageDropLowest([80, 90, 70]), 85, "Test of getAverageDropLowest([80, 90, 70])");
              self.assertEqual(getAverageDropLowest([20, 52, 80, 90]), 74, "Test of getAverageDropLowest([20, 52, 80, 90])");

      myTests().main()
           
When you are finished with this problem, or are ready to move on, click the |finish| button and then go to the next page by clicking the right arrow |right| near the bottom right of this page.    
