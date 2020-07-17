# Pthon Notes for Reading Files

Notes - 7/17/2020(Jason, Jessica, Hana)

Reading Files

●	A text file can be thought of as a sequence of lines
●	Before we can read the contents of the file, we must tell Python which file we are going to work with and what we will be doing with the file using the open() function.
●	f = open('file.txt', 'r') - mode is optional and should be 'r' if we are planning to read the file and 'w' if we are going to write to the file
●	When Files are Missing f = open('file.txt') returns Traceback error into the screen.
●	The newline Character represents as \n in strings. Newline is still one character - not two
●	A file handle open for read can be treated as a sequence of strings where each line in the file is a string in the sequence
●	We can use the for statement to iterate through a sequence

#Prints the sequence of lines in the text document
f = open('file.txt')
for line in f:
    print(line)

#Counting Lines in a File and prints the number of lines
f = open('mbox.txt')
count = 0
for line in f:
    count = count + 1
print('Line Count:', count)


#Reading the *Whole* File
f = open('file.txt')
inp = f.read()
   print(len(inp))  
   print(inp[:20])

#Searching Through a File
●	We can put an if statement in our for loop to only print lines that meet some criteria

f = open('filet.txt')
for line in f:
    if line.startswith('From:') :
        print(line)

#Striping the whitespace between lines
●	We can strip the whitespace from the right-hand side of the string using rstrip() from the string library

f = open('file.txt')
for line in f:
    line = line.rstrip()
    if line.startswith('From:') :
        print(line)

#Skipping with continue statement 
●	We can conveniently skip a line by using the continue statement

f = open('file.txt')
for line in f:
    line = line.rstrip()
    if not line.startswith('From:') :
        continue
    print(line)

#Using ‘in’ to Select Lines
●	We can look for a string anywhere in a line as our selection criteria

	f = open('file.txt')
for line in f:
   	       line = line.rstrip()
   	       if not '@uct.ac.za' in line : 
        		continue
   	       print(line)

