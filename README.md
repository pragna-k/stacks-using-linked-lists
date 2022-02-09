# stacks-using-linked-lists
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *next;
};
struct node *top=NULL;
void push(int k)
{
    struct node *temp;
    temp=(struct node*)malloc(sizeof(struct node));
    temp->data=k;
    temp->next=NULL;
    if (top==NULL)
    {
        top=temp;
    }
    else
    {
    temp->next=top;
    top=temp;
    }
}
void pop()
{
    struct node *temp;
    if (top==NULL)
    {
        printf("no node to remove");
    }
    else
    {
        temp=top;
        printf("%d",temp->data);
        top=top->next;
        free(temp);
       
    }
   
}
void display()
{
    struct node *t;
    t=top;
    while (t!=NULL)
    {
        printf("%d",t->data);
        t=t->next;
       
    }
}
void main()
{
    int k,c;
    while(1)
    {
        printf("enter c:");
        scanf("%d",&c);
        switch(c)
        {
            case 1:printf("enter k:");
                   scanf("%d",&k);
                   push(k);
                   break;
            case 2:pop();
                   break;
            case 3:display();
                   break;
            case 4:exit(0);
        }
    }
   
}
