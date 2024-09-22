 Trình bày (bằng ngôn ngữ tựa C) giải thuật duyệt cây theo thứ tự giữa bằng giải thuật không đệ qui có sử dụng STACK. 
 Mỗi nút trên cây có cấu trúc như sau:
 ```
 P_L --> Trỏ vào cây con trái
 data --> Chứa dữ liệu X
 P_R --> Trỏ vào cây con phải

PUSH(S, T, X){
  if(T > n - 1)
    printf("Ngăn xếp tràn");
  else{
    T = T + 1;
    S[T] = X;
  }

POP(S, T){
  if ( T < 0 )
    printf("Ngăn xếp cạn");
  else{
    T = T - 1;
    return S[T + 1];
  }
}

/*  T là con trỏ trỏ tới gốc cây đã cho, S là một ngăn xếp (được cài đặt bằng mảng) với biến trỏ TOP trỏ tới đỉnh. 
Con trỏ P được dùng để trỏ tới nút hiện đang được xem xét. Có sử dụng các hàm PUSH, POP  */
TT_GIUA_S (T){
  if ( T == NULL){
    printf("Cây rỗng");
    return;
  }
  else{
    TOP = -1;
    P = T;
  }
  while (TOP > -1 || P != NULL){
    while ( P != NULL ){
      PUSH(S, TOP, P);
      P = P -> P_L;
    }
    P = POP(S, TOP);
    printf(P -> data);
    P = P -> P_R;
  }
}
``` 
