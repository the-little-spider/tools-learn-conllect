  **学习小组**
  >难度等级:中等

  * 课堂上有n个学生 (1<=n<=3e5)
  * 每个学生都有他们自己的学分ai(1<=ai<=1e9,ai>=ai-1)
  * 现要将他们分成 m 个小组(1<=m<=n)
  * 所有的小组都是由相邻的学生组成
  * 分组时需要让每个小组的学分差值尽量小(最大值减最小值)
  * 输出最后的每个小组的最小的差值的总和
  * 第一行和第二行输入两个数 n、m 表示有 n 个学生要分成 m 个小组
  * 再输入 n 个数，表示每个学生的学分
  * 示例
输入: 5  3  {1,4,5,7,8}
输出: 4

  ````java
public int solution(int n, int m, int[] nums) {
	int[] sub = new int[n-1];
	//计算出所有相邻的差值
	for(int i = 0; i < (n-1); i++){
		sub[i] = nums[i+1] - nums[i];
	}
	//升序排序
	Arrays.sort(sub);
	//极差减去最大的 m-1 个相邻的差值可得到最小的差值的总和
	int ans = nums[n-1] - nums[0];
	for(int i = 0;i< (m-1) ;i++){
		ans = ans - sub[n-2-i];
	}
	return ans;
}

  ````
