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
 11.C# Program to Create a File, Check the Existence of a File and Read the contents of the File. <br>
 *********************
 using System; <br>
using System.IO; <br>
namespace Exercises <br>
{ <br> <br>
    class FileRead <br>
    { <br>
        public static void Main() <br>
        { <br>
            string fileName; <br>
            while (true) <br>
            { <br>
                Console.WriteLine("\n --------------- MENU --------------- \n"); <br>
                Console.WriteLine("\n 1.Create a File "); <br>
                Console.WriteLine("\n 2.Existence of the File "); <br>
                Console.WriteLine("\n 3.Read the contents of the File "); <br>
                Console.WriteLine("\n 4.Exit "); <br>
                Console.Write("\n Enter your choice : "); <br>
                int ch = int.Parse(Console.ReadLine()); <br>
                switch (ch) <br>
                { <br>
                    case 1: <br>
                        Console.Write("\n Enter the file name to create: "); <br>
                        fileName = Console.ReadLine(); <br>
                        Console.WriteLine("\n Write the Contents to the File: \n"); string r = Console.ReadLine(); <br>
                        using (StreamWriter fileStr = File.CreateText(fileName)) <br>
                        { <br>
                            fileStr.WriteLine(r); <br>
                        } <br>
                        Console.WriteLine("File is Created…"); <br>
                        break; <br>
                    case 2: <br>
                        Console.Write("\n Enter the file name:"); <br>
                        fileName = Console.ReadLine(); <br>
                        if (File.Exists(fileName)) <br>
                        { <br>
                            Console.WriteLine("File exists..."); <br>
                        } <br>
                        else <br>
                        { <br>
                            Console.WriteLine("File does not exist in the current directory!"); <br>
                        } <br> <br>
                        break:<br>
                    case 3: <br>
                        Console.Write("Enter the file name to read the contents:\n"); fileName = Console.ReadLine(); <br>
                        if (File.Exists(fileName)) <br>
                        { <br>
                            using (StreamReader sr = File.OpenText(fileName)) <br>
                            { <br>
                                string s = ""; <br>
                                Console.WriteLine(" Here is the content of the file : "); while ((s = sr.ReadLine()) != null) <br>
                                { <br>
                                    Console.WriteLine(s); <br>
                                } <br>
                                Console.WriteLine(""); <br>
                            } <br>
                        } <br>
                        else <br>
                        { <br>
                            Console.WriteLine("File does not exists"); <br>
                        } <br>
                        break; <br>
                    case 4: <br>
                        Console.WriteLine("\n Exiting..."); <br>
                        return; <br>
                    default: <br>
                        Console.WriteLine("\n Invalid choice"); <br>
                        break; <br>
                } <br>
            } <br> <br>
        } <br>
    } <br>
} <br>

Output:<br>
*********<br>
File123:<br>
![Screenshot (81)](https://user-images.githubusercontent.com/97940277/156516015-4d489ee2-0997-4e89-bc95-80f5df37c95f.png)<br>


![Screenshot (83)](https://user-images.githubusercontent.com/97940277/156515950-2a53edbb-7d8a-46e1-9dcd-5bd9ba7a595a.png)<br>

![Screenshot (84)](https://user-images.githubusercontent.com/97940277/156515761-71d803b2-274d-4726-8c9c-fcf70a46212e.png)<br>

***********************************
12.C# program to perform file comparison.<br>
***********************************
 using System;<br>
 using System.IO;<br>
namespace Exercises<br>
{ <br>
    class FileRead<br>
{<br>
    public static void Main()<br>

   { <br>
       string file1;<br>
        string file2;<br>
        Console.Write("enter the first file path:");<br>
        file1 = Console.ReadLine();<br>
        Console.Write("enter the second file path:");<br>
        file2 = Console.ReadLine();<br>
        if (!File.Exists(file1))<br>
        {<br>
            Console.WriteLine("first file does not exist!");<br>
        }<br>
        else if (!File.Exists(file2))<br>
        {<br>
            Console.WriteLine("Second file doesnot exist!");<br>

      }<br>
     else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
     {<br>
            Console.WriteLine("Both files contain the same content");<br>

        }<br>
        else<br>
    {<br
    Console.WriteLine("Contents of files are not same");<br>
        }<br>
    }<br>
}<br>
}<br>

Output:<br>
*******<br>
file1.txt<br>

![Screenshot (98)](https://user-images.githubusercontent.com/97940277/157646779-c6548510-43de-452f-a85e-e12ee67a40fa.png)<br>

file2.txt<br>
![Screenshot (100)](https://user-images.githubusercontent.com/97940277/157647116-6524dcd6-4b86-4dcb-aaab-c2dd4aa9d4f2.png)<br>
![Screenshot (101)](https://user-images.githubusercontent.com/97940277/157647279-cb3d28e8-fa82-4247-b931-b56290bb8696.png)<br>
![Screenshot (102)](https://user-images.githubusercontent.com/97940277/157647450-7a885099-76d1-4ebd-b38d-a674e6a33405.png)<br>


************************************
13. C# orogram to implement IComparable interface using system.<br>
************************************
using System;<br>
namespace Exercises<br>v
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br><br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br><br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br><br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br><br>
    {<br>
        public static void Main()<br>
        {<br>
        Fraction[] a = {<br>
 new Fraction(5,2),<br>
 new Fraction(29,6),<br>
 new Fraction(4,5),<br>
 new Fraction(10,8),<br>
 new Fraction(34,7)<br>
 };<br>
            Array.Sort(a);
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying  Fractions : ");<br>
            foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>
Output:<br>
*******<br>
![Screenshot (88)](https://user-images.githubusercontent.com/97940277/157637312-3ee16d11-e5af-4ba1-9eed-f62fcef514c0.png)<br>

******************************
14.C# program to create thread pools<br>
******************************
using System;<br>
using System.Threading;<br>
namespace Exercises<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>
            }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i < 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1)); ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>
Output:<br>
*********<br>
![Screenshot (91)](https://user-images.githubusercontent.com/97940277/157638683-f94154c7-6d84-4522-a67f-46cc424559c3.png)<br>

*********************************
15.C# program to demonstrate error handling using Try,Catch and Finally block.<br>
*********************************
using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.")<br>;
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>

Output:<br>
*********<br>
![Screenshot (93)](https://user-images.githubusercontent.com/97940277/157641269-3f211faf-5572-4af4-824a-2166fd2b8802.png)<br>
*********************************************
PART-B WINDOWS APPLICATION<br>
**********************************************
16. C# Program to Convert Digits to Words.<br>
*********************************
![Screenshot (114)](https://user-images.githubusercontent.com/97940277/158944626-ed84687a-5ad8-4b29-a6b0-87b12c8e17d9.png)<br>

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace digits_to_words<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));<br>
        }<br>
        public string NumtoWord(long number)<br>
        {<br>
            string word = "";<br>
            if (number == 0)<br>
            {<br>
                return "Zero";<br>
            }<br>
            if (number < 0)<br>
            {<br>
                return "Minus" + Math.Abs(number);<br>
            }<br>
            if (number / 10000000 > 0)<br>
            {<br>
                word += NumtoWord(number / 10000000) + "Corer"; number %= 10000000;<br>
            }<br>

    if (number / 100000 > 0)<br>
           {<br>
             word += NumtoWord(number / 100000) + "Lacs";<br>
                number %= 100000;<br>
          }<br>
          if (number / 1000 > 0)<br>
            {<br>
                word += NumtoWord(number / 1000) + "Thousand";<br>
             number %= 1000;<br>
            }<br>
       if (number / 100 > 0)<br>
            {<br>
                word += NumtoWord(number / 100) + "Hundred";<br>
number %= 100;<br>
            }<br>
      if (number > 0)<br>
       {<br>
                string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen" };<br>
               string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" };<br>
         if (number < 20)<br>
                {<br>
            word += units[number];<br>
            }<br>
            else<br>
                {<br>
                word += Tens[number / 10];<br>
          if (number % 10 > 0)<br>
                    {<br>
                        word += units[number % 10];<br>
                    }<br>
              }<br>
            }<br>
          return word;<br>
      }<br>
    }<br>
}<br>
Output:<br>
*********<br>
![Screenshot (115)](https://user-images.githubusercontent.com/97940277/158945102-7908d808-2d36-43fe-90cd-63f513f9bccd.png)<br>

***********************
18.C# Program to Perform Reversal,Padding and Trimming Operations on string.<br>
*************************
![Screenshot (118)](https://user-images.githubusercontent.com/97940277/158945854-599059ad-be7f-4420-90bb-4c686d85a701.png)<br>

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
<br>
namespace Reversal_padding<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString, revstr = "";<br>
            int Length;<br>
            inputString = txtInput.Text;<br>
            Length = inputString.Length - 1;<br>
            while (Length >= 0)<br>
            {<br>
                revstr = revstr + inputString[Length];<br>
                Length--;<br>
            }<br>
            MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
        }<br>

        private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>

        private void button3_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text<br>;<br>
            inputString = inputString.PadLeft(10, '*');<br>
            inputString = inputString.PadRight(15, '*');<br>
            MessageBox.Show("String After Padding : " + inputString, "Result");<br>

        }<br>
    }<br>
}<br>
Output:<br>
**********<br>
![Screenshot (120)](https://user-images.githubusercontent.com/97940277/158945986-1be5b8d4-99e6-450a-a502-73153cce5264.png)<br>
![Screenshot (121)](https://user-images.githubusercontent.com/97940277/158946068-f40a891c-4984-424c-ba0e-5f0a85734f8f.png)<br>
![Screenshot (122)](https://user-images.githubusercontent.com/97940277/158946141-062f6423-ec11-4fce-855c-8a75925f2159.png)<br>

*********************************
19.C#Program to Create a Progress Bar Control.<br>
**********************************
![Screenshot (132)](https://user-images.githubusercontent.com/97940277/158947114-257de8af-5544-49d2-9214-22cd27ad7afe.png)<br>

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>
<br>
namespace Progress<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
        {<br>
            for (int i = 1; i <= 100; i++)<br><br>
            {<br>
                Thread.Sleep(50);<br>
                backgroundWorker1.ReportProgress(i);<br>
            }<br>
        }<br>

        private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
        {<br>
            {<br>
                progressBar1.Value = e.ProgressPercentage;<br>
                this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br>
            }<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            backgroundWorker1.WorkerReportsProgress = true;<br>
            backgroundWorker1.RunWorkerAsync();<br>

        }<br>
    }<br>

}<br>
Output:<br>
*********<br>
![Screenshot (129)](https://user-images.githubusercontent.com/97940277/158946808-0e57c0c8-f360-4dfb-9a36-561a54799efe.png)<br>

****************************************
20.Develop a winform application to create flat check.<br>
*****************************************
![Screenshot (138)](https://user-images.githubusercontent.com/97940277/158949783-89979e9d-c692-4a62-b346-2685f26eedac.png)<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace winform_app<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            timer1.Start();<br>
        }<br>

      private void Form1_Load(object sender, EventArgs e)<br>
       {<br>
          System.Timers.Timer timer = new System.Timers.Timer();<br>
           timer.Interval = 1000;//1s<br>
          timer.Elapsed += Timer_Elapsed;<br>
           timer.Start();<br>
       }<br>
       private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
       {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
         {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss"); circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM  }); <br>

            });<br>

        }<br>
    }<br>

}<br>
Output:<br>
*********<br>
![Screenshot (139)](https://user-images.githubusercontent.com/97940277/158950181-8ca58958-e847-4f8a-843d-4c0afad18728.png)<br>

*******************************************
21.C# Program to perform a number guessing game.<br>
*******************************************
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace guessinggame<br>
{<br>
    public partial class Form1 : Form<br>
    {
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        TextBox textBox1;<br>
        Button button1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
           
           value = r.Next(10);<br>
            this.Controls.Clear();<br>
            this.BackColor = Color.Pink;<br>
            this.AutoSize = true;<br>
            this.Padding = new Padding(16);<br>

            Label label = new Label();<br>
            label.Text = "Pick a number between 1 and 10";<br>
            label.Bounds = new Rectangle(10, 20, 340, 40);<br>
            label.Font = new Font("Arial", 16);<br>
            textBox1 = new TextBox();
            textBox1.Bounds = new Rectangle(20, 50, 120, 80);
            textBox1.Font = new Font("Arial", 24);
            button1 = new Button();
            button1.Text = " Check Your Guess ";
            button1.Bounds = new Rectangle(160, 50, 120, 40);
            button1.BackColor = Color.LightGray;
            button1.Click += new EventHandler(button1_Click);
            Label label2 = new Label();
            label2.Text = "Low Guess";
            label2.Font = new Font("Arial", 18);
            richTextBox1 = new RichTextBox();
            richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);
            richTextBox1.Font = new Font("Arial", 16);
            Label label3 = new Label();
            label3.Text = "High Guess";
            label3.Bounds = new Rectangle(180, 150, 160, 40);
            label3.Font = new Font("Arial", 18);
            richTextBox2 = new RichTextBox();
            richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);
            richTextBox2.Font = new Font("Arial", 16);
            label4 = new Label();
            label4.Bounds = new Rectangle(20, 100, 340, 40);
            label4.Font = new Font("Arial", 16);
            this.Controls.Add(label);
            this.Controls.Add(textBox1);
            this.Controls.Add(button1);
            this.Controls.Add(label4);
            this.Controls.Add(label2);
            this.Controls.Add(label3);
            this.Controls.Add(richTextBox1);
            this.Controls.Add(richTextBox2);


        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void button1_Click(object sender, EventArgs e)
        {
            // Coding of game
            if (textBox1.Text == "")
            {
                return;
            }
            guessnum = Convert.ToInt32(textBox1.Text);
            textBox1.Text = String.Empty;
            if (win >= 0)
            {
                if (guessnum == value)
                {
                    MessageBox.Show("You have guessed the number! \n The number was " + value);
                    InitializeComponent();
                }
                else if (guessnum < value)
                {
                    richTextBox1.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));

                }
                else if (guessnum > value)
                {
                    richTextBox2.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));

                }
                guess++;
                win--;
            }
            if (guess == 11)
            {
                label4.Text = "You loose,Correct Guess is " + value;
            }
        }
    }
}
<br>
![image](https://user-images.githubusercontent.com/97940277/159851401-cf2787a4-7a28-4bfa-a328-d36651000eb0.png)<br>
![image](https://user-images.githubusercontent.com/97940277/159851608-dcff2f5e-4005-4743-b094-d71eee8347ef.png)<br>

****************************************
22. Develop an application to create a notepad.<br>
****************************************
![Screenshot (146)](https://user-images.githubusercontent.com/97940277/161197465-95bc9189-113c-44d3-b217-6762592bfae8.png)<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br><br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

   namespace notepad3<br>
    {<br>
     public partial class Form1 : Form<br>
    {<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>


        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>

        }<br>
        
        <br>
            <br>
            internal Form1()<br>
            {<br>
                fileName = null;<br>
                initializeComponents();<br>
            }<br>
            void initializeComponents()<br>
            {<br>
                this.Text = "My notepad";<br>
                this.MinimumSize = new Size(600, 450);<br>
                this.FormClosing += new FormClosingEventHandler(NotepadClosing); this.MaximizeBox = true;<br>
                toolBar = new ToolBar();<br>
                toolBar.Font = new Font("Arial", 16);<br>
                toolBar.Padding = new Padding(4);<br>
                toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
                ToolBarButton toolBarButton1 = new ToolBarButton();<br>
                ToolBarButton toolBarButton2 = new ToolBarButton(); <br>
                ToolBarButton toolBarButton3 = new ToolBarButton(); toolBarButton1.Text = "New";<br>
                toolBarButton2.Text = "Open";<br>
                toolBarButton3.Text = "Save";<br>
                toolBar.Buttons.Add(toolBarButton1);<br>
                toolBar.Buttons.Add(toolBarButton2);<br>
                toolBar.Buttons.Add(toolBarButton3);<br>
                txtContent = new RichTextBox();<br>
                txtContent.Size = this.ClientSize;<br>
                txtContent.Height -= toolBar.Height;<br>
                txtContent.Top = toolBar.Height;<br>
                txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom;<br>
                txtContent.Font = new Font("Arial", 16);<br>
                txtContent.AcceptsTab = true;<br>
                txtContent.Padding = new Padding(8);<br>

            this.Controls.Add(toolBar);<br>
                this.Controls.Add(txtContent);<br>
            }<br>
            private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
            {
                saveFile();<br>
                switch (toolBar.Buttons.IndexOf(e.Button))<br>
                {<br>
                    case 0:<br>
                        this.Text += "My notepad";<br>
                        txtContent.Text = string.Empty;<br>
                        fileName = null;<br>
                        break;<br>
                    case 1:<br>
                        OpenFileDialog openDlg = new OpenFileDialog();<br>
                        if (DialogResult.OK == openDlg.ShowDialog())<br>
                        {<br>
                            fileName = openDlg.FileName; txtContent.LoadFile(fileName); this.Text = "My notepad " + fileName;<br>
                        }<br>
                        break;<br>
                }<br>
            }<br>
            void saveFile()<br>
            {<br>
                if (fileName == null)<br>
                {<br>
                    SaveFileDialog saveDlg = new SaveFileDialog();<br>
                    if (DialogResult.OK == saveDlg.ShowDialog())<br>
                    {<br>
                        fileName = saveDlg.FileName;<br><br>
                        this.Text += " " + fileName;<br>
                    }<br>
                }<br>
                else<br>
                {<br>
                    txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
                }<br>
            }<br>
            private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
            {<br>
                saveFile();<br>
            }<br>
           /* static void Main(String[] args)<br>
            {<br>

            Application.Run(new NotepadForm());<br>
            }*/<br>
        }<br>
    }<br>
Output:<br>
*********
![Screenshot (149)](https://user-images.githubusercontent.com/97940277/161198109-37a5f26e-93c2-4117-be8b-884827e90def.png)<br>


****************************************
23.C# Program to Perform Reversal, Padding and Trimming Operations on  string<br>
*****************************************
![Screenshot (143)](https://user-images.githubusercontent.com/97940277/161000441-beb5e26e-9096-489b-964a-e4b59af6c2d2.png)<br>

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
using System.Drawing.Drawing2D;<br>

namespace BinaryTree1<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private Node root;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br><br>
            this.root = null;<br>
            test();<br>

        }<br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "3";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "2";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "1";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "4";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "7";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "6";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "8";<br>
            btnAdd_Click(btnAdd, null);<br>
        }<br><br>


        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>

        }<br>

        private void button3_Click(object sender, EventArgs e)<br>
        {
            int value = int.Parse(textBox1.Text); if (root != null)<br>
            {<br>
                bool status = root.Remove(value, root, ref root); if (status == false)<br>
                {<br>
                    MessageBox.Show("the value does not exists");<br>
                }<br>
            }<br>
            drawTree();<br>

        }<br>

        private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
                root = new Node(value);<br>
            else<br>
            {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>
            }<br>
            drawTree();<br>

        }<br>

        private void button4_Click(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
            {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
            {<br>
                if (root.Exists(value))<br>
                {<br>
                    msg = "Value found";<br>
                }<br>
                else<br><br>
                {<br>
                    msg = "Value not found";<br>
                }<br>
            }<br>
            MessageBox.Show(msg);<br>

        }<br>
        void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
        

        private void btnAdd_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
                root = new Node(value);<br>
            else<br>
            {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>
            }<br>
            drawTree();<br>
<br>
        }<br>
    }<br>
    class Node<br>
    {
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;<br>
        private static Bitmap nodeBg = new Bitmap(30, 25); private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br><br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>

             {<br>
                    this.right = node;<br>
                    return true;<br>
                }<br>
 else<br>
                    return this.right.Add(value);<br>
            }
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br><br>
                }<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (right != null)<br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left; if (root == this)<br>
                        root = left;<br>
                }<br>
                else<br>
                {
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>

                    parent.right = right;<br>
                        if (root == this)<br><br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br><br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);<br>
            Image lNodeImg = null;<br>
            Image rNodeImg = null;<br>
            int lCenter = 0, rCenter = 0;<br>

            if (this.left != null)<br>
            {<br>
                lNodeImg = left.Draw();<br>
                lSize = lNodeImg.Size;<br>
                this.center = lSize.Width;<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br>
                rSize = rNodeImg.Size;<br>
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height; if (maxHeight > 0) maxHeight += 35;<br>

        Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
            Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize)); g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
            string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35); var points1 = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 - w/6, y1 + h/3.5f),<br>
 new PointF(x2 + w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2),<br>
 };<br>
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg<!= null)<br>
            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35); x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 + w/6, y1 + h/3.5f),<br>
 new PointF(x2 - w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2)<br>
 };<br>

            g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
            }<br>
            return result;<br>
        }<br>
        public bool Exists(int value)<br>
        {<br>
            bool res = value == this.value;<br>
            if (!res && left != null)<br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        }<br>
    }<br>
} 
<br>
Output:<br>
*******<br>
![Screenshot (144)](https://user-images.githubusercontent.com/97940277/161000735-8842cc2e-7801-4b9f-bb75-44355441168a.png)<br>


****************************************
 24.Money conversion program.
****************************************
 ![Screenshot (215)](https://user-images.githubusercontent.com/97940277/165697628-a4216d1b-3ad3-48c7-82c6-07dafb8443d0.png)<br>
 using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br><br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace money_coversion<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
        }<br><br>

        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            {<br>
                label4.Visible = true;<br>
                if (textBox1.Text == "")<br>
                {<br>
                    label4.Text = "Enter the amount";<br>
                }<br>
                else<br>
                {<br>
                    Double convertedamt = Convert.ToDouble(textBox1.Text);<br>
                    if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "USD")<br>
                    {<br>
                        Double a = convertedamt / 74;<br>
                        label4.Text = a + "$";<br>
                    }<br>
                    else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "SAR")<br>
                    {<br>
                        Double a = convertedamt / 17;<br>
                        label4.Text = a + "SAR";<br>
                    }<br>
                    else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "EUR")<br>
                    {<br>

                        Double a = convertedamt / 11;<br>
                        label4.Text = a + "EUR";<br>
                    }<br>
                    else<br>
                    {<br>
                        label4.Text = "Please Enter the conversion code";<br>
                    }<br>
                }<br>
            }<br>
        }<br>

        private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            textBox1.Text = "";<br>
            label4.Text = "";<br>

        }<br>
    }<br>
}<br>

![Screenshot (217)](https://user-images.githubusercontent.com/97940277/165697837-3c6f1b88-8911-4f13-8786-99339ee28c6c.png)<br>


    
    
    



    





















