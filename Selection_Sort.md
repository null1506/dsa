```
// sắp xếp tăng dần
Select_Sort(K[], n){
	for (i = 0; i < n – 1; i ++){
		m = i;
		for( j = i + 1; j < n; j++){
			if (K[j] < K[m])
				m = j;
		}
		if (i < m){
				x = K[i];
				K[i] = K[m];
				K[m] = x;
		}
	}
}

// sắp xếp giảm dần
Select_Sort(K, n){
	for (i = 0; i < n – 1; i ++){
		m = i;
		for( j = i + 1; j < n; j++){
			if (K[j] > K[m])
				m = j;
		}
		if (i < m){
				x = K[i];
				K[i] = K[m];
				K[m] = x;
		}
	}
}

Ví dụ: Sắp xếp giảm dần của dãy
42  23  65  11  87  36  94  50  79  68
Bắt đầu với i = 0
i       x
42  23  65  11  87  36  94  50  79  68
Khi cho j chạy từ 1, tức K[j] = 23, thì khi chạy đến j = 2 xuất hiện phần tử K[j] = 65 > K[m] = K[0] = 42
--> Gán m = j = 2, tức lúc này phần tử lớn nhất là K[2] = 65
--> i = 0 < m = 2 --> hoán đổi 42 cho 65
Ta được dãy
i               x
65  23  42  11  87  36  94  50  79  68
Vừa nãy j đã chạy đến 2, tiếp tục cho j chạy thì đến j = 4 xuất hiện phần tử K[j] = 87 > K[m] = K[2] = 65
--> Gán m = j = 4, tức lúc này phần tử lớn nhất là K[4] = 87
--> i = 0 < m = 4 --> hoán đổi 65 cho 87
Ta được dãy
i                       x
87  23  42  11  65  36  94  50  79  68
Vừa nãy j đã chạy đến 4, tiếp tục cho j chạy thì đến j = 6 xuất hiện phần tử K[j] = 94 > K[m] = K[4] = 87
--> Gán m = j = 6, tức lúc này phần tử lớn nhất là K[6] = 94
--> i = 0 < m = 6 --> hoán đổi 87 cho 94
Ta được dãy
i
94  23  42  11  65  36  87  50  79  68
Vừa nãy j đã chạy đến 6, tiếp tục cho j chạy đến n - 1 = 9 thì ko còn xuất hiện phần tử nào khiến cho K[j] > K[m]
Kết thúc vòng lặp i = 0
-------
Bắt đầu với i = 1
    i   x
94  23  42  11  65  36  87  50  79  69
Khi cho j chạy từ 2, tức K[j] = 42, xuất hiện phần tử K[j] = 42 > K[m] = K[1] = 23
--> Gán m = j = 42, tức lúc này phần tử lớn nhất là K[2] = 42
--> i = 1 < m = 2 --> hoán đổi 23 cho 42
Ta được dãy
    i           x
94  42  23  11  65  36  87  50  79  69
Vừa nãy j đã chạy đến 2, tiếp tục cho j chạy thì đến j = 4 xuất hiện phần tử K[j] = 65 > K[m] = K[2] = 42
--> Gán m = j = 4, tức lúc này phần tử lớn nhất là K[4] = 65
--> i = 1 < m = 4 --> hoán đổi 42 cho 65
Ta được dãy
    i                   x
94  65  23  11  42  36  87  50  79  69
Vừa nãy j đã chạy đến 4, tiếp tục cho j chạy thì đến j = 6 xuất hiện phần tử K[j] = 87 > K[m] = K[4] = 65
--> Gán m = j = 6, tức lúc này phần tử lớn nhất là K[6] = 87
--> i = 1 < m = 6 --> hoán đổi 65 cho 87
Ta được dãy
    i                   
94  87  23  11  42  36  65  50  79  69
Vừa nãy j đã chạy đến 6, tiếp tục cho j chạy đến n - 1 = 9 thì ko còn xuất hiện phần tử nào khiến cho K[j] > K[m]
Kết thúc vòng lặp i = 1
-------
Bắt đầu với i = 2
        i       x
94  87  23  11  42  36  65  50  79  69
        i               x
94  87  42  11  23  36  65  50  79  69
        i                       x
94  87  65  11  23  36  42  50  79  69
        i                       
94  87  79  11  23  36  42  50  65  69
-------
Bắt đầu với i = 3
            i   x                       
94  87  79  11  23  36  42  50  65  69
            i       x                
94  87  79  23  11  36  42  50  65  69
            i           x       
94  87  79  36  11  23  42  50  65  69
            i               x
94  87  79  42  11  23  36  50  65  69
            i                   x
94  87  79  50  11  23  36  42  65  69
            i                       x       
94  87  79  65  11  23  36  42  50  69
            i
94  87  79  69  11  23  36  42  50  65
------
Bắt đầu với i = 4
                i   x
94  87  79  69  11  23  36  42  50  65
                i       x
94  87  79  69  23  11  36  42  50  65
                i           x
94  87  79  69  36  11  23  42  50  65
                i               x
94  87  79  69  42  11  23  36  50  65
                i                   x
94  87  79  69  50  11  23  36  42  65
                i               
94  87  79  69  65  11  23  36  42  50
-------
Bắt đầu với  i = 5
                    i   x           
94  87  79  69  65  11  23  36  42  50
                    i       x       
94  87  79  69  65  23  11  36  42  50
                    i           x   
94  87  79  69  65  36  11  23  42  50
                    i               x
94  87  79  69  65  42  11  23  36  50
                    i               
94  87  79  69  65  50  11  23  36  42
-------
Bắt đầu với i = 6
                        i   x          
94  87  79  69  65  50  11  23  36  42
                        i       x        
94  87  79  69  65  50  23  11  36  42
                        i           x    
94  87  79  69  65  50  36  11  23  42
                        i               
94  87  79  69  65  50  42  11  23  36
------
Bắt đầu với i = 7
                            i   x            
94  87  79  69  65  50  42  11  23  36
                            i       x        
94  87  79  69  65  50  42  23  11  36
                            i               
94  87  79  69  65  50  42  36  11  23
--------
Bắt đầu với i = 8
                                i   x            
94  87  79  69  65  50  42  36  11  23
                                i               
94  87  79  69  65  50  42  36  23  11
Dừng
```
![photo_2024-09-14_17-19-55](https://github.com/user-attachments/assets/abd7a15b-074d-4427-8b1f-5822bc39f1d6)
![photo_2024-09-14_17-19-58](https://github.com/user-attachments/assets/d2fbb059-88e9-4dd4-b943-c46fe2a8f787)

