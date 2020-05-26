# SQL 1 Afternoon

## Person

create table person (
person_id serial primary key,
  name varchar(30),
  age int,
  height int,
  city varchar(20),
  favorite_color varchar(15)
);

insert into person
(name, age, height, city, favorite_color)
values
('Ben', 23, 178, 'Chico', 'Blue'),
('Dalton', 23, 190, 'Redding', 'Green'),
('Nick', 24, 172, 'Chico', 'Orange'),
('Andrew', 22, 167, 'Redding', 'Red'),
('Josh', 30, 180, 'Orem', 'Blue');

select * from person order by height desc;

select * from person order by height asc;

select * from person order by age desc;

select * from person
where age > 20;

select * from person
where age = 18;

select * from person
where age < 20
or age > 30;

select * from person
where age != 27;

select * from person
where favorite_color != 'Red';

select * from person
where favorite_color != 'Red'
and favorite_color != 'Blue';

select * from person
where favorite_color = 'Orange'
or favorite_color = 'Green';

select * from person
where favorite_color in ('Orange', 'Green', 'Blue');

select * from person
where favorite_color in ('Purple', 'Yellow');


## Table

create table orders (
order_id serial primary key,
  person_id int,
  product_name varchar(50),
  product_price numeric(4, 2),
  quantity int
);

insert into orders (person_id, product_name, product_price, quantity)
values
(1, 'basketball', 15.23, 3),
(2, 'toothpaste', 5.26, 2);

select * from orders;

select sum(quantity) from orders;

select sum(quantity * product_price) from orders;

select sum(quantity * product_price) from orders
where person_id = 1


## Artist

insert into artist (name)
values
('Bob Ross'),
('Vangauh'),
('Picasso');

select * from artist order by name desc limit 10;

select * from artist order by name asc limit 5;

select * from artist
where name like ('Black%');

select * from artist
where name like ('%Black%');


## Employee

select (first_name, last_name) from employee
where city = 'Calgary';

select birth_date from employee
order by birth_date desc limit 1;

select birth_date from employee
order by birth_date asc limit 1;

select * from employee
where reports_to = 2;

select count(*) from employee
where city = 'Lethbridge';


## Invoice

select count(*) from invoice
where billing_country = 'USA';

select total from invoice
order by total desc limit 1;

select total from invoice
order by total asc limit 1;

select * from invoice
where total > 5;

select * from invoice
where total < 5;

select count(*) from invoice
where billing_state in ('CA', 'TX', 'AZ');

select avg(total) from invoice;

select sum(total) from invoice;