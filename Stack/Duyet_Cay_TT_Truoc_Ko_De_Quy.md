Trình bày (bằng ngôn ngữ tựa C) giải thuật duyệt cây theo thứ tự trước bằng giải thuật 
không đệ qui có sử dụng STACK. Mỗi nút trên cây có cấu trúc như sau: 
P_R --> Trỏ vào phần tử đứng trước nó ( đứng bên trái )
data --> Chứa dữ liệu X
P_L --> Trỏ vào phần tử đứng sau nó ( đứng bên phải )
```
T là con trỏ trỏ tới gốc cây đã cho, S là một ngăn xếp (được cài đặt bằng mảng) với biến trỏ TOP trỏ tới đỉnh.
Con trỏ P được dùng để trỏ tới nút hiện đang được xem xét. Có sử dụng các hàm PUSH, POP
PUSH (S, T, X){
  if ( T > n - 1 )
    printf("Ngăn xếp tràn");
  else{
    T = T + 1;
    S[T] = X;
  }
}

POP(S, T){
  if ( T < 0 )
    printf("Ngăn xếp cạn");
  else{
    T = T - 1;
    return S[T + 1];
  }
}

TT_TRUOC_S (T){
  if( T == NULL ){
    printf("Cây rỗng");
    return;
  }
  else{
    TOP = -1;
    PUSH(S, TOP, T);
  }
  while ( TOP > -1 ){ // Thực hiện duyệt
    P = POP(S, TOP);
    while ( P != NULL ){ // thăm nút cha rồi xuống con trái
      printf(P -> data);  // thăm nút cha
      if(P -> P_R != NULL)
        PUSH(S, TOP, P -> P_R); // lưu trữ địa chỉ gốc của con phải để lát nữa duyệt xong trái thì sẽ đến phải
      P = P -> P_L; // xuống nút con trái
    }
  }
}
```  
  
