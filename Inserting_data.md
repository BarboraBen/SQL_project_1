## Insert data to table customer
```
INSERT INTO customer (first_name, last_name, email, mobile, address)
VALUES 
	('Jana', 'Malá', 'jana.mala@gmail.com', '+420775645789', 'Komenského 45, Praha 3, 13000'),
	('Jan', 'Nový', 'jan.novy@gmail.com', '+420775645123', 'Palackého 5, Praha 3, 13000'),
	('Karel', 'Novák', 'karel.novak@gmail.com', '+420775645456', 'Hrdinů 55, Praha 3, 13000'),
	('Lenka', 'Veselá', 'lenka.vesela@gmail.com', '+420775645987', 'Hamsíkova 65, Praha 3, 13000'),
	('Martin', 'Beneš', 'martin.benes@gmail.com', '+420775645654', 'Italská 75, Praha 3, 13000'),
	('Petra', 'Krásná', 'petra.krasna@gmail.com', '+420775645321', 'Kudrnova 85, Praha 3, 13000'),
	('Lada', 'Janů', 'lada.janu@gmail.com', '+420605645789', 'Budějovická 95, Praha 3, 13000'),
	('Dan', 'Kovář', 'dan.kovar@gmail.com', '+420728645789', 'Plzeňská 6, Praha 3, 13000'),
	('Jan', 'Jílek', 'jan.jilek@gmail.com', '+420702645789', 'Vrchlického 15, Praha 3, 13000'),
	('Dana', 'Kosová', 'dana.kosova@gmail.com', '+420721645789', 'Růžová 63, Praha 3, 13000');
```

 ## Insert data to table country
```
INSERT INTO country (country_name, country_code)
VALUES 
	('Italy', 'ITA' ),
	('France', 'FRA' ),
	('Spain', 'ESP' ),
	('Greece', 'GRC' ),
	('Portugal', 'PRT' ),
	('Bulgaria', 'BGR' );
```
 
 ## Insert data to table hotel
```
INSERT INTO hotel (country_id, address, star_rating, hotel_name)
VALUES 
	(1,"Via Ballino 50, Roma",4,"Pacific"),
  (1,"Via Roma 50, Venezia",4,"Sonya"),
  (2,"Rue Parradis 50, Nice",5,"Condesa"),
  (2,"Rue de France 50, Marseille",5,"Rocamar"),
  (3,"Avenida Diagonal 5, Barcelona",4,"Barcelona Princess"),
  (3,"Ramon Turro 15, Malaga",3,"Ilunion"),
  (4,"Leoforos Venizelou 33, Athens",4,"Arion"),
  (4,"Acharnon 33",3,"Xenophon"),
  (5,"Rua Nova 50, Porto",4,"Alameda"),
  (5,"Av. Rovisco 50, Lisabon",3,"Smy Lisboa"),
  (6,"Siemenovsko shosse 64, Sofia",3,"Jasmin");
```


  ## Insert data to table flight_tickets
```
INSERT INTO flight_tickets (depart_airport, destination_airport, airlines, depart_time, return_depart_time)
VALUES 
	('Václav Havel Airport Prague', 'Rome–Fiumicino International Airport', 'Wizz Air', '2023-07-05 12:00:00+01', '2023-07-10 18:00:00+02' ),
	('Václav Havel Airport Prague', 'Barcelona–El Prat', 'Wizz Air', '2023-08-05 12:00:00+01', '2023-08-15 18:00:00+02' ),
	('Václav Havel Airport Prague', 'Athens International', 'Wizz Air', '2023-08-04 12:00:00+01', '2023-08-16 18:00:00+02' ),
	('Václav Havel Airport Prague', 'Lisbon Portela', 'Wizz Air', '2023-07-06 12:00:00+01', '2023-07-16 18:00:00+02' ),
	('Václav Havel Airport Prague', 'Nice Côte d Azur International', 'Wizz Air', '2023-09-05 12:00:00+01', '2023-09-12 18:00:00+02' ),
	('Václav Havel Airport Prague', 'Sofia', 'Ryanair', '2023-08-20 12:00:00+01', '2023-08-30 18:00:00+02' );
```


  ## Insert data to table holiday_package
```
INSERT INTO holiday_package (hotel_id, f_tickets_id, depart_date, return_date, price_adult, price_child)
VALUES 
	(401, 601, '2023-07-05', '2023-07-10, 20000, 10000),
	(405, 602, '2023-08-05', '2023-08-15', 30000, 15000),
	(407, 603, '2023-08-04', '2023-08-16', 35000, 20000),
	(410, 604, '2023-07-06', '2023-07-16',33000, 24000),
	(403, 605, '2023-09-05', '2023-09-12', 40000, 25000),
	(411, 606, '2023-08-20', '2023-08-30', 25000, 15000);
```
	
 ## Insert data to table booking
```
INSERT INTO booking (customer_id, h_package_id, book_date, no_adults, no_children)
VALUES 
	(1, 307, '2023-03-06', 2, 1 ),
	(1, 308, '2023-03-07', 2, 0 ),
	(2, 308, '2023-04-06', 4, 0 ),
	(3, 308, '2023-04-06', 2, 3 ),
	(4, 309, '2023-04-06', 2, 0 ),
	(5, 309, '2023-05-06', 1, 0 ),
	(6, 309, '2023-05-06', 2, 1 ),
	(7, 311, '2023-06-06', 2, 2 ),
	(8, 311, '2023-06-06', 2, 2 ),
	(9, 311, '2023-06-08', 2, 0 ),
	(10, 312, '2023-07-06', 3, 0);
```

  ## Insert data to table payment
```
INSERT INTO booking (customer_id, booking_id, card_number, date_of payment)
VALUES 
	(1, 223, 123456981236,'2023-03-20'),
	(1, 224, 123456987894,'2023-03-20'),
	(2, 225, 123456986547, '2023-04-30'),
	(3, 226, 123456983698, '2023-04-30'),
	(4, 227, 123456987895, '2023-04-30'),
	(5, 228, 123456982587, '2023-05-30'),
	(6, 229, 123456987412, '2023-05-30' ),
	(7, 230, 123456982584, '2023-06-15'),
	(8, 231, 123456983652, '2023-06-15'),
	(9, 232, 123456981452, '2023-06-15',
	(10, 233, 123456987856, '2023-07-06');
``` 
	
