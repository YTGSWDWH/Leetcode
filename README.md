# Leetcode刷题总结
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
def recursion(path, candidate):
    if len(path) == n:
        res.append(path)
        return
    for i in range(len(candidate)):
        recursion(path + [candidate[i]], candidate[:i] + candidate[i+1:])
res = []
recursion([], nums)
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
### 双指针
* **相关leetcode题目**
    * 15.三数之和
## 排序算法
* **O(n^2)时间复杂度**
    * 冒泡排序
    	* 模板代码
		```python
		def BubleSort(arr):
		    n = len(arr)
            for i in range(1,n):
                for j in range(n-i):
                    if arr[j] > arr[j+1]:
                        arr[j], arr[j+1] = arr[j+1], arr[j]
		        print(arr)
		    return arr
		```
    * 选择排序
    	* 模板代码
    	```python
		def SelectionSort(arr):
		    n = len(arr)
            for i in range(n-1):
                for j in range(i+1, n):
		            if arr[j] < arr[i]:
		                arr[i], arr[j] = arr[j], arr[i]
		        print(arr)
            return arr
		```
    * 插入排序
        * 模板代码
        ```python
        def InsertionSort(arr):
            for i in range(1, len(arr)):
                key = arr[i]
                j = i-1
                while j >= 0 and key < arr[j]:
                    arr[j+1] = arr[j]
                    j = j - 1
                arr[j+1] = key
        ```
* **O(nlogn)时间复杂度**
	* 快速排序
	    * 模板代码
	    ```python
        def quicksort(arr):
            if len(arr) < 2:
                return arr
            else:
                pivot = arr[0]
                less = [each for each in arr[1:] if each <= pivot]
                greater = [each for each in arr[1:] if each > pivot]
                return quicksort(less) + [pivot] + quicksort(greater)
        ```
	* 归并排序
	    * 模板代码
	    ```python
        def merge(left, right):
            result = []
            i, j = 0, 0
            while i < len(left) and j < len(right):
                if left[i] <= right[j]:
                    result.append(left[i])
                    i += 1
                else:
                    result.append(right[j])
                    j += 1
            result += left[i:]
            result += right[j:]
            return result
        def mergesort(arr):
            n = len(arr)
            if n <= 1:
                return arr
            mid = n // 2
            left = mergesort(arr[:mid])
            right = mergesort(arr[mid:])
            return merge(left, right)
        ```
	* 堆排序
	    * 模板代码
	    ```python
        
        ```
* **稳定性**
    * 稳定的排序算法
        * 冒泡排序
        * 插入排序
        * 归并排序
    * 不稳定的排序算法
        * 选择排序
        * 快速排序
        * 堆排序
