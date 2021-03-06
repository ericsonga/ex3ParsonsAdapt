..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. setup for automatic question numbering.

..     qnum::
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
    
.. |checkme| image:: Figures/checkMe.png
    :height: 20px
    :align: top
    :alt: check me
    
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
           self.assertEqual(getMinInRange([-3, 5, 8, 4], 1, 3),4, "Test of getMinInRange([-3, 5, 8, 4], 1, 3)")
           self.assertEqual(getMinInRange([20, 10, 5], 0, 2), 5, "Test of getMinInRange([20, 10, 5], 0, 2)")
           self.assertEqual(getMinInRange([20, 10, 5], 0, 1), 10, "Test of getMinInRange([20, 10, 5],0, 1)")
           self.assertEqual(getMinInRange([20, 10, 5], 1, 2), 5, "Test of getMinInRange([20, 10, 5], 1, 2)")
           self.assertEqual(getMinInRange([-20, -10, -5], 1, 2),-10,"Test of getMinInRange([-20, -10, -5], 1, 2)")

   myTests().main()
   
Practice 4: Get Max In Range
------------------------------

The following code should return the maximum of all the values between a specified start and end index (inclusive), but the code is mixed up and contains extra blocks that are not needed in the correct solution.  To find the maximum value in a range of indices, first create a variable to keep track of the maximum and initialize it to the value at the start index.  Then loop from the start index to the end index (inclusive).  Get the value at the current index.  If the value at the current index is greater than the maximum then set the maximum to the current value.  After the loop return the maximum value found.

.. note ::
   
    Remember that you should set the maximum value found so far to the first value in the range, not to the first element in the list.  
    
Examples
=========

For example ``getMaxInRange([-3, 5, 2, 4], 2, 3)`` should return 4 and ``getMaxInRange([-20, -10, -5], 1, 2)`` should return -5.  

Order Code Here
================

The following code is mixed up and contains extra blocks that are not needed in a correct solution.

Click on the |start| button below when you are ready to try to order this code.  You will have up to 10 minutes to try to solve it.  Click the |runbutton| button to check your solution.  Click on the |finish| button when you have solved this problem or wish to move on without solving it.

.. timed:: get_max_in_range_order_timed
   :timelimit: 10
   :noresult:
   :nofeedback:
   :fullwidth:
    
   .. parsonsprob:: Get_Max_In_Range
      :order: 9, 10, 6, 2, 4, 12, 1, 7, 3, 5, 8, 0, 11
      :adaptive:
      :maxdist: 4

      The code is mixed up and contains extra blocks that are not needed.  Drag the needed code from the left to the right and put them in order with the correct indention so that the code would work correctly.  To indent just drag the block further to the right. Click the "Check Me" button to see if your solution is correct. 
      -----
      def getMaxInRange(numList, start, end):
      =====
      def getMaxInRange(numList, start, end: #paired
      =====
          max = numList[start]
      =====
          max = numList[0] #paired
      =====
          for index in range(start, end+1):
      =====
          for index in range(start, end) #paired
      =====
              value = numList[index]
      =====
              value = index #paired
      =====
              if value > max:
      =====
              if value < max: #paired
      =====
                 max = value
      =====
                 value = max #paired
      =====
          return max

           
When you are finished with this problem, or are ready to move on, click the |finish| button and then go to the next page by clicking the right arrow |right| near the bottom right of this page.    
