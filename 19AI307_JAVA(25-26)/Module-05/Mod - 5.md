# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a Java program to write characters to a file using FileWriter.

## AIM:
To write character data into a file using the FileWriter class in Java.

## ALGORITHM :
1.	Import java.io.FileWriter and java.io.IOException.
2.	Take user input using Scanner.
3.	Create a FileWriter object with the desired file name.
4.	Use write() method to write text into the file.
5.	Close the FileWriter and handle exceptions using try-catch.

## PROGRAM:
 ```
/*
Program to implement a InputStreamReader using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.io.*;

public class FileWriteExample {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            String filename = br.readLine();
            String content = br.readLine();

            FileWriter fw = new FileWriter(filename);
            fw.write(content);
            fw.close();

            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
```






## OUTPUT:
<img width="1239" height="395" alt="image" src="https://github.com/user-attachments/assets/f1eb5219-05ab-4882-990c-ab044ebd6ca8" />

## RESULT:
The program successfully writes the entered text into output.txt using FileWriter.



# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to read a string from the user, compress it in memory using ByteArrayOutputStream + GZIPOutputStream, and then decompress it back using ByteArrayInputStream + GZIPInputStream.

## AIM:
To demonstrate string compression and decompression using ByteArrayOutputStream, GZIPOutputStream, ByteArrayInputStream, and GZIPInputStream.

## ALGORITHM :
1.	Read a string from the user.
2.	Create a ByteArrayOutputStream and wrap it in a GZIPOutputStream to compress the string.
3.	Convert the compressed output to a byte array.
4.	Use ByteArrayInputStream and GZIPInputStream to decompress the byte array back to the original string.
5.	Display both compressed size and decompressed string.





## PROGRAM:
 ```
/*
Program to implement a Serialization and Deserialization using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.io.*;
import java.util.Scanner;
import java.util.zip.GZIPOutputStream;
import java.util.zip.GZIPInputStream;

public class GZIPMemoryExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            String input = scanner.nextLine();

            ByteArrayOutputStream baos = new ByteArrayOutputStream();
            GZIPOutputStream gzipOut = new GZIPOutputStream(baos);
            gzipOut.write(input.getBytes("UTF-8"));
            gzipOut.close();

            byte[] compressedData = baos.toByteArray();
            System.out.println("Compressed data (bytes):");
            for (byte b : compressedData) {
                System.out.print(b + " ");
            }
            System.out.println("\nTotal bytes: " + compressedData.length);

            ByteArrayInputStream bais = new ByteArrayInputStream(compressedData);
            GZIPInputStream gzipIn = new GZIPInputStream(bais);
            InputStreamReader reader = new InputStreamReader(gzipIn, "UTF-8");
            BufferedReader br = new BufferedReader(reader);

            StringBuilder decompressed = new StringBuilder();
            String line;
            while ((line = br.readLine()) != null) {
                decompressed.append(line);
            }

            System.out.println("\nDecompressed string:");
            System.out.println(decompressed.toString());

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }

        scanner.close();
    }
}
```

## OUTPUT:
<img width="1271" height="577" alt="image" src="https://github.com/user-attachments/assets/ec980f76-7dcd-46aa-8c14-33fe5d578589" />


## RESULT:
The program successfully compresses and decompresses a string in memory using GZIP streams, showing reduced data size and restoring the original text accurately.



# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to count the number of characters in a file.

## AIM:
To count and display the total number of characters in a file using FileReader.

## ALGORITHM :
1.	Ask the user for the file name.
2.	Open the file using FileReader.
3.	Read each character one by one until the end of the file.
4.	Increment a counter for each character read.
5.	Display the total character count.

## PROGRAM:
 ```
/*
Program to implement a File Handling using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.io.*;

public class FileCharacterCount {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

            String text = br.readLine();

            String fileName = "output.txt";

            try (FileWriter fw = new FileWriter(fileName)) {
                if (text != null) {
                    fw.write(text);
                }
            }

            int charCount = 0;
            try (FileReader fr = new FileReader(fileName)) {
                while (fr.read() != -1) {
                    charCount++;
                }
            }

            System.out.println("Number of characters written to the file: " + charCount);

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

```

## OUTPUT:
<img width="1271" height="303" alt="image" src="https://github.com/user-attachments/assets/8417184e-b934-4c43-a19c-4bc7cec02f4e" />



## RESULT:
The program successfully reads the file and prints the total number of characters present in it.


# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for determine the priority and name of the current thread.

Note : Read the threadname from the User

## AIM:
To read a thread name from the user and display the current thread’s name and priority.

## ALGORITHM :
1.	Read the thread name from the user.
2.	Get the reference of the current thread using Thread.currentThread().
3.	Set the name of the current thread using setName().
4.	Retrieve the thread’s name and priority using getName() and getPriority().
5.	Display both values.




## PROGRAM:
 ```
/*
Program to implement a Thread Priority Concept using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

public class ThreadInfoExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String threadName = scanner.nextLine();

        Thread t = new Thread(() -> {}, threadName);

        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());

        System.out.println(t);

        scanner.close();
    }
}
```

## OUTPUT:
<img width="1313" height="265" alt="image" src="https://github.com/user-attachments/assets/f363db08-7cdb-4761-a39c-556870905f3c" />



## RESULT:
The program successfully reads the thread name from the user and displays the current thread’s name and priority.


# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Maintain two int variables a and b, read their initial values from user. Use synchronized block to swap them and print swapped values.

Input:

Two lines: a and b values

Output:

a = <swapped_a>

b = <swapped_b>

## AIM:
To demonstrate the use of a synchronized block for safely swapping two integer variables.

## ALGORITHM :
1.	Read two integer values a and b from the user.
2.	Create a lock object for synchronization.
3.	Use a synchronized(lock) block to perform the swapping.
4.	Swap values using a temporary variable.
5.	Print the swapped values of a and b.


## PROGRAM:
 ```
/*
Program to implement a Synchronization concept using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

public class SwapSynchronized {
    private int a;
    private int b;

    public SwapSynchronized(int a, int b) {
        this.a = a;
        this.b = b;
    }

    public void swap() {
        Object lock = new Object();
        synchronized (lock) {
            int temp = a;
            a = b;
            b = temp;
        }
    }

    public void printValues() {
        System.out.println("a = " + a);
        System.out.println("b = " + b);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int a = Integer.parseInt(sc.nextLine());
        int b = Integer.parseInt(sc.nextLine());

        SwapSynchronized swapper = new SwapSynchronized(a, b);
        swapper.swap();
        swapper.printValues();

        sc.close();
    }
}
```

## OUTPUT:
<img width="1315" height="352" alt="image" src="https://github.com/user-attachments/assets/4ac75d2b-e703-4ae2-9edb-c22bc5dc3b45" />


## RESULT:
The program successfully swaps the two integers inside a synchronized block and displays the swapped values safely.

