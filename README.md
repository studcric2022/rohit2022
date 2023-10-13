                                                                                                             STOCK TABLE

CREATE A PROGRAM THAT SHOULD HAVE THE USER ABLE TO ENTER INFORMATION ABOUT
					VARIOUS STOCKS, THE AMOUNT OF SHARES, AND THE PRICE. THE USER CAN THEN ENTER A QUERY
					ABOUT A CERTAIN STOCK AND THE COST ACCORDING TO THE LIFO ACCOUNTING METHODS FOR A
	CERTAIN NUMBER OF SHARES.
			• The name of the stock (a string or int)
			• The number of shares of a stock (an int)
			• The purchase price (can be a decimal)
	The following could be your menu:
			• PRESS 1 TO ENTER A NEW STOCK.
			• PRESS 2 TO FIND THE LIFO PRICE FOR A STOCK.
			• IF 1 IS PRESSED, THE USER NEEDS TO ENTER THE STOCK SYMBOL, AND THE NUMBER OF
				SHARES, AND THE PRICE.
			• IF 2 IS PRESSED, THE USER NEEDS TO ENTER THE STOCK SYMBOL BEING QUERIED AND
				THE NUMBER OF SHARES IN QUESTION
Advantages:-
You can view details of the available stock at different locations and make a purchase or sales
decision accordingly. A clear view of the purchase and sales order outstanding helps you
further decide on the next steps to improve the cash flow in your business.
			• It aggregates the data from different times
			• It shows visual display of the results
			• It helps in understanding the performance of the company
			• Comparison can be made between different companies
Disadvantages:-
You can view details of the available stock at different locations and make a purchase or sales
decision accordingly. A clear view of the purchase and sales order outstanding helps you
further decide on the next steps to improve the cash flow in your business.
			• Some time data can be inaccurate
			• Because of dynamic memory allocation if we not use all memory space then there will
				be wastage of memory space
			• Creating too many objects on the stack can increase the risk of stack over flow.
			• Random access is not possible.                                                                                          
ALGORITHM
			STEP 1:- create two string called stock name and stock
							symbol , long long int for entering stock price.
			STEP 2:- using switch case if 1 is entered add_stock()
							function will takes place,if 2 is entered find_stock()
							function will takes place , if 3 is entered display() will
							takes place ,if 0 is entered program will be terminated.
			STEP 3:-in add_stock() enter the stock name and symbol
							and price of stock
			STEP 4:-in find_stock() enter the stock name and symbol
			STEP 5:-display() function will display all the added stock
							details 
			                                                                             IMPLEMENTATION
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
16
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
17
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
18
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
19
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
20
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
																																													Output
																						 ![image](https://github.com/studcric2022/rohit2022/assets/128765237/f1de18a0-4d58-41b3-a06b-da8d8e4e3b5f)
											                       ![image](https://github.com/studcric2022/rohit2022/assets/128765237/191b3d57-29bf-4bfe-befb-bd0c6fd880e5)
         																		![image](https://github.com/studcric2022/rohit2022/assets/128765237/3e7a2d98-502a-45a3-b5c8-e17e442ee616)

