# Summative-Assessment-code-3
#Final submission (Vending Machine)
#include<iostream>
using namespace std;
int greeting();
int coffee();
int tea();
int restart();
int main()  //using main function
{
	int choice;
	greeting();  //calling 'greeting' function
	cout << "\n\t\t\tToday's menu includes Coffee and Tea, please choose one of the two.\n\t\t\tEnter 1 for Coffee and 2 for Tea\n\t\t\tWhat would you like to order : ";
	cin >> choice;
	while (cin.fail() != 0)
	{
		cout << "\n\t\t\tInvalid Command. \n\t\t\tPlease enter a number : ";
		cin.clear();
		cin.ignore();
		cin >> choice;
	}
	switch (choice)  //using switch statement
	{
	case 1:     //if user enters '1' then it will call the 'coffee' function
		coffee();
		break;
	case 2:    //if user enters '2' then it will call 'tea' function
		tea();
		break;
	default:   //default case if the user enters any other number 
		cout << "\a\n\t\t\tSorry the number you entered is incorrect.\n\t\t\tPlease enter either 1 or 2 to place an order : ";
		cin >> choice;
		if (choice == 1)
		{
			coffee();
		}
		else if (choice == 2)
		{
			tea();
		}
		else
		{
			cout << "\a\t\t\tIncorrect command. Sorry we don't have the drink you want ";
		}
		break;
	}
	restart();  //calling 'restart' function to ask the user if he wants to order again
}
int greeting()  //user-defined function
{
	for (int j = 0; j <= 58; j++)
	{
		cout << "--";
	}
	cout << "\n\t\t\t\tHello customer! Welcome to the VENDING MACHINE.\n";
	for (int j = 0; j <= 58; j++)
	{
		cout << "--";
	}
	cout << "  \n\t\t\t\t\t  ____ ____   _____  _____             ";
	cout << " \n\t\t\t\t\t |    |    | |      |     | |     |";
	cout << " \n\t\t\t\t\t |    |    | |_____ |     | |     |";
	cout << " \n\t\t\t\t\t |    |    | |      |     | |     |";
	cout << " \n\t\t\t\t\t |    |    | |_____ |     | |_____|";
	cout << "\n";

	string coffdrinks[3] = { "Iced Coffee","Milk Coffee","Black Coffee" };
	string teadrinks[3] = { "Iced Tea","Milk Tea","Black Tea" };
	int coffmon[3] = { 3,2,1 };
	int teamon[3] = { 3,2,1 };
	cout << "\n\t\tCoffee\t\t\tPrice (AED)\t\tTea\t\t\tPrice(AED)";
	for (int i = 0; i < 3; i++)
	{
		cout << "\n\t\t" << coffdrinks[i] << "\t\t" << coffmon[i] << "\t\t\t" << teadrinks[i] << "\t\t" << teamon[i];
	}
	return 0;
}
int coffee()
{
	char sugar, coffeetype;
	int entermoney, quantity, totalmoney, remainmoney;
	cout << "\n\t\tYou selected coffee. Enter 'I' for Iced Coffee, 'M' for Milk Coffee, 'B' for black coffee : ";
	cin >> coffeetype;
	switch (coffeetype)   //using switch statement
	{
	case 'I':   //if user enters 'i' or 'I' then this case will execute
	case 'i':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Iced Coffee with sugar.";
			totalmoney = quantity * 3;
			cout << "\n\t\t\tTotal : " << totalmoney;  //display the total money
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)  //if money entered is greater than or equal to 'totalmoney' then if statement will execute
			{
				remainmoney = entermoney - totalmoney;   //calculating remaining money
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else  //if money entered is less than 'totalmoney' then else atatement will be executed
			{
				do {    //using do-while loop
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Iced Coffee without sugar.";
			totalmoney = quantity * 3;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	case 'M':
	case 'm':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Milk Coffee with sugar.";
			totalmoney = quantity * 2;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Milk Coffee without sugar.";
			totalmoney = quantity * 2;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	case 'B':
	case 'b':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Black Coffee with sugar.";
			totalmoney = quantity * 1;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Black Coffee without sugar.";
			totalmoney = quantity * 1;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	default:   //if user enters any other character other than 'I' , 'M' , 'B' for example 'o' it will ask the user to enter again
		cout << "\n\t\t\tYou entered incorrect option.\n\t\t\tEnter 'I' for Iced Coffee, 'M' for Milk Coffee, 'B' for Black Coffee : ";
		cin >> coffeetype;
		coffee();
		break;
	}
	return 0;
}
int tea()
{
	char sugar, teatype;   //declaring variables
	int entermoney, quantity, totalmoney, remainmoney;
	cout << "\n\t\t\tYou selected tea. Enter 'I' for Iced Tea, 'M' for Milk Tea, 'B' for Black Tea : ";
	cin >> teatype;
	switch (teatype)
	{
	case 'I':
	case 'i':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Iced Tea with sugar.";
			totalmoney = quantity * 3;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Iced Tea without sugar.";
			totalmoney = quantity * 3;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	case 'M':
	case 'm':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Milk Tea with sugar.";
			totalmoney = quantity * 2;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! "<< quantity << " Milk Tea without sugar.";
			totalmoney = quantity * 2;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	case 'B':
	case 'b':
		cout << "\n\t\t\tWould you like to add sugar (Y/N): ";
		cin >> sugar;
		switch (sugar)
		{
		case 'Y':
		case 'y':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Black Tea with sugar.";
			totalmoney = quantity * 1;
			cout << "\n\t\t\tTotal : " << totalmoney;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		case 'N':
		case 'n':
			cout << "\n\t\t\tHow many would you like to buy : ";
			cin >> quantity;
			while (cin.fail() != 0)
			{
				cout << "\n\t\t\tInvalid number entered.\n\t\t\tPlease enter a valid number : ";
				cin.clear();
				cin.ignore();
				cin >> quantity;
			}
			cout << "\n\t\t\tAlright! " << quantity << " Black Tea without sugar.";
			totalmoney = quantity * 1;
			cout << "\n\t\t\tTotal : " << totalmoney ;
			cout << "\n\t\t\tPLease enter the money : ";
			cin >> entermoney;
			if (entermoney >= totalmoney)
			{
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			else
			{
				do {
					cout << "\n\t\t\tInsufficient money. Enter money again : ";
					cin >> entermoney;
				} while (entermoney < totalmoney);
				remainmoney = entermoney - totalmoney;
				cout << "\n\t\t\tRemaining money : " << remainmoney << " AED " << endl;
			}
			break;
		default:
			cout << "\a\n\t\t\tIncorrect command! Please enter again : ";
			cin >> sugar;
			break;
		}
		break;
	default:

		cout << "\n\t\t\tYou entered incorrect option.";

		break;
		while ((teatype != 'I' || teatype != 'i') && (teatype != 'M' || teatype != 'm') && (teatype != 'B' || teatype != 'b')) {
			cout << "\n\t\t\tEnter 'I' for Iced Tea, 'M' for Milk Tea, 'B' for Black Tea : ";
			cin >> teatype;
			tea();
		}
	}
	return 0;
}
int restart()
{
	string yesorno;
	cout << "\n\t\t\tDo you want to order again ('YES' if you want to and 'NO' if you don't want to) : ";
	cin >> yesorno;
	if (yesorno == "YES" || yesorno == "yes")//if user enters 'YES' or 'yes' then control will be shifted to main function
	{
		main();
	}
	else   //if user enters 'NO' or 'no' then the program will end with the following message
	{
		cout << "\n\t\t\tTHANK YOU FOR VISITING US\n\t\t\tHave a nice day";

	}
	return 0;
}
