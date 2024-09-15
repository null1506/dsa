```
Bubble Sort
// Sắp xếp tăng dần
  Bubble_Sort(K,n){
  	for (i = 0; i < n – 1; i ++){
  		for ( j = n – 1; j > i; j --){
  			if (K[j] < K[j – 1]){
  				x = K[j];
  				K[j] = K[j – 1];
  				K[j – 1] = x;
  			}
  		}
  	}
   }
//Sắp xếp giảm dần
Bubble Sort
  Bubble_Sort(K,n){
  	for (i = 0; i < n – 1; i ++){
  		for ( j = n – 1; j > i; j --){
  			if (K[j] > K[j – 1]){
  				x = K[j];
  				K[j] = K[j – 1];
  				K[j – 1] = x;
  			}
  		}



  	}
  }
```
![photo_2024-09-14_17-19-43](https://github.com/user-attachments/assets/44fa43af-577d-4009-af30-7d463ada90cb)

![photo_2024-09-14_17-19-48](https://github.com/user-attachments/assets/0fe49d37-fd01-4a4d-95d2-61e5fcca1e12)

