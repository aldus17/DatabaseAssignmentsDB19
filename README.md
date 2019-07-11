# DatabaseAssignmentsDB19
This repository is created for Database assignment that I have made throughout my Database course.
The Assignements are based on the book "Database Systems The Complete Book Second Edition" by Hector Garcia Molina
# Chapter 2 Assignments

### Assignment 2.2.1.

**a)**  The attributes of each relation.
Accounts relation has 3 attributes acctNo, type, balance.
Customers relation has 4 attributes firstName, lastName, idNo and account.

**b)**  The tuples of each relation.
Tuples of Accounts relation:
12345 savings 12000
23456 checking 1000
34567 savings 25
	
Tuples of Customers relation:
Robbie Banks 901-222 12345
Lena Hand 805-333 12345
Lena Hand 805-333 23456
	
**c)**  The components of one tuple from each relation.
Accounts:
123456 acctNo
Savings type
12000 balance
	
Costumers:
Robbie firstName
Banks lastName
901-222 idNo
12345 account

**d)**  The relation schema for each relation.
Account: Accounts (acctNo, type. balance) 
Customers: Customers (firstName, lastName, idNo, account).

**e)**  The database schema.
Accounts (acctNo: integer, type: string, balance: float) 
Customers (firstName: string, lastName: string, idNo: string, account: integer).

**f)**  A suitable domain for each attribute.
Accounts: AccountNumber, typeOfAccount, AccountBalance
Costumers: firstName, lastName, idNumber, ccustomerAccount

### Assignment 2.2.2.

We indicate the attribute or attributes that form a key for a relation by
underlining the key attribute(s). For instance, the Movies relation could have
its schema written as:

Movies(title, year, length, genre)
Beers(name, manf(Manufactured), alcoProcent)

### Assignment 2.2.3.

**a)**  Three attributes and three tuples, like the relation Accounts of Fig. 2.6?
The order is irrelevant as long as they are not duplicated as there cannot be 2 same instances of a key. 
But 3 * 3 = 9, different ways to represent the relation.

**b)**  Four attributes and five tuples?
With 4 attributes, any one of them could be listed first, then of the remaining two, either could be next. 
So, there’s 4 * 5 = 20  possibilities for the ordering of the attributes. 
There’s 5 ways to order the tuples. So, overall, there’s 5*20 = 100  possible ways to represent the instance. 

**c)**  n attributes and m tuples?
N * M = X number of ways to represent the relation.

### Assignment 2.3.1.

a)  A suitable schema for relation Product.
```sql
	CREATE TABLE Product (
	        maker VARCHAR(30),
	        model INT, PRIMARY KEY
	        type VARCHAR(30)
	);
	
	Product(model, maker, type)
	
	b)  A suitable schema for relation PC.
	
	CREATE TABLE PC (
	        model INT, PRIMARY KEY
	        speed FLOAT, 
	        ram FLOAT
	        hd FLOAT,
	        price INT
	);
	
	PC(model, speed, ram, hd, price)
	
	c)  A suitable schema for relation Laptop.
	
	CREATE TABLE Laptop (
	        model INT, PRIMARY KEY
	        speed FLOAT,
	        ram FLOAT
	        hd FLOAT,
	        screen FLOAT,
	        price INT
	);
	
	Laptop(model, speed, ram, hd, screen, price)
	
	d)  A suitable schema for relation Printer.
	
	CREATE TABLE Printer (
	        model INT, PRIMARY KEY
	        color BOOLEAN, 
	        type VARCHAR(30),
	        price INT
	);
	
	Printer(model, color, type, price)
	
	e)  An alteration to your Printer schema from (d) to delete the attribute
color.

	ALTER TABLE Printer DROP color;
	
	f)  An alteration to your Laptop schema from (c) to add the attribute od
(optical-disk type, e.g., cd or dvd). Let the default value for this attribute
be ’none’ if the laptop does not have an optical disk.

	AFTER TABLE Laptop ADD od VARCHAR(30) DEFAULT ‘none’;
```
### Assignment 2.3.2.

A suitable schema for relation Classes.
```sql
	CREATE TABLE Classes (
	    class INT, PRIMARY KEY
	    type VARCHAR(30),
	    country VARCHAR(30),
	    numGuns INT,
	    bore FLOAT,
	    displacement FLOAT
	);
	
	Classes(class, type, country, numGuns, bore, displacement)
	
	b)  A suitable schema for relation Ships.
	Ships( _name_ , _class_ , launched)
	c)  A suitable schema for relation Battles .
	Battles( _name_ , date)
	
	d)  A suitable schema for relation Outcomes.
	Outcomes( _ships_ , battle, result)
	e)  An alteration to your Classes relation from (a) to delete the attribute
bore.
```sql
	    1 ALTER TABLE Classes DROP bore;
	
	f)  An alteration to your Ships relation from (b) to include the attribute
	yard giving the shipyard where the ship was built.
	```sql
    1 AFTER TABLE Ships ADD shipYardName VARCHAR(100) DEFAULT ‘none’;
```
# Chapter 5 Assignments

### Assignment 5.1.1.


The  value as a set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06}

As a bag:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}

Average value of the set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06} = 2,37

Average value of the bag would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}/13 = 2,48


### Assignment 5.1.2. 


The value of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160}

The average of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160} = 202

The value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}

The average value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}/13 = 215,38

### Assignment 5.1.2a. 

The relation πbore(Classes) as a set:
Bore{15, 16, 14, 18}

The relation πbore(Classes) as a bag:
Bore{15, 16, 14, 16, 15, 15, 14, 18}


### Assignment 5.1.2b. 

To make sure we get the bore for each ship, we can assume we make a bag projection which does not eliminate any typles created and use natural join as we both relations has attributes class.
PI_bore(Ships NATURAL JOIN Classes)

# Chapter 6 Assignments



