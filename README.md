# LCS
Longest_Common_subsequence
 def lcs(self,x,y,s1,s2):
        dp=[[-1 for j in range(y+1)]for i in range(x+1)]
        for i in range(x+1):
            for j in range(y+1):
                if i==0 or j==0:
                    dp[i][j]=0
                elif s1[i-1]==s2[j-1]:
                    dp[i][j]=1+dp[i-1][j-1]
                else:
                    dp[i][j]=max(dp[i][j-1],dp[i-1][j])
        return dp[x][y]
