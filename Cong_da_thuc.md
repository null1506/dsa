```
#include<stdio.h>
#include<math.h>
int main(){
    printf("Hello world");
}*/


/*
typedef struct Element{
    int coef; // hệ số khác 0
    int exp; //số mũ
}Element;

typedef struct _Node{
    Element value;
    struct _Node *next;
}Node;

//Khởi tạo danh sách
void init(Node *head){
    head = NULL;
}
// tạo node
Node *createNode(Element el){
    Node *p = (Node *)malloc(sizeof(Node));
	if (p == NULL)
	{
		printf("Error in mem allocation\n");
		exit(1);
	}
	p->value = el;
	p->next = NULL;
	return p;
}
//chèn node
void insertNode(Node *head, Element el){
    Node *p = createNode(el);
    if (head == NULL){ //ds rỗng
        head = p;
        return;
    }
    Node *r = head;
    Node *prev = NULL;
    while (r != NULL && r->value.exp <= el.exp){
        if (r->value.exp == el.exp) //phần tử cần chèn đã có (tức mũ đó đã có, chỉ cập nhật giá trị hệ số)
        {
            r->value = el;
            break;
        }
        prev = r; //biến lưu giá trị trước đó của r
        r = r->next;
    }

    if (r == NULL){ // thêm phần tử vào cuối
            prev->next = p;
    }
    else if(r->value.exp != el.exp){
        
        p->next = r;
        if (prev == NULL){ //thêm phần tử vào đầu
            head = p;
        }
        else
            prev->next = p;
        
    }
}

//hàm xuất danh sách
void export(Node *head){
    Node *p = head;
    while (p != NULL){
        printf("%d*x^%d",p->value.coef,p->value.exp);
        if (p->next != NULL)
            printf(" + ");
        p = p->next;
    }
}
int main(){
    Node *head;
    init(head);
    Element e2, e5;
    e2.exp = 2;
    e2.coef = 15;
    e5.exp = 5;
    e5.coef = 55;
   
    insertNode(head, e2);
    //insertNode(head, e5);
    export(head);
}
```
