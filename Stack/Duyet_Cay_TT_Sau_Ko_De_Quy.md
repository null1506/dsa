Trình bày (bằng ngôn ngữ tựa C) giải thuật duyệt cây theo thứ tự sau bằng giải thuật không đệ qui có sử dụng STACK. 
Mỗi nút trên cây có cấu trúc như sau:  
P_L --> Trỏ tới cây con trái
data --> Chứa dữ liệu X
P_R --> Trỏ tới cây con phải
```
/*  trong phép duyệt này, nút gốc chỉ được thăm sau khi đã duyệt xong 2 con của nó. Như vậy, 
chỉ từ khi con phải đi lên gặp gốc thì gốc mới được thăm, chứ k phải ở lần gặp gốc khi từ con trái đi lên. 
Do đó, để phân biệt, người ta đưa thêm dấu âm vào địa chỉ ( địa chỉ âm) để đánh dấu cho lần đi lên từ con phải  */

TT_SAU_S (T){
  if ( T == NULL ){
    printf("Cây rỗng");
    return;
  }
  else{
    TOP = -1;
    P = T;
  }
  while(1){
    while( P != NULL ){  // lưu địa chỉ gốc và xuống con trái để lưu con trái
      PUSH(S, TOP, P);
      P = P -> P_L;
    }
    while ( S[TOP] < 0 ){ 
      P = POP(S, TOP);
      printf(P -> data);
      if (TOP == 0)
        return;
    }
    P = S[TOP] -> P_R;  // xuống con phải để đánh dấu
    S[TOP] = -S[TOP];
  }
}
```
