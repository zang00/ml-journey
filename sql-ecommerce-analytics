-- ============================================
-- СОЗДАНИЕ ТАБЛИЦ (Schema)
-- ============================================

CREATE TABLE Customers (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    registration_date DATE,
    city VARCHAR(100)
);

CREATE TABLE Products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    category VARCHAR(100),
    price DECIMAL(10, 2)
);

CREATE TABLE Orders (
    id SERIAL PRIMARY KEY,
    customer_id INT REFERENCES Customers(id),
    order_date DATE,
    status VARCHAR(50)
);

CREATE TABLE OrderItems (
    id SERIAL PRIMARY KEY,
    order_id INT REFERENCES Orders(id),
    product_id INT REFERENCES Products(id),
    quantity INT,
    price_at_purchase DECIMAL(10, 2)
);


-- ============================================
-- БАЗОВЫЙ УРОВЕНЬ
-- ============================================

-- 1. Топ-10 самых дорогих товаров
SELECT name, price 
FROM products 
ORDER BY price DESC 
LIMIT 10;

-- 2. Все заказы со статусом 'cancelled'
SELECT id, status 
FROM orders 
WHERE status = 'cancelled';

-- 3. Клиенты из Алматы, отсортированные по дате регистрации
SELECT name, email, registration_date 
FROM customers 
WHERE city = 'Almaty' 
ORDER BY registration_date;


-- ============================================
-- JOIN
-- ============================================

-- 4. Имя клиента + дата заказа
SELECT customers.name, orders.order_date
FROM orders
JOIN customers ON orders.customer_id = customers.id;

-- 5. Название товара + количество
SELECT products.name, order_items.quantity
FROM order_items
JOIN products ON order_items.product_id = products.id;

-- 6. Полная информация: клиент + товар + количество
SELECT customers.name AS customer_name, products.name AS product_name, order_items.quantity
FROM order_items
JOIN products ON order_items.product_id = products.id
JOIN orders ON order_items.order_id = orders.id
JOIN customers ON orders.customer_id = customers.id;


-- ============================================
-- GROUP BY + АГРЕГАТЫ
-- ============================================

-- 7. Сколько заказов у каждого клиента (5+)
SELECT customers.name, COUNT(orders.id) AS orders_count
FROM customers
JOIN orders ON customers.id = orders.customer_id
GROUP BY customers.name
HAVING COUNT(orders.id) >= 5;

-- 8. Средний чек по каждой категории товаров
SELECT products.category, AVG(order_items.price_at_purchase * order_items.quantity) AS avg_check
FROM order_items
JOIN products ON order_items.product_id = products.id
GROUP BY products.category;

-- 9. Общая выручка по месяцам
SELECT 
    DATE_TRUNC('month', orders.order_date) AS month,
    SUM(order_items.price_at_purchase * order_items.quantity) AS revenue
FROM orders
JOIN order_items ON orders.id = order_items.order_id
GROUP BY DATE_TRUNC('month', orders.order_date)
ORDER BY month;

-- 10. Средняя сумма заказа для каждого клиента
SELECT customers.name, AVG(price_at_purchase * quantity) AS avg_order_value
FROM order_items
JOIN orders ON order_items.order_id = orders.id
JOIN customers ON orders.customer_id = customers.id
GROUP BY customers.name;

-- 11. Клиенты без единого заказа
SELECT customers.name
FROM customers
LEFT JOIN orders ON customers.id = orders.customer_id
WHERE orders.id IS NULL;


-- ============================================
-- ПРОДВИНУТОЕ: ПОДЗАПРОСЫ
-- ============================================

-- 12. Самая популярная категория (по сумме проданных штук)
SELECT category, SUM(quantity) AS total_sold 
FROM order_items
JOIN products ON order_items.product_id = products.id
GROUP BY category
ORDER BY total_sold DESC
LIMIT 1;


-- ============================================
-- WINDOW FUNCTIONS + CTE
-- ============================================

-- 13. Ранжирование клиентов по общей сумме потраченных денег
WITH customer_totals AS (
    SELECT customers.name, SUM(price_at_purchase * quantity) AS total_spent
    FROM order_items
    JOIN orders ON order_items.order_id = orders.id
    JOIN customers ON orders.customer_id = customers.id
    GROUP BY customers.name
)
SELECT name, total_spent, RANK() OVER (ORDER BY total_spent DESC) AS spending_rank
FROM customer_totals;

-- 14. Топ-3 самых продаваемых товара в каждой категории
WITH top_3 AS (
    SELECT category, products.name, SUM(quantity) AS sum_quan 
    FROM order_items
    JOIN products ON order_items.product_id = products.id
    GROUP BY category, products.name
),
ranked AS (
    SELECT name, category, sum_quan, 
        RANK() OVER (PARTITION BY category ORDER BY sum_quan DESC) AS product_rank
    FROM top_3
)
SELECT * FROM ranked WHERE product_rank <= 3;
