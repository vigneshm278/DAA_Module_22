# EX 4B DYNAMIC PROGRAMMING – 2

## DATE :

## AIM :

To find the longest string (or strings) that is a substring (or are substrings) of two strings.

## Algorithm :

1.Take two strings as input.

2.Create a table to store matching lengths.

3.This table keeps track of how many characters match continuously.

4.Compare each character of the first string with each character of the second string.

5.If characters match, increase the match length from the previous diagonal cell in the table.

6.Keep track of the longest match length and where it ends in the first string.

7.At the end, use that information to extract the longest matching part from the first string.

8.Print the result — the longest common substring.

## Program :

### Developed by: VIGNESH M
### Register Number: 212223240176

```
def LCS(X, Y, m, n):
 
    maxLength = 0          
    endingIndex = m        
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]
    
if __name__ == '__main__':
    X = input()
    Y = input()
    m = len(X)
    n = len(Y)
    print('The longest common substring is', LCS(X, Y, m, n))
```

## Output :

![image](https://github.com/user-attachments/assets/049ca732-a6ec-4baf-8d06-d0a88a386750)


## Result :

Thus the program was executed successfully for finding the longest common substring .
