\\MY-CAR-PARKING-PROJECT
#include<iostream>
#include<vector>
#include<sstream>
using namespace std;
int main()
{    int password,choice,slotno,booked=1,time;
string username;
	vector<string> usernames={"AHMED","USMAN","IHTISHAM","SIR NADEEM","TAHIR","ABDULREHMAN","DAIM","OWAIS","ZUBAIR","SHUJAH","AKHTAR","NASIR","ABBAS","ABDULLAH","SAIM","QAISER","AMEER","ZULFIQAR","MOOSA","ALI","SAAD","REHMAN","HUSSAIN","HASSAN","MOHAMMAD","AHSAN","DANISH","FAHAD","INSHAL","ASGHAR"};
    vector<int>     passcode={65235   ,63682,   76598,     90876,12300,44453,90324,45119,44322,87687,45092,12312,34576,11876,23409,34908,11151,43256,12097,12353,12945,88811,87124,29086,98237,44565,14266,33333,29343,15523	};
    int slot[50]={0};
     int j=0;
	 do {
    int login=0;	
	cout<<"\n___CHOOSE ONE OPTION FOR CONTINUATION"<<endl<<"1)_ LOGIN "<<endl<<"2)_ REGISTRATION"<<endl;
    cin>>choice;
    if (choice==1){
	 cout<<" PLZ ENTER YOUR USERNAME TO PROCEED:-    ";
     cin>>username; 
     cout<<"\nPLZ ENTER YOU PASSWORD TO PROCEED:-    ";
     cin>>password; 
     for (int i=0;i<usernames.size();i++)
     {
     	if (usernames[i]==username&&passcode[i]==password)
     	{
     		cout<<"\n>LOGIN SUCESSFUL   WELCOME TO RIPHAH INTERNATIONAL UNIVERSITY CAR PARKING<"<<endl;
     		cout<<"_______________________________________________________________________________"<<endl;
     		login++;
     		cout<<endl<<"NAME:-"<<usernames[i]<<endl;
		 }
	 }
	 if (login==0)
	 {
	 	
	 	cout<<"\nWRONG USERNAME OR PASSWORD?____"<<endl<<"\nWE ARE NOT ALLOWED TO ENTER YOUR CAR IN PARKING"<<endl<<"\n OR CONTACT YOUR SSD OFFICE TO REGISTER YOUR CAR";
	
	 }   
	 
}
if (choice==2)
{
    
	int password2;
	string username2;
	cout<<"ENTER YOUR  USERNAME\n ____";
	cin>>username2;
	cout<<"ENTER YOUR  PASSWORD\n______";
	cin>>password2;
	usernames.push_back(username2);
	passcode.push_back(password2);
}

if (login==1)
{  
cout<<"****************************************PLZ ENTER YOUR CAR DETAILS TO PROCEED ****************************************"<<endl;
struct car_details{  int PLATE_no; int  Model ; string Car_name ; string Colour;
};
 car_details   cardetails[50];
 cout<<" PLATE NO  ";
 cin>>cardetails[j].PLATE_no;
 cout<<" MODEL ";
 cin>>cardetails[j].Model;
 cout<<" CAR NAME  ";
 cin>>cardetails[j].Car_name;
 cout<<" Colour ";
 cin>>cardetails[j].Colour;
    for (int r=0;r<50;r++){
	cout<<"\n CHOOSE ANY SLOT FROM 50"<<endl;
	cin>>slotno;
	if (slot[slotno]!=booked)
	{
	slot[slotno]=booked;
	cout<<"\n``````````````HOW MUCH TIME YOU WANT TO PARK YOUR CAR AT THE SLOT```````````````";
	cin>>time;
	switch (time){
	 case 1:    cout<<"PLZ PAY 500 RUPEES!!!!";  break;
	 case 2: cout<<"PLZ PAY 1000 RUPEES!!!!!" ;   break;
	 case 3: cout<<"PLZ PAY 1500 RUPEES!!!!";   break;
	 case 4:    cout<<"PLZ PAY 2000 RUPEES!!!!";  break;
	 case 5: cout<<"PLZ PAY 2500 RUPEES!!!!" ;   break;
	 case 6: cout<<"PLZ PAY 3000 RUPEES!!!!";   break;}
	 if (time>6&&time<=10)
	 { cout<<" PLZ PAY 3500 RUPEES!!!!"<<endl;}
	 else if (time>10)   { cout<<"PLZ PAY 5000 RUPEES!!!!";
	 }
	 cout<<"YOUR CAR MODEL IS    "<<cardetails[j].Model<<endl;
	 cout<<" _____YOU CAR NAME IS     "<<cardetails[j].Car_name<<endl;
	 cout<<"________YOUR CAR PLATE NO IS    "<<cardetails[j].PLATE_no<<endl;
	 cout<<"_____________ YOUR CAR  COLOUR IS   "<<cardetails[j].Colour<<endl;
	 cout<<"\n________________THANK_YOU__________FOR-PATIENCE"<<endl;
	 cout<<"\n*****************************_____PLZ__PARK__YOUR___CAR___AT____THE____CHOSEN___SLOT*********************** "<<endl;
	 
	     
	break;
	}
	else if (slot[slotno]==booked)
	{
		cout<<"THIS SLOT NO IS BOOKED PLZ CHOOSE ANOTHER ONE!!!!!!!!!!!!!!_____??????";
	    
	}
	
	
}}
	 j++;
} while(j<100);
return 0;}
