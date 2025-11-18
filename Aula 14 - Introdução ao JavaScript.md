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

## 3️⃣ Entendendo os operadores 👨🏻‍🏭

### **Operadores Aritméticos (Matemáticos)**

| Operador | Nome          | Descrição                           | Exemplo         | Resultado |
| -------- | ------------- | ----------------------------------- | --------------- | --------- |
| `+`      | Adição        | Soma dois valores                   | `5 + 3`         | `8`       |
| `-`      | Subtração     | Subtrai o segundo valor do primeiro | `10 - 4`        | `6`       |
| `*`      | Multiplicação | Multiplica dois valores             | `6 * 7`         | `42`      |
| `/`      | Divisão       | Divide o primeiro pelo segundo      | `20 / 5`        | `4`       |
| `%`      | Módulo        | Resto da divisão                    | `10 % 3`        | `1`       |
| `**`     | Exponenciação | Eleva o valor à potência            | `2 ** 3`        | `8`       |
| `++`     | Incremento    | Soma 1 ao valor                     | `let a=5; a++;` | `6`       |
| `--`     | Decremento    | Subtrai 1 do valor                  | `let a=5; a--;` | `4`       |

---

### **Operadores Comparativos**

| Operador | Nome              | Descrição                             | Exemplo     | Resultado |
| -------- | ----------------- | ------------------------------------- | ----------- | --------- |
| `==`     | Igualdade         | Compara valores (conversão implícita) | `5 == "5"`  | `true`    |
| `===`    | Igualdade estrita | Compara valor e tipo                  | `5 === "5"` | `false`   |
| `!=`     | Diferente         | Compara valores (conversão implícita) | `5 != "5"`  | `false`   |
| `!==`    | Diferente estrito | Compara valor e tipo                  | `5 !== "5"` | `true`    |
| `>`      | Maior que         | Verifica se o primeiro é maior        | `10 > 3`    | `true`    |
| `<`      | Menor que         | Verifica se o primeiro é menor        | `2 < 1`     | `false`   |
| `>=`     | Maior ou igual    |                                       | `5 >= 5`    | `true`    |
| `<=`     | Menor ou igual    |                                       | `3 <= 10`   | `true`    |

---

### **Operadores Lógicos**

| Operador | Nome           | Descrição                                | Exemplo           | Resultado |
| -------- | -------------- | ---------------------------------------- | ----------------- | --------- |
| `&&`     | AND (E lógico) | Retorna true se *ambos* forem true       | `true && false`   | `false`   |
| `\|\|`   | OR (OU lógico) | Retorna true se *pelo menos um* for true | `true \|\| false` | `true`    |
| `!`      | NOT (negação)  | Inverte o valor                          | `!true`           | `false`   |

---

## 4️⃣ Tomando decisões: if / else 🔀

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

## 5️⃣ Repetindo ações: loops 🔄

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

### Trabalhando com Arrays

Arrays são **listas** onde guardamos vários dados em uma única variável.

```javascript
let listaCompra = ["PS5", "Dollynho", "Pista do Tubarão Hot Wheels"];
```

#### 📌 Como acessar um item específico

Cada posição no array tem um índice que começa do **0**.

```javascript
console.log(listaCompra[0]); // "PS5"
console.log(listaCompra[2]); // "Pista do Tubarão Hot Wheels"
```

#### 📏 Como saber o tamanho do array

Usamos `.length`:

```javascript
console.log(listaCompra.length); // 3
```

#### ➕ Como adicionar itens

##### **1. No final (mais comum)**

```javascript
listaCompra.push("Café 3 Corações");
console.log(listaCompra);
```

##### **2. No início**

```javascript
listaCompra.unshift("TV Smart 50 Polegadas");
console.log(listaCompra);
```

#### ➖ Como remover itens

##### **1. Do final**

```javascript
listaCompra.pop(); // remove o último
```

##### **2. Do início**

```javascript
listaCompra.shift(); // remove o primeiro
```

#### ✂️ Como remover um item específico

Usando `splice(indice, quantidade)`:

```javascript
listaCompra.splice(1, 1); // remove 1 item na posição 1
```

Exemplo:

```javascript
let listaCompra = ["PS5", "Bicicleta", "Notebook Gamer Alienware 16 Aurora"];
listaCompra.splice(1, 1); 

console.log(listaCompra); // ["PS5", "Notebook Gamer Alienware 16 Aurora"]
```

#### 🔄 Como percorrer o array

##### **for tradicional**

```javascript
for (let i = 0; i < listaCompra.length; i++) {
  console.log(listaCompra[i]);
}
```

##### **for...of (mais simples)**

```javascript
for (const item of listaCompra) {
  console.log(item);
}
```

##### **forEach (bem usado no dia a dia)**

```javascript
listaCompra.forEach((item, index) => {
  console.log(`Índice ${index}: ${item}`);
});
```

---

## 6️⃣ Funções: blocos de código que podemos reutilizar 🛠️

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

## 7️⃣ Executando JavaScript fora do navegador 💻

Com o Node.js instalado, você pode criar um arquivo `.js` e rodar no terminal:

```bash
node arquivo.js
```

E usar `console.log()` para imprimir mensagens.

---

## 8️⃣ Entrada de dados no navegador: prompt ✏️

No navegador, podemos usar `prompt()` para pedir informações ao usuário.

```javascript
const nome = prompt("Qual seu nome?");
console.log(`Olá, ${nome}!`);
```

---

## 9️⃣ NPM: instalando ferramentas 📦

O Node tem um gerenciador de pacotes que permite instalar bibliotecas.

```bash
npm init -y
npm install prompt-sync
```

---

## 🔟 Exercícios para os iniciantes 🏋️

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
10. Faça um script com prompt-sync que saúda o usuário.
