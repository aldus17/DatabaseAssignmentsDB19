# DatabaseAssignmentsDB19
This repository is created for Database assignment that I have made throughout my Database course.
The Assignements are based on the book "Database Systems The Complete Book Second Edition" by Hector Garcia Molina
# Chapter 2 Assignments

### Assignment 2.2.1.:

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

### Assignment 2.2.2.:

We indicate the attribute or attributes that form a key for a relation by
underlining the key attribute(s). For instance, the Movies relation could have
its schema written as:

Movies(title, year, length, genre)
Beers(name, manf(Manufactured), alcoProcent)

### Assignment 2.2.3.:

**a)**  Three attributes and three tuples, like the relation Accounts of Fig. 2.6?
The order is irrelevant as long as they are not duplicated as there cannot be 2 same instances of a key. 
But 3 * 3 = 9, different ways to represent the relation.

**b)**  Four attributes and five tuples?
With 4 attributes, any one of them could be listed first, then of the remaining two, either could be next. 
So, there’s 4 * 5 = 20  possibilities for the ordering of the attributes. 
There’s 5 ways to order the tuples. So, overall, there’s 5*20 = 100  possible ways to represent the instance. 

**c)**  n attributes and m tuples?
N * M = X number of ways to represent the relation.

### Assignment 2.3.1.:

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

### Assignment 2.3.2.:

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

### Assignment 5.1.1.:


The  value as a set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06}

As a bag:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}

Average value of the set would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 2.20, 2.00, 1.86, 3.06} = 2,37

Average value of the bag would be:
Speed{2.66, 2.10, 1.42, 2.80, 3.20, 3.20, 2.20, 2.20, 2.00, 2.80 1.86, 2.80, 3.06}/13 = 2,48


### Assignment 5.1.2.:


The value of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160}

The average of hd(PC) would be as a set:
hd{250, 80, 320, 200, 160} = 202

The value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}

The average value of hd(PC) would be as a bag:
hd{250, 250, 80, 250, 250, 320, 200, 250, 250, 300, 160, 160, 80}/13 = 215,38

### Assignment 5.1.2a.:

The relation πbore(Classes) as a set:
Bore{15, 16, 14, 18}

The relation πbore(Classes) as a bag:
Bore{15, 16, 14, 16, 15, 15, 14, 18}


### Assignment 5.1.2b.: 

To make sure we get the bore for each ship, we can assume we make a bag projection which does not eliminate any typles created and use natural join as we both relations has attributes class.
PI_bore(Ships NATURAL JOIN Classes)

# Chapter 6 Assignments

### Assignment 6.1.1.:

If they are two different attributes, there will be a comma between them. Remember, in SQL, two names with no punctuation between them usually indicates that the second is an alias for the first:
```sql
    1 	SELECT A, B
```

### Assignment 6.1.2.:

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

### Assignment 6.1.3.:

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

### Assignment 6.1.5.:

**a)** a=10 OR b=20
All tuples where either a = 10 and NOT NULL while b takes any value (inclusive NULL as value);
Example could be: (10, 0), (10,1) … (10, -1) … (10, NULL).
Or b = 20 and NOT NULL, while a can take any value including NULL.
Examples could be: (0, 20), (1, 20) … (-1, 20) … (NULL, 20)
	
**b)** All tuples where a = 10 and b = 20 and none of them is NULL (10, 20)
	
### Assignment 6.2.1.:

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

### Assignment 6.2.2.:

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

**f)**
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

### Assignment 6.3.1.:

**a)**
```sql
	SELECT 	pro.maker AS maker, 
		pc.speed AS speedOfPC
	FROM 	Product pro, 
		Pc pc
	WHERE 	pc.model IN (
			SELECT pc.model
			FROM Pc
			WHERE pro.model = pc.model 
			AND pc.speed <= 3.0
	);
```

**b)**
```sql
	SELECT 	p1.price AS PrinterHigestPrice, 
		p1.model AS printerModel
	FROM 	Printer p1
	WHERE 	p1.price IN (
		SELECT MAX(p2.price)
		FROM Printer p2
	);
```

**c)**
```sql
	SELECT 	l1.model AS laptopModel, 
		l1.speed AS laptopSpeed
	FROM 	Laptop l1
	WHERE 	l1.speed < ANY (
		SELECT 	p1.speed
		FROM 	PC p1        
	);
```

**d)**
```sql
	SELECT 	model, 
		price
	FROM 	(
		SELECT 	model, 
			price
		FROM 	PC
	UNION
		SELECT 	model, 
			price
		FROM 	Laptop
	UNION
		SELECT 	model, 
			price
		FROM 	Printer) Mx1
	WHERE 	Mx1.price IN (
	SELECT MAX(price)
	FROM	(
		SELECT 	price
		FROM 	PC
	UNION
		SELECT 	price
		FROM 	Laptop
	UNION
		SELECT 	price
		FROM 	Printer
) Mx2);
```

**e)**
```sql
	SELECT 	pro.maker, 
		pro.model
	FROM 	Printer pri, 
		Product pro
	WHERE 	pri.color = true
		AND pro.model = pri.model
		AND pri.price <= all (
		SELECT 	p.price 
		FROM 	Printer p
		WHERE 	pri.color = true
	    );
```

### Assignment 6.3.2.:

**a)**
```sql
	SELECT 	cl1.country
	FROM 	Classes cl1
	WHERE 	cl1.numGuns >= ALL (
		SELECT 	cl2.numGuns
		FROM 	Classes cl2
	);
```

**OR THIS QUERY**

```sql
	SELECT 	cl1.country
	FROM 	Classes cl1
	WHERE 	cl1.numGuns = (
		SELECT 	MAX(cl2.numGuns)
		FROM 	Classes cl2
);
```

**b)**
```sql
	SELECT 	sh.class, 
		sh.name
	FROM 	Ships sh
	WHERE 	sh.name IN (
		SELECT 	o.ship
		FROM 	Outcomes o
		WHERE 	o.result = 'sunk'
);
```

**Or you can use EXISTS to test the condition under it.**

```sql
	SELECT sh.class, 
		sh.name
	FROM 	Ships sh
	WHERE EXISTS(
	SELECT 	*
	FROM 	Outcomes o
	WHERE 	sh.name = o.ship AND
		o.result= 'sunk');
```

**c)**
```sql
	SELECT 	sh1.name, cl1.bore
	FROM 	Ships sh1, 
		Classes cl1
	WHERE 	cl1.bore = ANY (
		SELECT 	cl2.bore
		FROM 	Classes cl2
		WHERE 	cl1.class = sh1.class
		AND cl2.bore = 16;
```

**d)**
```sql
	SELECT 	o.battle
	FROM 	Outcomes o
	WHERE 	o.ship IN (
		SELECT 	sh.name
		FROM 	Ships sh
		WHERE 	sh.class = 'Kongo'
);
```

### Assignment 6.4.1.:

**a)**
```sql
	SELECT DISTINCT ON 	(pc.speed) 
		pc.speed, 
		pc.model
	FROM 	PC pc 
	WHERE 	pc.speed <= 3;
```

**b)**
```sql
	SELECT DISTINCT ON 	(pr.maker) pr.maker, 
		lp.model, 
		lp.hd
	FROM 	Product pr, 
		Laptop lp
	WHERE 	pr.model = lp.model 
		AND lp.hd <= 100;
```

**c)**
```sql
	SELECT DISTINCT ON 	(PC.model, PC.price) PC.model, 
		PC.price
	FROM 	Product pr, 
		PC PC
	WHERE 	pr.maker='B' 
		AND pr.model = PC.model
	UNION
	SELECT DISTINCT ON 	(L.model, L.price) L.model, 
		L.price
	FROM 	Product pr, 
		Laptop L
	WHERE pr.maker='B' 
		AND pr.model = L.model
	UNION
	SELECT DISTINCT ON 	(print.model, print.price) print.model, 
		print.price
	FROM 	Product pr, 
		Printer print
	WHERE pr.maker='B' 
		AND pr.model = print.model
```

**d)**
```sql
	SELECT DISTINCT ON 	(print.model) print.model, 
		print.color
	FROM 	Printer print
	WHERE 	print.color = true;
```

**e)**
```sql
	SELECT DISTINCT ON 	(pr.maker) pr.maker, 
		pr.type
	FROM 	Product pr
	WHERE 	type = 'laptop';
```

### Assignment 6.4.6.:

**a)**
```sql
	SELECT 	AVG(pc.speed)
	FROM 	pcstore.PC pc;
```

**b)**
```sql
	SELECT 	AVG(lp.speed)
	FROM 	Laptop lp
	WHERE 	lp.price > 1000;
```

**c)**
```sql
	SELECT 	AVG(pc.speed)
	FROM 	PC pc
	JOIN 	Product pr
	ON 	pc.model = pr.model
	WHERE 	pr.maker = 'A';
```

**d)**
```sql
	SELECT AVG( price ) Avg_Price
	FROM((
		SELECT 	pc.Price
		FROM 	PC pc
		JOIN 	Product prod
		ON 	pc.Model = prod.Model
		WHERE 	prod.Maker = 'D')
		UNION ALL (
	SELECT 	l.Price
	FROM 	Laptop l
	JOIN 	Product prod
	ON 	l.Model = prod.Model
	WHERE 	prod.Maker = 'D')
) q;
```

**e)**
```sql
	SELECT 	AVG(pc.price), 
		pc.speed  
	FROM 	PC pc 
	GROUP BY 	pc.speed;
```
**f)**
```sql
	SELECT 	AVG(lp.screen),
		pr.maker  
	FROM 	Product pr
	JOIN 	Laptop lp
	ON pr.model = lp.model 
		AND pr.type = 'laptop'
	GROUP BY 	pr.maker;
```

**g)**
```sql
	SELECT 	pr.maker, 
		COUNT(pr.model) 
	FROM 	Product pr 
	WHERE 	pr.type='pc' 
	GROUP BY 	pr.maker 
	HAVING COUNT(pr.model) >=3;
```

**h)**
```sql
	SELECT DISTINCT pr.maker, 
		MAX(pc1.price) AS Max_Price
	FROM 	Product pr, 
		PC pc1
	WHERE 	pr.type='pc' 
		AND pc1.price=(
			SELECT DISTINCT MAX(pc2.price) 
			FROM 	PC pc2
			WHERE 	pc2.model = pr.model) 
			GROUP BY 	pr.maker;
```

**i)**
```sql
	SELECT DISTINCT 	pc.speed, 
		AVG(pc.price) AS AVG_Price 
	FROM 	PC pc 
	INNER JOIN 	Product pr 
	ON pc.model = pr.model 
	-- MAtching values in both tables
	WHERE 	pc.speed > 2
	GROUP BY 	pc.speed
```

### Assignment 6.4.7.:

**a)**
```sql
	SELECT 	COUNT(Class)
	FROM 	Classes cl
	WHERE 	cl.type = 'bb' 
	-- BB is battleship where BC are battlecrusiers
```

**b)**
```sql
	SELECT 	AVG(cl.numGuns), 
		cl.type
	FROM 	Classes cl
	WHERE 	cl.type = 'bb'
	GROUP by 	cl.type 
	-- Not needed, but just to check
```

**c)**
```sql
	SELECT 	AVG(cl.numGuns)
	FROM 	Classes cl, 
		Ships sh
	WHERE 	sh.class = cl.class 
		AND type = 'bb';
	-- The result is different for both, so yes, there is a difference on how we check the number of guns for only Classes or all the bb of the the Ships. 
```

**d)**
```sql
	SELECT 	MIN(sh.launched), 
		sh.class
	FROM 	Ships sh 
	GROUP BY 	sh.class
```

**e)**
```sql
	SELECT 	COUNT(o.ship), 
		sh.class
	FROM 	Outcomes o, 
		Ships sh
	WHERE 	o.ship = sh.name 
		AND o.result = 'sunk'
	GROUP BY 	sh.class
```

