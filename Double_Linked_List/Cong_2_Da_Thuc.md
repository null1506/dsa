Trình bày (bằng ngôn ngữ tựa C) giải thuật cộng 2 đa thức: C = A + B. Các phần tử trong mỗi đa thức có cấu trúc như sau:
```
HSO --> Ghi hệ số
MU --> Ghi số mũ
NEXT --> Ghi địa chỉ đến phần tử tiếp theo

/* Hàm này thực hiện việc tạo 1 nút mới, đưa vào thành phần HSO của nút này giá trị H, 
đưa vào thành phần MU giá trị M và gắn nút mới đó vào sau nút trỏ bởi D.  */

ATTACH(H, M, D){
  P = malloc();
  P->HSO = H;
  P->MU = M;
  if(C == NULL) // Chưa có đuôi
    C = P;
  else // Đã có đuôi
    D->NEXT = P;
  D = P; // Nút mới này trở thành đuôi
}

/* Hàm cộng 2 đa thức */

PADD(A, B, C){
  P = A;
  Q = B;
  C = NULL;
  while(P != NULL && Q != NULL){ // Cả 2 đa thức vẫn còn phần tử
    if(P->MU == Q->MU){
      H = P->HSO + Q->HSO; 
      if(H != 0)
        ATTACH(H, P->MU, D);
      P = P->NEXT;
      Q = Q->NEXT;
    }
    else{
      if(P->MU > Q->MU){
        ATTACH(P->HSO, P->MU, D); 
        P = P->NEXT; 
      }
      else{
        ATTACH(Q->HSO, Q->MU, D); 
        Q = Q->NEXT;
      }
    }
}

  if(Q == NULL){ // Danh sách ứng với B(x) đã hết
    while(P != NULL){
      ATTACH(P->HSO, P->MU, D); 
      P = P->NEXT;
    }
  }
  else{ // Danh sách ứng với A(x) đã hết
    while(Q != NULL){
      ATTACH(Q->HSO, Q->MU, D); 
      Q = Q->NEXT;
    }
  }
  D->NEXT = NULL; // Kết thúc danh sách C
}
```
