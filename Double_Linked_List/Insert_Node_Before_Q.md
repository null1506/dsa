Trình bày (bằng ngôn ngữ tựa C) giải thuật bổ sung 1 nút mới có chứa dữ liệu X vào trước nút trỏ bởi Q trong danh 
sách móc nối 2 chiều với: Pdau trỏ vào phần tử đầu, Pcuoi trỏ vào phần tử cuối, mỗi nút có cấu trúc như sau:
```
P_L --> Trỏ vào phần tử đứng trước nó ( tức đứng bên trái )
data --> Chứa dữ liệu X
P_R --> Trỏ vào phần tử đứng sau nó ( tức đứng bên phải )

Ngôn ngữ tựa C

DOUBLE_IN (Pdau, Pcuoi, Q, X){
  P = malloc(); // Tạo nút mới P->DATA = X;
  P->P_L = P->P_R = NULL;
  if(Pcuoi == NULL) // Trường hợp danh sách rỗng
    Pdau = Pcuoi = P; 
  else {
    if(Q == Pdau){ // Q trỏ tới nút đầu
      P->P_R = Q;
      Q->P_L = P;
      Pdau = P;
    }
    else { // Bổ sung vào giữa    Vì ta đang bổ sung một nút đứng trước Q --> ko có trường hợp bổ sung vào cuối list
      P->P_L = Q->P_L;            /* P->P_L = Q->P_L;
      P->P_R = Q;                    P->P_R = Q;
      Q->P_L = P;                    Q->P_L->P_R = P;
      P->P_L->P_R = P;               Q->P_L = P; */
    }
  }
}
```
