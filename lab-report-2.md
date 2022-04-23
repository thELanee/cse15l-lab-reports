# Lab Report 2

## Change 1  
![image](https://user-images.githubusercontent.com/92767729/164882288-964f58cd-8229-4918-862a-602ca4f278fa.png)  
[Test file that caused the failure](https://github.com/thELanee/markdown-parser/blob/main/test-file3.md)  
  
Running the prior code with test file 2 resulted in an infinite loop.  
We added code to check if there is another open bracket and if the open bracket does not exist, we end the loop. If there is an open bracket but no closing bracket following it, we also end the loop.  
  
When parsing for links, if there is any text after the last link, the while loop will continue to scan for links over and over again because there was a lack of proper exit conditions for the loop. Just checking for an open bracket is not enough, because there could be a linkless open bracket randomly in the text, which is why test file 2 causes an infinite while loop even if we check for an open bracket, because that is not the only thing we need to check for before ending our loop.
