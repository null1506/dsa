Trình bày (bằng ngôn ngữ tựa C) giải thuật loại bỏ 1 nút trỏ bởi Q trong danh sách móc nối 2 chiều với:
Pdau trỏ vào phần tử đầu, Pcuoi trỏ vào phần tử cuối, mỗi nút có cấu trúc như sau:
```
P_L --> Trỏ vào phần tử đứng trước nó ( đứng bên trái nó )
data --> Chứa dữ liệu X
P_R --> Trỏ vào phần tử đứng sau đó ( đứng bên phải nó )

DOUBLE_DEL(Pdau, Pcuoi, Q){
  if(Pcuoi == NULL)  // Trường hợp danh sách rỗng
    printf(“Danh sách rỗng”);
  else{  // Trường hợp danh sách ko rỗng
    if(Pdau == Pcuoi) // Danh sách chỉ có 1 nút và Q trỏ tới nút đó
      Pdau = Pcuoi = NULL;
    else{
      if(Q == Pdau){  // Nút đầu bị loại
        Pdau = Pdau->P_R; 
        Pdau->P_L = NULL;
       }
      else{
        if(Q == Pcuoi){ // Nút cuối bị loại
          Pcuoi = Pcuoi->P_L; 
          Pcuoi->P_R = NULL;
        }
        else{ // Loại bỏ nút bên trong
          Q->P_L->P_R = Q->P_R; 
          Q->P_R->P_L = Q->P_L;
        }
      }
    }
    free(Q);
  }
}
```
