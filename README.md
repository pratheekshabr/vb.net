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
output:<br>
*********<br>
![image](https://user-images.githubusercontent.com/97940277/154424310-683c4e72-1d56-42de-8157-6305eb621de2.png)<br>
***********************
2. C# Program to Check Whether the Entered Number is an Amicable Number  or Not. 
************************
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

Output:<br>
*******<br>
![image](https://user-images.githubusercontent.com/97940277/154425770-736ffae1-e0b1-47bb-9302-dc3bb7b0f174.png)<br>
*************************
3. C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). <br>
*************************
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
 int semester; <br>
 public CourseDetails(string name, int age, string gender, int regNo, string course, int semester)  : base(name, age, gender) <br>
 { <br>
 this.regNo = regNo; <br>
 this.course = course; <br>
 this.semester = semester<br>; 
 } <br>
 public override void Display()<br> 
 { <br>
 base.Display(); <br>
 Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>

 Console.WriteLine("Register Number : " + regNo); <br>
 Console.WriteLine("Course : " + course); <br>
 Console.WriteLine("Semester : " + semester); <br>
 } <br>
 } <br>
 class MarksDetails : CourseDetails<br> 
 { <br>
 int[] marks = new int[5];<br> 
 int total; <br>
 float average;<br> 
 string grade; <br>
 int flagFail; <br>
 public MarksDetails(string name, int age, string gender, int regNo, string course, int semester,  int[] marks) : base(name, age, gender, regNo, course, semester) <br>
 { <br>
 total = 0; <br>
 for(int i=0; i<5; i++) <br>
 { <br>
 this.marks[i] = marks[i]; <br>
 total += marks[i]; <br>
 if(marks[i]<35) <br>
 { <br>
 flagFail = 1; <br>
 } <br>
 } <br>
 Calculate(); <br>
 } <br>
 private void Calculate()<br> 
 { <br>
 average = total/5; <br>
 if(flagFail == 1 || average<40) <br>
 grade = "Fail"; <br>
 else if(average>=70) <br>
 grade = "Distinction"; <br>
 else if(average>=60) <br>
 grade = "First Class"; <br>
 else if(average>=50) <br>
 grade = "Second Class"; <br>
 

else <br>
 grade = "Pass Class";<br> 
 } <br>
 public override void Display() <br>
 { <br>
 base.Display(); <br>
 Console.WriteLine("\n-------- MARKS DETAILS --------\n"); <br>
 Console.Write("Marks in 5 subjects: "); <br>
 for(int i=0; i<5; i++) <br>
 Console.Write(marks[i] + " <br>
 Console.Write<br>
 Console.WriteLine("Total : " + total); <br>
 
 Console.WriteLine("Average : " + average); <br>
 Console.WriteLine("Grade : " + grade); <br>
 } <br>
 } <br>
 class MultiLevel <br>
 { <br>
 public static void Main(string[] args) <br>
 { <br>
 MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5,  new int[]{77,80,98,95,90}); <br>
 Student1.Display(); <br>
 } <br>
 } <br>
}<br>
output:<br>
![Screenshot (2)](https://user-images.githubusercontent.com/97940277/154626095-6285ac41-c5d1-43f9-b32f-4633d2e02030.png)<br>
**********************
4. C# Program to Create a Gray Code.<br>
*******************
using System; <br>
namespace Exercises <br>
{ <br>
 class GrayCode <br>
 { <br>
  
 static int getGray(int n) <br>
 { <br>
 return n^(n>>1); <br>
 } <br>
 static void Main(string[] args) <br>
 { <br>
 int InputNum, GrayNum; <br>
 Console.Write("\nEnter the decimal number: "); <br>
 InputNum = Convert.ToInt32(Console.ReadLine()); <br>
 Console.WriteLine("\nBinary equivalent of {0}: {1}", InputNum,  Convert.ToString(InputNum, 2)); <br>
 GrayNum = getGray(InputNum); <br>
 Console.WriteLine("\nGray Code equivalent of {0}: {1}", InputNum,  Convert.ToString(GrayNum, 2)); <br>
 } <br>
 } <br>
} <br>

Output:<br>
![Screenshot (4)](https://user-images.githubusercontent.com/97940277/154628717-e1674fe3-eb2f-4265-80ca-84070f18b137.png)<br>

************************************
5. C# program to calculate volume of 2 boxes and find the resultant volume  after addition of 2 boxes by implementing operator overloading.<br> 
*****************************************
using System;<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = height;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override String ToString()<br>
        {<br>
            return "box with width " + width + ", height " + height + " and length " + length;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is: {1}", box1, box1.Volume); Console.WriteLine("Volume of {0} is: {1}", box2, box2.Volume);<br>

        Console.WriteLine("Volume after adding boxes: {0}", box1 + box2);<br>
        }<br>
    }<br>
}<br>

Output:<br>
***********<br>
![Screenshot (6)](https://user-images.githubusercontent.com/97940277/154629462-8db67286-8206-4499-a9f4-332a2a467ab8.png)<br>
******************
6. C# Program to Implement Principles of Delegates (converting input string to  uppercase first, last and entire string). 
***************
using System; <br>
namespace Exercises <br>
{ <br>
 class Delegates<br><br> 
 { <br>
 delegate string UppercaseDelegate(string input); <br>
 static string UppercaseFirst(string input)<br> 
 { <br>
 char[] buffer = input.ToCharArray(); <br>
 buffer[0] = char.ToUpper(buffer[0]); <br>
 return new string(buffer); <br>
 } <br>
 static string UppercaseLast(string input) <br>
 { <br>
 char[] buffer = input.ToCharArray(); <br>
 buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);  return new string(buffer); <br>
 } <br>
 static string UppercaseAll(string input) <br>
 { <br>
 return input.ToUpper(); <br>
 } <br>
 static void WriteOutput(string input, UppercaseDelegate del) <br>
 { <br>
 Console.WriteLine("Input String: {0}", input); <br>
 Console.WriteLine("Output String: {0}", del(input)); <br>
 } <br>
 static void Main() <br>
 { <br>
 WriteOutput("tom ", new UppercaseDelegate(UppercaseFirst)); <br>
 WriteOutput("tom", new UppercaseDelegate(UppercaseLast)); <br>
 WriteOutput("tom", new UppercaseDelegate(UppercaseAll)); <br>
 Console.ReadLine(); <br>
 } <br>
 } <br>
}<br>

Output:<br>
 ![Screenshot (8)](https://user-images.githubusercontent.com/97940277/154631240-41ca6a79-7405-492b-92fa-a0480c9c1587.png)<br>
***************
 7. C# Program to Generate Register Number automatically for 100 Students  using Static Constructor.<br>
***********************
 using System; <br>
namespace Exercises <br>
{ <br>
 class RegisterNum <br>
 { <br>
 int regNo; <br>
 static int startNum;<br> 
 static RegisterNum() <br>
 { <br>
 startNum = 20210000; <br>
 } <br>
 RegisterNum()<br> 
 { <br>
 regNo = ++startNum; <br>
 } <br>
 public static void Main(string[] args) <br>
 { <br>
 for(int i = 0; i<100; i++) <br>
 { <br>
 RegisterNum Student = new RegisterNum(); <br>
 Console.WriteLine("Student {0} : {1}", i+1, Student.regNo);<br> 
 } <br>
 } <br>
 } <br>
} <br>
 Output:<br>
 ********<br>
 ![Screenshot (11)](https://user-images.githubusercontent.com/97940277/154634643-d5f0df4c-099a-438c-958b-b7b58cd0741a.png)![Screenshot (12)](https://user-images.githubusercontent.com/97940277/154634798-467fda08-180c-4240-bce2-37ef552d001f.png)
<br>

 **********************
 8. C# Program to Find the Frequency of the Word ʺisʺ in a given Sentence. <br>
 *******************
using System;<br> 
namespace Exercises <br>
{ <br>
class FrequencyIS <br>
{ <br>
static void Main(string[] args) <br>
{ <br>
int count=0;<br>
string inputString; <br>
Console.WriteLine("\n----------- Frequency of word 'is' ----------"); <br>
Console.Write("\n Enter the input string: "); <br>
inputString = Console.ReadLine(); <br>
char[] separator = { ',', ' ', '.' , '!', '\n' }; <br>
string testString = inputString.ToLower(); <br>
String[] outcomes = testString.Split(separator); <br>
foreach(String s in outcomes) <br>
{ <br>
Console.WriteLine(s); <br>
if(s == "is") <br>
count++; <br>
} 
Console.WriteLine("\n Number of 'is' in '" + inputString + "' is: " + count); }<br> 
} <br>
}<br>


Output:<br>
************
 ![Screenshot (14)](https://user-images.githubusercontent.com/97940277/154635459-86a50bf4-1669-4cd4-89c0-9478c1b3ee1f.png)<br>

*******************
 9. C# program that benchmarks 2D, jagged array allocation. <br>
******************
using System;<br>
using System.Diagnostics;<br>
namespace Exercises<br>
{<br>
    class BenchmarkAllocation<br>
    {<br>
        const int _max = 100000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>
            for (int i = 0; i < 100; i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                    }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>

 Console.Write("\n Time taken for allocation in case of 2D array: "); <br>
 Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + " milliseconds");<br>
 Console.Write("\n Time taken for allocation in case of Jagged array: ");  <br>
 Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + " milliseconds");  } <br>
 } <br>
} <br>
                            
 Output:<br>
 ********<br>
 ![Screenshot (16)](https://user-images.githubusercontent.com/97940277/154636652-e0ddfc0e-52db-4442-9000-3c2bb79673e9.png)<br>

*****************
10.C# Program to Find the Sum of the Values on Diagonal of the Matrix. <br>
 *****************
 System; <br>
namespace Exercises <br>
{ <br 
 class SumOfDiagonals <br>
 { <br>
 static void Main(string[] args) <br>
 { <br>
 int MaxRow, MaxCol, Sum=0;<br> 
 int[,] Matrix; <br>
 Console.WriteLine("\n---------- SUM OF DIAGONAL OF A MATRIX ----------\n");  Console.Write("\nEnter the number of rows: "); <br><br>
 MaxRow = Convert.ToInt32(Console.ReadLine()); <br>
 Console.Write("\nEnter the number of columns: "); <br>
 MaxCol = Convert.ToInt32(Console.ReadLine()); <br>
 if(MaxRow != MaxCol) <br>

 { <br>
 Console.WriteLine("\nThe Dimensions entered are not of Square Matrix.");  Console.WriteLine("\nExiting the Program.."); <br>
 return; <br>
 } <br>
 Matrix = new int[MaxRow, MaxCol]; <br>
 for(int i=0; i<MaxRow; i++)  <br>
 {  <br>
 for(int j=0; j<MaxCol; j++)  <br>
 { 
 Console.Write("\nEnter the ({0},{1})th element of the matrix: ", (i+1), (j+1));  Matrix[i, j] = Convert.ToInt32(Console.ReadLine());  <br>
 }  <br> <br>
 }  <br>
 Console.WriteLine("\nThe entered Matrix is: ");  <br>
 for(int i=0; i<MaxRow; i++)  <br>
 {  <br>
 for(int j=0; j<MaxCol; j++)  <br>
 {  <br>
 Console.Write(" " + Matrix[i, j]);  <br>
 if( i == j)  <br>
 {  <br>
 Sum += Matrix[i,j];  <br>
 }  <br>
 }  <br>
 Console.WriteLine();  <br>
 } <br>
 Console.WriteLine("\nThe Sum of Diagonal is " + Sum);  <br>
 }  <br>
 }  <br>
}  <br>
 
 Output:<br>
 *********<br>
 ![Screenshot (77)](https://user-images.githubusercontent.com/97940277/156511984-209b9084-4c84-481b-85cf-a269ff600d25.png)<br>
 
 *******************
 11.C# Program to Create a File, Check the Existence of a File and Read the  Contents of the File. <br>
 *********************
 using System;
using System.IO;
namespace Exercises
{
    class FileRead
    {
        public static void Main()
        {
            string fileName;
            while (true)
            {
                Console.WriteLine("\n --------------- MENU --------------- \n");
                Console.WriteLine("\n 1.Create a File ");
                Console.WriteLine("\n 2.Existence of the File ");
                Console.WriteLine("\n 3.Read the contents of the File ");
                Console.WriteLine("\n 4.Exit ");
                Console.Write("\n Enter your choice : ");
                int ch = int.Parse(Console.ReadLine());
                switch (ch)
                {
                    case 1:
                        Console.Write("\n Enter the file name to create: ");
                        fileName = Console.ReadLine();
                        Console.WriteLine("\n Write the Contents to the File: \n"); string r = Console.ReadLine();
                        using (StreamWriter fileStr = File.CreateText(fileName))
                        {
                            fileStr.WriteLine(r);
                        }
                        Console.WriteLine("File is Created…");
                        break;
                    case 2:
                        Console.Write("\n Enter the file name:");
                        fileName = Console.ReadLine();
                        if (File.Exists(fileName))
                        {
                            Console.WriteLine("File exists...");
                        }
                        else
                        {
                            Console.WriteLine("File does not exist in the current directory!");
                        }
                        break;
                    case 3:
                        Console.Write("Enter the file name to read the contents:\n"); fileName = Console.ReadLine();
                        if (File.Exists(fileName))
                        {
                            using (StreamReader sr = File.OpenText(fileName))
                            {
                                string s = "";
                                Console.WriteLine(" Here is the content of the file : "); while ((s = sr.ReadLine()) != null)
                                {
                                    Console.WriteLine(s);
                                }
                                Console.WriteLine("");
                            }
                        }
                        else
                        {
                            Console.WriteLine("File does not exists");
                        }
                        break;
                    case 4:
                        Console.WriteLine("\n Exiting...");
                        return;
                    default:
                        Console.WriteLine("\n Invalid choice");
                        break;
                }
            }
        }
    }
}
