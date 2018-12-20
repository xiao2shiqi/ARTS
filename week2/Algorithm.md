## Algorithm
上周写了一个简单的冒泡排序<br>
这期加一个小优化通过flag标记位，来判断是否对数组进行再次冒泡排序<br>简化了代码和增加了可读性
```java
    public void bulleSortFlag(int[] a){
        int temp;
        int len = a.length
        boolean flag = true;
        while(flag){
            flag = false;       //未发生排序，则不进入循环
            for(int j = 1; j < len; j++){
                if(a[j - 1] > a[j]){
                    temp = a[j];
                    a[j - 1] = a[j];        //交换
                    a[j] = temp;
                    flag = true;
                }
            }
        }
    }
```