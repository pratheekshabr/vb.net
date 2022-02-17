# vb.net
using System; <br>
namespace Exercises 
{ 
 class BinaryTriangle 
 { 
 static void Main(string[] args) 
 { 
 int number,digit=1; 
 Console.Write("\nEnter the number of lines: "); 
 number = Convert.ToInt32(Console.ReadLine()); 
 for(int i=1; i<=number; i++) 
 { 
 for(int space=number-i; space>0; space--) 
 { 
 Console.Write(" "); 
 } 
 for(int j=0; j<i; j++) 
 { 
 Console.Write(digit + " "); 
 digit = (digit==1) ? 0:1; 
 } 
 Console.Write("\n"); 
 } 
 } 
 } 
} 
output
![image](https://user-images.githubusercontent.com/97940277/154424310-683c4e72-1d56-42de-8157-6305eb621de2.png)<br>
