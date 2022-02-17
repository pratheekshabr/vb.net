# vb.net
using System; <br>
namespace Exercises <br>
{ <br>
 class BinaryTriangle<br> 
 { <br>
 static void Main(string[] args)<br> 
 { <br>
 int number,digit=1; <br>
 Console.Write("\nEnter the number of lines: "); <br>
 number = Convert.ToInt32(Console.ReadLine()); <br>
 for(int i=1; i<=number; i++) <br>
 { <br>
 for(int space=number-i; space>0; space--) <br>
 { <br>
 Console.Write(" "); <br>
 } <br>
 for(int j=0; j<i; j++) <br>
 { <br>
 Console.Write(digit + " "); <br>
 digit = (digit==1) ? 0:1; <br>
 }<br> 
 Console.Write("\n"); <br>
 } <br>
 } <br>
 } <br>
} <br>
output:

![image](https://user-images.githubusercontent.com/97940277/154424310-683c4e72-1d56-42de-8157-6305eb621de2.png)<br>


