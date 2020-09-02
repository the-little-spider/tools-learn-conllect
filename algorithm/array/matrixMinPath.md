  **矩阵最小路径和**
   > 难度等级:中等
  
  * 给定一个矩阵，大小为 m
  * 从左上角开始每次只能向右走或者向下走
  * 终点为右下角
  * 路径中所有数字累加起来就是路径和
  * 求所有路径的最小路径和
  * 示例
  * 输入矩阵为:
  * 4 1 3 5
  * 3 2 7 7
  * 6 5 2 8
  * 8 9 4 5
  * 最小路径为: 23
  
    ````java
    public int solution(int[][] m) {  
        if(m==null){  
            return 0;  
        }  
        if(m.length==0){  
            return 0;  
        }  
        int[][] dp = new int[m.length][m[0].length];  
        dp[0][0] = m[0][0];  
        //先计算第一行  
        for (int i = 1; i < m.length; i++) {  
            dp[i][0] = dp[i-1][0]+m[i][0];  
        }  
        //计算第一列  
        for (int i = 1; i < m[0].length; i++) {  
            dp[0][i] = dp[0][i-1]+m[0][i];  
        }  
        //从上->下，左->右 计算当前位置的最小值  
        for (int i = 1; i < m.length; i++) {  

            for (int j = 1; j < m[0].length; j++) {  
                dp[i][j] = Math.min(dp[i][j-1],dp[i-1][j]) + m[i][j];  
            }  

        }
        return dp[m.length-1][m[0].length-1];  
    }
    ````
