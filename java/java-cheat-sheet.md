Courtesy of: http://egek.us/JavaCheatSheet/)

1. [the basics](https://github.com/egek92/JavaCheatSheet#the-basics)
2. [string manipulation](https://github.com/egek92/JavaCheatSheet#string-manupilation)
3. [working with data structures](https://github.com/egek92/JavaCheatSheet#working-with-data-structures)
4. [dates and times](https://github.com/egek92/JavaCheatSheet#dates-and-times)
5. [regular expressions](https://github.com/egek92/JavaCheatSheet#regular-expressions)
6. [dealing with numbers and math](https://github.com/egek92/JavaCheatSheet#dealing-with-numbers-and-math)
7. [input - output operations](https://github.com/egek92/JavaCheatSheet#input---output-operations)
8. [working with files and directories](https://github.com/egek92/JavaCheatSheet#working-with-files-and-directories)
9. [network clients](https://github.com/egek92/JavaCheatSheet#network-clients)
10. [packaging and documenting](https://github.com/egek92/JavaCheatSheet#packaging-and-documenting)
11. [sorting algorithms](https://github.com/egek92/JavaCheatSheet#sorting-algorithms)




## the basics

#### hello, world! :

[![hello.png](https://s4.postimg.org/jzvh0kiwd/hello.png)](https://postimg.org/image/r33cg6obt/)

#### if-else:

[![nested-if-else.png](https://s28.postimg.org/44ozxhghp/nested_if_else.png)](https://postimg.org/image/7bjjh40xl/)

#### loops:

[![for-while.png](https://s29.postimg.org/bs5idrk2v/for_while.png)](https://postimg.org/image/88jknyhcz/)

#### do-while:

	do {
            System.out.println("Count is: " + count);
            count++;
        } while (count < 11);
	
#### switch-case:

[![switch.png](https://s15.postimg.org/vthdiexx7/switch.png)](https://postimg.org/image/7cz7nxx6f/)

#### arrays:

[![Ekran Resmi 2017-03-04 18.11.17.png](https://s3.postimg.org/dbp4l5mxv/Ekran_Resmi_2017_03_04_18_11_17.png)](https://postimg.org/image/92keizjof/)

#### two-dimentional arrays:

[![Ekran Resmi 2017-03-04 18.12.38.png](https://s14.postimg.org/4j6jd2269/Ekran_Resmi_2017_03_04_18_12_38.png)](https://postimg.org/image/a7cu3y6il/)

#### objects:

[![object.png](https://s2.postimg.org/o8ugyzmrt/object.png)](https://postimg.org/image/vc2cels79/)

#### classes:

[![class.png](https://s24.postimg.org/b0l9lgr4l/class.png)](https://postimg.org/image/ohi84c1g1/)

#### methods:

[![instance-method.png](https://s14.postimg.org/4qltgprbl/instance_method.png)](https://postimg.org/image/41314cqrx/)

#### Java IDE comparison:

[![Ekran Resmi 2017-03-04 11.02.18.png](https://s18.postimg.org/4pba52mgp/Ekran_Resmi_2017_03_04_11_02_18.png)](https://postimg.org/image/7w5top6wl/)
yes I took this from Wikipedia

I recommend [IntelliJ IDEA](https://www.jetbrains.com/idea/) it's free for [students](https://www.jetbrains.com/student/).



## string manipulation 

#### comparing strings:
```
boolean result = str1.equals(str2);
boolean result = str1.equalsIgnoreCase(str2);
```

#### searching and rerieving substrings:

```
int result = str1.indexOf(str2);
int result = str1.indexOf(str2,5);
String index = str1.substring(14);
```

#### processing a string one character at a time:
```
for (int i=0;i<str1.length();i++){

char aChar = str1.charAt(i);
}
```

#### Reversing a String by Character:

```

public class Main {

    public static void main(String[] args) {

        String str1 = "whatever string something";

        StringBuffer str1buff = new StringBuffer(str1);

        String str1rev = str1buff.reverse().toString();

        System.out.println(str1rev);


    }
}
```


#### Reversing a String by Word:
```

public class Main {

public static void main(String[] args) {

    String str1 = "reverse this string";

    Stack<Object> stack = new Stack<>();

    StringTokenizer strTok = new StringTokenizer(str1);

    while(strTok.hasMoreTokens()){

        stack.push(strTok.nextElement());
    }

    StringBuffer str1rev = new StringBuffer();

    while(!stack.empty()){

        str1rev.append(stack.pop());
        str1rev.append(" ");


    }

    System.out.println(str1rev);



}
}
```



#### making a string upper or lowercase:
```


String strUpper = str1.toUpperCase();
String strLower = str1.toLowerCase();
```


#### removing end and start spaces:
```

String str1 = "     asdfsdf   ";
str1.trim(); //asdfsdf
```

#### removing all spaces:
```
str1.replace(" ","");
```

#### parsing a comma separated string:

```
String str = "tim,kerry,timmy,camden";
String[] results = str.split(",");
```

## working with data structures

#### resizing an array:

```     
int[] myArray = new int[10];

int[] tmp = new int[myArray.length + 10];
System.arraycopy(myArray, 0, tmp, 0, myArray.length);
myArray = tmp;

``` 

#### iterating over a collection:
``` 
 for (Iterator it = map.entrySet().iterator();it.hasNext();){

            Map.Entry entry = (Map.Entry)it.next();
            Object key = entry.getKey();
            Object value = entry.getValue();
        }
``` 

#### creating a mapped collection:
``` 
        HashMap map = new HashMap();
        map.put(key1,obj1);
        map.put(key2,obj2);
        map.put(key2,obj2);
``` 

#### sorting an array:
```
       int[] nums = {1,4,7,324,0,-4};
       Arrays.sort(nums);
       System.out.println(Arrays.toString(nums));
```

#### sorting an arrayList:
```
        List<String> unsortList = new ArrayList<String>();

		unsortList.add("CCC");
		unsortList.add("111");
		unsortList.add("AAA");
        Collections.sort(unsortList);
```
#### finding an object in arrayList:
```
int index = arrayList.indexOf(obj);
```
#### finding an object by value in a hashmap:
```
hashmap.containsValue(obj);
```
#### finding an object by key in a hashmap:
```
hashmap.containsKey(obj);
```
#### binary search in an array:
```
int[] nums = new int[]{7,5,1,3,6,8,9,2};
Arrays.sort(nums);
int index = Arrays.binarySearch(nums,6);
System.out.println("6 is at index: "+ index);
```
#### converting arrayList to array:
```
Object[] objects = arrayList.toArray();
```
#### converting hashmap to array:
```
Object[] objects = hashmap.entrySet().toArray();
```

## dates and times

#### printing date and time:
```
Date todaysDate = new Date(); //todays date
SimpleDateFormat formatter = new SimpleDateFormat("EEE, dd MMM yyyy HH:mm:ss"); //date format
String formattedDate = formatter.format(todaysDate);
System.out.println(formattedDate);
```

#### converting date to calendar:
```
Date mDate = new Date();
Calendar mCal = Calendar.getInstance();
mCal.setTime(mDate);
```

#### converting calendar to date:
```
Calendar mCal = Calendar.getInstance();
Date mDate = mCal.getTime();
```

#### parsing Strings into dates:
```
public void StringtoDate(String x) throws ParseException{
String date = "March 20, 1992 or 3:30:32pm";
DateFormat df = DateFormat.getDateInstance();
Date newDate = df.parse(date);
     
    }
 ```
 
#### date arithmetic using date objects:
 ``` 
Date date = new Date();
long time = date.getTime();
time += 5*24*60*60*1000; //may give a numeric overflow error on IntelliJ IDEA
Date futureDate = new Date(time);

System.out.println(futureDate);
 ```
 
#### date arithmetic using calendar objects:
 ``` 
Calendar today = Calendar.getInstance();
today.add(Calendar.DATE,5);
 ```
#### difference between two dates:
  ```
 long diff = time1 - time2;
 diff = diff/(1000*60*60*24);
  ```
#### comparing dates:
  ```
 boolean result = date1.equals(date2);
  ```
  
#### getting details from calendar:
  ```
  
Calendar cal = Calendar.getInstance();
cal.get(Calendar.MONTH);
cal.get(Calendar.YEAR);
cal.get(Calendar.DAY_OF_YEAR);
cal.get(Calendar.WEEK_OF_YEAR);
cal.get(Calendar.DAY_OF_MONTH);
cal.get(Calendar.DAY_OF_WEEK_IN_MONTH);
cal.get(Calendar.DAY_OF_MONTH);
cal.get(Calendar.HOUR_OF_DAY);
```


#### calculating the elapsed time:
 ```        
long startTime = System.currentTimeMillis();
//times flies by..
long finishTime =  System.currentTimeMillis();
long timeElapsed = startTime-finishTime;
System.out.println(timeElapsed);
```

## regular expressions

#### finding matching text using REGEX:
```
String pattern = "[TJ]im";
       Pattern regPat = Pattern.compile(pattern,Pattern.CASE_INSENSITIVE);
       String text = "This is Jim and that's Tim";
       Matcher matcher = regPat.matcher(text);
       
       if (matcher.find()){
           
           String matchedText = matcher.group();
           System.out.println(matchedText);
       }
```
       
#### replacing a matched text:

```
	String pattern = "[TJ]im";
       Pattern regPat = Pattern.compile(pattern,Pattern.CASE_INSENSITIVE);
       String text = "This is jim and that's Tim";
       Matcher matcher = regPat.matcher(text);
       String text2 = matcher.replaceAll("Tom");
       System.out.println(text2);
```
       
#### replacing a matched text using StringBuffer:
```
 Pattern p = Pattern.compile("My");
       Matcher m = p.matcher("My dad and My mom");
       StringBuffer sb = new StringBuffer();
       boolean found = m.find();

       while(found){
           m.appendReplacement(sb,"Our");
           found = m.find();

       }
        m.appendTail(sb);
        System.out.println(sb);
```	
#### finding all occurences of a pattern:
```
String pattern = "\\sa(\\w)*t(\\w)*"; //contains "at"
      Pattern regPat = Pattern.compile(pattern);
      String text = "words something at atte afdgdatdsf hey";
      Matcher matcher = regPat.matcher(text);
      while(matcher.find()){


          String matched = matcher.group();
          System.out.println(matched);
      }
 ```    
#### printing lines containing a pattern:
```
 String pattern = "^a";
      Pattern regPat = Pattern.compile(pattern);
      Matcher matcher = regPat.matcher("");
        BufferedReader reader = new BufferedReader(new FileReader("file.txt"));
        String line;
        while ((line = reader.readLine())!= null){
            matcher.reset(line);
            if (matcher.find()){
                System.out.println(line);
            }
        }
```	
#### matching new lines in text:
```
String pattern = "\\d$"; //any single digit
     String text = "line one\n line two\n line three\n";
     Pattern regPat = Pattern.compile(pattern, Pattern.MULTILINE);
     Matcher matcher = regPat.matcher(text);
     while (matcher.find()){

         System.out.println(matcher.group());


     }
 ```    
#### regex:

* beginning of a string: ^
* end of a string: $ 
* 0 or 1 times: ?
* 0 or more times:  (*) //without brackets
* 1 or more times: +
* alternative characters: [...]
* alternative patterns: |
* any character: .
* a digit: \d
* a non-digit: \D
* whitespace: \s
* non-whitespace: \S
* word character: \w
* non word character: \W

       
## dealing with numbers and math

#### built-in types:

![alt tag](https://s3.postimg.org/7ihyxdvar/Ekran_Resmi_2017_03_04_10_03_48.png)

* byte: 8bits, Byte
* short: 16bits, Short
* long: 64bits, Long
* float: 32bits, Float

#### checking whether a string is valid number:

``` 

  String str = "dsfdfsd54353%%%";

     try{

         int result = Integer.parseInt(str);

     }

     catch (NumberFormatException e){
         System.out.println("not valid");
     }
``` 
     
#### comparing Double:
``` 
Double a = 4.5;
      Double b= 4.5;

      boolean result = a.equals(b);

      if (result) System.out.println("equal");
 ```      
#### rounding:
``` 
double doubleVal = 43.234234200000000234040324;
       float floatVal = 2.98f;

      long longResult = Math.round(doubleVal);
      int intResult = Math.round(floatVal);

        System.out.println(longResult + " and " + intResult); // 43 and 3
``` 	
#### formatting numbers:
``` 
double value = 2343.8798;
        NumberFormat numberFormatter;
        String formattedValue;
        numberFormatter = NumberFormat.getNumberInstance();
        formattedValue = numberFormatter.format(value);
        System.out.format("%s%n",formattedValue); //2.343,88
``` 	
#### formatting currencies:
``` 
double currency = 234546457.99;
       NumberFormat currencyFormatter;
       String formattedCurrency;

       currencyFormatter = NumberFormat.getCurrencyInstance();

       formattedCurrency = currencyFormatter.format(currency);

        System.out.format("%s%n",formattedCurrency); // $ 234.546.457,99
``` 	
#### binary, octal and hexadecimal conversion:
``` 
int val = 25;
String binaryStr = Integer.toBinaryString(val);
String octalStr = Integer.toOctalString(val);
String hexStr = Integer.toHexString(val);
``` 
#### generating random numbers:
``` 
double rn = Math.random();
        int rint = (int) (Math.random()*10); // random int between 0-10

        System.out.println(rn);
        System.out.println(rint);
``` 	
#### calculating trigonometric functions:
``` 
double cos = Math.cos(45);
        double sin = Math.sin(45);
        double tan = Math.tan(45);
``` 	
#### calculating logarithm
``` 
double logVal = Math.log(125.5);
``` 
#### Math library:

[![Ekran Resmi 2017-03-04 10.42.52.png](https://s27.postimg.org/fuya7a83n/Ekran_Resmi_2017_03_04_10_42_52.png)](https://postimg.org/image/f5fhux7jz/)

[![library-calls.png](https://s29.postimg.org/ux3o2zijb/library_calls.png)](https://postimg.org/image/ow5z5wvwz/)

## input - output operations:

#### reading a text from input:
``` 
//throw IOexception first

BufferedReader inStream = new BufferedReader(new InputStreamReader(System.in));
      String inline ="";
      while (!(inline.equalsIgnoreCase("quit"))){
          System.out.println("prompt> ");
          inline=inStream.readLine();
      }
```       
#### formatting output:
``` 
StringBuffer buffer = new StringBuffer();
      Formatter formatter = new Formatter(buffer, Locale.US);
      formatter.format("PI: "+Math.PI);
        System.out.println(buffer.toString());
``` 	
#### formatter format calls:

[![Ekran Resmi 2017-03-04 11.21.45.png](https://s24.postimg.org/6st8e3epx/Ekran_Resmi_2017_03_04_11_21_45.png)](https://postimg.org/image/qanvu1bnl/)



#### opening file by name:


	BufferedReader br = new BufferedReader(new FileReader(textFile.txt)); //for reading
        BufferedWriter bw = new BufferedWriter(new FileWriter(textFile.txt)); //for writing
	
#### reading a binary data:

 	InputStream is = new FileInputStream(fileName);
        int offset = 0;
        int bytesRead = is.read(bytes, ofset, bytes.length-offset);
	
#### seeking in a file:

	 File file = new File(something.bin);
        RandomAccessFile raf = new RandomAccessFile(file,"rw");
        raf.seek(file.length());
	
#### reading a Jar/zip/rar file:

	ZipFile file =new ZipFile(filename);
        Enumeration entries = file.entries();
        while(entries.hasMoreElements()){

            ZipEntry entry = (ZipEntry) entries.nextElement();
            if (entry.isDirectory()){
                //do something
            }
            else{
                //do something
            }
        }
        file.close();
	
## working with files and directories

#### creating a file:

	File f = new File("textFile.txt");
	boolean result = f.createNewFile();
	
#### renaming a file:
 
 	File f = new File("textFile.txt");
	File newf = new File("newTextFile.txt");
	boolean result = f.renameto(newf);

#### deleting a file:

	File f = new File("somefile.txt");
	f.delete();

#### changing file attributes:

	File f = new File("somefile.txt");
	f.setReadOnly(); // making the file read only
	f.setLastModified(desired time); 

#### getting the size of a file:
 	File f = new File("somefile.txt");
	long length = file.length();
	
#### checking if a file exist or not:

	File f = new File("somefile.txt");
	boolean status = f.exists();
	
#### moving a file to another directory:

	File f = new File("somefile.txt");
	File dir = new File("directoryName");
	boolean success = f.renameTo(new File(dir, file.getName()));
	
#### getting an absolute filename path:

	File f = new File("somefile.txt");
	File absPath = f.getAbsoluteFile();
	
#### determining if it's a file or a directory:

	File f = new File("somefile.txt");
        boolean isDirectory = f.isDirectory();
        System.out.println(isDirectory); //false
	
#### listing a directory:

	File directory = new File("users/ege");
        String[] result = directory.list();
	
#### creating a directory:

	boolean result = new File("users/ege").mkdir();
	
## network clients

#### contacting a server:

	String serverName = "www.egek.us";
    Socket socket = new Socket(serverName, 80);
    System.out.println(socket);
	
#### handling network errors:

	try {
            Socket sock = new Socket(server_name, tcp_port);
            System.out.println("Connected to " + server_name);
         	sock.close(  );

        } catch (UnknownHostException e) {
            System.err.println(server_name + " Unknown host");
            return;
        } catch (NoRouteToHostException e) {
            System.err.println(server_name + " Unreachable" );
            return;
        } catch (ConnectException e) {
            System.err.println(server_name + " connect refused");
            return;
        } catch (java.io.IOException e) {
            System.err.println(server_name + ' ' + e.getMessage(  ));
            return;
        }
	

## packaging and documenting

#### creating a package:

	package com.ege.example;
	
#### documenting classes with JavaDoc:

	javadoc -d \home\html
		-sourcepath \home\src
		-subpackages java.net
		
#### archiving classes with Jar:

	jar cf project.jar *.class
	
#### running a program from a Jar:

	java -jar something.jar
	

## sorting algorithms

* Bubble Sort
* Linear Search
* Binary Search
* Selection Sort
* Insertion Sort

[Over here](https://github.com/egek92/SortAlgorithms)


	

	
	



        
