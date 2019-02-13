# LeetCodeSample4J
## 初级算法
### 数组
* 从排序数组中删除重复项
> 给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。**不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。**
```java 
class Solution {
    public int removeDuplicates(int[] nums) {
        int i = 0;// 当前下标
        int j = 1;// 比较下标
        for (; j < nums.length;j++) {
            if(nums[i] != nums[j]){
                i++;
                nums[i] = nums[j];
            }
        }
        return i+1 ;// 数组长度 下标+1
    }
}
```
* 买卖股票的最佳时机 II
> 给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。

**注意：** 你不能同时参与多笔交易（你必须在再次购买前出售掉之前的股票）。

解题思路：`只要今天比明天便宜，就应该进行一次买卖!`
```java
class Solution {
    public int maxProfit(int[] prices) {
        int sum = 0;
        for(int i = 0; i< prices.length-1; i++){
            if(prices[i]<prices[i+1]){
                sum = sum + prices[i+1] - prices[i];
            }
        }
        return sum;
    }
}
```
* 旋转数组
> 给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。**尽可能想出更多的解决方案，至少有三种不同的方法可以解决这个问题。要求使用空间复杂度为 O(1) 的原地算法。**
解题思路：`我这只提供了一种实现方式，即每次移动整个数组一个位置，移动几个位置，就循环几次。`
```java
class Solution {
    public void rotate(int[] nums, int k) {
        int tmp = -1;
        for(;k>0;k--){
            tmp = nums[nums.length-1];
            for(int i = nums.length-1; i > 0; i--){
                nums[i] = nums[i-1];
            }
            nums[0] = tmp;
        }
    }
}
```



