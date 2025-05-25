# EX 6D BRUTE FORCE ALGORITHM
## DATE:
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.




## Algorithm
1. Take the main string and the substring as input.
2. Find the lengths of both strings.
3. Loop through the main string from index 0 to len(main) - len(substring).
4. At each position, extract a slice equal to the length of the substring.
5. Compare the slice with the substring; if they match, print the starting index.
6. Continue until all possible positions are checked.

## Program:
```
To implement the program using brute force method of searching for the given substring in the main string.
Developed by: R Guruprasad
Register Number: 212222240033
```
```py
def match(string,sub):
    l = len(string)
    ls = len(sub)
    # start = sub[0]
    for i in range(l-ls+1):
        j=0
        while j<ls and string[i+j]==sub[j]:
            j+=1
        if j==ls:
            print("Found at index",i)
    return -1

    ########### Add your code here #######

str1=input()
str2=input()

```

## Output:
![image](https://github.com/user-attachments/assets/cf982d3d-502d-400c-a9eb-7806f92d73a0)



## Result:
Thus the above program was executed successfully for searching the substring at respective index.
