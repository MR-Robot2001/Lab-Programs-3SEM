#include<stdio.h>
#include<cstdlib>
int stack[100],choice,top,item,MAX;

void pop()
{
	int item;
	if(top <= -1)
	  printf("\n Stack Underflow");
	else
	{
	  item = stack[top--];
	  printf("\n the deleted item is %d:",item);
	}
}

void push()
 {
if (top >= (MAX-1))
	 printf("\n Stack Overflow");
else
{
	printf("Enter the element to be inserted:\t");
	scanf("%d", &item);
	stack[++top] = item;
}
}

void display()
{
	int i;
	if(top == -1)
		printf("\n Stack is Empty");
	else
	{
		printf("\n The stack contents are:");
		for(i=top; i>=0; i--)
			printf("\n %d ", stack[i]);
	}
}

void palindrome()
{
  int i=0,m,item,revstack[20];
  m = top;
  for(i=0;i<=m;i++)
  {
	revstack[i]=stack[top];
	printf("%d",revstack[i]);
	top--;
  }
  top=m;
   //for(i=top;i>=0;i--)
   while(top>=0)
   {
     if(revstack[top]==stack[top])
	top--;
     else
	{
		printf("\nNot a palindrome!\n");
		break;
	}
  }
  if(top < 0)
  {
	printf("\n It is a palindrome! \n");
  }
  top = m;
}



int main()
{

    top=-1;
    printf("\n Enter the size of STACK[MAX=100]:");
    scanf("%d",&MAX);
    do
    {
	printf("\n STACK OPERATIONS USING ARRAY");
	printf("\n------------");
	printf("\n1.PUSH\n2.POP\n3.DISPLAY\n4.PALINDROME\n5.EXIT");
	printf("\n----------");
	printf("\n Enter the Choice:");
	scanf("%d",&choice);
	switch(choice)
	{
	    case 1:
		   push();
		   break;
	    case 2:
		   pop();
		   break;
	    case 3:
		   display();
		   break;
	    case 4:
		   palindrome();
		   break;
	    case 5:
		   exit(0);
		   break;
	    default:
		printf ("\n\t Please Enter a Valid Choice(1/2/3/4/5)!");
	}
    }
    while(choice!=5);
    return 0;

}
