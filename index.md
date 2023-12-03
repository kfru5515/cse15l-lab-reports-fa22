LabReport5 <br> 
HYEONJUN JUN <br>
A17181983 <br>
---
### Part1 - Debugging Scenario
![Screenshot 2023-12-03 103614](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/0dbe958e-30ba-4acd-93e3-6e9af487315d)<br>
![LAB5-3](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/887b8a63-ef39-40c6-9d20-25d648ef3645)<br>
Seems like you learning code on widows system but in your bash file line 1 Cpath is for mac os. In a Unix-based system like macOS (which is based on Unix), the classpath separator is usually a colon :. However, in Windows, it's typically a semicolon ;. So, if you're specifying the classpath for Java on both platforms, you might need to adjust the path separator accordingly. so you were code CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar' changed to CPATH='.;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar' <br>For the second photo has error on junit file thus error for Classpath Configuration:includes the directory or JAR file containing the StringChecker class/interface. For example, if StringChecker is part of an external JAR file, include that JAR in your classpath.  
![Lab5-1](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/000a43b1-07b4-42e9-98cc-9f6da2cc8252)
### Part2 - Reflection
From Cse15L Learned about Github, debugging and SSH. GitHub is like this awesome platform our code while working on group projects and create a space called a repository for your project, and it keeps track of all the changes you make, can easily go back to an older version if you break something. Pull requests are like a way to show off your changes to the team before actually putting them into the main code. And when things go wrong, debugging is like detective work. we put these print things in your code to figure out where it's going wrong, use fancy tools to step through your code, and write tests to catch problems early. all I learend from this class, will help my futures. 
