  **Codancer 的炸弹引爆**
  > 难度等级:困难
 
 * Codancer 终于抵达了恶龙的城堡。
 * 现在他在城堡周围摆放了 n 枚电力炸弹
 * 每个电力炸弹有两种属性 m 和 p
 * 引爆 m 枚电力炸弹或者 Codancer 直接花费 p 的电力，第 i 枚炸弹才会被引爆
 * 请计算最少需要多少电力全部引爆
 * 1<=n<200000,1<=p<=100,1<=m<=n
 * 示例
 输入: 
 5
 [[2, 6], [8, 5], [9, 4], [4, 9], [6, 5]]
 输出:
 6
 
 
  ````java
 public static void bomb(int n, int[][] array) {
        //使用冒泡排序对二维数组降序排序
        for (int i = 0; i < array.length - 1; i++) {
            for (int j = i; j < array.length; j++) {
                if (array[i][1] < array[j][1]) {
                    int temp1 = array[i][1];
                    array[i][1] = array[j][1];
                    array[j][1] = temp1;
                    int temp2 = array[i][0];
                    array[i][0] = array[j][0];
                    array[j][0] = temp2;
                }
            }
        }
        int length = array.length;
        int minP = 0;//最小的电力
        int aCount = 0;//当前引爆的数量
        int bCount = n;//当前未引爆的数量
        for (int i = 0; i < length; i++) {
            int p = array[i][1];
            aCount = n - i;
            bCount = i;
            if (bCount == 0) {
                minP = p;
                continue;
            }
            int [][] copy = array;
            //对于i之前的炸弹按m升序排序
            for (int j = 0; j < i - 1; j++) {
                for (int k = j; k < i; k++) {
                    if (copy[j][0] > copy[k][0]) {
                        int temp1 = copy[j][0];
                        copy[j][0] = copy[k][0];
                        copy[k][0] = temp1;
                        int temp2 = copy[j][1];
                        copy[j][1] = copy[k][1];
                        copy[k][1] = temp2;
                    }
                }
            }
            //判断第一个到i-1个炸弹是否引爆
            //这里只要通过m判断,因为p已经固定
            for (int j = 0; j < i; j++) {
                if (copy[0][j] > aCount) {
                    System.out.println("最小电力的结果为:" + minP);
                    return;
                } else {
                    aCount++;
                }
            }
            //全部引爆
            aCount = 0;
            minP = p;
        }
    }
  ````
