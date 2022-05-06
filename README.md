# Leetcode
## 一、数组
* **相关leetcode题目**
    * 2210.统计数组中峰和谷的数量
    * 2103.环和杆(状态数组)
## 二、链表
## 三、堆
## 四、栈
* **相关leetcode题目**
    * 19.删除链表的倒数第N个节点
## 五、树
## 六、图
* **图的遍历**
* **图的连通性**
   * 最小生成树
* **图的最短路径**
## 七、哈希表
* **相关leetcode题目**
    * 36.有效的数独
## 八、常见算法
### 贪心算法：解决区间问题、分配问题
* **相关leetcode题目**
    - 2224.转化时间需要的最少操作数
    - 1903.字符串中的最大奇数
### DFS和回溯：解决排列、组合、集合问题
* **相关leetcode题目**  
    - 46.全排列
    - 47.全排列II  
    - 77.组合  
    - 93.复原IP地址
* **模板代码**
```python
def f(nums):
    n = len(nums)
    def recursion(path, candidate):
        if len(path) == n:
            res.append(path)
        for i in range(len(candidate)):
            recursion(path+[candidate[i]], candidate[:i] + candidate[i+1:])

    res = []
    recursion([], nums)
    return res
```
### 动态规划：解决重复结算的问题
* **相关leetcode题目**
    - 62.不同路径
* **模板代码**
```python
def f(n):
    if n == 1:
        return 1
    dp = [0] * n
    for i in range(n):
        dp[i] = dp[i-1] + dp[i-2]
    return dp[n]
```
## 七、双指针
    1. 15.三数之和
## 
