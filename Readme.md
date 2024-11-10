-- Create the ecommerce database

> CREATE DATABASE ecommerce;

-- Use the ecommerce database

> USE ecommerce;


-- Create the customers table

> CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,  
    name VARCHAR(255) NOT NULL,      
    email VARCHAR(255) UNIQUE NOT NULL,
    address TEXT NOT NULL              
);

-- Create the products table

> CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,  
    name VARCHAR(255) NOT NULL,           
    price DECIMAL(10, 2) NOT NULL,        
    description TEXT NOT NULL             
);

-- Create the orders table

> CREATE TABLE orders (
    id INT AUTO_INCREMENT PRIMARY KEY,      
    customer_id INT NOT NULL,               
    order_date DATE NOT NULL,               
    total_amount DECIMAL(10, 2) NOT NULL,   
    FOREIGN KEY (customer_id) REFERENCES customers(id) ON DELETE CASCADE  
);

-- Inserting sample data into the customers table

> INSERT INTO customers (name, email, address) VALUES
('Edward Torphy', 'Idella_Koss@gmail.com', 'Gary'),
('Jonas McCullough', 'Laurence_Pouros@example.com', 'West Daphney'),
('Vernon Glover', 'Antonio_Krajcik@hotmail.com', 'Lake Jacquelinaton'),
('Oral Mayer', 'Sheryl_Hirthe95@gmail.com', 'South Jessiebury'),
('Hellen Jast', 'Herbert_Turner72@hotmail.com', 'East Rupertbury'),
('Francisca Goyette', 'Barrett_Hagenes32@hotmail.com', 'Old Branch'),
('Avery Gorczany', 'Corey.Kerluke@hotmail.com', 'West Tami'),
('Kathie Hane', 'Cristina_Zemlak99@gmail.com', 'Port Jerad'),
('Clyde Trantow', 'Rosalie_Gislason2@gmail.com', 'Lacytown'),
('Leonard Schuppe', 'Lynn.Smitham75@gmail.com', 'South Bostony'),
('Raymond Kemmer', 'Candice_McKenzie50@yahoo.com', 'Kennethport'),
('Adella Sawayn', 'Lenny.Welch35@gmail.com', 'Owenbury'),
('Enrique Zboncak', 'Tom.Hayes23@yahoo.com', 'Chavezmouth'),
('Ezekiel Carter', 'Jaime.Terry33@gmail.com', 'Schenkburgh'),
('Derrick Mante', 'Clifton.Hirthe42@hotmail.com', 'North Kylarchester'),
('Francisca Torp', 'Georgiana.OHara56@hotmail.com', 'Port Zoie'),
('Reynaldo Kunze', 'Joan.Trantow28@hotmail.com', 'East Anjanette'),
('Herminia Erdman', 'Brennan.Lubowitz75@gmail.com', 'Bartellton'),
('Annalise Feest', 'Derrick_Krajcik73@yahoo.com', 'Tinabury'),
('Katherine Reilly', 'Roslyn.Krajcik23@yahoo.com', 'Fort Tyra'),
('Sherman Mraz', 'Gary_Kemmer@gmail.com', 'South Randimouth'),
('Rebeca Stokes', 'Rachelle.Krajcik@gmail.com', 'Lake Darrelview'),
('Josie Krajcik', 'Elinor_Zemlak80@yahoo.com', 'New Ceciliabury'),
('Jerrell Ratke', 'Hilton.Gibson@weber.com', 'North Earlmouth'),
('Wilbert Ondricka', 'Kiley_Kreiger@schuster.com', 'Lake Brackenville'),
('Glen Littel', 'Samara.Hegmann49@gmail.com', 'East Carletonland'),
('Antonio Paucek', 'Janae.Littel56@yahoo.com', 'Shelbyhaven'),
('Adella Schultz', 'Daisy.Ruecker88@yahoo.com', 'Tyreseburg'),
('Harold Stoltenberg', 'Sidney_Predovic90@hotmail.com', 'Bertsville'),
('Garry Bailey', 'Bertha.Parisi83@yahoo.com', 'South Bridgette'),
('Derrick Hoeger', 'Carmen_Crona@hotmail.com', 'North Oralia'),
('Jesse Rowe', 'Reba.Tremblay71@yahoo.com', 'Hedwigview'),
('Angela Satterfield', 'Marcelina_Krajcik51@hotmail.com', 'Haroldchester'),
('Elsie Watsica', 'Annette_Terry54@hotmail.com', 'West Boydcourt'),
('Mable Harris', 'Marcella_Wilkinson18@gmail.com', 'West Krystalborough'),
('Claudia Beatty', 'Elba.Stokes@yahoo.com', 'Davidton'),
('Regina Reilly', 'Marcella_Larson16@yahoo.com', 'Zulaufview'),
('Matthew Funk', 'Sheridan_Pfannerstill79@yahoo.com', 'West Dora'),
('Emmett Welch', 'Samuel.Marquardt92@yahoo.com', 'Tampaview'),
('Willie Langworth', 'Ervin_Marquardt44@yahoo.com', 'South Bryantland'),
('Paula Lockman', 'Julie_Wolf31@yahoo.com', 'West Alleneview');

-- Inserting sample data into the products table

> INSERT INTO products (name, price, description) VALUES
('Apple iPhone 14', 999.99, 'Latest model with A15 Bionic chip and improved camera capabilities.'),
('Samsung Galaxy S22', 849.99, 'Flagship smartphone with AMOLED display and powerful camera system.'),
('Sony WH-1000XM5', 349.99, 'Industry-leading noise-canceling headphones with long battery life.'),
('Dell XPS 13', 1249.99, '13-inch laptop with Intel Core i7 processor, ultra-thin design, and 4K display.'),
('Fitbit Charge 5', 179.95, 'Fitness tracker with built-in GPS, heart rate monitoring, and sleep tracking.'),
('Apple Watch Series 7', 399.99, 'Smartwatch with larger screen, faster charging, and advanced fitness features.'),
('Sony PlayStation 5', 499.99, 'Next-gen gaming console with ray tracing and lightning-fast SSD.'),
('Microsoft Xbox Series X', 499.99, 'Next-gen console with 4K gaming, ultra-fast load times, and backward compatibility.'),
('Nvidia GeForce RTX 3080', 699.99, 'High-performance graphics card with 10GB of GDDR6X memory for gaming and rendering.'),
('Intel Core i9-12900K', 749.99, 'Top-tier desktop CPU with 16 cores and hyper-threading for gaming and heavy workloads.'),
('Oculus Quest 2', 299.99, 'Standalone VR headset with access to a wide range of games and experiences.'),
('Bose QuietComfort 35 II', 299.99, 'Wireless noise-canceling headphones with exceptional sound and comfort.'),
('Anker PowerCore 26800', 69.99, 'Portable power bank with 26,800mAh capacity for multiple device charging.'),
('Google Pixel 6', 599.99, 'Flagship Android phone with Google Tensor chip, exceptional camera, and 5G support.'),
('Razer BlackWidow V3', 129.99, 'Mechanical keyboard with RGB lighting and tactile switches for gaming.'),
('Apple AirPods Pro', 249.99, 'True wireless earbuds with active noise cancellation and superb sound quality.'),
('HP Spectre x360', 1299.99, 'Convertible 2-in-1 laptop with Intel Core i7, high-res display, and sleek design.'),
('Samsung Galaxy Buds Pro', 199.99, 'Premium wireless earbuds with noise cancellation and 3 microphones for calls.'),
('Nikon D850', 2799.99, 'Full-frame DSLR with 45.7MP sensor, fast autofocus, and high-quality 4K video.'),
('Canon EOS R5', 3899.99, 'Mirrorless camera with 8K video and exceptional image quality in all conditions.'),
('GoPro HERO10 Black', 499.99, 'Waterproof action camera with 5.3K video and enhanced stabilization.'),
('Dyson V11 Torque Drive', 599.99, 'Cordless vacuum cleaner with powerful suction and adaptive cleaning modes.'),
('iRobot Roomba i7+', 799.99, 'Robot vacuum with smart mapping, self-emptying base, and powerful suction.'),
('Instant Pot Duo 7-in-1', 89.99, 'Electric pressure cooker with 7-in-1 functionality for easy cooking.'),
('Sony A7 III', 1999.99, 'Full-frame mirrorless camera with outstanding autofocus and image quality.'),
('LG OLED CX', 1499.99, '55-inch OLED 4K TV with self-lighting pixels and stunning contrast.'),
('Apple MacBook Pro 16"', 2399.99, 'Powerful laptop with Apple M1 Pro chip, 16GB RAM, and retina display.'),
('Fujifilm X-T4', 1699.99, 'Mirrorless camera with 4K video, fast autofocus, and great color science.'),
('Seagate Backup Plus 4TB', 109.99, 'External hard drive with 4TB capacity for backup and storage.'),
('Sony 65" 4K LED TV', 799.99, 'Smart TV with 4K resolution, HDR support, and Android TV platform.'),
('KitchenAid Stand Mixer', 349.99, 'Iconic stand mixer for baking with multiple attachments for versatility.'),
('Philips Sonicare HX9937', 149.99, 'Electric toothbrush with smart sensor technology and 2-week battery life.'),
('Kindle Paperwhite', 129.99, 'E-reader with high-resolution display, adjustable lighting, and 8GB storage.'),
('GoPro HERO9 Black', 399.99, 'Action camera with 5K video, front-facing screen, and enhanced stabilization.'),
('Samsung Galaxy Tab S7', 649.99, 'Android tablet with S Pen, 11-inch display, and high-performance specs.'),
('Logitech MX Master 3', 99.99, 'Wireless mouse with customizable buttons and ergonomic design.'),
('Samsung 970 EVO 1TB SSD', 139.99, 'Fast NVMe solid-state drive with 1TB storage for desktops and laptops.');



-- 1 Query to get all customers who have placed an order in the last 30 days

> SELECT DISTINCT c.name, c.email, c.address
FROM customers c
JOIN orders o ON c.id = o.customer_id
WHERE o.order_date >= CURDATE() - INTERVAL 30 DAY;


-- 2 Query to get total amount of all orders placed by each customer

> SELECT c.name, SUM(o.total_amount) AS total_spent
FROM customers c
JOIN orders o ON c.id = o.customer_id
GROUP BY c.id;

-- 3 Query to update the price of Product C

> UPDATE products
SET price = 45000
WHERE name = 'Canon EOS R5';

-- 4 Query to add a 'discount' column to the products table

> ALTER TABLE products
ADD COLUMN discount DECIMAL(5,2) DEFAULT 0.00;


-- 5 Query to get the top 3 products with the highest price

> SELECT name, price
FROM products
ORDER BY price DESC
LIMIT 3;


-- 6 Query to get the name of the customers who ordered Sony PlayStation 5

SELECT c.name
FROM customers AS c
JOIN orders AS o ON c.id = o.customers_id
JOIN order_items AS oi ON o.id = oi.order_id
JOIN products AS p ON oi.product_id = p.id
WHERE p.name = 'Sony PlayStation 5';



-- 7 Query to retrieve customer's name and order date for each order

> SELECT c.name AS customer_name, o.order_date
FROM customers AS c
JOIN orders AS o ON c.id = o.customers_id;



-- 8 Query to get orders with a total amount greater than 150

> SELECT * 
FROM orders
WHERE total_amount > 150.00;


-- 9 Create order_items table to store order details

> CREATE TABLE order_items (
    id INT AUTO_INCREMENT PRIMARY KEY,        
    order_id INT NOT NULL,                           
    product_id INT NOT NULL,                        
    quantity INT NOT NULL,                          
    price DECIMAL(10, 2) NOT NULL,                   
    FOREIGN KEY (order_id) REFERENCES orders(id) 
    FOREIGN KEY (product_id) REFERENCES products(id) 
);


-- Update orders table to reference order_items
-- (This involves removing any unnecessary columns from the orders table and updating the logic for data insertion)

-- Query to get the average total of all orders

>   SELECT AVG(total_amount) AS average_order_total
FROM orders;

