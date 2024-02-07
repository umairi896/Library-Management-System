# Library-Management-System

Asalamo Aluikum...and have a nice day!
NAME : 	 UMAIR AZIZ
REG.NO : 20-CP-47 (ALPHA)
PROJECT NAME : LIBRARY MANAGEMENT SYSTEM
This Readme file contains the detailed explanation of code of library management system project that is written in C++ language. I shall explain every part of my code separately.

////Feautres of Project////////
First of all, i will describe the features of my project. 
It contains following features:
* Add a book
* Sort all books
* Search a book
* Display all books
* Delete a book
* Modify or update a book

///////////////////////////////////
//////////Header Files/////////////
//////////////////////////////////

#include<iostream>: iostream stands for standard input-output stream. This header file contains definitions to objects like cin, cout etc.... This header file is used 		to handle the data being read from a file as input or data being written into the file as output.
#include<iomanip>: The header <iomanip> consists of functions that are used to manipulate the output of the program.
#include<fstream>: The header <fstream> is inluded to create files and store and read information from the files.
#include<conio.h>: This header declares several useful library functions for performing "console input and output" from a program.  
#include<string.h>: It is included to use strings in the program.
#include<stdio.h>: stdio. h is the header file for standard input and output. This is useful for getting the input from the user(Keyboard) and output result text to 		the monitor(screen). Without this header file, one can not display the results to the users on the screen or cannot input the values through the keyboard.   
#include <cstdlib>: This header defines several general purpose functions, including dynamic memory management, random number generation, communication with the 		environment, integer arithmetics, searching, sorting and converting. It is included to use functions to convert strings to integers and floats.
#include <windows.h>: This library is used for control of cursor position on console.

//////////////////////////////////////
//////function prototypes/////////////
//////////////////////////////////////

This section of code contains all the functions that i had declared first and i had used in my program. Mostly, functions perform similar function but i had used separate function for each operation that makes the code easy to understand. Beow is the list of used functions:
void gotoxy(short , short ); 
void display(); 		//display function
void add();     		//add function
void search();  		//search function
void sort();    		//sort function
void del();     		//delete function
void modify();  		//modify function
void sbyname(); 		//search by name
void sbyid();   		//search by id
void sbycategory();  		//search by category
void sbypubcom();    		//search by publcation company
void sbypubyear();   		//search by publishing year
void sbyauthor();    		//search by author
void sortas();     		//sort in ascending order
void sortds();     		//sort in descending order
void sortasname(); 		//sort in ascending order by name
void sortasid();   		//sort in ascending order by id
void sortascategory();  	//sort in ascending order by category
void sortaspubcom();   		//sort in ascending order by publication company
void sortaspubyear();  		//sort in ascending order by publication year
void sortasauthor();  		//sort in ascending order by author
void sortdsname();   		//sort in descending order by name
void sortdsid();     		//sort in descending order by id
void sortdscategory();  	//sort in descending order by category
void sortdspubcom();    	//sort in descending order by publication company
void sortdspubyear();  		//sort in descending order by publication year
void sortdsauthor();    	//sort in descending order by author
void dbyname();    		//delete by name
void dbyid();      		//delete by id
void dbycategory();  		//delete by category
void dbypubcom();    		//delete by publication company
void dbypubyear();   		//delete by publication year
void dbyauthor();    		//delete by author
void mbyname();      		//modify by name
void mbyid();       		//modify by id
void mbycategory();  		//modify by cateory
void mbypubcom();    		//modify by publication company
void mbypubyear();    		//modify by publication year
void mbyauthor();    		//modify by author

I shall explain every function separately that is declared in functions prototypes and below it is defined in my code. 

/////structure of name book/////

After declaration of functions, i had used a structure of book globally in which members of library are declared. Members are actually the feautres that i had discussed above.
I had used integer type variable for bookid and book publication year (bookpubyear).
Also, i had used 5 array of character type and declared their indexes as: 
bookname[60], authorname[40], bookcategory[20], bookpubcom[30], bookpubmonth[10].

//////Global Variable and Array//////////

After sturcture of book, i had used Global array and one global integer-type variable 'n' that is intialized to 0. This shows that initially there is no record present. So, first of all, we had to add the record of books in library. 
I had used Global array of 1000 size b/c i wanted to use this array in functions as well as in main functions. For example, if we want any searching in my program than i had used this array in that function.
And the next global variable is used for record that i had initialized to 0. For example, if we want to add any record than this 'n' will check that on which index our record gets store. Similarly, in display, sort functions and in loops it is used. As initially, i had no record thats'why, 'n' is 0.

******************************************
***Brief introduction of Functions used***
******************************************
1. Add Function: Whenever the add function is called the program takes the data members of the structure for the element at nth index of array from the user. And then at the end, it increments n variable by one so that the next time record is to be stored in next index.
2. Sort Function: First of all, it asks the user to sort by ascending or descending order. Then it asks whether you want to sort by name, id or author e.t.c. Then it uses bubble sort mechanism to sort it.
3. Search Function: First of all it asks the user to search by name, id or author and when we select any of them, it will move to next window where we are able to search it.
4. Display Function: It simply uses a loop to display all the records present in the array of structures.
5. Delete Function: First of all, it runs a search function to find the position of record to be deleted. For example, if we want to delete the data at 4 index, then the data at 5 index is copied to 4 index and 4 index data gets removed and then similarly, coming indexes data is copied to the one coming previous one, and at the end the last 02 indexes data gets same, so last index  data gets deleted. After this 1 is decremented from 'n' and when we go to display function it will show n-1 elements only b/c one has been deleted.
6. Modify and Update Function: First of all, it asks the user which data member we want to modify and then search the record using that data member and asks for the new value of data member. 

Now, I shall explain every function separately that is declared in functions prototypes and below is the explanation of these functions. The working of mostly functions are same, thats'why i shall explain one from same category functions.

First of all, i shall explain our main function.
//////////////////////////////////////
//////////Main function//////////////
/////////////////////////////////////

First of all, in this function, "cls" command will clear the screen and then i had used a while-loop to output the name of project and a brief introduction about myself and then the feautres of the project is shown. Then, i had used a gotoxy function that specifies the position of the cursor. At last, i had used a switch statement to prompt from the user which category he/she wants to select whether he/she wants to add the book, search a book e.t.c. Whichever category we wants to select, simply press the prescribed button as shown, to move to that window. As, there is no any record so it is required to first add a book along with all its information and then we can display it, modify or sort it e.t.c.
And if we want to move back to main menu, we press any button from keyboard , it will move to main menu b/c i had used while-loop with True(1). 

//////////////////////////////////////
/////////Display Function/////////////
/////////////////////////////////////

In this function, if the books are added then it will show the book name, id, publication company, publication month and year. And if there is no book in the library then it will show no book record. Thats'why, first of all we had to enter the book in the library.
In this function, it simply outputs/displays the data/Record of the books that is entered in the add function. I had used a for-loop so as many books records i had entered in add function must be displayed here.

//////////////////////////////////////
///////////Add Function//////////////
/////////////////////////////////////

In this function, first of all, it prompt the user to enter the character. If the character is 'A', then this add function is executed. As in this project, i had taken all the input using strings so i had taken two char-type array as id1 and year. Now i had used a do-while-loop, which intially excutes without any condition but on second iteration it asks the user if he/she wants to enter the record of next book or not.  This function, simply prompt the user to enter all the information regarding book including its name, id, Author name, book category, pubication company name, publication month and publication year. I had used the function for each category to get the information. When the user presses, 'n' or 'N', this function stops working and control moves to main menu.

//////////////////////////////////////
/////////Search Function/////////////
/////////////////////////////////////

This function simply prompt the user to whether he/she wants to search by name, id, author, category, publication company or publication year. As, the user input the command, then control moves to next function. As, the working of all these search functions are same, thats'why i shall discuss only from all. 

void sbyname(); 		//search by name
void sbyid();   		//search by id
void sbycategory();  		//search by category
void sbypubcom();    		//search by publcation company
void sbypubyear();   		//search by publishing year
void sbyauthor();    		//search by author

I shall discuss only search-by-name function here:
///////Search by name///////
First of all, it will prompt the user to enter a name. Then it will run the found function and find the name, if its present it will we be shown but if not it shows the message of 'Record not found.
In this function, it actually compares both strings of entered book in add function and in search function, if it finds book name it displays that Record found! and if not than it shows that Record not found!
Similarly, others functions of id, category, publication company and publication year works.

//////////////////////////////////////
///////////Sort Function/////////////
/////////////////////////////////////

In this function, First of all, it prompt the user he/she wants to sort according to ascending order or decending order. According to the user choice, it moves to sortas function or sortds function. The working of both functions is same, so thats'why i am discusing them collectively. Afterwards, it prompts the user, whether he/she wants to sort by name, id, author name, category, publication company or publication year for this i had use a switch which will move the user to that function that he had selected. As the role of each function is same thats'why i shall disuss one of them. In each function, i had used a bubble sort mechanism to sort. The only difference between ascending and desending functions is the use of iteration of loop. In desending functions, i had reversed the iteration that i had used in ascending order.

void sortas();     		//sort in ascending order
void sortds();     		//sort in descending order
void sortasname(); 		//sort in ascending order by name
void sortasid();   		//sort in ascending order by id
void sortascategory();  	//sort in ascending order by category
void sortaspubcom();   		//sort in ascending order by publication company
void sortaspubyear();  		//sort in ascending order by publication year
void sortasauthor();  		//sort in ascending order by author
void sortdsname();   		//sort in descending order by name
void sortdsid();     		//sort in descending order by id
void sortdscategory();  	//sort in descending order by category
void sortdspubcom();    	//sort in descending order by publication company
void sortdspubyear();  		//sort in descending order by publication year
void sortdsauthor();    	//sort in descending order by author

Here we will discuss, Sort in Ascending order by name:

///////Sort in Ascending order by name/////// 

In this function, i had used 2 for-loops and inside an if-statement in which bubble sort mechanism in present. After sorting, it will call the display function, where it shows the sorting. Same procedure occurs in all the sorting functions.
	
//////////////////////////////////////
/////////Delete Function/////////////
/////////////////////////////////////

In this function, First of all, it prompt the user wether he/she wants to delete according to name, id, category e.t.c. For this like all functions that i had disscussed previously i had used a switch statements that will move the user to delete by name, id, or e.t.c functions in which it delete the record. Here i had used 4 functions for delete. All have same working, so i'll disuss only one of them.

void dbyname();    		//delete by name
void dbyid();      		//delete by id
void dbycategory();  		//delete by category
void dbypubcom();    		//delete by publication company
void dbypubyear();   		//delete by publication year
void dbyauthor();    		//delete by author

///////Delete by id///////

In this function, it will prompt the user to enter the id, he/she wants to delete. It will the id, if id not found meassage is shows that record not found! If found the record than it will store the location in 'i' variable and move the iteration to n-1 b/c last record gets deleted.

//////////////////////////////////////
/////////Modify Function/////////////
/////////////////////////////////////

In this function, First of all, it prompt the user wether he/she wants to modify according to name, id, category e.t.c. For this like all functions that i had disscussed previously i had used a switch statements that will move the user to modify by name, id, or categories e.t.c functions. Here i had used 4 functions for modify or update. All have same working, so i'll disuss only one of them.

void mbyname();      		//modify by name
void mbyid();       		//modify by id
void mbycategory();  		//modify by cateory
void mbypubcom();    		//modify by publication company
void mbypubyear();    		//modify by publication year
void mbyauthor();    		//modify by author

///////Modify by name///////

In this function, First of all it will prompt the user to enter the old name of book. After entering the name, found function will search it. If record found, it will ask you to enter new name of book and provides a location and displays the message of Modified! If record not found, it will display the message of, Record not found!
Similarly, other functions of modify also work in similar way.

////////////////////////////////////////
/////////////gotoxy function///////////
///////////////////////////////////////

This function is basically used to handle that we can use to write on the console. 'SetConsoleCursorPosition' then uses that handle and the coordinates you specified to place the blinking cursor in your command prompt. We can say that it generally makes a graph on console, and whatever the value we give to x and y, it will blink the cursor to that position.

//////////////////////////////////////////
/////////End of Code ////////////////////
/////////////////////////////////////////
