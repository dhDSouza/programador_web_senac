# 🧠 Aula 10 - Introdução ao CSS 🎨

## 🎯 Objetivos da Aula

Ao final dessa aula, você será capaz de:

* Entender o que é o CSS e sua função no desenvolvimento web;
* Diferenciar **Inline**, **Interno** e **Externo**;
* Utilizar **seletores**, **classes** e **IDs**;
* Aplicar as principais **propriedades básicas** do CSS.

---

## 1️⃣ O que é CSS?

CSS (Cascading Style Sheets) é a linguagem usada para **estilizar páginas HTML** — ou seja, definir cores, tamanhos, fontes, espaçamentos, alinhamentos, etc.

> [!TIP]
> Ele **separa o conteúdo (HTML)** da **apresentação (CSS)**, o que torna o código mais organizado e fácil de manter.

<div align="center">
  <img src="./esqueleto_drip.png">
  <h4>Nosso esqueleto estiloso</h4>
</div>

---

## 2️⃣ Formas de aplicar CSS

### 🧩 1. CSS Inline

Aplicado **diretamente na tag HTML** com o atributo `style`.

📘 Exemplo:

```html
<p style="color: blue; font-size: 18px;">Olá, mundo!</p>
```

💬 **Vantagem:** rápido e simples pra testar algo.   
⚠️ **Desvantagem:** difícil de manter — cada elemento precisa ser alterado manualmente.

---

### 🧱 2. CSS Interno (Internal)

Adicionado dentro da tag `<style>` no `<head>` do HTML.

📘 Exemplo:

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    p {
      color: green;
      font-size: 20px;
    }
  </style>
</head>
<body>
  <p>Olá, CSS interno!</p>
</body>
</html>
```

💬 **Vantagem:** centraliza o estilo dentro do mesmo arquivo.   
⚠️ **Desvantagem:** ainda não é ideal pra sites com várias páginas.

---

### 🌐 3. CSS Externo (External)

É o método **profissional e mais usado**.
O CSS fica em um **arquivo separado** (ex: `style.css`), e o HTML o importa com `<link>`.

📘 Exemplo:

**HTML**

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <p>Olá, CSS externo!</p>
</body>
</html>
```

**style.css**

```css
p {
  color: red;
  font-size: 22px;
}
```

💬 **Vantagens:** fácil manutenção, reutilização e melhor performance.

⚠️ **Desvantagem:** precisa gerenciar mais arquivos.

---

## 3️⃣ Seletores 🎯

Um **seletor** é o que o CSS usa para **“apontar”** quais elementos serão estilizados.

### 🔹 Seletor por **tag**

Aplica o estilo a todas as tags daquele tipo.

```css
h1 {
  color: purple;
}
```

### 🔹 Seletor por **classe** (`.`)

Usado quando queremos aplicar o mesmo estilo a vários elementos.

📘 Exemplo:

```html
<p class="destaque">Texto com classe!</p>
```

```css
.destaque {
  color: orange;
  font-weight: bold;
}
```

### 🔹 Seletor por **ID** (`#`)

Usado para **um elemento único**.

📘 Exemplo:

```html
<p id="principal">Texto com ID!</p>
```

```css
#principal {
  color: blue;
  font-size: 24px;
}
```

💡 Dica:

* Use **classe** para estilos **repetidos**.
* Use **ID** para algo **único**, tipo um cabeçalho ou rodapé.

---

## 4️⃣ Comandos básicos do CSS ⚙️

Aqui vão algumas propriedades fundamentais:

| Propriedade        | O que faz            | Exemplo                           |
|:------------------:|:--------------------:|:---------------------------------:|
| `color`            | cor do texto         | `color: red;`                     |
| `background-color` | cor de fundo         | `background-color: lightgray;`    |
| `font-size`        | tamanho da fonte     | `font-size: 20px;`                |
| `font-family`      | tipo de fonte        | `font-family: Arial, sans-serif;` |
| `text-align`       | alinhamento do texto | `text-align: center;`             |
| `margin`           | espaçamento externo  | `margin: 10px;`                   |
| `padding`          | espaçamento interno  | `padding: 20px;`                  |
| `border`           | borda                | `border: 2px solid black;`        |
| `width` / `height` | largura / altura     | `width: 200px; height: 100px;`    |

📘 Exemplo prático:

```css
.caixa {
  background-color: #f5f5f5;
  color: #333;
  border: 2px solid black;
  padding: 20px;
  margin: 15px;
  text-align: center;
}
```

---

## 5️⃣ Mini Desafio 💪

Crie uma página `index.html` e um arquivo `style.css`.

* No HTML, coloque:

  * Um título (`h1`)
  * Um parágrafo (`p`)
  * Um botão (`button`)

* No CSS:

  * Faça o `h1` azul e centralizado;
  * Faça o parágrafo cinza e com tamanho 18px;
  * Faça o botão com fundo vermelho, texto branco e bordas arredondadas.

---

## 🧩 Extra — Hierarquia (Cascata)

Se o mesmo elemento for estilizado de várias formas, o CSS decide **quem manda**:

1. **Inline** tem prioridade máxima;
2. Depois vem **Interno**;
3. Por último, o **Externo**.

📘 Exemplo:

```html
<p id="texto" style="color: red;">Teste</p>
```

Mesmo que no CSS externo diga `#texto { color: blue; }`,
👉 o **inline (red)** vence.

---

## 🎓 Encerramento

* CSS = aparência do site 🖌️
* Três formas de aplicar: Inline, Interno, Externo
* Seletor → define o alvo
* Classes e IDs → reaproveitamento e organização
* E sempre teste, brinque e explore 💡
