# Aula 14 – Introdução ao JavaScript 🚀

## 1️⃣ Antes de tudo: Para que serve o JavaScript? 🧠

JavaScript é a linguagem que faz as páginas deixarem de ser "figurinhas" estáticas. É o que dá vida, movimento, decisões e interação.

<div align="center">
  <img src="./esqueleto_js.png" alt="Esqueleto estiloso segurando uma carta de JS enqaunto caminha.">
</div>

* HTML → estrutura
* CSS → aparência
* JavaScript → comportamento

Ele roda principalmente **no navegador**, mas também pode ser executado **no servidor** usando o Node.js.

> [!TIP] 
> ### Pense no JS como o cérebro da aplicação 🧠.

---

## 2️⃣ Variáveis: onde guardamos informações 💾

Quando queremos salvar dados na memória para usar depois, usamos variáveis.

```javascript
let nome = "Maria";
const idade = 20;
```

* `let` → pode mudar
* `const` → não pode mudar
* Tipos comuns: `number`, `string`, `boolean` e `object`

---

## 3️⃣ Tomando decisões: if / else 🔀

Com JavaScript, podemos dizer "se acontecer X, faça Y".

```javascript
const nota = 8;

if (nota >= 7) {
  console.log("Aprovado!");
} else {
  console.log("Reprovado :(");
}
```

Também existe uma forma curtinha:

```javascript
const resultado = nota >= 7 ? "Aprovado" : "Reprovado";
```

---

## 4️⃣ Repetindo ações: loops 🔄

Quando precisamos repetir algo várias vezes:

### for

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### while

```javascript
let contador = 1;
while (contador <= 5) {
  console.log(contador);
  contador++;
}
```

### Trabalhando com arrays

```javascript
const frutas = ["maçã", "banana", "uva"];

for (const fruta of frutas) {
  console.log(fruta);
}
```

---

## 5️⃣ Funções: blocos de código que podemos reutilizar 🛠️

Funções guardam ações para serem executadas depois.

### Função tradicional

```javascript
function soma(a, b) {
  return a + b;
}
```

### Arrow function

```javascript
const subtrair = (a, b) => a - b;
```

---

## 6️⃣ Executando JavaScript fora do navegador 💻

Com o Node.js instalado, você pode criar um arquivo `.js` e rodar no terminal:

```bash
node arquivo.js
```

E usar `console.log()` para imprimir mensagens.

---

## 7️⃣ Entrada de dados no navegador: prompt ✏️

No navegador, podemos usar `prompt()` para pedir informações ao usuário.

```javascript
const nome = prompt("Qual seu nome?");
console.log(`Olá, ${nome}!`);
```

---

## 8️⃣ NPM: instalando ferramentas 📦

O Node tem um gerenciador de pacotes que permite instalar bibliotecas.

```bash
npm init -y
npm install express
```

---

## 9️⃣ Exercícios para os iniciantes 🏋️

A ideia é treinar lógica e sintaxe simples.

1. Peça ao usuário nome e idade e apresente uma frase no console.
2. Receba dois números e exiba soma e média.
3. Peça uma nota e diga se passou usando ternário.
4. Mostre se um número é par ou ímpar.
5. Receba um número de 1 a 7 e mostre o dia correspondente.
6. Some os números de um array usando for.
7. Imprima frutas usando for...of.
8. Crie uma função que recebe dois números e retorna o maior.
9. Crie uma arrow function que recebe um array e retorna a soma.
10. Faça um script com readline que saúda o usuário.
