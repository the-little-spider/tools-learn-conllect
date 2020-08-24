 **数组变换**

 * 给定一个长度为 n 的数组，和一个正整数 d
 * 你每次可以选择其中任意一个元素a[i] + d 或 a[i] - d，这算作一次操作
 * 你需要将所有的元素全部变成相等元素，如果有解，请输出最小操作次数，如果无解请输出-1
 *
 * 输入数字n，数字d，和一个长度为 n 的数组a
 * 1<=n<=100000,1<=d<.100,1<=a[i]<=100000
 
 
 ````java
 public static int change(int n, int d, int[] a) {
        if (n == 1) {
            return 0;
        }
        Arrays.sort(a);
        int result = 0;
        for (int i = 0; i < n / 2 + 1; i++) {
            if ((a[n - i - 1] - a[i]) % d == 0) {
                result += (a[n - i - 1] - a[i]) / d / 2 + 1;
            } else {
                return -1;
            }
        }
        return result;
    }
 ````
