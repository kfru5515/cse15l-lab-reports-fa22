LabReport2 <br> 
HYEONJUN JUN <br>
A17181983 <br>
---
### PART 1 CODE & PAGE SHOW
![Screenshot 2023-10-22 103942](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/286374e3-24ea-4863-8e2d-84dbc2d18271)

![Screenshot 2023-10-22 111137](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/92da7f1d-d56b-4c69-beb6-5218a6eeba9a)
![Screenshot 2023-10-22 133228](https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/a239a79c-8fb2-4d1e-9978-b9d4f378005e)

Question ans answer For part 1:
---
For each of the two screenshots, describe: <br>
Which methods in your code are called?. 
1. Which methods in your code are called?<br>
Answer: Handler classed when a request is made to the server and <br>
StringServer is also caleed when the program is executed, the command-line arguments.
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class? <br>
Answer: handleRequest(URI)method and relevant fileds of the handler class is message and count. <br>
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why. <br>
Answer: The 'message' filed changes when a request '/add-message' path is received and processed, and add new message to exisiting content. and The 'count' filed increase whenever a new message is succesfully added. if the request don't meet the specific conditions the values of both fields not changed. <br>

### PART 2
---
<img src= "https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/1954c1ba-59ce-417a-ba71-24b6a0761953"/>

<img src= "https://github.com/kfru5515/cse15l-lab-reports-fa23/assets/120256621/92dc858d-d86d-4df9-93da-9c378006f108"/>

### PART 3
---
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before.<br>
I used ssh couple times before this class, from this lab we learned about scp. It's evident that it provides a secure way to copy files between a local host and a remote host, so it provied us easy way to connect to the server, but it requires specifying the full path of the file on both the local and remote machines along with the relevant usernames. scp provides a straightforward and secure method for transferring files over SSH and is commonly used in various situations, including transferring data to and from remote servers and performing backups.


