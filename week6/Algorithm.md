## Algorithm
Leetcode #13: Valid Parentheses<br>
<br>
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.<br>
An input string is valid if:
1. Open brackets must be closed by the same type of brackets.
1. Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

解题思路<br>
栈匹配：时间复杂度O(n)
1. 通过索引下标遍历字符串
2. 判断索引值是左括号则压栈
3. 判断索引值是右括号则从栈顶弹出元素匹配
4. 如果索引值右括号和栈顶元素括号成对，则继续遍历，否则返回false
5. 最后若栈中为空，则为有效括号，否则为无效括号

```java
    public static boolean isValid(String s) {
        HashMap<Character, Character> mappings = new HashMap<Character, Character>(){{
            put(')','('); put('}','{'); put(']','[');
        }};
        Stack<Character> stack = new Stack<>();
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if(mappings.containsKey(c)) {
                //判断元素是右扩展，则从栈顶弹出元素来匹配
                char topElement = stack.empty() ? '#' : stack.pop();
                if(topElement != mappings.get(c)) {
                    return false;
                }
            } else {
                //左括号则将元素压栈
                stack.push(c);
            }
        }
        //空栈代表括号完全匹配
        return stack.isEmpty();
    }
```