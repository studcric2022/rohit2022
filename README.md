# rohit2022
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
struct node
{
char stock[100];
char shares[100];
long long int price;
struct node *next;
};
typedef struct node node;
node *head=NULL;


void add_stock()
{
node *nn,*temp;
nn=(node *)malloc(sizeof(node));
char s1[100],s2[100];
printf(" Enter Stock Name: ");
scanf("%s",s1);
strcpy(nn->stock,s1);
printf(" Enter Stock Symbol: ");
scanf(" %s",s2);

strcpy(nn->shares,s2);
long long int p;
printf(" Enter Stock Price: ");
scanf("%lld",&p);
nn->price=p;
nn->next=NULL;
if(head==NULL)
{
head=nn;
}
else
{
temp=head;
while(temp->next!=NULL)
{
temp=temp->next;
}
temp->next=nn;
}
printf("New stock added\n");
system("cls");
}


void find_stock()
{

printf("Enter the stock name: ");
char s1[100],s2[100];
scanf("%s",s1);
printf("Enter the stock Symbol: ");
scanf(" %s",s2);
system("cls");
node *temp=head;
while(temp!=NULL)
{
if(strcmp(temp->stock,s1)==0 && strcmp(temp-
>shares,s2)==0)
{
printf("Stock price is %lld\n",temp->price);
return;
}
temp=temp->next;
}
printf("NO STOCK AVAILABLE WITH THAT NAME/SHARE\n");

}


void display_stock()
{
node *temp;
if(head==NULL)

{
system("cls");
printf("NO STOCKS AVAILABLE\n");
return;
}
else
{
system("cls");
temp=head;
while(temp!=NULL)
{
printf(" STOCK NAME->%s\n STOCK SYMBOL ->%s\n
STOCK PRICE->%lld\n",temp->stock,temp->shares,temp->price);
printf("+++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++\n");
temp=temp->next;
}
}
}


int main()
{
int ch;
do
{printf("\n+++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++");
printf("\n");
printf("\t\t\t\t\t\tStock Table");
printf("\n");
printf("\n+++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++");
printf("\n Enter >1< To Enter A New Stock.");
printf("\n Enter >2< Find price for a stock.");
printf("\n Enter >3< Display stocks.");
printf("\n Enter >0< To Exit.\n");
 printf("\n Enter Your Choice : ");
scanf("%d",&ch);
if(ch==1)
{
add_stock();
}
else if(ch==2)
{
find_stock();
}

else if(ch==3)
{
display_stock();
}
else
{
break;
}
}while(ch!=0);
}