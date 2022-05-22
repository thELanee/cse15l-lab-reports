# Lab Report 4  
[link to my markdown-parse](https://github.com/thELanee/markdown-parser)  
[link to other group's repo](https://github.com/richmass1/markdown-parser)  

## Expected Output  

### Snippet 1  
![image](https://user-images.githubusercontent.com/92767729/169671364-ed811c50-c51d-4514-9113-bab2886ad5cb.png)  
"'google.com", "google.com", "ucsd.edu"  
  
### Snippet 2  
![image](https://user-images.githubusercontent.com/92767729/169671413-f889b1cc-2ca8-49d8-bdd1-87d640187e2f.png)  
"a.com", "a.com(())", "example.com"  
  
### Snippet 3  
![image](https://user-images.githubusercontent.com/92767729/169671439-70e2e84a-e83e-4180-9ed0-67989729d722.png)  
"https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule"
  
## Turning it into a test 
![image](https://user-images.githubusercontent.com/92767729/169671728-167e7a26-6d11-49ec-b862-70472051ceed.png)  
  
### Snippet 1 
(My implementation)  
![image](https://user-images.githubusercontent.com/92767729/169671793-09cf721e-fd82-4349-9c32-4db3c39b63e6.png)  
(Other implementation)  
![image](https://user-images.githubusercontent.com/92767729/169678818-49af7387-0082-4d0d-a7e4-d55269f39e7a.png)  

### Snippet 2 
(My implementation)  
![image](https://user-images.githubusercontent.com/92767729/169678933-88026bb2-09c5-43f9-87c0-74afd941e55b.png)  
(Other Implementation)  
![image](https://user-images.githubusercontent.com/92767729/169678842-873b6da6-af1d-4417-b8ac-a64a64aff721.png)  

### Snippet 3 
(My implementation)  
![image](https://user-images.githubusercontent.com/92767729/169671831-a07280e7-3813-4a3f-b181-3ada446ce38e.png)
(Other implementation)  
![image](https://user-images.githubusercontent.com/92767729/169678867-59e1cae0-13d2-46f4-b976-a164115c0b94.png)  

## Explanation  

### Snippet 1  
There is a small change that will allow my code to work for snippet 1 and all related cases with backticks. I just have to make it so that my program checks for if there are backticks enclosing the first or last bracket, so it would probably utilize a counter that keeps track of backticks, and if it finds a backtick before and after the first open bracket or last close bracket, updates the index to the next close parentheses. To do this, I also need to add a few lines of code that will help me find the last close bracket so that links like `'google.com` will register.

### Snippet 2  
There is also a small change here that will allow my code to work for snippet 2 and all related cases with nested parentheses and brackets. I would just need to implement a helper method or have code within the loop that looks for the last closed bracket in the link before the open parentheses and the last open bracket in the link. So it would probably need to look for a "](" string to find the last valid close bracket then whenever it finds a closing parenthesis, checks if there are more open parenthesis further down to look for the last one.  

### Snippet 3  
This change would be more involved because I would have to find a way to ignore newlines and spaces in the brackets and parentheses. I could probably increment the index to the next open parentheses if I detect a newline in the bracket and use indexes to cut out the newlines and whitespace in the parentheses when creating the link substring, with a condition that if there is a newline character before the next close parentheses to update the index to the next close parentheses instead of adding the link.






