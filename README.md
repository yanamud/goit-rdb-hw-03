# 1.1. вибрати всі стовпчики з таблиці products;
SELECT * FROM hw_3.products

# 1.2. вибрати тільки стовпчики name, phone з таблиці shippers
SELECT name, phone FROM hw_3.shippers

# 2. знайти середнє, максимальне та мінімальне значення стовпчика price таблички products
SELECT round(avg(price),2) as avg_price, max(price) as max_price, min(price) as min_price
FROM hw_3.products

# 3. обрати унікальні значення колонок category_id та price таблиці products.
#   порядок виведення за спаданням price та тільки 10 рядків. 
SELECT distinct category_id, price
FROM hw_3.products
ORDER BY price DESC
LIMIT 10

# 4. знайти кількість продуктів (рядків), які знаходиться в цінових межах від 20 до 100
SELECT count(price) as count
FROM hw_3.products
WHERE price between 20 AND 100

# 5. знайти кількість продуктів (рядків) та середню ціну (price)  у кожного постачальника (supplier_id)
SELECT supplier_id, count(supplier_id) as count_product, round(avg(price),2) as avg_price
FROM hw_3.products
GROUP BY supplier_id
ORDER BY supplier_id
