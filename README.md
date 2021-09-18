# checking-LinkedList-is-palindrome-when-no.-of-elements-are-odd-in-c-
checking LinkedList is palindrome when no. of elements are odd in C


#include <stdio.h>
#include <stdlib.h>

struct node{
    int data;
    struct node *next;        
};

void middle(struct node *fp , struct node *sp , struct node *head){
    struct node *midnext ;
    struct node *prev;
    
    while(fp->next!=NULL){
        prev=sp;
        sp=sp->next;
        fp=fp->next->next;
        
        
    }
    printf("\nmiddle=%d",sp->data);
    prev->next=NULL;
    midnext=sp->next;
   
    reverse(midnext , head);

    

    
}

void reverse(struct node *ptr , struct node *head){
    struct node *prev , *current , *next;
    
    
    current = ptr;
    prev =NULL;
    while(current !=NULL){
        next=current->next;
        current->next=prev;
        prev=current;
        current=next;
    }
    ptr =prev;

    printf("\n\nchecking palindrome");
    while(head!=NULL && ptr!=NULL){
    if(head->data == ptr->data ){
        printf("\nfirsthalf=%d",head->data);
        printf("\tsecondhalf=%d",ptr->data);
        
        
    }
    printf("\n");
    head=head->next;
    ptr=ptr->next;
    
    }
    
    
    
}





int main()
{
    int midval;
    

    struct node *head , *first , *second , *third , *fourth , *fifth , *six; 
    head = (struct node*) malloc(sizeof(struct node));
    first = (struct node*) malloc(sizeof(struct node));
    second = (struct node*) malloc(sizeof(struct node));
    third = (struct node*) malloc(sizeof(struct node));
    fourth = (struct node*) malloc(sizeof(struct node));
    fifth = (struct node*) malloc(sizeof(struct node));
    six = (struct node*) malloc(sizeof(struct node));
    
    head->data=1;
    head->next=first;
    
    first->data=2;
    first->next=second;
    
    second->data=1;
    second->next=third;
    
    third->data=4;
    third->next=fourth;
    
    fourth->data=1;
    fourth->next=fifth;
    
    fifth->data=2;
    fifth->next=six;
    
    six->data=1;
    six->next=NULL;
    

    
    middle(head,head,head);
    

    return 0;
}

