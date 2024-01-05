# Longest-Increasing-Subsequence

import bisect

class Solution:
    def lengthOfLIS(self, nums):
        if not nums:
            return 0

        lis = [nums[0]]

        for num in nums[1:]:
            if num > lis[-1]:
                lis.append(num)
            else:
                index = bisect.bisect_left(lis, num)
                lis[index] = num

        return len(lis)


solution_instance = Solution()

nums1 = [10, 9, 2, 5, 3, 7, 101, 18]
nums2 = [0, 1, 0, 3, 2, 3]
nums3 = [7, 7, 7, 7, 7, 7, 7]

print(solution_instance.lengthOfLIS(nums1))  
print(solution_instance.lengthOfLIS(nums2))  
print(solution_instance.lengthOfLIS(nums3)) 
