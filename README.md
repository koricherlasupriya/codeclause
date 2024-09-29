import java.util.Scanner;
import java.sql.*;
class TeluguMovie extends Movie
{
 String telugumovie;
 Scanner sc=new Scanner(System.in);
 static boolean seats[]=new boolean[10];
 static int seatfill=0;
 static int seat_remaining;
 String customer_name;

 TeluguMovie(String customer_name)
 {
   telugumovie="Mathu Vadalara 2";
   this.customer_name=customer_name;
 }
 void displaymovie()
 {
   System.out.println("-----Telugu Movie-----");
   System.out.println("current Telugu movie in theater is:"+telugumovie);
   System.out.println("If you want to book ticket (1=YES,other=NO)");
   System.out.println("Enter your choice");
   int choice=sc.nextInt();
   if(choice==1)
   {
     bookmovie();
   }
   else if(choice!=1)
   {
    System.out.println(customer_name+" you want to see English or Hindi Movie:(1=ENGLISH 2=HINDI and        other=NONE)");
    int choice1=sc.nextInt();
    if(choice1==1)
    {
     EnglishMovie english=new EnglishMovie(customer_name);
     english.displaymovie();
    }
    else if(choice1==2)
    {
     HindiMovie hindi=new HindiMovie(customer_name);
     hindi.displaymovie();
    }
    else if(choice1!=1 && choice!=2)
    {
     System.out.println("Thank you !! visit Again...");
     System.exit(0);
    }
   }
}
void bookmovie()
{
 seat_remaining=10-seatfill;
 System.out.println("Total capacity are:"+seats.length+"and remaining capacity is:"+seat_remaining);
 System.out.println("Enter no of seats:");
 int no_of_seats=sc.nextInt();
 int demo_no_of_seats=no_of_seats;
 if(no_of_seats<=seat_remaining)
 {
  while(no_of_seats!=0)
  {
   seats[seatfill++]=true;
   no_of_seats--;
  }
  System.out.println(customer_name+" Your "+demo_no_of_seats+" seats is booked successfully and total payment is:"+(demo_no_of_seats*100));
 }
 else if(no_of_seats > seat_remaining)
 {
  System.out.println("Sorry !! we don't have "+no_of_seats+"seats or seat is full already!!Sorry for  Inconvenience"+customer_name);
System.exit(0);
}
}
}
class EnglishMovie
{
 String englishmovie;
 Scanner sc=new Scanner(System.in);
 static boolean seats[]=new boolean[10];
 static int seatfill=0;
 static int seat_remaining;
 String customer_name;

 EnglishMovie(String customer_name)
 {
  englishmovie="Kung Fu Panda 4";
  this.customer_name=customer_name;
 }
 
 void displaymovie()
 {
  System.out.println("-----English Movie-----");
  System.out.println("current English movie in theater is:"+englishmovie);
  System.out.println("If you want to book ticket (1=YES,other=NO)");
  System.out.println("Enter your choice");
  int choice=sc.nextInt();
  if(choice==1)
  {
   bookmovie();
  }
  else if(choice!=1)
  {
   System.out.println(customer_name+" you want to see Telugu or Hindi Movie:(1=TELUGU 2=HINDI and        other=NONE)");
   int choice1=sc.nextInt();
   if(choice1==1)
   {
    TeluguMovie telugu=new TeluguMovie(customer_name);
    telugu.displaymovie();
   }
   else if(choice1==2)
   {
    HindiMovie hindi=new HindiMovie(customer_name);
    hindi.displaymovie();
   }
   else if(choice1!=1 && choice1!=2)
   {
    System.out.println("Thank you !! visit Again...");
    System.exit(0);
   }
 }
}
void bookmovie()
{
 seat_remaining=10-seatfill;
 System.out.println("Total capacity are:"+seats.length+"and remaining capacity is:"+seat_remaining);
 System.out.println("Enter no of seats:");
 int no_of_seats=sc.nextInt();
 int demo_no_of_seats=no_of_seats;
 if(no_of_seats<=seat_remaining)
 {
  while(no_of_seats!=0)
  {
   seats[seatfill++]=true;
   no_of_seats--;
  }
  System.out.println(customer_name+" Your "+demo_no_of_seats+" seats is booked successfully and total payment is:"+(demo_no_of_seats*150));
 }
 else if(no_of_seats > seat_remaining)
 {
  System.out.println("Sorry !! we don't have "+no_of_seats+"seats or seat is full already!!Sorry for  Inconvenience"+customer_name);
System.exit(0);
 }
}
}
class HindiMovie
{
 String hindimovie;
 Scanner sc=new Scanner(System.in);
 static boolean seats[]=new boolean[10];
 static int seatfill=0;
 static int seat_remaining;
 String customer_name;
 HindiMovie(String customer_name)
 {
  hindimovie="3 Iidots";
  this.customer_name=customer_name;
 }
 void displaymovie()
 {
  System.out.println("-----Hindi Movie-----");
  System.out.println("current Hindi movie in theater is:"+hindimovie);
  System.out.println("If you want to book ticket (1=YES,other=NO)");
  System.out.println("Enter your choice");
  int choice=sc.nextInt();
  if(choice==1)
 {
  bookmovie();
 }
 else if(choice!=1)
 {
  System.out.println(customer_name+" you want to see Telugu or English Movie:(1=TELUGU 2=ENGLISH and other=NONE)");
  int choice1=sc.nextInt();
  if(choice1==1)
  {
   TeluguMovie telugu=new TeluguMovie(customer_name);
   telugu.displaymovie();
  }
  else if(choice1==2)
  {
   EnglishMovie english=new EnglishMovie(customer_name);
   english.displaymovie();
  }
  else if(choice1!=1 && choice1!=2)
  {
   System.out.println("Thank You!! visit Again...");
   System.exit(0);
  }
}
}
void bookmovie()
{
 seat_remaining=10-seatfill;
 System.out.println("Total capacity are:"+seats.length+" and remaining capacity is:"+seat_remaining);
 System.out.println("Enter no of seats:");
 int no_of_seats=sc.nextInt();
 int demo_no_of_seats=no_of_seats;
 if(no_of_seats<=seat_remaining)
 {
  while(no_of_seats!=0)
  {
   seats[seatfill++]=true;
   no_of_seats--;
  }
  System.out.println(customer_name+" Your "+demo_no_of_seats+" seats is booked successfully and total payment is:"+(demo_no_of_seats*130));
 }
  else if(no_of_seats > seat_remaining)
  {
   System.out.println("sorry !! we don't have "+no_of_seats+" seats or seat is full allready!!Sorry for Incovenience "+customer_name);
   System.exit(0);
  }
}
}
class Movie
{
 public static void main(String args[])throws Exception
 {
  Scanner sc=new Scanner(System.in);
  System.out.println("-----welcome to Big screen Bliss-----");
  int choice=0;
  do
  {
   System.out.println("Movie's in our theater are:");
   System.out.println("1.Telugu");
   System.out.println("2.English");
   System.out.println("3.Hindi");
   System.out.println("0.EXIT");
   System.out.println("Select the movie type:");
   choice=sc.nextInt();
   sc.nextLine();
   System.out.println("Enter your name:");
   String customer_name=sc.nextLine();
   TeluguMovie telugu=new TeluguMovie(customer_name);
   EnglishMovie english=new EnglishMovie(customer_name);
   HindiMovie hindi=new HindiMovie(customer_name);
   
   switch(choice)
   {
    case 1:telugu.displaymovie();
           break;
    case 2:english.displaymovie();
           break;
    case 3:hindi.displaymovie();
           break;
    case 0:System.exit(0);
    default:System.out.println("Invalid Choice");
   }
  }while(choice!=0);
 }
}

