# CODSOFT-TASK3-
import java.util.Scanner;

class ATM extends Bank
{
    int pin,choice;
    ATM()
    {
        super();
        pin=0;
        choice=0;
    }
    void options()
    {
        Scanner sc=new Scanner(System.in);
        System.out.println("\nWelcome");
        System.out.println("Insert your card");
        System.out.println("Enter Your 4 Digit PIN");
        pin=sc.nextInt();
        if(!(pin>=1000 && pin<=9999))
        {
            System.out.println("Please enter the correct PIN");
            return;
        }
        System.out.println("1.Deposit");
        System.out.println("2.Withdrawl");
        System.out.println("3.Check balance");
        System.out.println("4.Exit");
        System.out.println("Enter Your Option");
        choice=sc.nextInt();
    }
    void deposit(int amt)
    {
        balance=balance+amt;
    }
    void withdraw(int amt)
    {
        if(amt<balance)
        {
            balance=balance-amt;
            System.out.println(" Collect Your money");
        }
        else
        {
            System.out.println("Insufficient balance for withdraw");
            System.out.println("Transcation failed");
        }
    }
    void check()
    {
        System.out.println("Balance:"+balance);
    }
    void atm()
    {
        int amt;
        Scanner sc=new Scanner(System.in);
        input();
        do{
            options();
            switch(choice)
            {
                case 1:
                    System.out.println("enter amount to deposit");
                    amt=sc.nextInt();
                    deposit(amt);
                    break;
                    case 2:
                    System.out.println("Money withdraw");
                    amt=sc.nextInt();
                    withdraw(amt);
                    break;
                    case 3:
                        System.out.println("checking balance");
                        check();
                        break;
                        case 4:
                            break;
                            default:
                            System.out.println("Invalid option");
                            }
                            System.out.println("Thank You");
        } while(choice!=4);
    }
    public static void main(String args[])
    {
        ATM ob=new ATM();
        ob.atm();
    }
}
class Bank
{
    String cname;
    long acno;
    String actype;
    double balance;
    Bank()
    {
        cname=" ";
        actype=" ";
        acno=0;
        balance=0;
    }
    void input()
    {
        Scanner sc= new Scanner(System.in);
      System.out.println("enter customer name");
      cname=sc.nextLine();
      System.out.println("enter account number");
      acno=sc.nextLong();
      System.out.println("enter account type");
      sc.nextLine();
      actype=sc.nextLine();
      System.out.println("enter balance");
      balance=sc.nextDouble();
    }
    void display()
    {
       System.out.println("Name "+cname);
       System.out.println("account number"+acno);
       System.out.println("account type "+ actype);
       System.out.println("balance"+balance);
    }
}
