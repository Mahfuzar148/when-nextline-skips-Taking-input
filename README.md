# when-nextline-skips-Taking-input


Hi,

Actually nextLine() method of Scanner skips the console input, when we use it after next(), nextInt() and all nextXXX() methods. Because next() and nextXXX() input methods doesn’t process/consider the newline character (When you press ENTER key after input them) and that newline character processed by nextLine() method. Therefore nextLine() method doesn’t read the input (which you wished for). To overcome this problem, you have to invoke an extra nextLline() method after next() and nextXXX().

Let me show you few Scenarios:

Scenario-1 : Here both nextLine() methods will work fine.
Scanner sc =new Scanner(System.in);
String name=sc.nextLine();
String city=sc.nextLine();
System.out.println(name+” “+city);

Scenario-2 : Here nextLine() will skip the input, Because next() doesn’t process the new line Character after its input.

Scanner sc =new Scanner(System.in);
String name=sc.next(); //Input the String but not process newline char.
String city=sc.nextLine(); //So, newline will be processed by this line & input for City will be skipped.
System.out.println(name+” “+city);

Solution to the Problem:

Scenario-3 : You need to call an extra nextLine() method after next() or nextXXX() to process the new line Character.

Scanner sc =new Scanner(System.in);
String name=sc.next(); //Input the String but not process newline

sc.nextLine(); //Now newline char will be processed by this extra nextLine().

String city=sc.nextLine(); //So, this line will read the input for City.
System.out.println(name+” “+city);
