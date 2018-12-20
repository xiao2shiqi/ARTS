## Algorithm
桶排序：<br>
有一份考试分数结果[5,3,5,2,8]<br>
按照考试成绩排序，并且打印出来
```java
        //0-10分的桶
        int[] bucket = new int[10];
        //考试分数
        int[] score = new int[]{5,3,5,2,8,4,7,6};
        System.out.println("一个乱七八糟的考试成绩=========" + Arrays.toString(score));
        for (int i = 0; i < score.length; i++) {
            int bucketIndex = score[i];
            //根据分数结果，在成绩桶上进行++
            bucket[bucketIndex - 1] = bucket[bucketIndex - 1] + 1;
        }
        System.out.println("升序分割线=====================");
        //结果升序
        for (int i = 0; i < bucket.length; i++) {
            int people = bucket[i];
            if(people != 0){
                //按照人数打印
                for(int j = 0; j < people; j++){
                    System.out.println("test score : " + (i + 1));
                }
            }
        }
        System.out.println("降序分割线=====================");
        //结果降序
        for(int i = bucket.length - 1; i > 0; i--){
            int people = bucket[i];
            if(people != 0){
                for(int j = 0; j < people; j++){
                    System.out.println("test score : " + (i + 1));
                }
            }
        }
```