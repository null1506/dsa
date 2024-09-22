Trình bày (bằng ngôn ngữ tựa C) giải thuật tìm kiếm nhị phân. Đánh giá thời gian thực hiện giải thuật với dãy có n phần tử.
```
Binary_Search(K, left, right, x){  // K là mảng 
  if ( t > p )
    return -1; // ko tìm thấy
  else{
    g = (left + right)/2;
    if (x == K[g])
      return g;  // tìm thấy
    if (x < K[g])
      Binary_Search(K, left, g - 1, x); // tìm tiếp ở nửa trước
    else
      Binary_Search(K, g + 1, right, x); // tìm tiếp ở nửa sau
  }
}
```
      
