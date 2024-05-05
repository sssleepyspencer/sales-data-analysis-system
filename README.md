#sales-data-analysis-system
#create_database
CREATE DATABASE IF NOT EXISTS SalesAnalysis;

#Use_sales_database
USE SalesAnalysis;

#Create_sales_data_table
CREATE TABLE IF NOT EXISTS sales_data (
    id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(255) NOT NULL,
    quantity_sold INT NOT NULL,
    sale_date DATE NOT NULL,
    sale_amount DECIMAL(10, 2) NOT NULL,
    channel ENUM('online', 'offline') NOT NULL
);

#Create_customers_data_table
CREATE TABLE IF NOT EXISTS customer_data (
    customer_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_name VARCHAR(255) NOT NULL,
    contact_info VARCHAR(255),
    join_date DATE NOT NULL
);

#Create_items_data_table
CREATE TABLE IF NOT EXISTS product_data (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(255) NOT NULL UNIQUE,
    price DECIMAL(10, 2) NOT NULL,
    stock_quantity INT NOT NULL
);

#Create_user_permission_table
CREATE TABLE IF NOT EXISTS user_permissions (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) NOT NULL UNIQUE,
    role ENUM('admin', 'analyst', 'viewer') NOT NULL,
    password_hash VARCHAR(255) NOT NULL
);
