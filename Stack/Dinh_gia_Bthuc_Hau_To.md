Trình bày (bằng ngôn ngữ tựa C) giải thuật định giá biểu thức hậu tố bằng cách dùng STACK
Giải thuật này sử dụng một ngăn xếp S, với top được trỏ bởi T, ban đầu T = -1
```
/* bổ sung phần tử X vào ngăn xếp lưu trữ bởi mảng S có n phần tử.
T là biến trỏ đến đỉnh ngăn xếp */
PUSH(S, T, X){
  if (T > n - 1)
    printf("Ngăn xếp tràn);
  else{
    T = T + 1; // T trỏ vào vị trí mới
    S[T] = X;  // Bổ sung X vào vị trí mới T
  }
}

// Hàm dùng để đẩy phần tử Top của Stack ra ngoài
POP(S, T){
  if (T < 0)
    printf("Ngăn xếp cạn");
  else{
    T = T - 1; // T trỏ vào vị trí mới
    return S[T + 1]; // đưa phần tử bị loại ra
  }
}

// Hàm định giá biểu thức
DINH_GIA_BIEU_THUC(){
  T = -1;
  do{
    Đọc phần tử tiếp theo X trong biểu thức
    if ( X là toán hạng )
      PUSH(S, T, X);
    else{  // X là toán tử
      Y = POP(S, T);
      Z = POP(S, T);
      W = Z X Y;  // tác động phép toán X vào Y và Z rồi gán kết quả cho W
      PUSH(S, T, W);
    ]
  }while( Chưa gặp dấu kết thúc biểu thức );
  R = POP(S, T);
  printf(R);
}
```
