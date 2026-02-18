# IBM I

## What is IBM I

  IBM i is an operating system made by IBM for its
 Power Systems servers. It has built in database called DB2 so it can act like backend for running business applications.

   It’s mainly used by large businesses for
   secure, stable, and high-performance business applications.

 It is used for 

- Banking

- Manufacturing

- Retail

- Insurance

 IBM i is an operating system that supports programming languages like RPGLE, CL, COBOL, SQL, and Python.

 It is fast and secure trusted by HDFC, SBI, ICICI, Axis, Toyota, Big bazzar, FedEx.

## What is object-Based Architecture

```
IBM i System
│
├── QSYS (System Library)
│     ├── QCLSRC   (*FILE)
│     ├── QGPL     (*LIB)
│     └── QPRINT   (*OUTQ)
│
└── MYLIB (User Library)
      ├── PAYROLL   (*PGM)
      ├── EMPFILE   (*FILE)
      ├── MAINMENU  (*MENU)
      ├── STATUS    (*DTAARA)
      └── MYPF      (*FILE)

```

  The IBM i system contains many libraries.Each library contains many objects, such as:

- Programs (*PGM)

- Files (*FILE — physical, logical, display, or printer)

- Menus (*MENU)

- Data Areas (*DTAARA)

- Commands (*CMD)

- and many others.

### Object

  In IBM i, an object is the basic unit of
storage.It's how the system stores and manages everything like programs, files, libraries, and commands.

In simple statement the everything is an object the programs, files, commands, menus, and even libraries are objects stored in the system.

 When a user creates an object in IBM i, the object type is automatically assigned by the system that is based on what kind of object you’re creating.

5. Example code

```
  Object name      |       Object type
------------------ |----------------------
 CRTLIB MYLIB      |        Library
                   |
 CRTPF EMPFILE     |        Physical file
                   |
 CRTDSPF CUSTDSP   |        Display file
                   |
 CRTPGM PAYROLL    |        Program
                   |
 CRTMSGF MSGFILE   |        Message file

```
### Library

A Library in IBM i is a special object (type *LIB) that acts like a container or folder to store other objects such as programs, files, menus, and data areas.They keep the system organized.

 Help separate user data from system data.Allow library lists (LIBL) to find objects easily

 The code for Library.

```
CRTLIB MYLIB        /* Create a new library */
WRKLIB MYLIB        /* Work with library objects */
DSPLIB MYLIB        /* Display objects in library */
DLTLIB MYLIB        /* Delete the library */
```

### Program

 A Program in IBM i is an object (type *PGM) that contains compiled instructions written in a programming language like RPGLE, CL, COBOL, or C.
    
 which the system can execute to perform a specific task.A program is what actually does the work in the IBM i system it can read or update files, display screens, print reports, run calculations.

### File

 A File in IBM i is an object (type *FILE) that is used to store or handle data.Files can be used for data storage, screen display, or printing output — depending on the type of file.

There are 5 types of files they are physical file, logical file, display file, printer file and ICF file

#### Physical file

 A Physical File is used to store actual data — like a table in a database. Like an example a Excel sheet that contains real rows of data.

 Example code

```
A          R CUSTREC
A            CUSTID       5P 0
A            CUSTNAME    20A
A            CITY        15A

```

When you write or read data from a file in RPGLE, it’s usually a Physical File.

#### Logical file

 A Logical File does not store data itself. It shows data from a Physical File, but in a different view or order.

 Like an example filtered or sorted view of your Excel sheet the data is still in the same sheet (PF), but you see it differently.

### Display file

A Display File defines how information appears on the screen and how the user interacts with the program. It is used mainly in interactive programs (like RPGLE interactive applications).

Like an example a DSPF is the user interface (UI) of your IBM i program it shows messages, lists, or input fields on a 5250 terminal screen.

### Printer file

A Printer File defines how printed output will look it controls the layout, spacing, and fields of a printed report. It’s usually used in batch RPGLE programs (non-interactive ones).

Like an example a PRTF is like a report template
it tells the system what to print and how to format it.

### ICF file

ICFF (Inter-Device Communication Function File) is used when the IBM i system communicates with an external system or device.

Like an example ICFF acts like a bridge it allows data exchange between IBM i and other external systems.

## Menu

 A Menu is an *object (type *MENU) that provides a list of options or commands to help users navigate and run tasks easily.

 It acts as a user interface to help people run programs or commands easily — without typing them manually.

 A menu is like a main screen in IBM i where users can see choices like:

- 1. Display Employee Details  
- 2. Add New Employee  
- 3. Print Report  
- 4. Exit

## Status

  Status in IBM i means the current condition or state of something such as a job, system, device, or program at a particular time.

# IBM i Command System

##  Pattern of the command

  In IBM i command is easy to understand and it is using control language(CL) commands for IBM i commands.

  IBM i Command has comination that is 3+3+1 like example i need to display message you can write the code `DSPMSG`, `DSP` is 3 and `MSG` is another 3 but 1 is option this is a method.

  If you forget any command you write first letter of the command and put asterisk(*) `D*`, it will display what are the commands available. 

## License

 Without a license we can't access any file or folder in this even can' program.Code for license what are we can access.

```
GO LICPGM 
```
 `LICPGM` means license program this code is for we can see what are the license we have.

## Work with active jobs

It shows you a list of all active jobs like programs, users, or system processes currently running on the IBM i system.

You can also end, hold, or release jobs from this screen.You can see which jobs are active, how much CPU they’re using, and their current status.
The code for work with active jobs.

```
WRKACT JOB
```

## Work with system status

This command is used to view the current status and performance of your IBM i system like how much memory, CPU, and storage is being used right now. It is like the task manager in the window Code for the system status.

```
WRKSYS STS
```
## Difference b/w WRKACT JOB vs WRKSYS STS

### WRKACT JOB

- Shows details of all active jobs running on the system like each program, user, and subsystem.

- You can check what’s using CPU, or which job is slow or stuck.

### WRKSYS STS

- Shows overall system performance — like CPU usage, memory, and storage.

- It's like the task manger.

## Command entry

You can see what are the commands enter in the pub400 on that login.

```
CALL QCMD
```
      




---

# TN525j

## Definition

TN5250j is a Java-based 5250 terminal emulator. That allows a computer to connect to an IBM i (AS/400) system using the 5250 communication protocol.

That providing users with the ability to interact with the IBM i server’s green-screen interface, run programs, execute commands, and access files and databases. 

 IT get feels just like using a real IBM 5250 terminal.Supports tasks like running RPGLE programs, CL commands, and database operations.

---

# RPGLE

## Definition

 In this concept we are going to learn RPGLE program. The abbrevation of RPGLE is Report Program Generator Language – Extended. It is high-level programming language used on IBM i (AS/400) systems for developing business applications.

 It is an enhanced version of the original RPG language that supports modern programming features such as free-form coding, modularization, database access using SQL, and integration with other languages like Java or Python.

 It can interact with IBM i databases directly Programs written in RPGLE are typically compiled and run on IBM i. In this program there are lots of commands are used.

## Convertion of variable fixed format to free format

### Fixed format

Fixed format (in RPG or RPGLE) means the old style of writing RPG code where each part of the line must be written in a specific column. It is the traditional way of writing RPG before free-format was introduced.

Variable names in certain columns. Result fields in certain columns. Keywords in certain columns.

6. Example

```

D Number3    S    3I 0     

```
 D means Definition specification it means it is used to declare
Variables, Data structures, Constants, Arrays, Prototypes (procedures).

Number 3 is variable name and S means standalone it means a standalone variable means a variable that is not part of any group, class, array, structure, or object and it exists independently by itself.

3I 0 means I means data type like integer, float, packed and zoned and 3 means length of the variable. 

### Free format

Free format in RPGLE means you can write your code anywhere on the line, without following strict column positions.

It is the modern style of RPG programming. Write code freely like Java, Python, C. More readable and easier to learn.

5. Example

```

DCL-S Number3 int(3);

```

DCL means declare and S means standalone and Number3 means variable name and int means data types and 3 means length of the variable. 

### Convertion of fixed format to free format

```

D Number3    S    3I 0   --- Fixed format

DCL-S Number3 int(3); --- Free format

```

## Convertion of character fixed format to free format

It is same like convertion of character fixed format to fre format. Convertion using char keyword

```

D FirstName     S     30A  -- Fixed format

DCL-S FirstName     char(30); -- Free format

```
3. Converstion using varying keyword

```

D FirstName     S     30A   varying   -- Fixed format

DCL-S FirstName     varchar(30); -- Free format

```

4. Converstion using Like keyword

```

D LastName     S          Like(FirstName)   -- Fixed format

DCL-S LastName     Like(FirstName); -- Free format

```
## My first program 

```

**FREE
      DSPLY 'HELLO WORLD' ;
      *INLR = *ON ;
      RETURN;

```

**FREE is used to enable free format syntax and you can write code anywhere on the line. DSPLY 'HELLO WORLD' if call the program the hello world will be display.

*INLR = *ON means last record indicator and *ON means true.























