# SQL-1-afternoon-answers

    Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color.
    id should be an auto-incrementing id/primary key - Use type: SERIAL
CREATE TABLE person (
  id SERIAL,
  name TEXT,
  age INTEGER,
  height INTEGER,
  city TEXT,
  favorite_color TEXT
  );



      Add 5 different people into the person database.
      Remember to not include the person_id because it should auto-increment.
INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Grace', 24, 165, 'Nashville', 'green'), ('Scott', 22, 180, 'Tanktopia', 'blue'), ('Andrew', 20, 200, 'Culver City', 'green'), ('Megan', 25, 170, 'Idk', 'purple'), ('Kara', 28, 190, 'Orange County', 'yellow');

//Andrew you’re 25 now, you’re welcome



          List all the people in the person table by height from tallest to shortest.
SELECT * 
FROM person
ORDER BY height DESC;
List all the people in the person table by height from shortest to tallest.
SELECT *
FROM person
ORDER BY height ASC;
 

        List all the people in the person table by age from oldest to youngest.
SELECT * 
FROM person
ORDER BY age DESC;
 
          List all the people in the person table older than age 20.
SELECT *
FROM person
WHERE age > 20;
 
 

          List all the people in the person table that are exactly 18.
SELECT *
FROM person
WHERE age = 18;
 
          List all the people in the person table that are less than 20 and older than 30
SELECT *
FROM person
WHERE age < 20 OR age > 30;
 
          List all the people in the person table that are not 27 (Use not equals).
SELECT *
FROM person
WHERE age != 27;
 
          List all the people in the person table where their favorite color is not red.
SELECT *
FROM person
WHERE favorite_color != 'red';
 
 
 
          List all the people in the person table where their favorite color is not red and is not blue.
SELECT * 
FROM person
WHERE favorite_color != 'red' AND favorite_color != 'blue';
 
            List all the people in the person table where their favorite color is orange or green.
SELECT * 
FROM person 
WHERE favorite_color = 'orange' OR favorite_color = 'green';
 
 
          List all the people in the person table where their favorite color is orange, green or blue (use IN).
SELECT *
FROM person
WHERE favorite_color IN ('orange', 'green', 'blue');
 
 
 
 
 
          List all the people in the person table where their favorite color is yellow or purple (use IN).
SELECT *
FROM person
WHERE favorite_color IN ('yellow', 'purple');
 
     Create a table called orders that records: 
          order_id,
           Person_id,
           product_name, 
          Product_price, 
           quantity.
CREATE TABLE orders (
  id INT PRIMARY KEY,
  product_name TEXT,
  product_price INTEGER,
  quantity INTEGER
  );
ALTER TABLE orders
ADD COLUMN person_id INTEGER;
 
 

          Add 5 orders to the orders table.
          Make orders for at least two different people.
          person_id should be different for different people.
  INSERT INTO orders
(quantity, id, product_name, product_price, person_id)
VALUES
(1, 1, 'shoe', 75, 1), (1, 2, ‘coffee’, 2, 2), (1, 3, 'water', 2, 3), (1, 4, ‘t-shirt’, 10, 4), (1, 5, ‘pillow’, 25, 5);

          Select all the records from the orders table.
SELECT *
FROM orders;
Calculate the total number of products ordered.
SELECT count(id)
FROM orders;
 
        Calculate the total order price.
SELECT sum(product_price)
FROM orders;
 
          Calculate the total order price by a single person_id.
SELECT sum(product_price)
FROM orders
WHERE person_id = 1;
 
 
 
 
 
          Add 3 new artists to the artist table. ( It's already created )
INSERT INTO artist
(artist_id, name)
VALUES 
(280,'Billy'), (281,'Bob'), (282, 'Joe');
 
 
          Select 10 artists in reverse alphabetical order.
SELECT *
FROM artist
ORDER BY name DESC LIMIT 10;
 
          Select 5 artists in alphabetical order.
SELECT *
FROM artist
ORDER BY name ASC LIMIT 5;
 
          Select all artists that start with the word 'Black'.
SELECT *
FROM artist
WHERE name LIKE 'Black%';
 
 
          Select all artists that contain the word 'Black'.
SELECT *
FROM artist
WHERE name LIKE '%Black%';






















          List all employee first and last names only that live in Calgary.
SELECT first_name, last_name
FROM employee
WHERE city = 'Calgary';
 
          Find the birthdate for the youngest employee.
SELECT *
FROM employee 
ORDER BY birth_date DESC LIMIT 1;
 
 
            Find the birthdate for the oldest employee.
SELECT *
FROM employee
ORDER BY birth_date ASC LIMIT 1;
 
          Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
              You will need to query the employee table to find the Id for Nancy Edwards
SELECT *
FROM employee
WHERE first_name = 'Nancy';

SELECT *
FROM employee
WHERE reports_to = 2;

          Count how many people live in Lethbridge.
SELECT count(*)
FROM employee
WHERE city = 'LethBridge';
 

          Count how many orders were made from the USA.
SELECT count(*)
FROM invoice
WHERE billing_country = 'USA';
 
 
    Find the largest order total amount.

SELECT *
FROM invoice
ORDER BY total DESC LIMIT 1;
 
    Find the smallest order total amount.

SELECT *
FROM invoice
ORDER BY total ASC LIMIT 1;
 
Find all orders bigger than $5.
SELECT *
FROM invoice
WHERE total > 5;
 
Count how many orders were smaller than $5.
SELECT count(*)
FROM invoice
WHERE total < 5;
 
 
Count how many orders were in CA, TX, or AZ (use IN).
  SELECT count(*)
  FROM invoice
  WHERE billing_state IN ('CA','TX','AZ');
 
Get the average total of the orders.
SELECT avg(total)
  FROM invoice;
 
Get the total sum of the orders.
SELECT sum(invoice_id)
FROM invoice;

