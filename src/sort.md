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
    for(int j = 0;j < n-i-1;++j)
    {
      if(arr[j] > arr[j+1])
      {
        int temp = arr[j];
        arr[j] = arr[j+1];
        arr[j+1] = temp;
      }
    }
  }
}
```
