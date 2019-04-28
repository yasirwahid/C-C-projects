#include<stdio.h>
#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<process.h>

//Global variables............
int advance[5]={750,500,400,500,750};
int  r_no[5]={1,2,3,4,5};
int room;
tot[5]={0,0,0,0,0};
int g_tot=0;
int  r_charge[5];
char r_type[5][7];
char r_cust[5][20]={"N.A","N.A","N.A","N.A","N.A"};
char c_city[5][20];
char name[30];
int  c_mem[5];
char c_nat[5][20];
char r_avail[5];
int  r_per[5];
int  no[5];
int year[5];
int month[5];
int day[5];
int i;

//Function prototypes.........
void getavail();
void putavail();
void features();
void allocate();
void putcust();
void restaurant();
void deallocate();
void cancel();
void intro();
void screenheader();

//Function definitions..........
void screenheader()
 {
   printf("\n                       :::::::::::::::::::::::::::::::::::::");
   printf("\n                       ::                                 ::");
   printf("\n                       ::     @@@@@@@@@@@@@@@@@@@@@@@     ::");
   printf("\n                       ::     @                     @     ::");
   printf("\n                       ::     @      WELCOME TO     @     ::");
   printf("\n                       ::     @                     @     ::");
   printf("\n                       ::     @    Programers4You  @     ::");
   printf("\n                       ::     @                     @     ::");
   printf("\n                       ::     @@@@@@@@@@@@@@@@@@@@@@@     ::");
   printf("\n                       ::                                 ::");
   printf("\n                       :::::::::::::::::::::::::::::::::::::\n\n");
 }
void intro()
 {
   printf("\n\t             Near BSF Chowk, G.T. Road, Jalandhar City,\n\t\t\t\t Punjab 144001, INDIA");
   printf("\n\n                              Ph. No.:011-27223959");
   printf("\n\n\n                             WELCOMES YOU..............");
   printf("\n\n\n\tHotel Ganga Inn is one of the newest Hotel in Jalandhar. The Hotel is \t\tequipped with with all the general amenities and facilities that go \t\talong with memorable stay. Set amidst beautifully landscaped gardens, \t\tit proves to be a ideal dream destination for perceptive traveller.");
   printf("\n\n\tThe Hotel have well furnished rooms along with rooms providing pleasent \tviews of the city. The hotel satisfies the needs of business as well \t\tas the leisure traveller. All the rooms at the thotel are furnished \t\tbeautifully. All the rooms are fitted with amenities.");
   printf("\n\n                             AMENITIES .......\n");
   printf("\n\t\t\t1. 100% Power backup.\n");
   printf("\t\t\t2. Automatic lift.\n");
   printf("\t\t\t3. Ample parking space.\n");
   printf("\t\t\t4. Round the clock security.\n");
   printf("\t\t\t5. Running hot and cold water.\n");
   printf("\t\t\t6. Free internet service.\n");
   printf("\t\t\t7. 24 hours room service.\n");
   printf("\t\t\t8. Laundary service.\n");
   printf("\nPress any character to continue:");
   getch();
 }
void getavail()
 {
   for(i=0;i<5;i++)
     {
       if(r_no[i]==1)
  {
    strcpy(r_type[i],"Sp Dlx");
    r_charge[i]=1500;
    if(strcmp(r_cust[i],"N.A")==0)
      {
        r_avail[i]='Y';
        r_per[i]=0;
      }
  }
       else if(r_no[i]==2)
  {
    strcpy(r_type[i],"Dlx");
    r_charge[i]=1000;
    if(strcmp(r_cust[i],"N.A")==0)
      {
        r_avail[i]='Y';
        r_per[i]=0;
      }
  }
       else if(r_no[i]==3)
  {
    strcpy(r_type[i],"Gen");
    r_charge[i]=750;
    if(strcmp(r_cust[i],"N.A")==0)
      {
        r_avail[i]='Y';
        r_per[i]=0;
      }
  }
       else if(r_no[i]==4)
  {
    strcpy(r_type[i],"Coupl");
    r_charge[i]=1000;
    if(strcmp(r_cust[i],"N.A")==0)
      {
        r_avail[i]='Y';
        r_per[i]=0;
      }
  }
       else if(r_no[i]==5)
  {
    strcpy(r_type[i],"C Dlx");
    r_charge[i]=1500;
    if(strcmp(r_cust[i],"N.A")==0)
      {
        r_avail[i]='Y';
        r_per[i]=0;
      }
  }
     }
 }
void putavail()
 {
   clrscr();
   screenheader();
   printf("\n                          ROOM AVAILABILITY");
   printf("\n                         -------------------");
   printf("\nRoom No| Type | Charge | Availability | Cust_Name | Period |");
   for(i=0;i<5;i++)
     {
       printf("\n%d\t",r_no[i]);
       cputs(r_type[i]);
       if(i==0)
  printf("    %d\t%c\t     ",r_charge[i],r_avail[i]);
       if((i==1) || (i==2))
  printf("       %d\t   %c\t        ",r_charge[i],r_avail[i]);
       if(i==3 || i==4)
  printf("     %d\t %c\t      ",r_charge[i],r_avail[i]);
       cputs(r_cust[i]);
       if((i==1) || (i==2))
  printf("\t %d",r_per[i]);
       else if((i==3) || (i==4))
  printf("\t       %d",r_per[i]);
       else
  printf("\t      %d",r_per[i]);
     }
 }
void features()
 {
   int typ;
   clrscr();
   screenheader();
   printf("\nChoose the room type:\n1. Sp. Delux\n2. Delux");
   printf("\n3. General\n4. Couple\n5. C. Delux\n");
   scanf("%d",&typ);
   if(typ>5)
     {
       printf("\nWrong choice!! Choose a number between 1-5:");
       features();
     }
   switch(typ)
     {
       case 1:clrscr();
       screenheader();
       printf("\n Room number            >>>1");
       printf("\n Advance                >>>750\n\n");
       printf("\n                      FEATURES OF THIS ROOM                       ");
       printf("\n------------------------------------------------------------------");
       printf("\n\n Room Type            >>> Sp.delux");
       printf("\n\n Room charges         >>> Rs.1500 per day");
       printf("\n\n 1. Bed               >>>      2");
       printf("\n\n 2.Capacity           >>>      5");
       printf("\n\n 3.Balcony available     ");
       printf("\n------------------------------------------------------------------");
       printf("\n                     ADDITIONAL FEATURES                        ");
       printf("\n------------------------------------------------------------------");
       printf("\n\n 1.A/C  available ");
       printf("\n\n 2.Geyser available");
       printf("\n\n 3.TV available      ");
       printf("\n------------------------------------------------------------------");
       printf("\n NOTE :- Extra bed will cost Rs.50 per bed ");
       break;
       case 2:clrscr();
       screenheader();
       printf("\n Room number            >>>2\n\n");
       printf("\n Advance                >>>500\n\n");
       printf("\n                      FEATURES OF THIS ROOM                       ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n Room Type            >>> Delux                                      ");
       printf("\n\n Room charges         >>>Rs.1000 per day");
       printf("\n\n 1. Bed               >>>      2");
       printf("\n\n 2.Capacity           >>>      5");
       printf("\n-------------------------------------------------------------------");
       printf("\n                    ADDITIONAL FEATURES                        ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n 1.A/C available   ");
       printf("\n\n 2.Geyser available");
       printf("\n\n 3.TV available      ");
       printf("\n-------------------------------------------------------------------");
       printf("\n NOTE :- Extra bed will cost Rs.50 per bed ");
       break;
       case 3:clrscr();
       screenheader();
       printf("\n Room number            >>>3\n\n");
       printf("\n Advance                >>>400\n\n");
       printf("\n                      FEATURES OF THIS ROOM                       ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n Room Type            >>> General                                    ");
       printf("\n\n Room charges         >>>Rs.750 per day");
       printf("\n\n 1. Bed               >>>      2");
       printf("\n\n 2.Capacity           >>>      5");
       printf("\n-------------------------------------------------------------------");
       printf("\n                    ADDITIONAL FEATURES                        ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n 1.Geyser available      ");
       printf("\n-------------------------------------------------------------------");
       printf("\n NOTE :- Extra bed will cost Rs.50 per bed ");
       break;
       case 4:clrscr();
       screenheader();
       printf("\n Room number            >>>4\n\n");
       printf("\n Advance                >>>500\n\n");
       printf("\n                      FEATURES OF THIS ROOM                       ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n Room Type            >>> Couple                                     ");
       printf("\n\n Room charges         >>>Rs.1000 per day");
       printf("\n\n 1. Bed               >>>      1");
       printf("\n\n 2.Capacity           >>>      2");
       printf("\n-------------------------------------------------------------------");
       printf("\n                    ADDITIONAL FEATURES                        ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n 1.Geyser available");
       printf("\n\n 2.TV available      ");
       printf("\n-------------------------------------------------------------------");
       printf("\n NOTE :- Extra bed will cost Rs.50 per bed ");
       break;
       case 5:clrscr();
       screenheader();
       printf("\n Room number            >>>5\n\n");
       printf("\n Advance                >>>750\n\n");
       printf("\n                      FEATURES OF THIS ROOM                       ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n Room Type            >>> Couple Delux                                    ");
       printf("\n\n Room charges         >>>Rs.1500 per day");
       printf("\n\n 1. Bed               >>>      1");
       printf("\n\n 2.Capacity           >>>      2");
       printf("\n-------------------------------------------------------------------");
       printf("\n                    ADDITIONAL FEATURES                        ");
       printf("\n-------------------------------------------------------------------");
       printf("\n\n 1.A/C available   ");
       printf("\n\n 2.Geyser available");
       printf("\n\n 3.TV available      ");
       printf("\n-------------------------------------------------------------------");
       printf("\n NOTE :- Extra bed will cost Rs.50 per bed ");
       break;
     }
 }
void allocate()
 {
   clrscr();
   screenheader();
   getavail();
   printf("\n Enter the room number in which you want to stay:");
   scanf("%d",&room);
   if(r_avail[room-1]=='Y')
     {
       fflush(stdin);
       printf("\n Enter Name of cust living :");
       gets(r_cust[room-1]);
       printf("\n Enter city name :");
       gets(c_city[room-1]);
       printf("\n Enter nationality :");
       gets(c_nat[room-1]);
       printf("\n For how many days cust want the room :");
       scanf("%d",&r_per[room-1]);
       printf("\n Enter no. of member in your group :");
       scanf("%d",&c_mem[room-1]);
       if((room==1)||(room==2)||(room==3))
  if((c_mem[room-1]<1)||(c_mem[room-1]>5))
    {
      printf("\n %d members cannot be allocated this room.Allowed members are between 1-5.",c_mem[room-1]);
      getch();
      allocate();
    }
       else if((room==4)||(room==5))
  if((c_mem[room-1]<1)||(c_mem[room-1]>2))
    {
      printf("\n %d members cannot be allocated this room.Allowed members are between 1-2.",c_mem[room-1]);
      getch();
      allocate();
    }
       printf("\n Enter the date of arrival :");
       printf("\n------------------------------");
       printf("\n Year : ");
       scanf("%d",&year[room-1]);
       printf("\n Month :");
       scanf("%d",&month[room-1]);
       printf("\n Day :");
       scanf("%d",&day[room-1]);
       if((year[room-1]>9999)||(month[room-1]>12)||(month[room-1]<1)||(day[room-1]<1)||(((month[room-1]==1)||(month[room-1]==3)||(month[room-1]==5)||(month[room-1]==7)||(month[room-1]==8)||(month[room-1]==10)||(month[room-1]==12))&&(day[room-1]>31))||(((month[room-1]==4)||(month[room-1]==6)||(month[room-1]==9)||(month[room-1]==11))&&(day[room-1]>30))||((month[room-1]==2)&&((year[room-1]%400==0)||((year[room-1]%4==0)&&(year[room-1]%100!=0)))&&(day[room-1]>29))||((month[room-1]==2)&&(year[room-1]%4!=0)&&(day[room-1]>28)))
  {
    delay(200);
    printf("\n\n!!!!!INVALID DATE........");
    getch();
    allocate();
  }
       else
  {
    printf("\n... Room is allocated to ");
    cputs(r_cust[room-1]);
    printf(" for %d days.",r_per[room-1]);
    r_avail[room-1]='N';
    getch();
  }
     }
   else
     {
       printf("\n ERROR : Room cannot be allocated ...");
       printf("\n Room is not available...");
       getch();
     }
 }
void deallocate()
 {
   clrscr();
   screenheader();
   printf("\nEnter the room number:");
   scanf("%d",&room);
   if(r_cust[room-1]=="N.A")
     {
       printf("\nThe room is empty........");
       getch();
     }
   else
     {
       printf("\nEnter the name of the person staying in the room:");
       fflush(stdin);
       gets(name);
       if(strcmpi(name,r_cust[room-1])==0)
  {
    printf("\nRoom number %d is deallocated......",room);
    strcpy(r_cust[room-1],"N.A");
    getch();
  }
       else
  {
    printf("\nInvalid name........");
    getch();
    deallocate();
  }
     }
   g_tot=(r_per[room-1]*r_charge[room-1])-advance[room-1]+tot[room-1];
   printf("\n\nYour total bill is %d",g_tot);
   printf("\n\n\nThanks for staying in this hotel.........");
 }
void cancel()
 {
   clrscr();
   screenheader();
   printf("\nEnter the room number:");
   scanf("%d",&room);
   if(r_cust[room-1]=="N.A")
     {
       printf("\nThe room is empty........");
       getch();
     }
   else
     {
       printf("\nEnter the name of the person staying in the room:");
       fflush(stdin);
       gets(name);
       if(strcmpi(name,r_cust[room-1])==0)
  {
    printf("\nReservation for room number %d is cancelled......",room);
    strcpy(r_cust[room-1],"N.A");
    getch();
  }
       else
  {
    printf("\nInvalid name........");
    getch();
    cancel();
  }
     }
   g_tot=advance[room-1];
   printf("\n\nYour total bill is %d",g_tot);
 }
void putcust()
 {
   int j;
   clrscr();
   screenheader();
   printf("\nEnter the room number :");
   scanf("%d",&room);
   j=strcmp(r_cust[room-1],"N.A");
   if(j==0)
     {
       printf("\n Data not available ");
       getch();
     }
   else
     {
       printf("\n Room No        :%d",r_no[room-1]);
       printf("\n Customer Name  :");
       cputs(r_cust[room-1]);
       printf("\n Period         :%d",r_per[room-1]);
       printf("\n City           :");
       cputs(c_city[room-1]);
       printf("\n Nationality    :");
       cputs(c_nat[room-1]);
       printf("\n No of member   :%d",c_mem[room-1]);
       printf("\n Arrival Date   :%d/%d/%d",day[room-1],month[room-1],year[room-1]);
       getch();
     }
 }
void restaurant()
 {
   int count=0,z=0,fc[113],answ;
   char ans;
   int price[113]={245,245,245,245,240,240,240,240,235,235,250,235,235,220,
   215,230,215,240,250,250,250,250,250,250,250,255,245,245,245,245,250,240,
   240,360,290,360,290,370,295,360,290,360,290,250,360,290,360,290,250,370,
   290,360,290,250,250,280,245,290,235,265,240,290,300,256,240,265,270,255,
   255,240,240,235,220,25,30,25,30,35,35,25,30,35,25,35,25,25,30,100,105,105,
   100,105,100,105,125,105,105,100,105,110,115,100,100,100,105,105,105,105,
   125,105,120,120,100};
   char food[113][30]={"SHAHI PANEER","KADAI PANEER","CHEESE KORMA",
   "MALAI KOFTA","MATAR PANEER","PALAK PANEER","MIX VEG.","ALOO GOBI",
   "ALOO JEERA","CHANA MASALA","MATAR MUSHROOM","RAJMA MAKHANI","DAL MAKHANI",
   "MIXED RAITA","BUNDI RAITA","PINEAPPLE RAITA","SALAD(GREEN)","DUM ALOO",
   "MUSHROOM PANEER","MUTTON MASALA","MUTTON MUGHLAI","MUTTON KORMA",
   "MUTTON DO PYAZA","MUTTON SAGH","MUTTON DAHI","MUTTON ROGAN JOSH",
   "MUTTON CURRY","KADAI MUTTON","KEEMA LEVER","KEEMA MATAR","KEEMA EGG",
   "BRAIN CURRY","EGG CURRY","BUTTER CHICKEN","BUTTER CHICKEN(1/2)",
   "KADAI CHICKEN","KADAI CHICKEN(1/2)","BUTTER CHICKEN(BL)",
   "BUTTER CHICKEN(BL)(1/2)","CHICKEN MUGHLAI","CHICKEN MUGHLAI(1/2)",
   "CHICKEN MASALA","CHICKEN MASALA(1/2)","CHICKEN MASALA(1/4)",
   "CHICKEN SAGH","CHICKEN SAGH(1/2)","CHICKEN DAHI","CHICKEN DAHI(1/2)",
   "CHICKEN DAHI(1/4)","CHICKEN KORMA","CHICKEN KORMA(1/2)",
   "CHICKEN DO PYAZA","CHICKEN DO PYAZA(1/2)","FISH CURRY","CHICKEN CURRY",
   "CHICKEN CURRY(1/2)","CHICKEN CURRY(1/4)","CHILLI CHICKEN","TANDOORI ALOO",
   "CHICKEN TIKKA","SEEKH KABAB","FISH TIKKA","CHICKEN TANDOORI",
   "CHICKEN TANDOORI(1/2)","PANEER TIKKA","CHICKEN SEEKH KABAB",
   "CHICKEN HARA KABAB","CHICKEN BIRYANI","MUTTON BIRYANI","PANEER PULAO",
   "VEG.PULAO","JEERA RICE","STEAMED RICE","RUMALI ROTI","ROTI","NAN",
   "ALOO NAN","PANEER NAN","KEEMA NAN","PARANTHA","ALOO PARANTHA",
   "PANEER PARANTHA","PUDINA PARANTHA","BUTTER NAN","LACHCHA PARANTHA",
   "MISSI ROTI","KHASTA ROTI","VEG.BURGER","PANEER BURGER","CHEESE SANDWICH",
   "VEG.PATTI","CHICKEN PATTI","TEA","COFFEE","COLD COFFEE","PINEAPPLE",
   "STRAWBERRY","CHOCOLATE","BLACK FOREST","DOUBLE STORIED","TRIPLE STORIED",
   "SOFT CONE","VANILLA","STRAWBERRY","CHOCOLATE","CHOCO CHIPS","MANGO",
   "TUTTI FRUITY","LICHI","PISTA BADAM","CHOCOLATE PISTA BADAM","CHOCO DIP",
   "CHOCOLATE LICHI"};
   clrscr();
   screenheader();
   printf("\n                        *********");
   printf("\n                        MENU CARD");
   printf("\n                        *********");
   printf("\n\n                        VEGETARIAN");
   for(i=0;i<113;count++,i++)
     {
       gotoxy(17,count+20);
       printf("%d",i+1);
       gotoxy(30,count+20);
       cputs(food[i]);
       gotoxy(55,count+20);
       printf("%d",price[i]);
       if(count==17)
  {
    count=0;
    printf("\n                              PRESS ANY KEY TO CONTINUE");
    getch();
    clrscr();
    screenheader();
  }
       if(i==18)
  {
    printf("\n\n       MUTTON\n");
    count +=3;
  }
       if(i==32)
  {
    printf("\n\n       CHICKEN\n");
    count +=3;
  }
       if(i==57)
  {
    printf("\n\n       BAR-BE-QUE\n");
    count +=3;
  }
       if(i==72)
  {
    printf("\n\n       ROTI-NAN-PARANTHA\n");
    count +=3;
  }
       if(i==91)
  {
    printf("\n\n       BEVERAGES\n");
    count +=3;
  }
       if(i==100)
  {
    printf("\n\n       ICE-CREAMS\n");
    count +=3;
  }
     }
   getch();
   clrscr();
   screenheader();
   printf("\n\nPRESS 0 TO GO BACK TO MENU CARD\nPRESS 1 TO CONTINUE ");
   scanf("%d",&answ);
   switch(answ)
     {
       case 0:restaurant();
       break;

       case 1 :clrscr();
        do
   {
     printf("ENTER THE FOOD CODE YOU WANT TO HAVE :: ");
     scanf("%d",&fc[z]);
     z++;
     puts("DO YOU WANT MORE(Y/N) ::");
     fflush(stdin);
     scanf("%c",&ans);
   }while ((ans=='y')||(ans=='Y'));
        printf("\nEnter your room number:");
        scanf("%d",&room);
        printf("\nEnter your name:");
        fflush(stdin);
        gets(name);
        if(strcmpi(name,r_cust[room-1])!=0)
   {
     printf("\nWrong name...:");
     getch();
     restaurant();
   }
        getch();
        clrscr();
        screenheader();
        for(i=0;i<z;i++)
   {
     cputs(food[fc[i]-1]);
     printf("\t\t\t%d\n",price[fc[i]-1]);
     tot[room-1] +=price[fc[i]-1];
   }
        printf("TOTAL\t\t\t\t%d",tot[room-1]);
        break;

       default:printf("\nWrong choice entered!!!");
        getch();
        restaurant();
     }
 }
void main()
 {
   char ans;
   int ch;
   clrscr();
   screenheader();
   intro();
   do
     {
       clrscr();
       screenheader();
       printf("\n\n\n                      Choose a category:\n");
       printf("                        1. Get availability\n");
       printf("                     2. Features of room\n");
       printf("                        3. Room allocation\n");
       printf("           4. Show customer details\n");
       printf("           5. Restaurant\n");
       printf("                        6. Cancellation\n");
       printf("                        7. Room Deallocation\n");
       printf("                 8. Exit\n");
       scanf("%d",&ch);
       switch(ch)
   {
     case 1:getavail();
     putavail();
     break;
     case 2:features();
     break;
     case 3:allocate();
     break;
     case 4:putcust();
     break;
     case 5:restaurant();
     break;
     case 6:cancel();
     break;
     case 7:deallocate();
     break;
     case 8:exit(0);
     default:printf("\n\n\nWrong choice!!!!\n\nPlease choose 1-6");
      getch();
   }
 printf("\n\nDo you want to continue:");
 fflush(stdin);
 scanf("%c",&ans);
     }while(ans=='y'||ans=='Y');
 }
