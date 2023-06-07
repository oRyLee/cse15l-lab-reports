LAB REPORT 4

Step 4: Log into ieng6

-open a terminal 

-type in ```ssh``` + a course specific username type + ```@ieng6.ucsd.edu```

-after that then input your password to the account

-after successfully entering the username and password you should be met with a screen like this


<img width="620" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/88478b32-9af0-4585-88af-425bccc4f821">





Step 5: Clone your fork of the repository from your Github account

-go to Github using the link [https://github.com/ucsd-cse15l-s23/lab7](https://github.com/ucsd-cse15l-s23/lab7)

-there is a button that says "Fork" (which is shown below) and press that in order to fork the repository


<img width="1274" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/c7bddb09-283e-47ee-b057-6f885aa9c312">

-after pressing "Fork" you should be met with the screen shown below and after pressing the green "Fork" button the repository


<img width="1181" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/89221b6a-5280-441b-bb6a-ac6340fd0e23">

-then in the terminal type in ```git clone``` and your specific fork link to finish forking! You should have something similar to the screen below 


<img width="635" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/3e4f181b-4972-4f11-83fb-e1af14f5beda">





Step 6: Run the tests, demonstrating if they fail

- type in ```cd lab7``` to get into the lab7 directory

-in the terminal type in ```bash test.sh``` in order to run the tests

-after running the tests in the terminal the tests will have failed (as shown below)


<img width="911" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/106155a7-47c7-432e-ae82-4b2f83345c5c">





Step 7: Edit the code file ListExamples.java to fix the failing test 

now that it's evident there is a bug in the code, go to ListExamples.java to find the error!

-to edit ListExamples.java go into the terminal and type in ```vim ListExamples.java```

-now the terminal should look like the image below with the entirety of the ListExamples.java file


<img width="350" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/e6375a41-919f-4e48-afff-b667c36cd17b">

-once you're in the file scroll down to the 44th line or type ```j``` 43 times (j is the command for scrolling down)

-highlight the "1" in "index1"



<img width="343" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/fbd2aca8-50b9-47e4-a1a3-3b252e8df34d">

-the press x to delete the "1"


<img width="472" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/a0488e1d-0e4d-43b4-9bfe-471d783a0e4c">

-type i which goes into insert mode

-then type in 2 to make "index2" as shown in the image below



<img width="420" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/bb321343-ca2c-454f-bffd-af020d3c24e5">

-after completing the change press the <esc> key to exit insert mode

-once done editing type in ```:wq``` to save the file and quit vim, now you're done editing!



  
  
 

Step 8: Run the tests, demonstrating that they now succeed

-once again, type in ```bash test.sh``` into the terminal in order to run tests and they should all be successful like in the image below
  
  
<img width="610" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/4c28c7b6-a2ce-4de3-b460-ba892259987c">


  
  
Step 9: Commit and push the resulting change to your Github account (you can pick any commit message!)

- type in ```git commit -a``` into the terminal 
- now type in whatever committ message of your choosing
- after writing the message press ```esc``` to exit insert mode
- then type ```:wq``` to save the work
- after that press enter and you should be met with this screen
  
  
  
-<img width="657" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/fb582ee4-7949-4487-bae6-c747d0299874">
  
  
 -then in the terminal type ```git add .``` to confirm changes in all files and ```git status``` will show you if the 
  changes were made (it'll look like the photo below)
  
  
  <img width="402" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/bb086260-0f08-495e-999f-725c63d69538">
  
  

-in order to git push, firstly make a token (instructions on how to do so can be found here [https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

  
<img width="869" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/b34f4e86-8c04-4da4-ae03-1e03807d506e">


-once you've made a token enter ```git push``` in the terminal

-enter your github username, and as for the password copy and paste the token you created

-once done the screen should look like this and that is it!


<img width="581" alt="image" src="https://github.com/oRyLee/cse15l-lab-reports/assets/130015533/4d4e97cc-bd3d-4706-84b5-92095f623110">







