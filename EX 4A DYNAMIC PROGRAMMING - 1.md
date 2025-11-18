# EX 4A DYNAMIC PROGRAMMING - 1

## DATE :

## AIM :

To find longest common subsequence using Dynamic Programming.

## Algorithm :

1.Take two strings – Let's call them X and Y.

2.Create a table (2D list) to store results for all combinations of characters from both strings.

3.Go through each character of X and Y.

4.If characters match, increase the value from the previous diagonal by 1.

5.If characters don’t match, take the maximum value from the left or top cell.

6.The final number in the bottom-right of the table tells you the length of the LCS.

7.To find the actual LCS string:Start from the bottom-right of the table.

8.Move up, left, or diagonally to collect the matching characters.

9.Return the LCS string.

## Program :

### Developed by: VIGNESH M
### Register Number: 212223240176

```
def longest_common_subsequence(X, Y):
    m = len(X)
    n = len(Y)

    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

    lcs_length = dp[m][n]
    lcs = [''] * lcs_length
    i, j = m, n

    while i > 0 and j > 0:
        if X[i - 1] == Y[j - 1]:
            lcs[lcs_length - 1] = X[i - 1]
            i -= 1
            j -= 1
            lcs_length -= 1
        elif dp[i - 1][j] > dp[i][j - 1]:
            i -= 1
        else:
            j -= 1

    return ''.join(lcs)
X = input()
Y = input()

result = longest_common_subsequence(X, Y)
print(result)

```

## Output :

![image](https://github.com/user-attachments/assets/7a55a1f2-46d0-45cb-8a39-b80cec1939d3)


## Result :

Thus the program was executed successfully for computing the length of longest common subsequence.
