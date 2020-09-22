<div align="center">

## Teller Banking system


</div>

### Description

This Program is really good example of class for the beginners.

In this program we have 2 bank and 4 tellers and 2 tellers for each bank. so, client of the first bank can't work with second bank and teller of the second bank and so on...
 
### More Info
 
Input is bank#, teller# and account# and transactions like credit or debit and so on...

(two)tellers of the first bank can't work with second bank.

Balance of the account and finally total report of the bank with total transcations and final balance of the bank and so on..

NO side effects


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Devendra Patel](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/devendra-patel.md)
**Level**          |Beginner
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Classes/ Frameworks/ OOP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/classes-frameworks-oop__3-31.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/devendra-patel-teller-banking-system__3-2926/archive/master.zip)





### Source Code

```
//******************************************************************************************//
// Name : Devendra Patel
// Mini Project # 2 (Small banking system)
// Description: This program is a banking system that operates with objects of 3 classes.
//					A bank class, teller class and account class. And here we have 2 banks,
//					4 tellers and 10 accounts.
//       And user should be promplted to enter transactions until he/she wants to stop
//				for performing the transaction user should be enter the teller num. and an
//				account num. and if these both are valid then transaction can be performed.
//				and it will update the balance and all kind of transactons at same time and
//				at last it will print the report of the bank.
//******************************************************************************************//
#include <iostream>
#include <string>
#include <cmath>
#include <iomanip>
using namespace std;
class bank								// bank class and initlaize its all data members
{										// and public functions.
private:
	float assets;
	long transcations;
public:
	int bank_num;
	int settrans();
	float setassets(float y);
	long gettrans();
	float getassets();
	bank();
	~bank();
};
bank::bank()								//bank constructor
	{
		transcations = 0;
		assets = 0;
		cout<<"bank c ";
	}
bank::~bank()								//bank destructor
{
	cout<<" bank d  ";
}
class teller								// class teller and its all data members
{											// and its public functions.
private:
	long transactions;
public:
	long employee_num;
	int bank_num;
  int gettrans();
	int settrans();
	teller();
	~teller();
};
teller::teller()							// teller constructor
	{
		transactions = 0;
		cout<<" tel c ";
	}
teller::~teller()							// teller destructor
	{
		cout<<" tel d ";
	}
class account								// class account and its data members and
{											// and its public functions.
private:
	float balance;
public:
	int bank_num;
	int accont_num;
  float getbal();
  float setbalance(float a);
	account();
	~account();
};
account::account()							// account constructor
	{
		balance = 0;
		cout<<" acc c  ";
	}
account::~account()							// account destructor
	{
		cout<<" acc d  ";
	}
float account::getbal()
	{
		return balance;
	}
float bank::setassets(float x)						// public function setassets of class bank
	{										// which update and return the assets of the bank.
		float newAssets;
		newAssets = assets + x;
		assets = newAssets;
		return assets;
	}
float account::setbalance(float k)					// public function setbalance of class account
	{										// which update and return the balance of each account
		float newbalance = balance + k;
		balance = newbalance;
		return balance;
	}
float bank::getassets()						// public function getassets of class bank
	{										// which return the assets of the bank.
		return assets;
	}
int bank::settrans()						// public function settrans of class bank
	{										// which returns transactions and update it.
	return ++transcations;
	}
long bank::gettrans()						// public function getrans of class bank
	{										// which returns the numbers of transactions
		return transcations;				// of the bank.
	}
int teller::gettrans()					// public function settrnas of class teller
	{										// which update the transactons of each teller.
		return transactions;
	}
int teller::settrans()						// publiic function settrans of class teller
	{										// which return tranactions.
		return ++transactions;
	}
int main()
{
	bank banks[2];							// objects of class bank.
	teller tellers[4];						// objects of class teller.
	account accounts[10];					// objects of class account.
	banks[0].bank_num = 0;					// intializing the object banks with
	banks[1].bank_num = 1;					// bank_num=0 and bank_num=1
	for (int i=0; i<4;i++)					// intializing the object tellers.
	{
		tellers[i].employee_num = i;
	}
	for (i=0; i<10; i++)					// intializing the object accouts.
	{
		accounts[i].accont_num = i;
	}
	for (i=0; i<4; i++)						// assign the tellers 0 and 1 to bank#0
	{										// and tellers 2 and 3 to bank#1
		tellers[i].bank_num = i/2;
	}
	for (i=0; i<10;i++)						// assign the accounts 0 to 4 to bank#0
	{										// and accounts 5 to 9 to bank#1
		accounts[i].bank_num = i/5;
	}
	// This is the do_while loop which will continue until user don't want to enter other
	// transaction.
	char reply;
	do
	{
		int j,l;
		float k;
		cout<<"****************************************************************************"<<endl;
		// Here prompting the user to enter the teller number and if teller num is more than
		// three it will ask the user reenter again.
		cout<<"\n Please enter the teller number : ";
		cin>>l;
		if (l>3)
		{
			cout<<"****************************************************************************"<<endl;
			cout<<"teller number does not exist. "<<endl;
			cout<<"\n Please enter the teller number : ";
			cin>>l;
			cout<<"****************************************************************************"<<endl;
		}
		// Here prompting the user to enter the account number and if account num is more than
		// nine it will ask the user reenter again.
		cout<<"\n Please enter the account number : ";
	  cin>>j;
		if (j>9)
		{
			cout<<"****************************************************************************"<<endl;
			cout<<"account number does not exist. "<<endl;
			cout<<"\n Please enter the account number : ";
			cin>>j;
			cout<<"****************************************************************************"<<endl;
		}
		// This while loop check that enterd teller number and account number is of the same bank
		// or not and if it is not same it will reprompt the user for teller number and account
		// number and if it is valid than it will allow the customer to enter the transacion amount.
		while (tellers[l].bank_num != accounts[j].bank_num)
		{
			cout<<"****************************************************************************"<<endl;
			cout<<"****  teller number and account number is wrong  ****"<<endl;
			cout<<"****************************************************************************"<<endl;
			cout<<"Please enter the teller number and account number again "<<endl;
			cout<<"\n Please enter the teller number : ";
			cin>>l;
			cout<<"\n Please enter the account number : ";
	    cin>>j;
		}
		do
		{
			cout<<"\n Please enter the transcation amount : $ ";
			cin>>k;
			// This if statement check the balance of the entered account if there is not enough
			// balance then it will not allow the customer to withdraw the money.
	    if(k + accounts[j].getbal() < 0)
			{
				cout << "There is not enough balance in your account to withdraw money \n";
			}
		}while(k+accounts[j].getbal() < 0);
		int num;
		num = tellers[l].bank_num;
		cout<<"****************************************************************************"<<endl;
		cout<<endl<<"The last transaction entered is : $ "<<k<<endl;
		cout<<"The total Assest for bank is  : $ "<<banks[num].setassets(k)<<endl;
		cout<<"The balance in this account is:  $ "<<accounts[j].setbalance(k)<<endl;
		cout<<"The total number of transaction for this bank is : "<<banks[num].settrans()<<endl;
		cout<<"The total number of transaction for this teller is : "<<tellers[l].settrans()<<endl;
		cout<<"****************************************************************************"<<endl;
		cout<<"\nDo you want to enter another transaction press y/Y : ";
		cin>>reply;
		cout<<"****************************************************************************"<<endl;
		}while (tolower(reply) == 'y');
		// This while loop here ask for the BANK REPORT and if yes enter y/Y.
		char data;
		cout<<"****************************************************************************"<<endl;
	  cout<<"****************************************************************************"<<endl;
		cout<<"Do you want to see the REPORT of the bank if yes please press y/Y : ";
		cin>>data;
		// This while loop here ask for bank number for looking the REPORT of the bank.
		// it is switch statement and case '0' for BANK#0 and case '1' for BANK#1.
		while(tolower(data) == 'y')
		{
			cout<<"****************************************************************************"<<endl;
			cout<<"enter: 0 :for DATA REPORT of BANK#0 \n"
				<<"enter: 1 :for DATA REPORT of BANK#1 \n";
			int select;
			cin>>select;
			switch(select)
			{
			case 0:
				{
				cout<<"****************************************************************************"<<endl;
				cout<<" DATA OF THE THE BANKS IS AS BELOW :  "<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"BANK NUMBER : "<<banks[0].bank_num<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"BANK TRANSACTIONS : "<<banks[0].gettrans()<<" | "
				<<"TOTAL BANK ASSETS : $ "<<banks[0].getassets()<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
				cout<<"|"<<"TELLER NUMBER "<<"|"<<" TELLER TRANSACTIONS "<<"|"<<endl;;
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
			for (int l=0; l<2; l++)
			{
				cout<<"| "<<setw(4)<<tellers[l].employee_num <<"     |"<<setw(11)<<tellers[l].gettrans()<<setw(13)<<" | "<<endl;
			}
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
				cout<<"|"<<"ACCOUNT NUMBER "<<"|"<<" ACCOUNT BALANCE "<<" |"<<endl;
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
			for (int j=0; j<5;j++)
				{
					cout<<"| "<<setw(4)<<accounts[j].accont_num<<"      |"<<setw(11)<<accounts[j].getbal()<<setw(11)<<" | "<<endl;
				}
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
				}
			break;
			case 1:
				{
				cout<<"****************************************************************************"<<endl;
				cout<<" DATA OF THE THE BANKS IS AS BELOW :  "<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"BANK NUMBER : "<<banks[1].bank_num<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"BANK TRANSACTIONS :"<<banks[1].gettrans()<<" | "
				<<"TOTAL BANK ASSETS : $ "<<banks[1].getassets()<<endl<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
				cout<<"|"<<"TELLER NUMBER "<<"|"<<" TELLER TRANSACTIONS "<<"|"<<endl;;
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
			for (int l=2; l<4; l++)
			{
				cout<<"| "<<setw(4)<<tellers[l].employee_num <<"     |"<<setw(11)<<tellers[l].gettrans()<<setw(13)<<" | "<<endl;
			}
				cout<<"|"<<"--------------------------------------"<<"|"<<endl;
				cout<<"****************************************************************************"<<endl;
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
				cout<<"|"<<"ACCOUNT NUMBER "<<"|"<<" ACCOUNT BALANCE "<<" |"<<endl;
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
			for (int j=5; j<10; j++)
			{
				cout<<"| "<<setw(4)<<accounts[j].accont_num<<"      |"<<setw(11)<<accounts[j].getbal()<<setw(11)<<" | "<<endl;
			}
				cout<<"|"<<"-------------------------------------"<<"|"<<endl;
			}
		break;
		default:
				cout<<"You entered the wrong select : "<<endl;
				cout<<"****************************************************************************"<<endl;
				}
				cout<<"Do you want to see the report again or for other bank please enter y/Y \n";
				cin>>data;
				cout<<"****************************************************************************"<<endl;
			}
	return 0;
}
```

