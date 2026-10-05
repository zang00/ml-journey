# SQL E-commerce Analytics

## Description
A relational database for an online store (PostgreSQL, Supabase), 
designed from scratch, with business analytics built on top using SQL.

## Database structure
4 related tables: Customers, Products, Orders, OrderItems 
(classic "an order contains multiple products" schema).

## Technologies
PostgreSQL, Python (Faker, SQLAlchemy) — for generating and loading 
synthetic data (200 customers, 50 products, 500 orders).

## What this project demonstrates
- Database schema design with foreign keys (REFERENCES)
- Different JOIN types (INNER, LEFT), including joining 3+ tables
- Data aggregation (GROUP BY, HAVING)
- Finding "missing relationships" (LEFT JOIN + IS NULL)
- Window functions (RANK with PARTITION BY)
- Multiple CTEs (Common Table Expressions) for complex queries

## Example business questions solved
- Top 3 best-selling products in each category
- Ranking customers by total spend
- Customers with zero orders
- Monthly revenue trends

## Files
`queries.sql` — full DB schema + 14 analytical queries

---

# SQL Аналитика интернет-магазина

## Описание
Спроектированная с нуля реляционная база данных интернет-магазина 
(PostgreSQL, Supabase) с последующей бизнес-аналитикой через SQL.

## Структура базы данных
4 связанные таблицы: Customers, Products, Orders, OrderItems 
(классическая схема "заказ содержит несколько товаров").

## Технологии
PostgreSQL, Python (Faker, SQLAlchemy) — для генерации и загрузки 
синтетических данных (200 клиентов, 50 товаров, 500 заказов).

## Что показано в проекте
- Проектирование схемы БД с внешними ключами (REFERENCES)
- JOIN разных типов (INNER, LEFT), включая соединение 3+ таблиц
- Агрегация данных (GROUP BY, HAVING)
- Поиск "отсутствующих связей" (LEFT JOIN + IS NULL)
- Оконные функции (RANK с PARTITION BY)
- Множественные CTE (Common Table Expressions) для сложных запросов

## Примеры решённых бизнес-задач
- Топ-3 самых продаваемых товара в каждой категории
- Ранжирование клиентов по объёму трат
- Клиенты без единого заказа
- Динамика выручки по месяцам

## Файлы
`queries.sql` — вся структура БД + 14 аналитических запросов
