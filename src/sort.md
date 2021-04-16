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
void bubble_sort(int arr[],int n)
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
void insert_sort(int arr[],int n)
{
  int i,j;
  for(i = 1;i < n;++i)
  {
    int temp = arr[i];
    for(j = i - 1;j >= 0 && arr[j] > temp;--j)
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
void slect_sort(int arr[],int n)
{
  int min = 0;
  for(int i = 0;i < n;++i)
  {
    min = i;
    for(int j = i;j < n;++j)
    {
      if(arr[min] > arr[j])
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

# 归并排序
```
* 时间复杂度
   * 最坏：O(nlogn);
   * 最好：O(nlogn);
   * 平均：O(nlogn);
* 空间复杂度：O(n);
* 稳定性：稳定；
```
```c
void merge_sort_rec(int arr[],int reg[],int start,int end)
{
  if(start >= end)
    return;
  int len = end - start;
  int mid = start + len/2;
  int start1 = start;
  int end1 = mid;
  int start2 = mid+1;
  int end2 = end;
  int k = start;
  
  merge_sort_rec(arr,reg,start1,end1);
  merge_sort_rec(arr,reg,start2,end2);
  while(start1 <= end1 && start2 <= end2)
    reg[k++] = (arr[start1] <= arr[start2] ? arr[start1++] : arr[start2++]);
    
  while(start1 <= end1)
    reg[k++] = arr[start1++];
  while(start2 <= end2)
    reg[k++] = arr[start2++];
    
  for(int i = start;i <= end;++i)
    arr[i] = reg[i];
    
}

void merge_sort(int arr[],const int len)
{
  int reg[len];
  merge_sort_rec(arr,reg,0,len-1);
}
```

# 快速排序
```
* 时间复杂度
   * 最坏：O(n^2);
   * 最好：O(nlogn);
   * 平均：O(nlogn);
* 空间复杂度：O(1);
* 稳定性：不稳定；
```
```c
int partation(int arr[],int p,int r)
{
  int pivot = arr[r];
  int k = p;
  for(int i = p;i <= r-1;++i)
  {
    if(arr[i] < pivot)
    {
      int temp = arr[k]
      arr[k] = arr[i];
      arr[i] = temp;
      k++;
    }
  }
  int temp = arr[k];
  arr[k] = arr[r];
  arr[r] = temp;
  
  return k;
}

void quick_sort_c(int arr[],int start,int end)
{
  if(start >= end)
  {
    return;
  }
  int q = partation(arr,start,end);
  quick_sort_c(arr,start,q-1);
  quick_sort_c(arr,q+1,end);
  
}

void quick_sort(int arr[],int len)
{
  quick_sort_c(arr,0,len-1);
}
```
