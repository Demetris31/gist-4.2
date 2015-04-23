#include <iostream>
#include <fstream>
#include <stdlib.h>
#include <conio.h>

using namespace std;

int m,n;
int x=0,sum=0,b[10];


int PRNT(int**array1)
{
	for(int i=0; i<m; i++)
	{
	     for(int j=0; j<n; j++)
	     {
	     	cout << array1[i][j]<< "\t";
	     }
	     cout << "\n";
	}       
	return 0;	
}

int OBR(int**array2)
{
	for(int i=0; i<m; i++)
	{
		for(int j=0; j<n; j++)
		{
			x = array2[0][j];
			if(x < array2[i][j]) x = array2[i][j];
			else j++;
		}
	}
	
	int i;
	
	for(i=0; i<n; i++)
	{
		b[i] = x;
		cout << "\nMax elements of columns: " << b[i] << "\n";
		sum+=b[i];
		cout << "\nSum of max elements: " << sum;
	}
	return 0;
}

int INPT()
{
	cout << "Write the number of rows: ";
    cin >> m;
    cout << "Write the number of columns: ";
    cin >> n;
    
    int**array = new int*[m];
    for(int i=0; i<m; i++)
	{
        array[i] = new int[n];
        for(int j =0; j<n; j++)
		{
            array[i][j] = rand()%100;
        }
    }
	PRNT(array);
    OBR(array);
    return 0;
}

int main()
{
//	setlocale(LC_ALL,"Russian");
	INPT();
}
