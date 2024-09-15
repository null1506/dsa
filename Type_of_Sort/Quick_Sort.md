```
Quick Sort
Giải thuật 1: Chọn a[(left + right)/2] làm chốt
// sắp xếp theo thứ tự tăng dần
QuickSort(a,left,right){
x = a[(left + right)/2];
i = left;
j = right;
do {
	while (a[i] < x)
		i ++;
	while (a[j] > x)
		j --;
	if (i <= j){
		swap(a[i], a[j]);
		tmp = a[i];
            	a[i] = a[j];
            	a[j] = tmp;
		i ++; // qua phần tử kế tiếp
		j --; // qua phần tử đứng trước
	}
}while (i <= j);
if (left < j)	// phân đoạn bên trái
	QuickSort(a, left, j);
if (right > i) // phân đoạn bên phải
	QuickSort(a, i, right);

} 
// sắp xếp theo thứ tự giảm dần
QuickSort(a,left,right){
x = a[(left + right)/2];
i = left;
j = right;
do {
	while (a[i] > x)
		i ++;
	while (a[j] < x)
		j --;
	if (i <= j){
		swap(a[i], a[j]);
		tmp = a[i];
            	a[i] = a[j];
            	a[j] = tmp;
		i ++; // qua phần tử kế tiếp
		j --; // qua phần tử đứng trước
	}
}while (i <= j);
if (left < j)	// phân đoạn bên trái
	QuickSort(a, left, j);
if (right > i) // phân đoạn bên phải
	QuickSort(a, i, right);

} 
```
![photo_2024-09-14_17-20-05](https://github.com/user-attachments/assets/a3780841-bfb3-44f5-9a1b-e4dabb749c5a)

```
Giải thuật 2: Chọn phần tử đầu tiên làm chốt
// sắp xếp theo thứ tự tăng dần
Partition(K, t, p, j){
	//chốt là K[t]
	i = t + 1;
	j = p;
	do {
		while ((i <= j) && (K[i] < K[t]))
			i = i + 1;
		while ((i <= j) && (K[j] > K[t]))
			j = j – 1;
		if (i < j){
			swap(K[i], K[j]); // đổi chỗ K[i] và K[j]
			i = i + 1;
			j = j – 1;
		}
	}while (i <= j);
	swap(K[t], K[j]); // đổi chỗ K[t](chốt) và K[j]
}

QuickSort(K, t, p){
	if (t < p){
		Partition(K, t, p, j);
		QuickSort(K, t, j – 1);
		QuickSort(K, j + 1, p);
	}
}

// sắp xếp theo thứ tự giảm dần
Partition(K, t, p, j){
	//chốt là K[t]
	i = t + 1;
	j = p;
	do {
		while ((i <= j) && (K[i] > K[t]))
			i = i + 1;
		while ((i <= j) && (K[j] < K[t]))
			j = j – 1;
		if (i < j){
			swap(K[i], K[j]); // đổi chỗ K[i] và K[j]
			i = i + 1;
			j = j – 1;
		}
	}while (i <= j);
	swap(K[t], K[j]); // đổi chỗ K[t](chốt) và K[j]
}

QuickSort(K, t, p){
	if (t < p){
		Partition(K, t, p, j);
		QuickSort(K, t, j – 1);
		QuickSort(K, j + 1, p);
	}
}
```
![photo_2024-09-14_17-20-02](https://github.com/user-attachments/assets/35476f44-db50-4967-aa6d-16cc2a0052a1)

