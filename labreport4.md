LAB REPORT 4

Step 4: Log into ieng6

-open a terminal 

-type in ```ssh``` + a course specific username type + ```@ieng6.ucsd.edu```

-after that then input your password to the account

-after successfully entering the username and password you should be met with a screen like this

<img width="620" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/88478b32-9af0-4585-88af-425bccc4f821">



Step 5: Clone your fork of the repository from your Github account

-go to Github using the link https://github.com/ucsd-cse15l-s23/lab7

-there is a button that says "Fork" (which is shown below) and press that in order to fork the repository

<img width="1274" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/c7bddb09-283e-47ee-b057-6f885aa9c312">

-after pressing "Fork" you should be met with the screen shown below and after pressing the green "Fork" button the repository will be successfully forked!

<img width="1181" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/89221b6a-5280-441b-bb6a-ac6340fd0e23">


Step 6: Run the tests, demonstrating if they fail


-in the terminal type in ```bash test.sh``` in order to run the tests

-after running the tests in the terminal the tests will have failed (as shown below)

<img width="752" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/c02949ed-93d9-4447-8564-83bf38dfedf1">

<img width="911" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/106155a7-47c7-432e-ae82-4b2f83345c5c">



Step 7: Edit the code file ListExamples.java to fix the failing test 

-now that it's evident there is a bug in the code, go to ListExamples.java to find the error

-to edit ListExamples.java go into the terminal and type in ```vim ListExamples.java```

-once you're in the file scroll down to the 44th line or press ```j``` 43 times (j is the command for scrolling down)

-once on line 44 edit ```index1 += 1``` to ```index2 +=1``` by pressing ```x``` (delete command) to delete the ```1``` and press ```i``` (insert command) to insert a ```2``` in place of the ```1``` , after it should look like this

<img width="350" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/e6375a41-919f-4e48-afff-b667c36cd17b">

-once done editing type in ```:wq``` to quit vim and now you're done editing!


<img width="685" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/5b809a65-3523-4903-82d3-fe2d17a83228">


<img width="673" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/bd37cba3-9bf7-4760-8bc3-ab557f8b9f47">


-after typing that in the terminal should look like with the entirety of the ListExamples.java file

-after looking through the code, line 44 is where the error was because the index1 should've been an index2

-after fixing the error the code should look like this 

<img width="872" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/a5a75751-8e45-4799-b88f-2b18dcf0a92e">



Step 8: Run the tests, demonstrating that they now succeed

-once again, type in ```bash test.sh``` into the terminal in order to run tests
<img width="610" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/4c28c7b6-a2ce-4de3-b460-ba892259987c">





