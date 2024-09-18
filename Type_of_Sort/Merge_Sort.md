```
Merge Sort
// Hàm dùng để thêm lần lượt các phần tử ở mảng K ( mảng K gồm 2 mảng con đã được sắp xếp theo thứ tự tăng dần ) vào mảng X
--> Mảng X là mảng sau khi đã được sắp xếp
MERGE(K, b, m, n, X){
  i = t = b;  // gán i = t = b ( t là vị trí bắt đầu mảng X, b là vị trí bắt đầu mảng K ( tức mảng con 1 )
  j = m + 1;  // m là vị trí kết thúc mảng con 1 ( của mảng K ), m + 1 là vị trí bắt đầu mảng con 2 ( của mảng K )
  while ( i <= m ) && ( j <= n ){ // chừng nào 2 mảng con phần còn phần tử 
    if ( K[i] < K[j] ) // so sánh để chọn được phần tử nhỏ hơn
      X[t++] = K[i++];
    else 
      X[t++] = K[j++];
  // Xét trường hợp 1 trong 2 mảng con hết phần tử trước
  if ( i > m ){ // mảng 1 hết phần tử trước
    for ( ; j <= n; )
      X[t++] = K[j++];
  }
  else{ // mảng 2 hết phần tử trước
    for( ; i <= m; )
      X[t++] = K[i++];
  }
}

// Hàm MPASS sẽ liên tiếp gọi hàm MERGE để hòa nhập các cặp mạch có độ dài L dọc theo độ dài của mảng
MPASS(K, X, n, h){ // h là độ dài mạch
  i = 0;
  while ( i + 2*h <= n ){ // hòa nhập cặp mạch có độ dài h
    MERGE(K, i, i + h - 1; i + 2 * h - 1, X);
    i = i + 2 * h;
  }
  if ( i + h < n ) // hòa nhập cặp mạch còn lại với tổng độ dài < 2*h
    MERGE(K, i, i + h - 1, n - 1, X);
  else{ // trường hợp chỉ còn 1 mạch
    for ( ; i < n; i ++ )
      X[i] = K[i];
  }

  // hàm Straight_MSORT sẽ liên tiếp tăng gấp đôi độ dài mạch từ L = 1 cho đến khi L >= n thì dừng. Ứng với mỗi giá trị của độ dài mạch L sẽ gọi hàm MPASS
  STRAIGHT_MSORT(K, n){
    h = 1;
    while( h < n ){
      MPASS(K, X, n, h);
      h = h * 2;
      MPASS(X, K, n, h);
      h = h*2;
  }
  ```
  ![photo_2024-09-18_18-38-37](https://github.com/user-attachments/assets/e253a160-7cff-4848-b408-c4d79d2a2baf)
