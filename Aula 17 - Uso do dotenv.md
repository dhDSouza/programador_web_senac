# Aula 17 – Uso do dotenv no Node.js (Express + MySQL)

## 🎯 Objetivo da aula

* Entender o que são **variáveis de ambiente**
* Compreender por que **dados sensíveis não devem ficar no código**
* Utilizar o pacote **dotenv** em projetos Node.js
* Organizar corretamente um arquivo `.env`
* Aplicar boas práticas usadas no mercado de trabalho

---

## 1️⃣ O problema: dados sensíveis no código

Em muitos projetos iniciantes, é comum encontrar algo como:

```js
const conn = mysql.createConnection({
    host: 'localhost',
    user: 'root',
    password: '123456',
    database: 'sistema'
});
```

### ❌ Problemas dessa abordagem

* 🔓 **Risco de segurança**: se o projeto for enviado para o GitHub, a senha do banco fica pública
* 🔁 **Pouca flexibilidade**: mudar ambiente (local, teste, produção) exige alterar o código
* 🛠 **Manutenção ruim**: qualquer alteração de configuração obriga mudança no código-fonte
* 🚫 **Fora do padrão profissional**: em empresas, isso normalmente não passa em revisão de código

👉 Conclusão importante:

> **Configuração não é código. Configuração é ambiente.**

---

## 2️⃣ O que são variáveis de ambiente?

Variáveis de ambiente são valores definidos **fora do código**, mas que podem ser acessados durante a execução da aplicação.

No Node.js, elas ficam disponíveis no objeto:

```js
process.env
```

Exemplos:

```js
process.env.PORT
process.env.DB_USER
process.env.DB_PASSWORD
```

Essas variáveis pertencem ao **sistema operacional ou servidor**, não ao arquivo JavaScript.

---

## 3️⃣ O que é o dotenv?

O **dotenv** é um pacote que carrega variáveis de um arquivo `.env` e as injeta automaticamente no `process.env`.

Em outras palavras:

* Lê o arquivo `.env`
* Interpreta suas variáveis
* Disponibiliza tudo dentro do `process.env`

Isso permite separar **configuração** de **lógica da aplicação**.

---

## 4️⃣ Instalando o dotenv

No terminal, dentro do projeto:

```bash
npm install dotenv
```

---

## 5️⃣ Criando o arquivo `.env`

O arquivo `.env` deve ficar na **raiz do projeto**.

Exemplo:

```env
PORT=3000

DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=meubanco
DB_USER=root
DB_PASSWORD=123456
```

### ⚠️ Regras importantes

* Não usar aspas
* Não colocar espaços antes ou depois do `=`
* Uma variável por linha

---

## 6️⃣ Usando dotenv no código

Importe o pacote:

```js
const dotenv = require('dotenv');
```

E carregue as variáveis **antes de usá-las**:

```js
dotenv.config();
```

📌 Essa linha é essencial: sem ela, o `process.env` não será populado com os dados do `.env`.

---

## 7️⃣ Código completo utilizando dotenv

```js
const express = require('express');
const mysql = require('mysql2');
const bodyParser = require('body-parser');
const cors = require('cors');
const dotenv = require('dotenv');

// Carrega as variáveis de ambiente
dotenv.config();

const app = express();
const PORT = process.env.PORT || 3000;

app.use(bodyParser.json());
app.use(cors());

// Desestruturação das variáveis do .env
const { DB_HOST, DB_PORT, DB_DATABASE, DB_USER, DB_PASSWORD } = process.env;

const conn = mysql.createConnection({
    host: DB_HOST,
    port: DB_PORT,
    database: DB_DATABASE,
    user: DB_USER,
    password: DB_PASSWORD
});

conn.connect(error => {
    if (error) {
        console.error('Erro ao conectar ao banco de dados! ' + error.stack);
        return;
    }
    console.log('Sucesso ao conectar com o banco de dados!');
});

app.get('/users', (req, res) => {
    conn.query('SELECT * FROM users', (error, results) => {
        if (error) {
            res.status(500).send('Erro ao obter dados.');
            return;
        }
        res.status(200).json(results);
    });
});

app.get('/users/:id', (req, res) => {
    const id = parseInt(req.params.id);
    
    conn.query('SELECT * FROM users WHERE id = ?', [id], (error, results) => {
        if (error) {
            res.status(500).send('Erro ao obter dados.');
            return;
        }
        res.status(200).json(results[0]);
    });
});

app.post('/users', (req, res) => {
    const { nome, email, senha } = req.body;

    conn.query(
        'INSERT INTO users (nome, email, senha) VALUES (?, ?, ?)',
        [nome, email, senha],
        (error) => {
            if (error) {
                res.status(500).send('Erro ao inserir um novo usuário!');
                return;
            }
            res.status(201).send('Usuário criado com sucesso!');
        }
    );
});

app.listen(PORT, () => {
    console.log(`Servidor rodando em http://localhost:${PORT}`);
});
```

---

## 8️⃣ Segurança: `.env` e Git

O arquivo `.env` **NUNCA** deve ser enviado para o repositório.

No `.gitignore`:

```gitignore
node_modules
.env
```

Cada desenvolvedor e cada servidor terá seu próprio `.env`.

---

## 9️⃣ Boa prática: `.env.example`

Crie um arquivo apenas como modelo:

```env
PORT=
DB_HOST=
DB_PORT=
DB_DATABASE=
DB_USER=
DB_PASSWORD=
```

✔ Pode subir para o GitHub   
✔ Serve como documentação   
✔ Facilita a configuração do projeto   

---

## 🔟 Erros comuns com dotenv

* Esquecer de chamar `dotenv.config()`
* Tentar acessar `process.env` antes do `config()`
* Nome da variável no `.env` diferente do código
* Não criar o arquivo `.env`

---

## ✅ Conclusão

O uso do `dotenv` é um **padrão profissional** no desenvolvimento backend.

Ele garante:

* 🔐 Mais segurança
* 🔧 Melhor organização
* 🌍 Facilidade para múltiplos ambientes
* 🚀 Código mais limpo e escalável

> Um sistema profissional separa claramente **código** de **configuração**.
