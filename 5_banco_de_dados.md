# 1 - Geração de tabelas

Gere uma query para criar uma tabela de produtos, onde preciso dos campos: nome, preço, se está ou não em estoque, data de produção, sku e cor

# 2 - Geração de dados para tabela

Crie uma query para inserir 5 produtos na tabela

# 3 - Analises de consultas

<!--

SELECT COUNT(*) FROM vendas;

SELECT AVG(preco) FROM produtos;

SELECT * FROM vendas WHERE data BETWEEN '2020-01-01' AND '2021-01-01';

-->

Melhore esta query

# 4 - Explicando queries complexas

<!--

SELECT p.name AS product_name, s.name AS supplier_name, o.order_date, o.quantity, o.unit_price
FROM products p
INNER JOIN suppliers s ON p.supplier_id = s.id
INNER JOIN order_details o ON p.id = o.product_id
WHERE o.order_date BETWEEN '2020-01-01' AND '2021-01-01'
AND s.country = 'BR'
AND (o.quantity * o.unit_price) > 500
ORDER BY o.order_date DESC;

 -->

Explique esta query:

# 5 - Transformar query para outro banco

<!--

SELECT c.customer_id, c.first_name, c.last_name, SUM(p.amount) AS total_spent
FROM customers c
INNER JOIN payments p ON c.customer_id = p.customer_id
WHERE c.city = 'São Paulo' AND c.country = 'BR'
GROUP BY c.customer_id
HAVING total_spent > 5000
ORDER BY total_spent DESC;

 -->

Transforme essa query para o banco PostgreSQL:

Transforme essa query para o banco MongoDB, que é NoSQL:
