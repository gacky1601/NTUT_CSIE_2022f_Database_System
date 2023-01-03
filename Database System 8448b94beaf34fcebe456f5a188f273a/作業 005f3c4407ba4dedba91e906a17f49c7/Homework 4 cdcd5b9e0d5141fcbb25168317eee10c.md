# Homework 4

## 資工三 109310324 蔡宇翔

1.  Consider the universal relation 
    
    R = {A, B, C, D, E, F, G, H, I, J} 
    
    and the set of functional dependencies 
    
    F = {   {A, B}→{C},   {B, D}→{E, F},   {A, D}→{G, H},   {A}→{I},   {H}→{J} }.
    
    (a)What is the key for R?
    
    A,B,D，因為有A,B可以決定C、有A,D可以決定G,H,J、有B,D可以決定E,F，\
    
    有ABD即可決定A~J
    
    (b)Decompose R into 2NF.
    
    R1 = {A,B,C}
    F1 = {{A,B}→{C}}
    
    R2 = {B,D,E,F}
    F2 = {{B,D}→{E,F}}
    
    R3 = {A,D,G,H,J}
    F3 = {{A,D}→{G,H},{H}→{J}}
    
    R4 = {A,I}
    F4 = {{A}→{I}}
    
     
    
    (c)Based on your result in (b), decompose R into 3NF.
    
    R1 = {A,B,C}
    F1 = {{A,B}→{C}}
    
    R2 = {B,D,E,F}
    F2 = {{B,D}→{E,F}}
    
    R3 = {A,D,G,H}
    F3 = {{A,D}→{G,H}}
    
    R4 = {A,I}
    F4 = {{A}→{I}}
    
    R5 = {H,J}
    F5 = {{H}→{J}}
    
     
    
2. Consider the relation R, which has attributes that hold schedules of courses
and sections at a university; 
    
    R = {Course_no, Sec_no, Offering_dept,Credit_hours, Course_level, Instructor_ssn, Semester, Year, Days_hours,Room_no, No_of_students}. 
    
    Suppose that the following functional dependencies hold on R:
    
    {Course_no} → {Offering_dept, Credit_hours, Course_level}
    
    {Course_no, Sec_no, Semester, Year} → {Days_hours, Room_no,No_of_students, Instructor_ssn}
    
    {Room_no, Days_hours, Semester, Year} → {Instructor_ssn, Course_no,
    Sec_no}
    
    (a)What normal form is the relation in?
    
    1NF，{Course_no} → {Offering_dept,Credit_hours, Course_level},因此這個表格還存在部分功能相依
    
    故不滿足2NF
    
    (b)Try to determine which sets of attributes form keys of R.
    
    {Course_no, Sec_no, Semester, Year} 
    
    {Room_no, Days_hours, Semester, Year} 
    
    (c) Apply normalization until you cannot decompose the relations further.
    State the reasons behind each decomposition.
    
    R1 = {Course_no,Offering_dept, Credit_hours, Course_level}
    
    R2 = {Course_no, Sec_no, Semester, Year,Days_hours, Room_no,No_of_students,Instructor_ssn}
    

3.

(a) 

R=(30+9+9+40+10+8+1+4+4)+1=116bytes

(b) 

bfr= floor(B/R) = floor(512/116)=4 recored per block

b=ceiling(r/bfr)=ceiling(30000/4)=7500 blocks

(c) 

i.

Ri=(Vssn+P)=(9+6)=15bytes

bfri = 512/15 → 34

ii.

first-level index entries =number of disk blocks = 7500
⼀個block可以放34個record → 7500/34 = 221 blocks

iii.

second-level index entries = first-level index blocks = 221
second-level index blocks = 221/34 = 7
third-level index entries = second-level index blocks⼀樣 = 7
third-level index blocks = 7/34 = 1
因為只有1個block所以最⾼就到third-level

iv.

bi=221+7+1=229

v.

3+1=4

(d)

i.

the index record size is (Ssn + P) = 9 + 6 = 15

bfri = 512/15 = 34

ii.

first-level index entries=30000

blocks = 30000/34 = 883

iii.

second-level index entries = first-level index blocks = 883

second-level index blocks = 883/34 = 26

iv.

third-level index entries = second-level index blocks = 26

third-level index blocks = 26/34 = 1

最高third-level

v.

3 + 1 = 4

4.

![Untitled](Homework%204%20cdcd5b9e0d5141fcbb25168317eee10c/Untitled.png)

Primary index : data file is ordered on a keyfield (primary key) 

Secondary index : It may be generated from a field which is candidate key or nonkey with duplicate values

Clustering index : data file is ordered on a nonkey field