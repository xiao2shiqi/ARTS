## Algorithm
Leetcode Easy题：两数之和<br>
描述<br>
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。<br>

示例<br>
给定 nums = [2, 7, 11, 15], target = 9<br>
因为 nums[0] + nums[1] = 2 + 7 = 9<br>
所以返回 [0, 1]

解题思路<br>
暴力破解：时间复杂度O（n2）
1. 使用2层循环遍历元素
2. 外循环索引i内循环索引j，避免重复相加j的索引只会=i + 1
3. 判读nums[i] + nums[j] = targer 则返回 i, j 的索引值，退出循环

两次哈希：时间复杂度O（n）
1. 将元素和索引值以key:value格式放入HashMap
2. 遍历数组，通过 target - nums[i] 得到结果Key
3. 判断map包含containsKey，并且value(索引值)不等于当前值
4. 返回i, map(key)的索引值，退出循环

```java
    public static int[] twoSum(int[] nums, int target) {
        //暴力破解法 时间复杂度为 O （n2）
        int length = nums.length;
        for(int i = 0; i < length; i++) {
            for(int j = i + 1; j < length; j++) {
                if(nums[i] + nums[j] == target){
                    return new int[]{i, j};
                }
            }
        }

        //两次哈希，时间复杂度为 O（n）
        Map<Integer, Integer> numHash = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            numHash.put(nums[i], i);
        }
        for (int i = 0; i < nums.length; i++) {
            int targetKey = target - nums[i];
            //不跟自己合并
            if(numHash.containsKey(targetKey) && numHash.get(targetKey) != i) {
                return new int[]{i, numHash.get(targetKey)};
            }
        }
        return new int[]{0, 0};
    }
```