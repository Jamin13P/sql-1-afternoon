# SQL 1 Afternoon

## Person

- 1 create table person (
person_id serial primary key,
  name varchar(30),
  age int,
  height int,
  city varchar(20),
  favorite_color varchar(15)
);

- 2 insert into person
(name, age, height, city, favorite_color)
values
('Ben', 23, 178, 'Chico', 'Blue'),
('Dalton', 23, 190, 'Redding', 'Green'),
('Nick', 24, 172, 'Chico', 'Orange'),
('Andrew', 22, 167, 'Redding', 'Red'),
('Josh', 30, 180, 'Orem', 'Blue');

- 3 select * from person order by height desc;

- 4 select * from person order by height asc;

- 5 select * from person order by age desc;

- 6 select * from person
where age > 20;

- 7 select * from person
where age = 18;

- 8 select * from person
where age < 20
or age > 30;

- 9 select * from person
where age != 27;

- 10 select * from person
where favorite_color != 'Red';

- 11 select * from person
where favorite_color != 'Red'
and favorite_color != 'Blue';

- 12 select * from person
where favorite_color = 'Orange'
or favorite_color = 'Green';

- 13 select * from person
where favorite_color in ('Orange', 'Green', 'Blue');

- 14 select * from person
where favorite_color in ('Purple', 'Yellow');


## Table

- 1 create table orders (
order_id serial primary key,
  person_id int,
  product_name varchar(50),
  product_price numeric(4, 2),
  quantity int
);

- 2 insert into orders (person_id, product_name, product_price, quantity)
values
(1, 'basketball', 15.23, 3),
(2, 'toothpaste', 5.26, 2);

- 3 select * from orders;

- 4 select sum(quantity) from orders;

- 5 select sum(quantity * product_price) from orders;

- 6 select sum(quantity * product_price) from orders
where person_id = 1


## Artist

- 1 insert into artist (name)
values
('Bob Ross'),
('Vangauh'),
('Picasso');

- 2 select * from artist order by name desc limit 10;

- 3 select * from artist order by name asc limit 5;

- 4 select * from artist
where name like ('Black%');

- 5 select * from artist
where name like ('%Black%');


## Employee

- 1 select (first_name, last_name) from employee
where city = 'Calgary';

- 2 select birth_date from employee
order by birth_date desc limit 1;

- 3 select birth_date from employee
order by birth_date asc limit 1;

- 4 select * from employee
where reports_to = 2;

- 5 select count(*) from employee
where city = 'Lethbridge';


## Invoice

- 1 select count(*) from invoice
where billing_country = 'USA';

- 2 select total from invoice
order by total desc limit 1;

- 3 select total from invoice
order by total asc limit 1;

- 4 select * from invoice
where total > 5;

- 5 select * from invoice
where total < 5;

- 6 select count(*) from invoice
where billing_state in ('CA', 'TX', 'AZ');

- 7 select avg(total) from invoice;

- 8 select sum(total) from invoice;