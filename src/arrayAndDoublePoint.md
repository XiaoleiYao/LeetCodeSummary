# 15. 三数之和
给你一个包含 n 个整数的数组 nums，判断 nums 中是否存在三个元素 a，b，c ，使得 a + b + c = 0 ？请你找出所有和为 0 且不重复的三元组。

注意：答案中不可以包含重复的三元组。
## 示例 1：
```
输入：nums = [-1,0,1,2,-1,-4]
输出：[[-1,-1,2],[-1,0,1]]
```
## 示例 2：
```
输入：nums = []
输出：[]
```
## 示例 3：
```
输入：nums = [0]
输出：[]
```
```c++
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        int n = nums.size();
        vector<vector<int>> res;
        if(n <3)
        {
            return res;
        }
        sort(nums.begin(),nums.end());
        if(nums[0] > 0)
        {
            return res;
        }
        for(int i = 0;i < n;++i)
        {
            if(i > 0 && nums[i] == nums[i-1])
            {
                continue;
            }
            int right = n - 1;
            for(int left = i + 1;left < n;++left)
            {
                if(left > i + 1 && nums[left] == nums[left-1])
                {
                    continue;
                }
                while(left < right && nums[i] + nums[left] + nums[right] > 0)
                {
                    right--;
                }
                if(left >= right)
                {
                    break;
                }
                if(nums[i] + nums[left] + nums[right] == 0)
                {
                    res.push_back({nums[i],nums[left],nums[right]});
                }
            }
        }
        return res;
    }
};
```

# 11. 盛最多水的容器
给你 n 个非负整数 a1，a2，...，an，每个数代表坐标中的一个点 (i, ai) 。在坐标内画 n 条垂直线，垂直线 i 的两个端点分别为 (i, ai) 和 (i, 0) 。找出其中的两条线，使得它们与 x 轴共同构成的容器可以容纳最多的水。

说明：你不能倾斜容器。
## 示例 1：
![image](https://user-images.githubusercontent.com/60544624/113107537-a2135f80-9236-11eb-9e94-836c31e7b87d.png)
```
输入：[1,8,6,2,5,4,8,3,7]
输出：49 
解释：图中垂直线代表输入数组 [1,8,6,2,5,4,8,3,7]。在此情况下，容器能够容纳水（表示为蓝色部分）的最大值为 49。
```
## 提示
```
n = height.length
2 <= n <= 3 * 104
0 <= height[i] <= 3 * 104
```
```c++
class Solution {
public:
    int maxArea(vector<int>& height) {
        int l = 0;
        int r = height.size()-1;
        int res = 0;
        while(l < r)
        {
            int area = min(height[l],height[r]) * (r-l);
            res = max(res,area);
            if(height[l] < height[r])
            {
                l++;
            }
            else
            {
                r--;
            }
        }
        return res;
    }
};
```

