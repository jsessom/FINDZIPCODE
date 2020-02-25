# FINDZIPCODE
TRIES TO FIND ZIPCODE
#include<iostream>
#include<fstream>
#include<regex> 
#include<cstdlib>
#include<string>
using namespace std;


int main() 
{
	// string to search
	regex zipcode("(77004)(.*)");

	
	ifstream Accountfile("real_acct.txt"); // read from account file

	int counter = 0;
	//if we cant open the file
	if (!Accountfile) {
		cout << "Uh oh, sorry this file could not be opened! \n";
		exit(1);
	}

	//if the file can open
	while (Accountfile)
	{

		string data;
		Accountfile >> data;

		if (regex_match(data, zipcode)) 
		{
			counter++;
			cout << counter << endl;
		}


	}

	return 0;
}
