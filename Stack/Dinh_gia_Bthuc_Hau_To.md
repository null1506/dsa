Trình bày (bằng ngôn ngữ tựa C) giải thuật định giá biểu thức hậu tố bằng cách dùng STACK
Giải thuật này sử dụng một ngăn xếp S, với top được trỏ bởi T, ban đầu T = -1

// Hàm dùng để thêm phần tử X vào Stack
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
