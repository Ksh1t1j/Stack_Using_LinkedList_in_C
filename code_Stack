#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>
struct ListNode{
    struct NumOp* record;
    struct ListNode* next;
};
struct NumOp{
    char type;
    double num;
    char op;
};

struct ListNode* CreateStack(){
    struct ListNode* n;
    n= (struct ListNode*)malloc(sizeof(struct ListNode));
    return(n);
}
int IsEmpty(struct ListNode* S){
    if(S==NULL){
        return 1;
    }
    else{
        return 0;
    }
}
void Push(struct ListNode** S, struct NumOp* key){
    struct ListNode* n;
    n=CreateStack();
    if(n!=NULL){
        n->record =key;
        n->next=*S;
        *S=n;
        printf("$\n");
    }
}
struct NumOp* Top(struct ListNode* S){
    return S->record;
}
struct NumOp* Pop(struct ListNode** S){
    struct ListNode* r;
    struct NumOp* i;
    i=(*S)->record;
    r=*S;
    *S=r->next;
    free(r);
    return i;
}
int main() {
    int q;
    struct ListNode* S = NULL;
    scanf("%d\n",&q);
    int i;
    for (i=0;i<q;i++){
        int queryType;
        scanf("%d", &queryType);
        struct NumOp* j = (struct NumOp*) malloc(sizeof(struct NumOp));
        if(queryType == 1){
            double num;
            scanf("%lf", &num);
            if(num>=1 && num<=100){
                j->type='n';
                j->num=num;
                j->op='\0';
                Push(&S,j);
            }
        }
        else if(queryType == 2){
            char op;
            scanf(" %c", &op);
            if (op=='+'||op=='/'||op=='*'||op=='-'){
                j->type='o';
                j->num=0;
                j->op=op;
                Push(&S,j);
            }
        }
        else if(queryType == 3){
            if(IsEmpty(S)==1)
                printf("error\n");
            else{
                struct NumOp* r=Top(S);
                if(r->type=='n')
                    printf("%lf\n",r->num);
                else if (r->type=='o')
                    printf("%c\n",r->op);
            }
        }
        else if(queryType == 4){
            int c=IsEmpty(S);
            if(c==0){
                printf("False\n");
            }
            else
                printf("True\n");
        }
        else if(queryType == 5){
            if(IsEmpty(S)==1)
                printf("error\n");
            else{
                struct NumOp* r=Pop(&S);
                if(r->type=='n')
                    printf("%lf\n",r->num);
                else if (r->type=='o')
                    printf("%c\n",r->op);
            }
        }
    }
    return 0;
}
