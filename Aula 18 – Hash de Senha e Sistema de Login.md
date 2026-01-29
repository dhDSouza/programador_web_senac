# Aula 18 – Hash de Senha e Sistema de Login (Node.js + Express + MySQL)

## 🎯 Objetivo da aula

* Entender **por que senhas nunca devem ser armazenadas em texto puro**
* Compreender o conceito de **hash de senha**
* Utilizar o **bcrypt** para gerar e validar hashes
* Implementar um **mini sistema de cadastro e login**
* Aplicar boas práticas de segurança usadas no mercado

---

## 1️⃣ O problema: senha em texto puro

Exemplo muito comum (e muito errado):

```sql
senha = "123456"
```

Ou no código:

```js
INSERT INTO users (email, senha) VALUES ('email@email.com', '123456');
```

### ❌ Por que isso é grave?

* 🔓 Se o banco vazar, **todas as senhas vazam**
* 🔁 Usuários costumam reutilizar senhas
* 🚫 Viola boas práticas e leis de proteção de dados
* 💣 Facilita ataques e compromete o sistema inteiro

> [!NOTE]
> **O sistema nunca deve saber a senha real do usuário.**

---

## 2️⃣ O que é hash de senha?

Hash é uma função matemática que:

* Recebe um valor de entrada (senha)
* Gera uma **sequência irreversível** de caracteres

Exemplo:

```
123456  →  $2b$10$QwErTyUiOp...
```

### Características importantes

* 🔁 A mesma senha gera hashes diferentes (com salt)
* 🔐 Não é possível "descriptografar" o hash
* ✅ A verificação é feita comparando senha + hash

---

## 3️⃣ Por que usar bcrypt?

O **bcrypt** é uma biblioteca feita especificamente para senhas:

* Usa **salt automaticamente**
* É **lento de propósito** (dificulta força bruta)
* Muito utilizado no mercado
* Simples de usar com Node.js

---

## 4️⃣ Instalando o bcrypt

No terminal:

```bash
npm install bcrypt
```

---

## 5️⃣ Fluxo de um sistema de login seguro

### Cadastro

1. Usuário envia senha
2. Sistema gera hash da senha
3. Hash é salvo no banco

### Login

1. Usuário envia senha
2. Sistema compara senha digitada com o hash salvo
3. Se estiverem iguais → login permitido

> [!IMPORTANT]
> ⚠️ Em nenhum momento a senha original é salva.

---

## 6️⃣ Estrutura da tabela de usuários

Exemplo simplificado:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL
);
```

O campo `senha` armazena o **hash**, não a senha real.

---

## 7️⃣ Código base do sistema

### Importações

```js
const express = require('express');
const mysql = require('mysql2');
const bodyParser = require('body-parser');
const cors = require('cors');
const bcrypt = require('bcrypt');
const dotenv = require('dotenv');

// Carrega variáveis de ambiente
dotenv.config();
```

---

## 8️⃣ Cadastro de usuário com hash de senha

```js
app.post('/register', async (req, res) => {
    const { nome, email, senha } = req.body;

    if (!senha) {
        return res.status(400).send('Senha é obrigatória');
    }

    try {
        const saltRounds = 10;
        const senhaHash = await bcrypt.hash(senha, saltRounds);

        conn.query(
            'INSERT INTO users (nome, email, senha) VALUES (?, ?, ?)',
            [nome, email, senhaHash],
            (error) => {
                if (error) {
                    res.status(500).send('Erro ao cadastrar usuário');
                    return;
                }
                res.status(201).send('Usuário cadastrado com sucesso');
            }
        );
    } catch (err) {
        res.status(500).send('Erro ao gerar hash da senha');
    }
});
```

### 📌 O que está acontecendo aqui?

* `bcrypt.hash()` gera o hash da senha
* `saltRounds` define o custo de processamento
* O banco **nunca recebe a senha real**

---

## 9️⃣ Login de usuário (validação de senha)

```js
app.post('/login', (req, res) => {
    const { email, senha } = req.body;

    conn.query(
        'SELECT * FROM users WHERE email = ?',
        [email],
        async (error, results) => {
            if (error || results.length === 0) {
                res.status(401).send('Usuário ou senha inválidos');
                return;
            }

            const usuario = results[0];

            const senhaValida = await bcrypt.compare(senha, usuario.senha);

            if (!senhaValida) {
                res.status(401).send('Usuário ou senha inválidos');
                return;
            }

            res.status(200).send('Login realizado com sucesso');
        }
    );
});
```

### 📌 Explicação

* `bcrypt.compare()` compara senha digitada com o hash
* Não existe `SELECT senha = ?`
* Segurança baseada em comparação de hash

---

## 🔟 Boas práticas importantes

* Nunca retornar mensagens diferentes para erro de email ou senha
* Nunca logar senhas ou hashes
* Sempre validar dados de entrada
* Usar HTTPS em produção

---

## 1️⃣1️⃣ Erros comuns

* Salvar senha sem hash
* Usar MD5 ou SHA1 (inseguros)
* Comparar senha diretamente no SQL
* Usar salt fixo

---

## ✅ Conclusão

Hash de senha não é opcional, é **obrigatório**.

Um sistema seguro:

* 🔐 Nunca armazena senha em texto puro
* 🧠 Compara hashes, não valores diretos
* 🚀 Segue padrões profissionais
