# 结构体排序

​	结构体排序可以用多种排序算法进行。在这里提供一个以冒泡排序实现的结构体排序的例子。

``` c
#include <stdio.h>

struct this_struct {
    int word1;
    int word2;
    char word3;
    double word4;
};

int main() {
  //创建结构体数组
    struct this_struct struct_array[114514];
  //结构体信息读入
    int i, j;
    int num;
    scanf("%d", &num);
    for (i = 0; i < num; i++) {
        scanf("%d%d%c%lf", &struct_array[i].word1, &struct_array[i].word2,
         &struct_array[i].word3, &struct_array[i].word4);
    }
  //第一个关键字的排序
    for (i = 0; i < num; i++) {
        for (j = 0; j < num - i - 1; j++) {
            if (struct_array[j].word1 > struct_array[j + 1].word1) {
                struct this_struct temp = struct_array[j];
                struct_array[j] = struct_array[j + 1];
                struct_array[j + 1] = temp;
            }
        }
    }
  //第二个关键字的排序
    for (i = 0; i < num; i++) {
        for (j = 0; j < num - i - 1; j++) {
            if (struct_array[j].word1 != struct_array[j + 1].word1) {
                continue;
            }
            if (struct_array[j].word2 > struct_array[j + 1].word2) {
                struct this_struct temp = struct_array[j];
                struct_array[j] = struct_array[j + 1];
                struct_array[j + 1] = temp;
            }
        }
    }
  //输出，程序结束
    for (i = 0; i < num; i++) {
        printf("%d %d %c %lf\n", struct_array[i].word1, struct_array[i].word2,
         struct_array[i].word3, struct_array[i].word4);
    }
    return 0;
}
```

