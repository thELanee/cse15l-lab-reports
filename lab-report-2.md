# Lab Report 2

## Change 1  
![image](https://user-images.githubusercontent.com/92767729/164882288-964f58cd-8229-4918-862a-602ca4f278fa.png)  
[Test file that caused the failure](https://github.com/thELanee/markdown-parser/blob/main/test-file3.md)  
  
Running the prior code with test file 3 resulted in an infinite loop.  
We added code to check if there is another open bracket and if the open bracket does not exist, we end the loop. If there is an open bracket but no closing bracket following it, we also end the loop.  
  
When parsing for links, if there is any text after the last link, the while loop will continue to scan for links over and over again because there was a lack of proper exit conditions for the loop. Just checking for an open bracket is not enough, because there could be a linkless open bracket randomly in the text, which is why test file 3 causes an infinite while loop even if we check for an open bracket, because that is not the only thing we need to check for before ending our loop.

## Change 2  
![image](https://user-images.githubusercontent.com/92767729/164882535-61e0b1ef-4872-4883-8bdd-dffce5d75159.png)  
[Test file that caused the failure](https://github.com/thELanee/markdown-parser/blob/main/test-file4.md)  
  
Running the prior code with test file 4 resulted in another infinite loop.  
We also realized that checking if there is another open bracket after storing the index of all the other link syntax stuff was redundant, so we just added a bunch of checkers to see if we can't find a open bracket followed by a close bracket, followed by an open parentheses and close parentheses. If these things can't be found in succession, then the loop ends.  

When parsing for links, the program detected an open bracket and close bracket so it continued to scan for links, resulting in an infinite while loop. This was because we lacked sufficient exit conditions for the loop, like checking for not only brackets, but parentheses. This is why test file 4 causes an infinite while loop, because it has both brackets and an open parentheses, but no close parentheses, so we don't find a link and keep scanning the file infinitely with no exit condition.  

## Change 3  
![image](https://user-images.githubusercontent.com/92767729/164882750-afd1eff1-9bfa-4217-9724-91c929a02034.png)
[Test file that caused the failure](https://github.com/thELanee/markdown-parser/blob/main/testfiles/test-file6.md)  
[This test file also caused a failure](https://github.com/thELanee/markdown-parser/blob/main/testfiles/test-file5.md)  

Running the prior code with test files 5 and 6 both resulted in unwanted outputs, such as an pulling an image link or text between parentheses. In one case, there was an index error. We added code to make sure that we only grab the link in between parentheses if the open parentheses is right after the close bracket as it should be in markdown notation. We also added code that will not grab the link and break the loop if we detect an exclamation mark before the opening bracket. Sometimes, this would cause an index error because we sometimes check for an exclamation mark before the opening bracket when the open bracket is the first character in the line, so we had to add a condition that it only checks for the exclamation mark if the index of the opening bracket is not 0.  
  
When parsing for links, the program detected that we had both brackets and parentheses, then grabbed the text in between the parentheses. However, this was unwanted output in both test files 5 and 6 because in file 5 we got non link text between parentheses that our code pulled because there were double brackets a few lines before. Test file 6 did the same for similar reasons because we did not check for an exclamation mark before the open bracket when the index of the open bracket is not 0.  
