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

![photo_2024-09-14_17-19-43](https://hackmd.io/_uploads/HJFWQ9ETR.jpg)
![photo_2024-09-14_17-19-48](https://hackmd.io/_uploads/SJ7Mm946R.jpg)
