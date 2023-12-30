#include<windows.h>
#include<stdio.h>
#include<conio.h>
#include <stdlib.h>
#include<string.h>
#include<ctype.h>
#include<dos.h>
#include<time.h>


void Password();
void delay();


int main()
{
Password();
getch();
return 0;
}

void Password(void)
{

char password[10]={"codewithc"};
system("cls");
char d[26]="  Encrypted Program";
char ch,pass[10];
int i=0,j;
for(j=0;j<20;j++)
{
Sleep(50);
printf("*");
}
for(j=1;j<20;j++)
{
Sleep(50);
printf("%c", d[j]);
}
for(j=0;j<20;j++)
{
Sleep(50);
printf("*");
}

printf("\n\nEnter Password:");

while(ch!=13)
{
ch=getch();

if(ch!=13 && ch!=8){
putch('*');
pass[i] = ch;
i++;
}
}
pass[i] = '\0';
if(strcmp(pass,password)==0)
{
printf("\nverifying...");
for (i=0; i < 1; i++)
{
 delay(3);
printf("\n\nPassword matched :)");
}
for(i=0;i<1;i++)
{
 delay(2);
printf("\nPress any key to continue...");
}
getch();
}
else
{
printf("\nverifying...");
for(i=0; i<1;i++)
{
 delay(3);
printf("\n\n[!]Password didn't match :(");
}
for(i=0;i<1;i++)
{
 delay(2);
printf("\nPress any key to try again...");
}
getch();
Password();
}
}


void delay(int number_of_seconds)
{
    // Converting time into milli_seconds
    int milli_seconds = 1000 * number_of_seconds;

    // Stroing start time
    clock_t start_time = clock();

    // looping till required time is not acheived
    while (clock() < start_time + milli_seconds)
        ;
}