# 冒泡排序
```
* 时间复杂度
   * 最坏：O(N^2);
   * 最好：O(N);
   * 平均：O(N^2);
* 空间复杂度：O(1);
* 稳定性：稳定；
```
```c
void bubble_sort(int[] arr,int n)
{
  for(int i = 0;i < n;++i)
  {
    int flag = -1;
    for(int j = 0;j < n-i-1;++j)
    {
      if(arr[j] > arr[j+1])
      {
        int temp = arr[j];
        arr[j] = arr[j+1];
        arr[j+1] = temp;
        flag = 0;
      }
    }
    if(flag)
    {
      break;
    }
  }
}
```

# 插入排序
```
* 时间复杂度
   * 最坏：O(N^2);
   * 最好：O(N);
   * 平均：O(N^2);
* 空间复杂度：O(1);
* 稳定性：稳定；
```
```c
void insert_sort(int[] arr,int n)
{
  for(int i = 1;i < n;++i)
  {
    int temp = arr[i];
    for(int j = i - 1;j >= 0 && arr[j] > temp;--j)
    {
      arr[j+1] = arr[j]
    }
    arr[j+1] = temp;
  }
}
```

# 选择排序
```
* 时间复杂度
   * 最坏：O(N^2);
   * 最好：O(N^2);
   * 平均：O(N^2);
* 空间复杂度：O(1);
* 稳定性：不稳定；
```
```c
void slect_sort(int[] arr,int n)
{
  int min = 0;
  for(int i = 0;i < n;++i)
  {
    min = i;
    for(int j = i;j < n;++j)
    {
      if(arr[min] < arr[j])
      {
        min = j;
      }
    }
    if(i != min)
    {
      int temp = arr[i];
      arr[i] = arr[min];
      arr[min] = temp;
    }
  }
}
```
