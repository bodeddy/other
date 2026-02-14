# Pseudocode design

I've been struggling a lot with completing tasks as set by The Odin Project, so I thought I would get better at writing pseudocode. In fact, and if I'm honest, I've not really been writing any pseudocode, which I believe is causing me problems. 

Resource: *Pseudocode, the Pseudocode Programming Process, and alternatives to the PPP* by Noah Doersing

Link: https://ps.informatik.uni-tuebingen.de/teaching/ss15/sct/StudentMaterial/09%20-%20Noah%20Doersing%20-%20pseudocode.pdf

## Good pseudocode

- Use precise, natural language descriptions of specific actions
- Avoid code-like statements
- Capture the intent of an action
- Describe what a design is doing, not exactly how it is going to be implemented

### Examples of good and bad pseudocode

**Good**
> Keep track of the current number of resources in use<br>
> If another resource is available<br>
>     Allocate a dialog box structure<br>
>     If a dialogue box structure could be allocated<br>
>         Note that one more resource is in use<br>
>         Initialize the resource<br>
>         Store the resource number at the location provided by the caller<br>
>     Endif<br>
> Endif<br>
> Return true if a new resource was crearted;else return false<br>

**Bad**
increment resource number by 1
allocate a dlg struct using malloc
if malloc() returns NULL then return 1
invoke OSrsrc_init to initialize a resource
    for the operating system
*hRsrcPtr = resource number
return 0

## PPP workflow

- Write a short high-level description of the routine
- Write high-level pseudocode
- Refine pseudocode until it is detailed enough to be translated into source code without much effort
- Check pseudocode for high-level mistakes and to understand all components
- Add high-level description of routine to code file
- Copy refined pseudocode into code file

### Example of different levels of pseudocode

**High-level description of routine**
> This routine returns a list of all students taking the SCT course in the given year, along with their final grades.

**High-level pseudocode**
> Validate the year
> Retrieve a list of students from the database
> Compute the final grades
> Return the names and grades as a list

**Mid-level pseudocode**
> If the year is valid
>     Connect to the database and retrieve info about all students in the given year
>     Keep a list of the students and their final grades
>     For all students
>         Calculate a weighted average of the three grades
>         Add their name and final grade to the list
>     Endfor
> Endif
> Return the list; or return false if no list could be generated for the given year
