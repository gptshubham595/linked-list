#include<stdlib.h>
#include<stdbool.h>
struct node{
int data;
struct node *link;
};
struct node *root=NULL;
//====================
//Append-add end,Add begin,add after,del first node,del spec node,display,length,rev list,swap node,sort element
void delfirstnode(){
printf("\nDeleted %d\n",root->data);
root=root->link;
}
void delspecnode(int pos){
printf("\nDeleted ");
struct node *t=(struct node *)malloc(sizeof(struct node));
t=root;int c=0;
while(t!=NULL){
        if(c==pos-2)break; c++;
        t=t->link;}
        struct node *t1=t->link;
        t->link=t1->link;
}
void delspecdata(int d){
struct node *t=(struct node *)malloc(sizeof(struct node));
struct node *p=root;
t=root;int c=0,i=0;
while(t!=NULL){
        c++;
        if(t->data==d){delspecnode(c);break;}
        t=t->link;}
        printf("c=%d",c);


}
void addbegin(){
struct node *t=(struct node *)malloc(sizeof(struct  node));
printf("\nenter data at place at begin:");
scanf("%d",&t->data);t->link=NULL;
if(root==NULL){root=t;}
else{
t->link=root;
root=t;
}
}
//===================
void append()
{
struct node *temp=(struct node *)malloc(sizeof(struct node));
scanf("%d",&temp->data);
temp->link=NULL;
if(root==NULL){root=temp;}
else{
    struct node *p;
    p=root;
    while(p->link!=NULL){p=p->link;}
    p->link=temp;
}
}
//====================
void addat(int val,int pos)
{struct node *newval=(struct node *)malloc(sizeof(struct node));
newval->data=val;
newval->link=NULL;
struct node *t=(struct node *)malloc(sizeof(struct node));
t=root;int i=0;
while(i<pos-2){i++;t=t->link;}
struct node *t2=t->link;
newval->link=t2;
t->link=newval;

}
//====================
void display(){
struct node *p;p=root; int c=0;
while(p!=NULL){printf(" %d,",p->data);p=p->link; }
}
int length(){
struct node *p;p=root; int c=0;
while(p!=NULL){c++;p=p->link; }
return c;
}
void search(int x){
struct node *p;p=root;int pos=0,ch=0;
while(p!=NULL){pos++;if(p->data==x){ch=1;break;} p=p->link; }
if(ch){printf("\nfound %d at location %d\n",x,pos);}
else{printf("\nSorry\n");}
}
//====================
int main(){
    //printf("\nlength=%d",length());
append();
append();
append();
printf("\nlength=%d",length());
printf("\ntraverse:");
display();
printf("\nEnter no. to search:");
int n;
scanf("%d",&n);
search(n);
addbegin();
display();
delfirstnode();
display();
printf("\nlength=%d",length());
printf("\n Removing 2:");

delspecnode(2);
printf("\n ");
display();
printf("\n Current:");
display();
printf("\n Inserting 50 at 2nd:\n");
addat(50,2);
printf("\n ");
display();
return 0;}
//======================

