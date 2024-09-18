```
Heap Sort
// Hàm dùng để vun đống với r là gốc (ta chọn) và n là số phần tử của cây
ADJUST(r, n){
  v = K[r]; // v nhận giá trị của nút gốc
  while ( r * 2 <= n - 2 ){
    c = r * 2 + 1; // xét nút con trái của r
    if (( c < n - 1 ) && (K[c] < K[c + 1])) // nút con trái bé hơn nút con phải
      c = c + 1;      // gán c là nút có giá trị max
    if ( K[c] < v ) // nút con trái và phải đều ko lớn hơn nút gốc
      break; // dừng do nút gốc giữ nguyên
    K[r] = K[c]; // Chuyển nút con c lên nút cha r
    r = c; // đi xuống xét nút con c
  }
  K[r] = v; // Xét nút con c ( do gán r = c ), gán giá trị v ( tức giá trị nút gốc trước khi hoán đổi ) cho nút con c và tiếp tục xét
}

//Hàm vun đống tổng ( vun từ phần tử i = floor((n - 2) / 2) )
for ( i = (n - 2) / 2; i <= 0; i --)
  ADJUST(i, n); 

Tổng hợp lại, sắp xếp kiểu vun đống có 2 giai đoạn:
1 - Giai đoạn tạo đống ban đầu
2 - Giai đoạn sắp xếp, gồm: ----- Đổi chỗ ( đổi nút con thành nút cha )
                            ----- Vun đống ( sau khi đổi thì vun đống lại )
Heap_Sort(K, n){
  // 1 - Tạo đống ban đầu
  for ( i = (n - 2) / 2; i <= 0; i --)
      ADJUST(i, n);
  // 2 - Sắp xếp gồm: đổi chỗ và vun đống
  for ( i = n - 1; i > 0; i -- ){ // Sau khi tìm được gốc ( túc phần tử có giá trị lớn nhất ) thì đổi chỗ cho phần tử ở cuối mảng
    x = K[0];
    K[0] = K[i];
    K[i] = x;
    ADJUST(0, i);
  }
}
```
![photo_2024-09-18_18-06-04](https://github.com/user-attachments/assets/2ce2379e-0716-456c-93c4-955f65a163bb)
![photo_2024-09-18_18-05-54](https://github.com/user-attachments/assets/3e3b49b8-913d-462e-9f7b-6f02957295cc)
