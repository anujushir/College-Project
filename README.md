# College-Project
//Vending Mchine System ,This is c++ code for VENDING MACHINE

//============================================================================
// Name        : PROJECT_Anuj_Ushir.cpp
// Author      : Anuj Pandit Ushir
// Version     :
// Copyright   : Your copyright notice
// Description : Hello World in C++, Ansi-style
//============================================================================

#include<iostream>
using namespace std;
class FoodShop
{
	public:
	 static int card_info;
	    FoodShop()
	    {
	    		cout<<endl;

	    }
	    ~FoodShop()
	    {
	    }
	static void input()
	    {
			cout<<"******************************************************************"<<endl;
	        cout<<"\n Swipe your Food Shop card:"<<card_info<<endl;
	        cout<<"******************************************************************"<<endl;

	    }
	inline void output()
	    {

	    cout<<"Your card has been scanned successfully,Plz remove your card"<<endl;
	    cout<<"******************************************************************"<<endl;

	    }
};
int FoodShop::card_info;
class Snacks:virtual public FoodShop
{
	public:
	int ch;
		void get()
		{
		do
		{

		cout<<"What kind of Snacks would you like to have:::"<<endl;
		cout<<" 1.Chips =₹10"<<endl;
		cout<<" 2.Pizza =₹100 "<<endl;
		cout<<" 3.Burger =₹50 "<<endl;
		cout<<" 4.Samossa =₹20"<<endl;
		cout<<" 5 Fries =₹40"<<endl;

		cout<<"Enter Your  choice Number:"<<endl;
		cin>>ch;
		cout<<"******************************************************************"<<endl;
		switch(ch)
		{
			case 1:
							cout<<"You have ordered CHIPS"<<endl;
							break;
			case 2:
							cout<<"You have ordered PIZZA"<<endl;
							break;
			 case 3:
							cout<<"You have ordered BURGER"<<endl;
							break;
			case 4:
							cout<<"You have ordered SAMOSSA"<<endl;
							break;
		 	case 5:
		 	  			cout<<"You have ordered FRIES "<<endl;
		 	  			break;
		}
		}while(ch<1);
		cout<<"******************************************************************"<<endl;
		}
	void put()
	{

		cout<<"Your order is Ready"<<endl;
		cout<<"******************************************************************"<<endl;
	}
		 	};
class Drinks:virtual public FoodShop
{
	public:
	int ch;
		void in()
		{
		do	{

		cout<<"What kind of Drinks would you like to have:::"<<endl;
		cout<<" 1.Water =₹10"<<endl;
		cout<<" 2.Coke =₹20 "<<endl;
		cout<<" 3.Lassi =₹50 "<<endl;
		cout<<" 4.Mango Juice =₹20"<<endl;
		cout<<" 5.Cold Coffee =₹50"<<endl;

		cout<<"Enter Your  choice Number:"<<endl;
		cin>>ch;
		cout<<"******************************************************************"<<endl;

		switch(ch)
		{
			case 1:
							cout<<"You have ordered WATER"<<endl;
							break;
			case 2:
							cout<<"You have ordered COKE"<<endl;
							break;
			 case 3:
							cout<<"You have ordered LASSI"<<endl;
							break;
			case 4:
							cout<<"You have ordered MANGO JUICE"<<endl;
							break;
		 	case 5:
		 	  			cout<<"You have ordered COLD COFFEE "<<endl;
		 	  			break;
		}
		}while(ch<1);
		}
	void out()
	{

		cout<<"Your order is Ready"<<endl;

	}
		 	};
	class Bill:public Drinks,public Snacks
	{ public:

		int a ,b,gst=12,ft=2;
	void getdata()
	{



			cout<<"############ Bill ###########"<<endl;

			cout<<"Enter your product prize:"<<endl;
			cin>>a;




			cout<<"GST=₹12 "<<"AND"<<" food_tax=₹2"<<endl;
			cout<<"Note: Given bill is include of Taxes(GST ,food tax)"<<endl;

	}
	void putdata()
	{
		b=gst+ft+a;
		cout<<"Total bill is:  "<<b;
		cout<<endl;
		cout<<"******************************************************************"<<endl;

	}

	};

			class Order
			{
				public:

			 virtual void display()
				{
				 cout<<"******************************************************************"<<endl;
					cout<<"Put all your Garbage and Plastic in dustbin:"<<endl;

				}
			};

			class Rule:public Order
			{
				public:
		 void display()
				{
			 cout<<"*****************************************************************"<<endl;
					cout<<"KEEP COUNTRY CLEAN"<<endl;
					cout<<"******************************************************************"<<endl;
					cout<<"####Thank for visiting FoodShop ####"<<endl;
					cout<<"********************************************************************"<<endl;
				}
			};
	int main()
	{

		int c;
		cout<<"############## WELCOME_TO_FOOD_SHOP ##################"<<endl;
		do{
		cout<<"  What would you like to have ? "<<endl;
		cout<<"   1. Snacks "<<endl;
		cout<<"   2.Drinks  "<<endl;
		cout<<"     Enter Your choice:     "<<endl;
		cin>>c;


	//	Drinks d;
	//	Snacks s;
		Bill b;
		switch(c)
		{
			case 1:
			cout<<"You have choosen Snacks"<<endl;
			b.input();
		//	FoodShop::input();
			b.get();
			b.put();
			b.output();


			break;
			case 2:
			cout<<"You have choosen Drinks"<<endl;
			b.input();

			b.in();
			b.out();
			b.output();
			break;
			default :
			cout<<"You have take wrong choice "<<endl<<"plz re_enter choice"<<endl;

			break;
		}

		b.getdata();
		b.putdata();

		Order *ptr;
		Order o;
		o.display();
		Rule r;
		ptr=&r;
		ptr->display();


		}while(c<4);
	/*	Order *a;
		Order o;
		a=&o;
		a->display();
	//	o.display();*/
		cout<<"**********************************THANK YOU********************************"<<endl;
	return 0;
	}
