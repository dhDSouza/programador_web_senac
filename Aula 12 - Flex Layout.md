# 🖥️ Aula 12 - Flex Layout em CSS 🚀

## O que é o `display: flex`? 🤔

A propriedade `display: flex` ativa o **Flexbox**, um modelo de layout poderoso que facilita a criação de layouts **flexíveis** e **responsivos** em CSS. Ele permite que você organize os itens dentro de um container de forma eficiente, mesmo que o tamanho dos itens seja dinâmico ou desconhecido. 🎨

---

## Como Funciona o Flexbox? 💡

Quando você define `display: flex` em um container, ele se torna um **flex container**. Os elementos dentro dele se tornam **flex items**. Esses itens são organizados automaticamente de acordo com o modelo **Flexbox**.

O Flexbox funciona com dois eixos principais:

1. **Eixo Principal (Main Axis)** ➡️: É o eixo ao longo do qual os itens são organizados. Por padrão, é **horizontal** (de esquerda para direita).
2. **Eixo Transversal (Cross Axis)** ⬇️: É o eixo perpendicular ao eixo principal. Por padrão, é **vertical** (de cima para baixo).

---

## 🛠️ Propriedades Principais do Flexbox

### No **Flex Container** 🧑‍💻

Essas são as propriedades que você pode usar no **flex container**:

#### 1. **`flex-direction`** 🧭

Define a direção dos itens no eixo principal.

* `row` (padrão): Alinha os itens **horizontalmente**.
* `column`: Alinha os itens **verticalmente**.
* `row-reverse`: Alinha os itens **horizontalmente**, mas na **ordem inversa**.
* `column-reverse`: Alinha os itens **verticalmente**, mas na **ordem inversa**.

Exemplo:

```css
.container {
  display: flex;
  flex-direction: column; /* Alinha os itens de forma vertical */
}
```

#### 2. **`flex-wrap`** 📦

Controla se os itens devem quebrar para a próxima linha quando o espaço não for suficiente.

* `nowrap` (padrão): Todos os itens ficam em **uma linha**.
* `wrap`: Os itens **quebram para a próxima linha** quando necessário.
* `wrap-reverse`: Os itens quebram, mas em ordem **inversa**.

Exemplo:

```css
.container {
  display: flex;
  flex-wrap: wrap; /* Os itens vão quebrar para a próxima linha, se necessário */
}
```

#### 3. **`flex-flow`** 🔄

É uma combinação de `flex-direction` e `flex-wrap`. A forma mais curta de declarar essas duas propriedades.

Exemplo:

```css
.container {
  display: flex;
  flex-flow: row wrap; /* Direção: horizontal e quebra: quando necessário */
}
```

#### 4. **`justify-content`** 🎯

Alinha os itens ao longo do **eixo principal** (horizontal, por padrão).

* `flex-start` (padrão): Itens alinhados **no início** do container.
* `center`: Itens alinhados **no centro**.
* `space-between`: Itens distribuídos com **espaço igual** entre eles.
* `space-around`: Itens distribuídos com **espaço igual ao redor** deles.
* `space-evenly`: Itens distribuídos com **espaço igual entre e ao redor** deles.

Exemplo:

```css
.container {
  display: flex;
  justify-content: space-between; /* Espaços iguais entre os itens */
}
```

#### 5. **`align-items`** 🎲

Alinha os itens ao longo do **eixo transversal** (vertical, por padrão).

* `stretch` (padrão): Os itens são esticados para preencher o container.
* `flex-start`: Alinha os itens no **início** do eixo transversal.
* `center`: Alinha os itens no **centro** do eixo transversal.
* `flex-end`: Alinha os itens no **final** do eixo transversal.
* `baseline`: Alinha os itens pela **linha de base** do texto.

Exemplo:

```css
.container {
  display: flex;
  align-items: center; /* Itens são centralizados verticalmente */
}
```

#### 6. **`align-content`** ↔️

Essa propriedade alinha **linhas de itens** (quando você tem várias linhas de flex items) no eixo transversal.

* `flex-start`: Alinha as linhas no **início** do container.
* `center`: Alinha as linhas no **centro**.
* `space-between`: Distribui as linhas com **espaço igual** entre elas.
* `space-around`: Distribui as linhas com **espaço igual ao redor** delas.
* `stretch`: Estica as linhas para preencher o container.

Exemplo:

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: space-between; /* Espaço igual entre as linhas */
}
```

#### 7. **`align-self`** 🧍‍♂️

Permite que um item individual se alinhe de maneira diferente dos outros itens, ao longo do eixo transversal. Ele sobrescreve a propriedade `align-items` para um item específico.

Exemplo:

```css
.item {
  align-self: flex-end; /* Esse item vai ser alinhado ao final do eixo transversal */
}
```

---

### Nos **Flex Items** ⚙️

Essas propriedades podem ser aplicadas diretamente aos **itens flexíveis**:

#### 1. **`flex`** 🎛️

É uma combinação de **`flex-grow`**, **`flex-shrink`** e **`flex-basis`**. Ela define como um item pode crescer ou encolher para preencher o espaço disponível.

Exemplo:

```css
.item {
  flex: 1; /* O item vai crescer para preencher o espaço disponível */
}
```

#### 2. **`flex-grow`** 📈

Define a capacidade de **crescimento** do item. O valor `1` significa que o item vai crescer para preencher o espaço disponível.

Exemplo:

```css
.item {
  flex-grow: 1; /* O item cresce para ocupar o máximo de espaço disponível */
}
```

#### 3. **`flex-shrink`** 📉

Define a capacidade de **encolher** do item. O valor `1` significa que o item pode encolher quando o espaço é limitado.

Exemplo:

```css
.item {
  flex-shrink: 1; /* O item encolhe se não houver espaço suficiente */
}
```

#### 4. **`flex-basis`** 📏

Define o **tamanho inicial** do item antes de distribuir o espaço disponível. Pode ser em pixels, porcentagens, etc.

Exemplo:

```css
.item {
  flex-basis: 200px; /* O item começa com 200px de largura */
}
```

#### 5. **`align-self`** 🧑‍🎨

Define a **aliança individual** do item no eixo transversal, sobrescrevendo o `align-items`.

Exemplo:

```css
.item {
  align-self: center; /* Alinha o item individualmente no centro */
}
```

---

## Quando Usar o Flexbox? 📝

O **Flexbox** é ideal para:

* **Layouts Responsivos**: Quando você quer que o layout se ajuste automaticamente em diferentes tamanhos de tela.
* **Alinhamento e Distribuição**: Quando precisar alinhar ou distribuir itens com espaço igualmente entre eles.
* **Organização de Layout**: Quando os itens precisam se ajustar dinamicamente, dependendo do conteúdo.

---

## Exemplo Prático de Flexbox 🏗️

```html
<!DOCTYPE html>
<html lang="pt">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        .container {
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }

        .item {
            background-color: lightblue;
            padding: 20px;
            border: 1px solid #333;
            width: 100px;
            text-align: center;
        }
    </style>
    <title>Exemplo Flexbox</title>
</head>

<body>
    <div class="container">
        <div class="item">Item 1</div>
        <div class="item">Item 2</div>
        <div class="item">Item 3</div>
    </div>
</body>

</html>
```
---

## 🎮 Desafio Flexbox Froggy

Para praticar tudo o que você aprendeu de uma forma divertida, você pode jogar o **Flexbox Froggy**, um jogo onde você ajuda sapos a se alinhar usando as propriedades do Flexbox. É uma maneira prática e interativa de entender o comportamento do Flexbox. 🐸

* [Acesse o Flexbox Froggy aqui!](https://flexboxfroggy.com/)


