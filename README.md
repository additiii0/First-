#include <stdio.h>
#include <stdlib.h>

struct node {
	int data;
	struct node* next;
};
void create()
{
struct node *head=NULL;
    head=(struct node*)malloc(sizeof(struct node));
    printf("enter the data");
    scanf("%d", &head->data);
    head->next=NULL;
}
void in_beg()
{
    struct node *head, *newnode;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter the data");
    scanf("%d", &newnode->data);
    newnode->next=head;
    head=newnode;
}
void in_end()
{
    struct node *head, *newnode, *temp;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter the data");
    scanf("%d", &newnode->data);
    temp=head;
    while(temp->next!=0)
    {
        temp=temp->next;
    }
    temp->next=newnode;
}
void in_sp()
{
    int pos, i=1;
    int count;
     struct node *head, *newnode, *temp;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter position");
    scanf("%d", &pos);
    
    if(pos>count)
    {
        printf("invalid pos");
    }
    else
    {
        temp=head;
        while(i<pos)
        {
            temp=temp->next;
            i++;
        }
    }
    printf("enter data");
    scanf("%d",&newnode->data);
    newnode->next=temp->next;
    temp->next=newnode;
}
void del_beg()
{
    struct node *head, *temp;
    temp=head;
    head=head->next;
    free(temp);
}
void del_end()
{
    struct node *head, *prev, *temp;
    temp = head;
    while(temp->next!=0)
    {
        prev=temp;
        temp=temp->next;
    }
    if(temp==head)
    {
        head=0;
    }
    else
    {
        prev->next=0;
    }
    free(temp);
}
void del_sp()
{
    int pos, i=1;
    struct node *head, *temp, *nextnode;
    printf("enter position");
    scanf("%d",&pos);
    temp=head;
    while(i<pos-1);
    {
        temp=temp->next;
        i++;
    }
    nextnode=temp->next;
    temp->next=nextnode->next;
    free(temp);
}

int main()
{

	int choice;
	while (1) {

	printf("\n1.create\n2.insertinbeg\n3.insertinend\n4.insertinpos\n5.deleteinbeg\n6.deleteinend\n7.deleteinpos\n");
		
		printf("\nEnter Choice :\n");
		scanf("%d", &choice);

		switch (choice) {
		case 1:
			create();
			break;
		case 2:
			in_beg();
			break;
		case 3:
			in_end();
			break;
		case 4:
			in_sp();
			break;
		case 5:
			del_beg();
			break;
		case 6:
			del_end();
			break;
		case 7:
			del_sp();
			break;
	
		case 8:
			exit(1);
			break;
		default:
			printf("Incorrect Choice\n");
		}
	}
	return 0;
}
