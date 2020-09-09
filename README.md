# Builder
Builder
https://4pda.ru/forum/index.php?showtopic=741456&view=findpost&p=99665952

Guys, as a bonus - please test this ApkBuilder:

https://4pda.ru/forum/index.php?showtopic=741456&view=findpost&p=99665952

Attached fileBuilder1.0.apk(16.88 MB)

Attached fileBuilder.zip(18.32 MB)


The application can: 
1. Execute simple Java programs ... 
2. Execute Shell or Bash scripts ... 
3. Build small Android Java projects written in the Eclipse style ... 
To run a .sh script in a program or in any file manager create a file with the .sh extension ... 
To create a file - in any folder available for writing - long click on any file or folder (press and hold) ... 
In the menu that appears, select "Create", then - in the input field, enter file name (let's say test.sh) and click "File" ... 
In it write a program in Shell or Bash, let's say:

while [1] 
do 
date 
sleep 1 
done

And press the "BACK" button (the exit button from the application) or from the menu (in the upper right corner there are three dots) the "Run" button ... 
The program will go into execution mode and the output of the result will appear on the screen, while the text is highlighted in blue .. . 
If you want to prematurely stop or exit from the cycle - double click on the button "BACK" ... 
If you want to run the same program in Java, create a folder, for example "Test", in it to another folder "src" and in her file , let's say Main.java ... The 
program will generate a standard minimum ... 
After editing or immediately launch it by analogy with the previous launch ... 
If we want to create an Android application,by analogy with the example, we prescribe everything we need and select the file AndroidManifest.xml in the program ...
The program reads data from it, in particular the "package" parameter and, on its basis, generates an assembly file and immediately executes it (made it so that each project does not clog with unnecessary files) ... 
If the assembly went without errors, we get a signed .apk at the output file and a request to install it ... 
Compilation and assembly data can be viewed in the "log.txt" file (from the file manager, press "Home") ... 
Also, with this "Home" button, you can get into the internal memory of the phone (it is useful if you want to change something) ... 
Here is a Java program that recursively deletes all folders with a given name ("build") from the memory card ("/ sdcard"):

import java.util. *; 
import java.io. *; 

public class Main 
{ 
	public static void main (String [] args) 
	{ 
		dir ("build", "/ sdcard"); 
		System.out.println ("Done!"); 
	} 

	public static void dir (String end, String dir) 
	{ 
		File [] ff = new File (dir) .listFiles (); 
		if (ff! = null) 
		{ 
			for (File f: ff) 
			{ 
				if (f.isDirectory ()) 
				{ 
					if (f.getName (). equals (end)) 
					{ 
						System.out.println (f.getAbsolutePath () ); 
						delete (f.getAbsolutePath ()); 
					} 
					else 
					{ 
						dir (end, f.getAbsolutePath ()); 
					}
				} 
			} 
		} 
	} 

	public static void delete (String fn) 
	{ 
		File x = new File (fn); 
		if (x.isDirectory ()) 
		{ 
			File [] ff = x.listFiles (); 
			if (ff! = null) 
			{ 
				for (File f: ff) 
				{ 
					delete (f.getAbsolutePath ()); 
				} 
			} 
		} 
		x.delete (); 
	} 
}

Here are the sources:
Attached fileMain.zip(999 bytes)

It is useful for clearing / sdcard ... 
Here are the main features of this version in brief ... 
There are also additional functions, in particular replace, search, zip, unzip and others, but I will write about them a little later ... 
Bye ... 
Thanks for reading ...

Thanks ...
