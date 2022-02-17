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

<br>
2. C# Program to Check Whether the Entered Number is an Amicable Number  or Not. 
using System; <br>
namespace Exercises <br>
{ <br>
 class AmicableNumber <br>
 { <br>
 static void Main(string[] args) <br>
 { <br>
 int num1, num2, sum1=0, sum2=0; <br>
 Console.WriteLine("\n--------AMICABLE NUMBERS-----------\n");  Console.Write("\nEnter the first number: "); <br>
 num1 = Convert.ToInt32(Console.ReadLine()); <br>
 Console.Write("\nEnter the second number: "); <br>
 num2 = Convert.ToInt32(Console.ReadLine()); <br>
 for(int i=1; i<num1; i++) <br>
 { <br>
 if(num1%i == 0) <br>
 { <br>
 sum1 += i; <br>
 } <br>
 } <br>
 for(int i=1; i<num2; i++) <br>
 { <br>
 if(num2%i == 0) <br>
 { <br>
 sum2 += i; <br>
 } <br>
 } <br>
 if(sum1 == num2 && sum2 == num1) <br>
 { <br>
 Console.WriteLine("\nThe numbers {0} and {1} are amiciable.", num1, num2);  } <br>
 else <br>
 { <br>
 Console.WriteLine("\nThe numbers {0} and {1} are not amiciable.", num1, num2);  } <br>
 } <br>
 } <br>
}<br>

Output:
![image](https://user-images.githubusercontent.com/97940277/154425770-736ffae1-e0b1-47bb-9302-dc3bb7b0f174.png)

3. C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). <br>
using System; <br>
namespace Exercises<br> 
{ <br>
 class PersonalDetails<br> 
 { <br>
 string name; <br>
 int age; <br>
 string gender; <br>
 public PersonalDetails(string name, int age, string gender) <br>
 { <br>
 this.name = name; <br>
 this.age = age; <br>
 this.gender = gender; <br>
 } <br>
 public virtual void Display() <br>
 { <br>
 Console.WriteLine("\n-------- PERSONAL DETAILS --------\n"); <br>
 Console.WriteLine("Name : " + name); <br>
 Console.WriteLine("Age : " + age); <br>
 Console.WriteLine("Gender : " + gender);<br> 
 } <br>
 } <br>
 class CourseDetails : PersonalDetails <br>
 { <br>
 int regNo;<br> 
 string course;<br> 
 int semester; 
 public CourseDetails(string name, int age, string gender, int regNo, string course, int semester)  : base(name, age, gender) 
 { 
 this.regNo = regNo; 
 this.course = course; 
 this.semester = semester; 
 } 
 public override void Display() 
 { 
 base.Display(); 
 Console.WriteLine("\n-------- COURSE DETAILS --------\n");
.NET TECHNOLOGY LAB 4 
 Console.WriteLine("Register Number : " + regNo); 
 Console.WriteLine("Course : " + course); 
 Console.WriteLine("Semester : " + semester); 
 } 
 } 
 class MarksDetails : CourseDetails 
 { 
 int[] marks = new int[5]; 
 int total; 
 float average; 
 string grade; 
 int flagFail; 
 public MarksDetails(string name, int age, string gender, int regNo, string course, int semester,  int[] marks) : base(name, age, gender, regNo, course, semester) 
 { 
 total = 0; 
 for(int i=0; i<5; i++) 
 { 
 this.marks[i] = marks[i]; 
 total += marks[i]; 
 if(marks[i]<35) 
 { 
 flagFail = 1; 
 } 
 } 
 Calculate(); 
 } 
 private void Calculate() 
 { 
 average = total/5; 
 if(flagFail == 1 || average<40) 
 grade = "Fail"; 
 else if(average>=70) 
 grade = "Distinction"; 
 else if(average>=60) 
 grade = "First Class"; 
 else if(average>=50) 
 grade = "Second Class"; 
 
.NET TECHNOLOGY LAB 5 
else 
 grade = "Pass Class"; 
 } 
 public override void Display() 
 { 
 base.Display(); 
 Console.WriteLine("\n-------- MARKS DETAILS --------\n"); 
 Console.Write("Marks in 5 subjects: "); 
 for(int i=0; i<5; i++) 
 Console.Write(marks[i] + " "); 
 Console.WriteLine(); 
 Console.WriteLine("Total : " + total); 
 Console.WriteLine("Average : " + average); 
 Console.WriteLine("Grade : " + grade); 
 } 
 } 
 class MultiLevel 
 { 
 public static void Main(string[] args) 
 { 
 MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5,  new int[]{77,80,98,95,90}); 
 Student1.Display(); 
 } 
 } 
}
