## Algorithm
Leetcode 题：罗马数字转整数
链接：https://leetcode-cn.com/problems/roman-to-integer/
描述
罗马数字包含以下七种字符: I， V， X， L，C，D 和 M。

```
字符          数值
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

例如， 罗马数字 2 写做 II ，即为两个并列的 1。12 写做 XII ，
即为 X + II 。 27 写做  XXVII, 即为 XX + V + II 。

通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况：

* I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。
* X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 
* C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。

给定一个罗马数字，将其转换成整数。输入确保在 1 到 3999 的范围内。

时间复杂度：O(n)
解题思路:
1. 用map保存字符对应数字
2. 用map保存字符对应特殊规则
3. 字符不包含特殊情况做正常计算
4. 字符包含特殊情况做特殊规则计算

```java
    public static int romanToInt(String s) {
        //罗马符号数字映射表
        Map<Character, Integer> romeNum = new HashMap<Character, Integer>(){{
            put('I', 1);put('V', 5);put('X', 10);put('L', 50);put('C', 100);put('D', 500);put('M', 1000);
        }};
        //特殊情况映射字符，便于扩展
        Map<Character, Character> special = new HashMap<Character, Character>(){{
            put('V', 'I');put('X', 'I');put('L', 'X');put('C', 'X');put('D', 'C');put('M', 'C');
        }};
        int sum = 0;
        //通过映射表求和
        for (int i = 0; i <= (s.length() - 1); i++) {
            char c = s.charAt(i);
            if(!romeNum.containsKey(c)) continue;
            sum = sum + romeNum.get(c);
            if(i == 0) continue;
            //处理特殊情况
            if(special.containsKey(c)){
                if(s.charAt(i - 1) == special.get(c)) sum = sum - romeNum.get(special.get(c)) * 2;
            }
        }
        //处理上限和下限
        if(sum < 1) return 1;
        if(sum > 3999) return 3999;
        return sum;
    }
```