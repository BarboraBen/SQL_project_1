## Create database
``` CREATE DATABASE Travel_agency; ```
## Create tables
```
CREATE TABLE IF NOT EXISTS customer
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    first_name character varying(20) NOT NULL,
    last_name character varying(20)  NOT NULL,
    email character varying(100)  NOT NULL,
    mobile character varying(15) NOT NULL,
    address character varying(100) NOT NULL,
    CONSTRAINT customer_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS booking
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 21 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    customer_id integer NOT NULL,
    h_package_id integer NOT NULL,
    book_date date NOT NULL,
    paid boolean NOT NULL DEFAULT false,
    no_adults integer NOT NULL,
    no_children integer NOT NULL DEFAULT 0,
    CONSTRAINT booking_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS holiday_package
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 301 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    hotel_id integer NOT NULL,
    f_ticket_id integer NOT NULL,
    country_id integer NOT NULL,
    depart_date date NOT NULL,
    return_date date NOT NULL,
    price_adult integer NOT NULL,
    price_child integer NOT NULL,
    CONSTRAINT holiday_package_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS payment
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    customer_id integer NOT NULL,
    h_package_id integer NOT NULL,
    card_number integer NOT NULL,
    date_of_payment date NOT NULL,
    CONSTRAINT payment_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS hotel
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    h_package_id integer NOT NULL,
    country_id integer NOT NULL,
    address character varying(100) NOT NULL,
    star_rating integer NOT NULL,
    CONSTRAINT hotel_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS country
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    name character varying(50) NOT NULL,
    country_cod character varying(3) NOT NULL,
    CONSTRAINT country_pkey PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS filght_tickets
(
    id integer NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 2147483647 CACHE 1 ),
    h_package_id integer NOT NULL,
    depart_airport character varying(100)  NOT NULL,
    destination_airport character varying(100) NOT NULL,
    "Airlines" character varying(100) NOT NULL,
    CONSTRAINT filght_tickets_pkey PRIMARY KEY (id)
);
```
