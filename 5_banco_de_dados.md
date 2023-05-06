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

# 6 - SQL para ORM

<!--

SELECT
  DATE_TRUNC('month', sales.date) AS month,
  products.category AS category,
  SUM(sales.quantity) AS quantity_sold,
  SUM(sales.price * sales.quantity) AS total_revenue,
  SUM((sales.price - sales.cost) * sales.quantity) AS total_profit,
  SUM((sales.price - sales.cost) * sales.quantity) / SUM(sales.price * sales.quantity) AS profit_margin
FROM
  sales
  JOIN products ON sales.product_id = products.id
GROUP BY
  month,
  category
ORDER BY
  month ASC,
  category ASC

   -->

Reescreva essa query com Sequelize:

<!--

User.findAll({
  attributes: ['id', 'name', [sequelize.fn('COUNT', 'posts.id'), 'postCount']],
  include: [{
    model: Post,
    attributes: [],
  }],
  group: ['user.id'],
  having: {
    postCount: { [Op.gt]: 5 },
  },
  order: [[sequelize.col('postCount'), 'DESC'], ['name', 'ASC']],
});

 -->

Reescreva este código em uma query de SQL:
