# Budget_Trackerproject
Track your daily budget using My Budget Tracker Interface.

PROGRAM:

#include<bits/stdc++.h>
using namespace std;

class Budget_Tracker
{
    private:
    float amount;
    float income;
    float expenses;
    public: 
    
    Budget_Tracker()
    {
        income=0;
        expenses=0;
    }
    void Addincome(float amount)
    {
        income+=amount;
        saveToFile("Income",amount);
        cout<<"***The Income is added successfully***"<<endl;

    }
    void Expenses(float amount)
    {
        expenses+=amount;
        saveToFile("Expenses",amount);
        cout<<"***The expense is added successfully***"<<endl;

    }
    void summary()
    {
        cout<<"---The summary of your Budget---"<<endl;
        cout<<"The Total Income is RS.: "<<income<<endl;
        cout<<"The Total expense is RS.: "<<expenses<<endl;
        cout<<"The Total Balance is RS.: "<<income-expenses<<endl;
        cout<<"Thank you"<<endl;
        
    }
    void saveToFile(string type,float amount)
    {
        ofstream file("DataTracker.txt",ios::app);
        file << type <<" "<<amount<<endl;
        file.close();
    }
};

int main()
{
    Budget_Tracker s1;
    int choice;
    float amount;

    do
    {
        cout<<"++++++WELCOME TO BUDGET TRACKER+++++ "<<endl;
        cout<<"1.Add_Income"<<endl;
        cout<<"2.Add_Expenses"<<endl;
        cout<<"3.View summary"<<endl;
        cout<<"4.Exit"<<endl;
        
        cout<<"Enter the choice: "<<endl;
        cin>>choice;

        switch(choice)
        {
            case 1:
            cout<<"Enter the amount of income: "<<endl;
            cin>>amount;
            s1.Addincome(amount);
            break;

            case 2:
            cout<<"Enter the amount of expenses: "<<endl;
            cin>>amount;
            s1.Expenses(amount);
            break;

            case 3:
            s1.summary();
            break;

            case 4:
            cout<<"Exited Successfully"<<endl;
            break;

            default:
            cout<<"oops Invalid choice!!!!"<<endl;
            cout<<"Please enter valid choice"<<endl;

        }
    } 
    while(choice!=4);

    return 0;
    
}

RESULTS:
++++++WELCOME TO BUDGET TRACKER+++++ 
1.Add_Income
2.Add_Expenses
3.View summary
4.Exit
Enter the choice: 
1
Enter the amount of income: 
120000
***The Income is added successfully***
++++++WELCOME TO BUDGET TRACKER+++++
1.Add_Income
2.Add_Expenses
3.View summary
4.Exit
Enter the choice:
2
Enter the amount of expenses:
50000
***The expense is added successfully***
++++++WELCOME TO BUDGET TRACKER+++++
1.Add_Income
2.Add_Expenses
3.View summary
4.Exit
Enter the choice:
3
---The summary of your Budget---
The Total Income is RS: 120000
The Total expense is RS: 50000
The Total Balance is RS : 70000
Thank you
