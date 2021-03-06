# Lab Report 5  
  
## Finding tests with different results  
I outputed the results of running all the tests to a text file for each implementation, then used vimdiff to see the differences between both files.  
## Test Files with Different Results  
[201.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md)   
[22.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/22.md)  
  
### Test 201.md  
My implementation is correct because it does not produce a link while the provided implementation does.  
![image](https://user-images.githubusercontent.com/92767729/171075260-a12443a6-7097-4260-9c40-89ece5e40d07.png)  
Expected Output: []  
![image](https://user-images.githubusercontent.com/92767729/171075529-e89cdde3-c555-490d-aae5-066953685446.png)  
  
#### Test 201.md Bug  
The problem with this implementation as can be seen in the code provided below, is that it does not check if the open parentheses and close bracket are right next to each other to see if the link is valid. As such, as long as the close bracket and open paren exist in the file, it will produce the link as the text between the parentheses, even if it is not a valid link in markdown. Potential fixes could be checking for '](' rather than ']' and '(' separately, or adding an if statement checking if the close bracket index is one index before the open paren index. 
![image](https://user-images.githubusercontent.com/92767729/171076402-d0bae9d4-395a-464f-94ab-2025558de649.png)  
  
### Test 22.md  
My implementation is correct because it produces a link while the provided implementation does not.  
![image](https://user-images.githubusercontent.com/92767729/171075238-18e4cb29-2c9a-4a55-8b5c-d498c5b53008.png)  
Expected Output: [/bar\* "ti\*tle"]  
![image](https://user-images.githubusercontent.com/92767729/171076640-0f2950d9-89d8-496c-94c4-06a8fe1312df.png)  
  
#### Test 22.md Bug
The reasons this implementation does not produce a link while the commonMark demo site does is that it does not add the link to the list of potential links if it detects either a space or newline character in the link substring. As such, links such as /bar\* "ti\*tle" would not be added because they would not pass the if statement check at the bottom due to containing a space. To fix this, you could just remove the statement checking for a space before deciding to add the link because markdown still recognizes links with spaces as valid.  
![image](https://user-images.githubusercontent.com/92767729/171077295-8c0fc754-1216-4472-b6fb-60b387388353.png)







