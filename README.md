# super-giggle
#include <iostream> 
#include <string> 
#include <iomanip> 
using namespace std; 
int main() 
{ 
  
cout << "=================================================" << endl; 
cout << " Program: GPA CALCULATOR" << endl; 
cout << " Author : [Irfan Danial]" << endl; 
cout << "=================================================" << endl; 
 
 
const int SIZE = 2; // Fixed size for now, nanti baru tukar ikut user nak 
string subjects[SIZE]; 
int credits[SIZE]; 
float scores[SIZE]; 
string grades[SIZE]; // To store letter grades (A, B+, etc.) 
float points[SIZE]; // To store grade points (4.0, 3.7, etc.) 
 
 
for(int i = 0; i < SIZE; i++) 
{ 
cout << "\nEnter details for subject " << (i + 1) << ":" << endl; 
cout << "Name of Subject: "; 
if(i>0) 
 cin.ignore(); 
getline(cin, subjects[i]); 
do 
{ 
cout << "Credit Hours (1-4): "; 
cin >> credits[i]; 
if(credits[i] < 1 || credits[i] > 4) 
{ 
cout << "Invalid credit hours! Enter between 1-4." << endl; 
} 
} 
while(credits[i] < 1 || credits[i] > 4); 
do 
{ 
cout << "Total Score (0-100): "; 
cin >> scores[i]; 
if(scores[i] < 0 || scores[i] > 100) 
{ 
cout << "Invalid score! Please enter between 0-100." << endl; 
} 
} 
 
while(scores[i] < 0 || scores[i] > 100); 
} 
 
for(int i = 0; i < SIZE; i++) 
{ 
if(scores[i] >= 80) 
{ 
grades[i] = "A"; 
points[i] = 4.0; 
} 
else if(scores[i] >= 75) 
{ 
grades[i] = "A-"; 
points[i] = 3.7; 
} 
else if(scores[i] >= 70) 
{ 
grades[i] = "B+"; 
points[i] = 3.3; 
} 
else if(scores[i] >= 65) 
{ 
grades[i] = "B"; 
points[i] = 3.0; 
} 
else if(scores[i] >= 60) 
{ 
grades[i] = "B-"; 
points[i] = 2.7; 
} 
else if(scores[i] >= 55) 
{ 
grades[i] = "C+"; 
points[i] = 2.3; 
} 
else if(scores[i] >= 50) 
{ 
grades[i] = "C"; 
points[i] = 2.0; 
} 
else if(scores[i] >= 47) 
{ 
grades[i] = "C-"; 
points[i] = 1.7; 
} 
else if(scores[i] >= 44) 
{ 
grades[i] = "D+"; 
points[i] = 1.3; 
} 
else if(scores[i] >= 40) 
{ 
grades[i] = "D"; 
points[i] = 1.0; 
} 
else if(scores[i] >= 0) 
{ 
grades[i] = "E"; 
points[i] = 0.0; 
} 
} 
 
float totalQualityPoints = 0; 
int totalCredits = 0; 
// Calculate quality points for each subject 
for(int i = 0; i < SIZE; i++) 
{ 
float qualityPoints = points[i] * credits[i]; 
totalQualityPoints = totalQualityPoints + qualityPoints; 
totalCredits = totalCredits + credits[i]; 
} 
// Calculate GPA 
float gpa = totalQualityPoints / totalCredits; 
 
cout << "\nCalculation verification:" << endl; 
cout << "Total Quality Points: " << totalQualityPoints << endl; 
cout << "Total Credits: " << totalCredits << endl; 
cout << "GPA: " << fixed << setprecision(2) << gpa << endl; 
 
cout << "\n=========================================================\n"; 
cout << "INDEX  SUBJECT   CREDIT  SCORE  GRADE  POINT\n"; 
cout << "=========================================================\n"; 
 
for(int i = 0; i < SIZE; i++) 
{ 
cout << left << setw(4) << (i + 1) << "    "; 
cout << left << setw(10) << subjects[i] << ""; 
cout << right << setw(2) << credits[i] << "     "; 
cout << right << setw(3) << scores[i] << "    "; 
cout << left << setw(4) << grades[i] << " "; 
cout << fixed << setprecision(2) << points[i] << endl; 
} 
 
cout << "=========================================================\n"; 
cout << "Your GPA for this semester: " 
<< fixed << setprecision(2) << gpa << endl; 
cout << "=========================================================\n"; 
 
return 0; 
 
}
