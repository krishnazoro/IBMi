# IBM i

## Definition

1. IBM i is an operating system made by IBM for its Power Systems servers.

2. It has built in database called DB2 so it can act like backend for running business applications

2. It’s mainly used by large businesses for secure, stable, and high-performance business applications.

3. It is used for 

- Banking

- Manufacturing

- Retail

- Insurance

4. IBM i is an operating system that supports programming languages like RPGLE, CL, COBOL, SQL, and Python.

5. It is fast and secure trusted by HDFC, SBI, ICICI, Axis, Toyota, Big bazzar, FedEx.

# Object-Based Architecture

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

1. The IBM i system contains many libraries.

2. Each library contains many objects, such as:

- Programs (*PGM)

- Files (*FILE — physical, logical, display, or printer)

- Menus (*MENU)

- Data Areas (*DTAARA)

- Commands (*CMD)

- and many others.

## Object

1. In IBM i, an object is the basic unit of storage.

2. It's how the system stores and manages everything like programs, files, libraries, and commands.

3. In simple statement the everything is an object the programs, files, commands, menus, and even libraries 
are objects stored in the system.

4. When a user creates an object in IBM i, the object type is automatically assigned by the system that is based on what kind of object you’re creating.

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
## Library

1. A Library in IBM i is a special object (type *LIB) that acts like a container or folder to store other objects such as programs, files, menus, and data areas.

2. They keep the system organized.

3. Help separate user data from system data.

4. Allow library lists (LIBL) to find objects easily

5. The code for Library.

```
CRTLIB MYLIB        /* Create a new library */
WRKLIB MYLIB        /* Work with library objects */
DSPLIB MYLIB        /* Display objects in library */
DLTLIB MYLIB        /* Delete the library */
```

## Program

1. A Program in IBM i is an object (type *PGM) that contains compiled instructions written in a programming language like RPGLE, CL, COBOL, or C.
    
2. which the system can execute to perform a specific task.

3. A program is what actually does the work in the IBM i system it can read or update files, display screens, print reports, run calculations.

## File

1. A File in IBM i is an object (type *FILE) that is used to store or handle data.

2. Files can be used for data storage, screen display, or printing output — depending on the type of file.

3. There are 5 types of files they are physical file, logical file, display file, printer file and ICF file

### Physical file

1. A Physical File is used to store actual data — like a table in a database.

2. Like an example a Excel sheet that contains real rows of data.

3. Example code

```
A          R CUSTREC
A            CUSTID       5P 0
A            CUSTNAME    20A
A            CITY        15A

```

4. When you write or read data from a file in RPGLE, it’s usually a Physical File.

### Logical file

1. A Logical File does not store data itself.

2. It shows data from a Physical File, but in a different view or order

3. Like an example filtered or sorted view of your Excel sheet the data is still in the same sheet (PF), but you see it differently.

### Display file

1. A Display File defines how information appears on the screen and how the user interacts with the program.

2. It is used mainly in interactive programs (like RPGLE interactive applications).

3. Like an example a DSPF is the user interface (UI) of your IBM i program it shows messages, lists, or input fields on a 5250 terminal screen.

### Printer file

1. A Printer File defines how printed output will look
it controls the layout, spacing, and fields of a printed report.

2. It’s usually used in batch RPGLE programs (non-interactive ones).

3. Like an example a PRTF is like a report template
it tells the system what to print and how to format it.

### ICF file

1. ICFF (Inter-Device Communication Function File) is used when the IBM i system communicates with an external system or device.

2. Like an example ICFF acts like a bridge it allows data exchange between IBM i and other external systems.

## Menu

1. A Menu is an *object (type *MENU) that provides a list of options or commands to help users navigate and run tasks easily.

2. It acts as a user interface to help people run programs or commands easily — without typing them manually.

3. A menu is like a main screen in IBM i where users can see choices like:

- 1. Display Employee Details  
- 2. Add New Employee  
- 3. Print Report  
- 4. Exit

## Status

1. Status in IBM i means the current condition or state of something such as a job, system, device, or program at a particular time.

# IBM i Command System

##  Pattern of the command

1. In IBM i command is easy to understand and it is using control language(CL) commands for IBM i commands. 

2. IBM i Command has comination that is 3+3+1 like example i need to display message you can write the code `DSPMSG`, `DSP` is 3 and `MSG` is another 3 but 1 is option this is a method.

3. If you forget any command you write first letter of the command and put asterisk(*) `D*`, it will display what are the commands available. 

## License

1. Without a license we can't access any file or folder in this even can' program.

2. Code for license what are we can access.

```
GO LICPGM 
```
3. `LICPGM` means license program this code is for we can see what are the license we have.

## Work with active jobs

1. It shows you a list of all active jobs like programs, users, or system processes currently running on the IBM i system.

2. You can also end, hold, or release jobs from this screen.

3. You can see which jobs are active, how much CPU they’re using, and their current status.

4. The code for work with active jobs.

```
WRKACT JOB
```

## Work with system status

1. This command is used to view the current status and performance of your IBM i system like how much memory, CPU, and storage is being used right now. 

2. It is like the task manager in the window.

3. Code for the system status.

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





---

# TN525j

## Definition

1. TN5250j is a Java-based 5250 terminal emulator.

2. That allows a computer to connect to an IBM i (AS/400) system using the 5250 communication protocol.

3. That providing users with the ability to interact with the IBM i server’s green-screen interface, run programs, execute commands, and access files and databases. 

4. IT get feels just like using a real IBM 5250 terminal.

5. Supports tasks like running RPGLE programs, CL commands, and database operations.

---

# RPGLE

## Definition

1. In this concept we are going to learn RPGLE program.

2. The abbrevation of RPGLE is Report Program Generator Language – Extended

3. It is high-level programming language used on IBM i (AS/400) systems for developing business applications.

4. It is an enhanced version of the original RPG language that supports modern programming features such as free-form coding, modularization, database access using SQL, and integration with other languages like Java or Python.

5. It can interact with IBM i databases directly.

6. Programs written in RPGLE are typically compiled and run on IBM i.

7. In this program there are lots of commands are used.




