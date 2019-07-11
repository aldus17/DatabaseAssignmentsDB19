# DatabaseAssignmentsDB19
This repository is created for Database assignment that I have made throughout my Database course.
The Assignements are based on the book "Database Systems The Complete Book Second Edition" by Hector Garcia Molina

# Chapter 5 Assignments

## Assignment 5.1.1.


The  value as a set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06}

As a bag:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}

Average value of the set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06} = 2,37

Average value of the bag would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}/13 = 2,48


## Assignment 5.1.2. 


The value of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160}

The average of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160} = 202

The value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}

The average value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}/13 = 215,38

## Assignment 5.1.2a. 

The relation πbore(Classes) as a set:
Bore{15, 16, 14, 18}

The relation πbore(Classes) as a bag:
Bore{15, 16, 14, 16, 15, 15, 14, 18}


## Assignment 5.1.2b. 

To make sure we get the bore for each ship, we can assume we make a bag projection which does not eliminate any typles created and use natural join as we both relations has attributes class.
PI_bore(Ships NATURAL JOIN Classes)

# Chapter 6 Assignments



