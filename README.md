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

**a)**  A suitable schema for relation Product.
```sql
CREATE TABLE Product (
	maker VARCHAR(30),
	model INT, PRIMARY KEY
	type VARCHAR(30)
	);
```
Product(model, maker, type)

**b)**  A suitable schema for relation PC.
```sql
CREATE TABLE PC (
	model INT, PRIMARY KEY
	speed FLOAT, 
	ram FLOAT
	hd FLOAT,
	price INT
	);
```
PC(model, speed, ram, hd, price)
	
**c)**  A suitable schema for relation Laptop.
```sql
CREATE TABLE Laptop (
	model INT, PRIMARY KEY
	speed FLOAT,
	ram FLOAT
	hd FLOAT,
	screen FLOAT,
	price INT
	);
```
Laptop(model, speed, ram, hd, screen, price)
	
**d)**  A suitable schema for relation Printer.
```sql
CREATE TABLE Printer (
	model INT, PRIMARY KEY
	color BOOLEAN, 
	type VARCHAR(30),
	price INT
	);
```	
Printer(model, color, type, price)
	
**e)**  An alteration to your Printer schema from (d) to delete the attribute
color.
```sql
ALTER TABLE Printer DROP color;
```
**f)**  An alteration to your Laptop schema from (c) to add the attribute od
(optical-disk type, e.g., cd or dvd). Let the default value for this attribute
be ’none’ if the laptop does not have an optical disk.
```sql
	AFTER TABLE Laptop ADD od VARCHAR(30) DEFAULT ‘none’;
```

### Assignment 2.3.2.

**a)** A suitable schema for relation Classes.
```sql
CREATE TABLE Classes (
	class INT, PRIMARY KEY
	type VARCHAR(30),
	country VARCHAR(30),
	numGuns INT,
	bore FLOAT,
	displacement FLOAT
	);
```
Classes(class, type, country, numGuns, bore, displacement)
	
**b)**  A suitable schema for relation Ships.
Ships( _name_ , _class_ , launched)

**c)**  A suitable schema for relation Battles .
Battles( _name_ , date)
	
**d)**  A suitable schema for relation Outcomes.
Outcomes( _ships_ , battle, result)

**e)** An alteration to your Classes relation from (a) to delete the attribute
bore.
```sql
ALTER TABLE Classes DROP bore;
```
**f)**  An alteration to your Ships relation from (b) to include the attribute
	yard giving the shipyard where the ship was built.
```sql
AFTER TABLE Ships ADD shipYardName VARCHAR(100) DEFAULT ‘none’;
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

### Assignment 6.1.1.

If they are two different attributes, there will be a comma between them. Remember, in SQL, two names with no punctuation between them usually indicates that the second is an alias for the first:
```sql
    1 	SELECT A, B
```

### Assignment 6.1.2.

**a)**
```sql
	SELECT 	address
	FROM 	Studio
	WHERE 	name = 'MGM studios';
```

**b)**
```sql
	SELECT 	birthdate
	FROM 	MovieStar
	WHERE 	name = 'Sandra Bullock';
```

**c)**
```sql
	SELECT 	starName
	FROM 	StarsIn
	WHERE 	movieYear = 1980 OR movieTitle LIKE '%Love%';
```

**d)**
```sql
	SELECT 	*
	FROM 	MovieExec
	WHERE 	netWorth >= 10000000;
```

**e)**
```sql
	SELECT 	*
	FROM 	MovieStar
	WHERE 	gender = 'm' OR address LIKE '%Malibu%'; //% is like a wilcard search
```

### Assignment 6.1.3.

**a)**
```sql
	SELECT 	model, 
		speed, 
		hd
	FROM 	PC
	WHERE 	price < 1000;
```

**b)**
```sql
	SELECT  model, 
		speed AS gigahertz, 
		hd AS gigabytes
	FROM 	PC
	WHERE 	price < 1000;
```

**c)**
```sql
	SELECT 	maker, 
		'type'
	FROM 	Printer, 
		Product
	WHERE 	Product.model = Printer.model;
```

**d)**
```sql
	SELECT 	model, 
		ram, 
		screen
	FROM 	Laptop
	WHERE 	price > 1500;
```

**e)**
```sql
	SELECT 	*
	FROM 	printer
	WHERE 	color; //Puts out true, if we wanted false, then we need to say, NOT color.
```
	
**f)**
```sql
	SELECT 	model, 
		hd
	FROM 	PC
	WHERE 	speed = 3.2 AND price < 2000;
```

### Assignment 6.1.5.

**a)** a=10 OR b=20
All tuples where either a = 10 and NOT NULL while b takes any value (inclusive NULL as value);
Example could be: (10, 0), (10,1) … (10, -1) … (10, NULL).
Or b = 20 and NOT NULL, while a can take any value including NULL.
Examples could be: (0, 20), (1, 20) … (-1, 20) … (NULL, 20)
	
**b)** All tuples where a = 10 and b = 20 and none of them is NULL (10, 20)
	
### Assignment 6.2.1.

**a)**
```sql
	SELECT 	name
	FROM 	MovieStar
	WHERE 	movieTitle = 'Titanic' AND gender = 'm';
```

**b)**
```sql
	SELECT 	MovieStar.*
	FROM 	MovieStar, 
		StarsIn, 
		Movie
	WHERE 	MovieStar.name = StarsIn.starName
		AND Movie.studioName = 'MGM' 
		AND StarsIn.movieYear = 1995;
```

**c)**
```sql
	SELECT 	MovieExec.name 
	FROM 	Studio, 
		MovieExec 
	WHERE 	Studio.name = 'MGM' AND 
		AND presC# = cert#; 
```

**d)**
```sql
	SELECT 	M1.title 
	FROM 	Movie AS M1, 
		Movie AS M2 
	WHERE 	M2.title = 'Gone With the Wind' 
		AND M1.length > M2.length; 
```

**e)**
```sql
	SELECT 	ME1.name
	FROM 	MovieExec AS ME1, 
		MovieExec AS ME2
	WHERE 	ME1.name = 'Merv Griffin' AND
		ME2.netWorth > ME1.netWorth;
```

### Assignment 6.2.2.

**a)**
```sql

	SELECT 	product.maker AS manufacturer, 
		laptop.speed AS gigahertz
	FROM 	Product product, 
		Laptop laptop
	WHERE	laptop.hd >= 30
		AND product.model = laptop.model
		AND product.type= 'laptop';
```

**b)**
```sql
(
	SELECT 	Product.model, 
		price
	FROM 	pcstore.Product, pcstore.PC
	WHERE 	Product.model = PC.model AND
		maker = 'B')
UNION
(
	SELECT 	Product.model, price
	FROM 	Product, Laptop
	WHERE 	Product.model = Laptop.model AND
		maker = 'B');
```

**c)**
```sql
	SELECT 	Product.maker AS manufacturer
	FROM 	Product
	WHERE 	type = 'laptop' 
		AND NOT (
			type = 'pc' 
			OR type = 'printer'
			);
```

**d)**
```sql
	SELECT 	P.hd AS HDDSize
	FROM 	PC P
	WHERE
	(
		SELECT 	COUNT(*) 
		FROM 	PC P1
		WHERE 	P.hd=P1.hd
		) > 1
```

**e)**
```sql
	SELECT DISTINCT p1.model, 
				p2.model, 
				p1.speed, 
				p1.ram
						
	FROM 		PC p1, 
				PC p2
	
	WHERE 		p1.model > p2.model
				AND p1.speed = p2.speed
				AND p1.ram = p2.ram;
```

**d)**
```sql
	SELECT DISTINCT P.maker, 
					P.type
						
	FROM 		Product P, 
				Product P1
						
	WHERE 		P.maker = P1.maker
					AND P.model in (
						SELECT 	PC.model
						FROM 	pcstore.PC
						WHERE 	PC.speed > 2.80                                
					UNION
						SELECT LP.model
						FROM pcstore.Laptop LP
						WHERE Lp.speed > 2.80
	                  )
		AND P1.model in (
				SELECT 	PC.model
				FROM 	PC
				WHERE 	PC.speed > 2.80
			UNION
				SELECT 	LP.model
				FROM 	Laptop LP
				WHERE 	LP.speed > 2.80)
		AND P.model <> P1.model 
```
### Assignment 6.2.3.:

**a)**
```sql
	SELECT 	S.name AS shipName, 
		C.class AS shipClass, 
		C.displacement
	FROM 	Ships S, 
		Classes C
	WHERE 	S.class = C.class 
		AND C.displacement > 35.000;
```

**b)**
```sql
	SELECT 	name, 
		displacement, 
		numguns
	FROM 	Classes CL, 
		Ships SH, 
		Outcomes OC
	WHERE 	CL.class = SH.class 
		AND SH.name = OC.ship 
		AND OC.battle='Guadalcanal';
```

**c)**
```sql
	(
	SELECT 	S.name AS shipName
	FROM 	Ships S
	)
	UNION
	(
	SELECT 	SO.ship AS shipName
	FROM 	Outcomes SO;
	)
```

**d)**
```sql
	SELECT 	C.country
	FROM 	Classes C
	WHERE 	type = 'bb'
	
	INTERSECT
	
	SELECT 	C.country
	FROM 	battleships.Classes C
	WHERE 	type = 'bc';
```

**e)**
```sql
	SELECT 	o1.ship 
	FROM 	outcomes o1 
		JOIN battles b1 ON o1.battle=b1.name,
		outcomes o2 
		JOIN battles b2 ON o2.battle = b2.name
	WHERE 	o1.ship = o2.ship
		AND o1.result='damaged';
```

**f)**
```sql
	SELECT 	battles.name, country 
	FROM 	battles,
		outcomes,
		ships,
		classes 
	WHERE 	battles.name=outcomes.battle 
		AND outcomes.ship = ships.name 
		AND ships.class=classes.class
	GROUP BY 	battles.name, 
		classes.country
	HAVING COUNT(classes.country) >= 1;
```