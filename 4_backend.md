# 1 - Criação de API com GPT

Crie uma estrutura base de API com Express JS, ela deve adicionar produtos com os atributos: nome, descrição e preço

Agora adicione uma rota para deletar produtos

# 2 - Aplicando TypeScript ao código

Reescreva esta API com TypeScript

# 3 - Reescrevendo em outra linguagem/ferramenta

Preciso deste mesmo código de API só que em Python, utilizando o framework Flask

# 4 - Gerando dados de Mock

Gere dados de teste para produtos, e uma rota em Express JS para exibir um produto individual

# 5 - Prevenção de falhas de segurança

<!--
    SQL injection

    const express = require('express');
const app = express();
const db = require('./db');

// Rota insegura para obter dados de um usuário por ID
app.get('/user/:id', (req, res) => {
  const userId = req.params.id;
  const query = `SELECT * FROM users WHERE id = ${userId}`;
  db.query(query, (err, results) => {
    if (err) {
      res.status(500).send('Erro ao obter usuário');
    } else if (results.length === 0) {
      res.status(404).send('Usuário não encontrado');
    } else {
      const user = results[0];
      res.send(user);
    }
  });
});

app.listen(3000, () => {
  console.log('Servidor iniciado na porta 3000');
});

 -->

Analise e corrija as falhas de segurança deste código:

# 6 - Gerando validações

<!--
// Rota para cadastrar um carro
const express = require('express');
const app = express();
const db = require('./db');

app.use(express.json());

// Rota para cadastrar um carro
app.post('/cars', (req, res) => {
  const { title, price, km, isAuction, color, options, extra } = req.body;
  const query = 'INSERT INTO cars (title, price, km, is_auction, color, options, extra) VALUES (?, ?, ?, ?, ?, ?, ?)';
  db.query(query, [title, price, km, isAuction, color, options, extra], (err, result) => {
    if (err) {
      console.error(err);
      res.status(500).send('Erro ao cadastrar carro');
    } else {
      res.status(201).send('Carro cadastrado com sucesso');
    }
  });
});

app.listen(3000, () => {
  console.log('Servidor iniciado na porta 3000');
});


 -->

Crie validações para todos os dados recebidos por esta rota:

# 7 - Gerando integrações

Crie um código de integração de API com Express para utilizar o Stripe

Crie um código para conexão de pymongo em uma API de Flask

# 8 - Gerando comentários e documentação

<!--

const express = require('express');
const router = express.Router();
const bcrypt = require('bcrypt');
const jwt = require('jsonwebtoken');
const User = require('../models/User');

router.post('/register', async (req, res) => {
  try {
    const { name, email, password } = req.body;
    const hashedPassword = await bcrypt.hash(password, 10);
    const user = new User({
      name,
      email,
      password: hashedPassword,
    });
    await user.save();
    res.status(201).send('Usuário cadastrado com sucesso');
  } catch (err) {
    console.error(err);
    res.status(500).send('Erro ao cadastrar usuário');
  }
});

router.post('/login', async (req, res) => {
  try {
    const { email, password } = req.body;
    const user = await User.findOne({ email });
    if (!user) {
      return res.status(401).send('Credenciais inválidas');
    }
    const isMatch = await bcrypt.compare(password, user.password);
    if (!isMatch) {
      return res.status(401).send('Credenciais inválidas');
    }
    const token = jwt.sign({ userId: user._id }, 'secretKey', { expiresIn: '1h' });
    res.send({ token });
  } catch (err) {
    console.error(err);
    res.status(500).send('Erro ao fazer login');
  }
});

module.exports = router;

 -->

Documente este código:

<!--

router.post('/register', async (req, res) => {
  try {
    const { name, email, password } = req.body;
    const hashedPassword = await bcrypt.hash(password, 10);
    const user = new User({
      name,
      email,
      password: hashedPassword,
    });
    await user.save();
    res.status(201).send('Usuário cadastrado com sucesso');
  } catch (err) {
    console.error(err);
    res.status(500).send('Erro ao cadastrar usuário');
  }
});

 -->

Insira comentários no código abaixo:

# 9 - Sugestão de stack

Preciso criar um sistema de Quiz, quais tecnologias você sugere? Quero uma stack com JavaScript

Gostaria de criar uma loja virtual do zero, utilizando PHP e MySQL, quais tecnologias você sugere? Preciso de gateway de pagamento e também de hospedagem

Seria melhor criar já com um framework próprio para ecommerce? tem alguma sugestão?
