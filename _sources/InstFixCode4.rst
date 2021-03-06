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
	:prefix: 4-4-

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
    
Example 4: Get Minimum Value in Range
---------------------------------------
      
To find the minimum value in a list of numbers between a start and end index (inclusive), first initialize the current minimum to the value at the start index.  Then loop from the start index to the end index (inclusive) and if the value at that index is less than the current minimum reset the current minimum to that value.  Return the minimum value found.

Examples
========

For example ``getMinInRange([-3, 5, 8, 4], 1, 3)`` should return 4 and ``getMinInRange([20, 10, 5], 0, 2)`` should return 5.  

Run Code
=========

Click the |runbutton| button to run the tests that check that this code is working correctly.  All tests should print |pass| since this is correct code.  Scroll down to try to solve the practice problem below.

.. activecode:: Get_Min_In_Range
   :nocodelens:

   # define the function
   def getMinInRange(numList, start, end):
   
       # init the minimum
       min = numList[start]
       
       # loop from start to end (inclusive)
       for index in range(start,end+1):
      
           # get the current value
           value = numList[index]
       
           # if new min
           if value < min:
           
               # reset min
               min = value
               
       # return the minimum 
       return min
       
   ====
      
   # code to test the isSorted function
   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

       def testOne(self):
           self.assertEqual(getMinInRange([-3, 5, 8, 4], 1, 3), 4, "Test of getMinInRange([-3, 5, 8, 4], 1, 3)")
           self.assertEqual(getMinInRange([20, 10, 5], 0, 2), 5, "Test of getMinInRange([20, 10, 5], 0, 2)")
           self.assertEqual(getMinInRange([20, 10, 5], 0, 1), 10, "Test of getMinInRange([20, 10, 5], 0, 1)")
           self.assertEqual(getMinInRange([20, 10, 5], 1, 2), 5, "Test of getMinInRange([20, 10, 5], 1, 2)")
           self.assertEqual(getMinInRange([-20, -10, -5], 1, 2), -10, "Test of getMinInRange([-20, -10, -5], 1, 2)")

   myTests().main()
   
   
Practice 4: Get Max In Range
------------------------------

The following code should return the maximum of all the values between a specified start and end index (inclusive), but the code contains errors.  To find the maximum value in a range of indices, first create a variable to keep track of the maximum and initialize it to the value at the start index.  Then loop from the start index to the end index (inclusive).  Get the value at the current index.  If the value at the current index is greater than the maximum then set the maximum to the current value.  After the loop return the maximum value found.

.. note ::
   
    Remember that you should set the maximum value found so far to the first value in the range, not to the first element in the list.  

Examples
=========

For example ``getMaxInRange([-3, 5, 2, 4], 2, 3)`` should return 4 and ``getMaxInRange([-20, -10, -5], 1, 2)`` should return -5.  


Fix Code Here
==============

Fix the errors so that all the tests print |pass| when you click the |runbutton| button.  The error messages and test results are displayed below the code. 

Click on the |start| button below when you are ready to try to fix this code.  You will have up to 10 minutes to try to fix it.  Click on the |finish| button when you have fixed this code or wish to move on without fixing all of it.


.. timed:: get_max_in_range_fix_timed
   :timelimit: 10
   :noresult:
   :nofeedback:
   :fullwidth:
   
   .. activecode:: Get_Max_In_Range_Fix

       # define the function
      def getMaxInRange(numList, start, end):

          # init the max
          max = numList[0] 
      
          # loop start to end (inclusive)
          for index in range(start, end):
          
              # get value at index
              value = index
     
              # if new max
              if value < max: 
              
                  # reset max
                  max = value 

          # return max
          return max
      ====
      
      # code to test the getAverageDropLowest function
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(getMaxInRange([-3, 5, 2, 4], 2, 3),4, "Test of getMaxInRange([-3, 5, 2, 4], 2, 3)")
              self.assertEqual(getMaxInRange([20, 10, 5], 0, 2), 20, "Test of getMaxInRange([20, 10, 5], 0, 2)")
              self.assertEqual(getMaxInRange([20, 10, 5], 0, 1), 20, "Test of getMaxInRange([20, 10, 5], 0, 1)")
              self.assertEqual(getMaxInRange([20, 10, 5], 1, 2), 10, "Test of getMaxInRange([20, 10, 5], 1, 2)")
              self.assertEqual(getMaxInRange([-20, -10, -5], 1, 2), -5, "Test of getMaxInRange([-20, -10, -5], 1, 2)")

      myTests().main()
           
When you are finished with this problem, or are ready to move on, click the |finish| button and then go to the next page by clicking the right arrow |right| near the bottom right of this page.    
