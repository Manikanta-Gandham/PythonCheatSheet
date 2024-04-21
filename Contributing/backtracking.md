
# Subsets

Subsets are the collections of elements from a given set, where the order of elements doesn't matter. Every set has at least two subsets: the empty set and itself. The number of subsets of a set with 
n elements is pow(2,n)
 . Subsets can contain any number of elements from zero to the total number of elements in the original set

 ## subsets
 ## subsets II

``` python
class Solution(object):
    def subsets(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        self.dfs(nums, [], res)
        return res
    
    def dfs(self, nums, path, res):
        res.append(path)
        for i in range(len(nums)):
            self.dfs(nums[i+1:], path + [nums[i]], res)

class Solution(object):
    def subsetsWithDup(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        nums.sort()
        self.dfs(nums, [], res)
        return res
    
    def dfs(self, nums, path, res):
        res.append(path)
        for i in range(len(nums)):
            if i > 0 and nums[i] == nums[i-1]:
                continue
            self.dfs(nums[i+1:], path + [nums[i]], res)
``` 

# Permuations

Permutations are the arrangements of elements of a set in a particular order. The order of the elements matters in permutations.The number of permutations of a set of 
n elements taken r at a time is denoted by P(n,r)

 ## Permutation
 ## permutation II
``` python
class Solution(object):
    def permute(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        self.dfs(nums, [], res)
        return res
    
    def dfs(self, nums, path, res):
        if len(nums) == 0:
            res.append(path)
            return
        for i in range(len(nums)):
            self.dfs(nums[:i] + nums[i+1:], path + [nums[i]], res)

class Solution(object):
    def permuteUnique(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        res = []
        nums.sort()
        self.dfs(nums, [], res)
        return res
    
    def dfs(self, nums, path, res):
        if len(nums) == 0:
            res.append(path)
        for i in range(len(nums)):
            if i > 0 and nums[i] == nums[i-1]:
                continue
            self.dfs(nums[:i] + nums[i+1:], path + [nums[i]], res)
``` 
# Combinations

Combinations are selections of items from a larger group, where the order doesn't matter. The number of combinations of a set of n elements taken 
r at a time is denoted by C(n,r)
 ## combinations
 ## combinations sum
 ## combination sum II

``` python
class Solution(object):
    def combine(self, n, k):
        """
        :type n: int
        :type k: int
        :rtype: List[List[int]]
        """
        res=[]
        self.dfs(range(1, n+1), k, [], res)
        return res
    
    def dfs(self, nums, k, path, res):
        if len(path) == k:
            res.append(path)
            return
        for i in range(len(nums)):
            self.dfs(nums[i+1:], k, path+ [nums[i]], res)

class Solution(object):
    def combinationSum(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        res = []
        candidates.sort()
        self.dfs(candidates, target, [], res)
        return res
    
    def dfs(self, candidates, target, path, res):
        if target < 0:
            return   #backtracking
        if target == 0:
            res.append(path)
            return
        for i in range(len(candidates)):
            self.dfs(candidates[i:], target - candidates[i], path + [candidates[i]], res)

class Solution(object):
    def combinationSum2(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        res = []
        candidates.sort()
        self.dfs(candidates, target, [], res)
        return res
    
    def dfs(self, candidates, target, path, res):
        if target < 0:
            return
        
        if target == 0:
            res.append(path)
        for i in range(len(candidates)):
            if i > 0 and candidates[i] == candidates[i-1]:
                continue
                
            if candidates[i]> target:
                break
                
            self.dfs(candidates[i+1:], target - candidates[i], path + [candidates[i]], res)



``` 
![image](https://github.com/Manikanta-Gandham/PythonCheatSheet/assets/19523549/41a644cb-5625-40fc-9feb-ae6859ed2585)
