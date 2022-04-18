# Dynamic Programming Question Collections

### ·Maximum Subarray(最大子段和) (1.4.1)

##### Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return *its sum*. [Leet code 53](https://leetcode.com/problems/maximum-subarray/)

- f(i): The maximum subarray of nums[0:i] containing nums[i]
- f(0) = nums[0] 
- f(i) = max(f(i-1),0) + nums[i]

[my code](https://pastebin.pl/view/a8362707)



###  ·Longest Common Subsequence(最长公共子序列) (1.4.2)

Given two strings `text1` and `text2`, return *the length of their longest **common subsequence**.* If there is no **common subsequence**, return `0`.

A **subsequence** of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

- For example, `"ace"` is a subsequence of `"abcde"`.

A **common subsequence** of two strings is a subsequence that is common to both strings. [leet code 1143](https://leetcode.com/problems/longest-common-subsequence/)

###### Recursive solution:

- LCS(text1, text2): return the longest common subsequence of text1 and text2
- if text1.length()==0 or text2.length() == 0: return 0
- if text1.length()==1 and text2.length() == 1: return text1 == text 2

- if text1[$n_1$] == text1[$n_2$]: LCS(text1,text2) = LCS(text1[1:$n_1$-1], text2[1:$n_2$-1]) + 1
- if text1[$n_1$] != text1[$n_2$]:  LCS(text1,text2) = MAX( LCS(text1, text2[1:$n_2$-1]) , LCS(text1[1:$n_1$-1], text2) )

[my code](https://paste-bin.xyz/51820)

T(n,m) = MAX(T(n-1,m-1)+ O(1), T(n-1,m)+T(n,m-1)+O(1))  

###### Iterative solution:

- f(i,j): the longest common subsequence of text1[1:i] and text2[1:j]; 1<=i<= n,1<=j<=m
- f(i,0) = f(0,j)=0 
- f(i,j): if (text1[i]==text2[j]) f(i,j) = 1+ f(i-1,j-1); else f(i,j) = MAX(f(i,j-1), f(i-1,j)), i,j >= 1

[my code](https://paste-bin.xyz/51823)





### ·Memoization(记忆化搜索) (1.4.4)

- #### Word Break [leetcode 139](https://leetcode.com/problems/word-break/)

  Given a string `s` and a dictionary of strings `wordDict`, return `true` if `s` can be segmented into a space-separated sequence of one or more dictionary words.

  **Note** that the same word in the dictionary may be reused multiple times in the segmentation.

  

  ###### Recursive version

  WB(s) = for (int i=0; i< s.length(); i++) any s[0:i] in wordDict and WB(s[i+1:])

  ###### Iterative version

  f(i): whether the s[0:i-1] can be constructed with words in wordDict

  f(0)= 0

  f(i) = OR(f(j) and check(s[j:i-1])) for some j in {1,..., i-1}, where check means checking whether the string is in wordDict

  [my solution](https://paste-bin.xyz/51836)

  Time complexity: $O(n^2)$







### ·最优矩阵链乘 (1.4.5)

### ·最优三角剖分 (1.4.6)

### ·背包问题（背包九讲）(1.4.7)

### ·滚动数组优化空间 (1.4.8)

### ·状压dp (1.4.9)

### ·区间dp (1.4.10)

### ·一般dp题（会自己想状态和转移方程）(1.4.11)

### 数位ar子集中sosdp (2.1.1)

### 矩阵加速dp (2.1.2)

### 四边形优化区间dp长链剖分优化 (2.1.3)

### 关链剖分优上下界优化 (2.1.4)

### 1D/1Ddp优化（单调队列优化、单调栈优化、分治优化、斜率优化）插头dp (2.1.5)

### LIS转LCS (2.1.6)