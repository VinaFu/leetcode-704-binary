# leetcode-704-binary

二分法：

      class Solution(object):
          def search(self, nums, target):
              """
              :type nums: List[int]
              :type target: int
              :rtype: int
              """
              l = 0
              r = len(nums)-1
                # 设置左右边界，用于取中间数，以及改变范围。
              while l <= r:
                # 这里用的while，不能用for取值。
                # <= 
                # 下面定义中间数：
                  mid = (l+r)//2
                  if target < nums[mid]:
                      r = mid-1
                        # 因为中间数不等于，所以下一次的时候可以把它去掉以节约时间，所以有了±1
                  elif target > nums[mid]:
                      l = mid+1
                  else:
                      return mid
                      # 这里的临界值是等于，所以直接返回等于。还有其他的题，要的就是临界值。考虑清楚取左还是右
              return -1
