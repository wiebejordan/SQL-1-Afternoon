# SQL-1-Afternoon

-- CREATE TABLE person (
--     person_id SERIAL PRIMARY KEY,
--   	age INTEGER,
--   	name VARCHAR(200),
--   	height_cm INTEGER,	
--   	city VARCHAR(200),
--   	favorite_color VARCHAR(200)

-- );

-- INSERT INTO person
-- (name, age, height_cm, city, favorite_color)
-- VALUES
-- ('jordan Wiebe', 21, 60, 'Salt Lake City', 'blue'),
-- ('Cicely Wiebe' ,28, 30, 'Tooele', 'red'),
-- ('justin Wiebe',20, 80, 'Bristol', 'green'),
-- ('tony Tiger',19, 70, 'Bristol', 'yellow'),
-- ('troy Fall',20, 75, 'Youngstown', 'black');

SELECT * FROM person 
ORDER BY height_cm DESC;

SELECT * FROM person 
ORDER BY height_cm ASC;

SELECT * FROM person 
ORDER BY age DESC;

SELECT * FROM person 
WHERE age > 20;

SELECT * FROM person 
WHERE age = 18;

SELECT * FROM person 
WHERE age < 20 AND age > 30;

SELECT * FROM person 
WHERE age != 27;

SELECT * FROM person 
WHERE favorite_color != 'red';

SELECT * FROM person 
WHERE favorite_color != 'red' and favorite_color != 'blue' ;

SELECT * FROM person 
WHERE favorite_color = 'orange' or favorite_color = 'green' ;

SELECT * FROM person 
WHERE favorite_color IN ('orange', 'green', 'blue');

SELECT * FROM person 
WHERE favorite_color IN ('purple', 'yellow');

******************************************

CREATE TABLE orders (
	order_id SERIAL PRIMARY KEY,
  person_id INTEGER,
  product_name VARCHAR(200),
  product_price NUMERIC,
  quantity INTEGER
);

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(1,'NImbus 2000', 29.99,3),
(2, 'Shake Weight',49.99,5);

SELECT * FROM orders;

SELECT sum(quantity) FROM orders;

SELECT sum(product_price) FROM orders;

SELECT sum(product_price * quantity) FROM orders WHERE order_id = 1;

*********************************************

INSERT INTO artist 
(name)
VALUES
('La Dispute'),
('Emery'),
('Hotel Books');

SELECT * FROM artist ORDER BY name DESC LIMIT 10; 

SELECT * FROM artist ORDER BY name ASC LIMIT 5; 


SELECT * FROM artist WHERE name LIKE 'Black%';

SELECT * FROM artist WHERE name LIKE '%Black%'; 

*********************************************

SELECT * FROM employee WHERE city = 'Calgary'; 

SELECT max(birth_date) FROM employee;

SELECT min(birth_date) FROM employee;

SELECT * FROM employee WHERE reports_to = 2;

select count(*) from employee where city = 'Lethbridge';

***********************************************

SELECT COUNT(*) FROM invoice WHERE billing_country = 'USA';

SELECT max(total) FROM invoice;

SELECT min(total) FROM invoice;

SELECT * FROM invoice WHERE total > 5;

SELECT COUNT(*) FROM invoice WHERE total > 5;

SELECT COUNT(*) FROM invoice WHERE billing_state IN
('CA', 'TX', 'AZ');

SELECT avg(total) FROM invoice;

SELECT sum(total) FROM invoice;