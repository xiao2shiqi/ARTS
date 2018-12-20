## Algorithm
冒泡排序是一种简单直观的排序算法

算法步骤：  
1 循环遍历数组，比较数组当前元素和下一个元素，如果第一个元素比第二个大，就交换他们   
2 对所有元素做同样的工作，遍历完所有元素后，最后的元素就是最大数  

```Java
    public static void bubbleSort(int[] intArray){
        int temp;
        int len = intArray.length;
        for (int i = 0; i < len; i++) {
            for(int j = 1; j < len - i; j++) {
                if(intArray[j - 1] > intArray[j]){
                    temp = intArray[j - 1];
                    intArray[j - 1] = intArray[j];
                    intArray[j] = temp;
                }
            }
        }
    }
```