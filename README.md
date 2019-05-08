# KBC
KBC game made in C programming language
Code


#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<stdlib.h>
#include<math.h>
static int amt=0,countr=0,count=0;
void show_rec();
void start();
void maingame();
void trial();
int main()
{
  char choice,ch;
  homepage:
    printf("\n\t\t________________________________________");
    printf("\n\t\t\t   WELCOME ");
    printf("\n\t\t\t   to ");
    printf("\n\t\t\t   THE GAME ");
    printf("\n\t\t________________________________________");
    printf("\n\t\t________________________________________");
    printf("\n\t\t   BECOME A MILLIONAIRE!!!!!!!!!!! ") ;
 printf("\n\t\t________________________________________");
    printf("\n\t\t________________________________________");
    printf("\n\t\t > Press S to start the game");
    printf("\n\t\t > press Q to quit   ");
    printf("\n\t\t(Once you start you cannot quit mid-way)");
    printf("\n\t\t________________________________________\n\n");
    scanf(" %c",&choice);
    choice=toupper(choice);
    switch(choice)
 {
     case 'S':
        start();
      printf("\n\nYou answered %d questions correctly and won $%d amount",countr,amt);
        printf("\n\nThanks for playing");
        break;
     case 'Q':{
        printf("\nAre you sure(y for yes and n for no):\n");
        scanf(" %c",&ch);
        ch=tolower(ch);
        switch(ch)
     {
     case 'y':{
        printf("\nThanks for playing");
        exit(0);
     }
        break;
     case 'n':{
     goto homepage;}
        break;
     }
        break;
     
        default:
        printf("\nPlease enter correct choice\n");
     goto homepage;
     }
     }
}
void start()
{
  int score;
   printf("\n\n Here are some tips you might wanna know before playing:");
   printf("\n -------------------------------------------------------------------------");
   printf("\n >> There are 2 rounds in this Quiz Game,WARMUP ROUND & CHALLANGE ROUND");
   printf("\n >> In warmup round you will be asked a total of 3 questions to test your");
  printf("\n  general knowledge. You are eligible to play the game if you give atleast 2");
   printf("\n  right answers, otherwise you can't proceed further to the Challenge Round.");
   printf("\n >> Your game starts with CHALLANGE ROUND. In this round you will be asked a");
   printf("\n  total of 10 questions. Each right answer will be awarded $100,000!");
   printf("\n  By this way you can win upto ONE MILLION cash prize!!!!!..........");
   printf("\n >> You will be given 4 options and you have to press A, B ,C or D for the");
   printf("\n  right option.");
   printf("\n >> You will be asked questions continuously, till right answers are given");
   printf("\n\n\t!!!!!!!!!!!!! ALL THE BEST !!!!!!!!!!!!!");
  trial();
   if(count>=2){
       printf("\nCONGRATULATIONS!!");
       printf("\nYou have unlocked the Challenge Round\n");
       maingame();}
  else{
       printf("\nSorry, you are not elligible");
       printf("\nTry the warm-up round again");
       start();}
}
void maingame()
{
  int l1,l2,r,s1,s2,t;
   printf("\n>>You will be asked to enter two different levels between 1 and 10 except for the two numbers themselves");
   printf("\nFor eg. if you enter levels as 3 and 6:");
   printf("\nCase 1:If your 1st and 2nd answer are correct but the 3rd is wrong you will recieve 0 cash prize");
   printf("\nCase 2:If all answers upto 4 are correct you win cash prize for question 3");
   printf("\nCase 3:If all answers upto 7 are correct you win cash prize of question 6");
  enter:
   printf("\nEnter 2 levels between 1 and 10 except 1 and 10 sucha that level 1 is smaller than level 2\n\n");
   scanf("%d,%d",&l1,&l2);
  if(l1==l2)
  goto enter;
   if(l1>l2)
  {
   t=l1;
   l1=l2;
   l2=t;
  }
   printf("\n\n!!LET THE GAME BEGIN!!");
  char ans;
  for(int i=1;i<=10;i++)
 {
 r=i;
 switch(r)
               {
               case 1:
               printf("\n\nWhat is the National Game of England?");
               printf("\n\nA.Football\t\tB.Basketball\n\nC.Cricket\t\tD.Baseball");
       getc(stdin);     scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='C')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {printf("\n\nWrong!!! The correct answer is C.Cricket");
              printf("\nCurrent amount:%d\n",amt);
             return; }
              printf("\nCurrent amount:%d\n",amt);
              break;
            
     case 2:
               printf("\n\n\nStudy of Earthquake is called............,");
               printf("\n\nA.Seismology\t\tB.Cosmology\n\nC.Orology\t\tD.Etimology");
       getc(stdin);     scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='A')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);
         }
               else
                   {printf("\n\nWrong!!! The correct answer is A.Seismology");
              if(r<l1){
              amt=0;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              else if(r>l1 && r<=l2)
                  s1=amt;
              else if(r>l2)
                   s2=amt;
               printf("\nCurrent amount:%d\n",amt);
              return;
                   }
              if(r==l1)
               s1=amt;
              else if(r==l2)
               s2=amt;
            printf("\nCurrent amount:%d\n",amt);
               break;
     case 3:
               printf("\n\n\nAmong the top 10 highest peaks in the world, how many lie in Nepal? ");
               printf("\n\nA.6\t\tB.7\n\nC.8\t\tD.9");
       getc(stdin);     scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='C')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);
         }
               else
                   {printf("\n\nWrong!!! The correct answer is C.8");
              if(r<=l1){
              amt=0;}
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
            
               if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 4:
               printf("\n\n\nThe Laws of Electromagnetic Induction were given by?");
               printf("\n\nA.Faraday\t\tB.Tesla\n\nC.Maxwell\t\tD.Coulomb");
       getc(stdin);  
       scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='A')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {
               printf("\n\nWrong!!! The correct answer is A.Faraday");
               if(r<=l1){
              amt=0;}
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 5:
               printf("\n\n\nIn what unit is electric power measured?");
               printf("\n\nA.Coulomb\t\tB.Watt\n\nC.Power\t\tD.Units");
       getc(stdin);  
       scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='B')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {
                       printf("\n\nWrong!!! The correct answer is B.Power");
               if(r<=l1)
              amt=0;
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
             break;
                   
               case 6:
               printf("\n\n\nWhich element is found in Vitamin B12?");
               printf("\n\nA.Zinc\t\tB.Cobalt\n\nC.Calcium\t\tD.Iron");
   getc(stdin);  
   scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='B' )
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);
                 }
               else
                   {printf("\n\nWrong!!! The correct answer is B.Cobalt");     
                   if(r<=l1)
              amt=0;
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 7:
               printf("\n\n\nWhat is the National Name of Japan?");
               printf("\n\nA.Polska\t\tB.Hellas\n\nC.Drukyul\t\tD.Nippon");
   getc(stdin);  
   scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='D')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {printf("\n\nWrong!!! The correct answer is D.Nippon");
                   if(r<=l1)
              amt=0;
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 8:
               printf("\n\n\nHow many times a piece of paper can be folded at the most?");
               printf("\n\nA.6\t\tB.7\n\nC.8\t\tD.Depends on the size of paper");
   getc(stdin);     scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='B')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {printf("\n\nWrong!!! The correct answer is B.7");
                   if(r<=l1)
              amt=0;
              else if(r>l1 && r<=l2)
           amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 9:
               printf("\n\n\nWhat is the capital of Denmark?");
               printf("\n\nA.Copenhagen\t\tB.Helsinki\n\nC.Ajax\t\tD.Galatasaray");
   getc(stdin);     scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='A')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5); }
               else
                   {printf("\n\nWrong!!! The correct answer is A.Copenhagen");
                   if(r<l1)
              amt=0;
              else if(r>l1 && r<=l2)
              amt=s1;
              else if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
     case 10:
               printf("\n\n\nWhich is the longest River in the world?");
               printf("\n\nA.Nile\t\tB.Koshi\n\nC.Ganga\t\tD.Amazon");
       getc(stdin);     scanf("%c",&ans);
       ans=toupper(ans);
               if (ans=='A')
                         {printf("\n\nCorrect!!!");countr++;
           amt=amt+pow(10,5);}
               else
                   {printf("\n\nWrong!!! The correct answer is A.Nile");
              if(r>l2)
              amt=s2;
               printf("\nCurrent amount:%d\n",amt);
              return;}
              if(r==l1)
               s1=amt;
               else if(r==l2)
               s2=amt;
               printf("\nCurrent amount:%d\n",amt);
               break;
         }     
 }
}
void trial()
{
  for(int i=1;i<=3;i++)
 {
  
 int r1=i;
 char ans;
    switch(r1)
               {
               case 1:
               printf("\n\nWhich of the following is a Palindrome number?");
               printf("\n\nA.42042\t\tB.101010\n\nC.23232\t\tD.01234");
   getc(stdin);
   scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='C'){
                 printf("\n\nCorrect!!!");
     count++;}
   else
                 printf("\n\nWrong!!! The correct answer is C.23232");
   break;
   case 2:
               printf("\n\n\nThe country with the highest environmental performance index is...");
               printf("\n\nA.France\t\tB.Denmark\n\nC.Switzerland\t\tD.Finland");
   getc(stdin);     scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='C')
                       {printf("\n\nCorrect!!!");
   count++;
                         break;}
               else
                   {printf("\n\nWrong!!! The correct answer is C.Switzerland");
                   break;}
     case 3:
               printf("\n\n\nWhich animal laughs like human being?");
               printf("\n\nA.Polar Bear\t\tB.Hyena\n\nC.Donkey\t\tD.Chimpanzee");
   getc(stdin);     scanf("%c",&ans);
   ans=toupper(ans);
               if (ans=='B')
                         {printf("\n\nCorrect!!!");count++;
                         break;}
               else
                   {printf("\n\nWrong!!! The correct answer is B.Hyena");
                   break;}
  
     }
 }
}


