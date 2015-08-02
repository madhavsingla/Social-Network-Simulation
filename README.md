#include<stdio.h>
#include<string.h>
void f_requester(char,char);
void f_requestee(char,char);
int main()
{
	struct users
	{
		char usrname[15];
		char f_name[15];
		char l_name[15];
		char psswrd[15];
		int f_count;//to count friends of user
	}u[25];
	int c,i=0,j,k,ch;
	char usr[15],usp[15];
	printf("SOCIAL NETWORK\n");
	printf("-----------------------\n");
	do{
	printf("MENU\n");
	printf("press 1 to sign up\n");
	printf("press 2 to login\n");
	scanf("%d",&c);
	switch(c)
	{
		case 1:
			printf("enter first name\n");
			scanf("%s",&u[i].f_name);
			printf("enter last name\n");
			scanf("%s",&u[i].l_name);
			printf("enter username\n");
			scanf("%s",&u[i].usrname);
			printf("enter password\n");
			scanf("%s",&u[i].psswrd);
			i++;//keeps count of users
			printf("user created");
			break;
		case 2:
			printf("enter username");
			scanf("%s",&usr);
			printf("enter password");
			scanf("%s",&usp);
			for(j=0;j<i;j++)
			{
				if(strcmp(usr,u[j].usrname)&&strcmp(usp,u[j].psswrd))
				{
					printf("user does not exist");
				}
				else
				{
				
				  printf("welcome\n\n\n\n");
				  /*if(u[j].f_count==0)
				  {
				  	prtinf(" you have no friends make some friends");
				  }*/
				  printf("1. to check your friend list");
				  printf("2. to check the users in the network");
				  scanf("%d",&c);
				    switch(c)
				    {
				    	case 2:
				    		for(k=0;k<i;k++)
				    		{
				    			printf("%s\n",u[k].usrname);
							}
					}
		        }
			}
			break;
	}
	printf("\nwant to continue press 1\n");
	scanf("%d",&ch);
}while(ch==1);
	getch();
	return 0;
}

