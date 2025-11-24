# Aula 15 - JavaScript para Front-End

Depois de construir o **esqueleto do nosso site** com **HTML** e dar aquele visual estiloso com **CSS**, chegou o momento de **dar vida a tudo isso**.   

O que veremos hoje:

1. **🎯 Eventos em JavaScript**
2. **🌳 Manipulação do DOM**

<div align="center">
  <img src="https://i.gifer.com/Af6V.gif" alt="esqueleto dançando"/>
  <p>Fonte: <a href="https://i.gifer.com/Af6V.gif" target="_blank">https://i.gifer.com/Af6V.gif</a></p>
</div>

## 🎯 Parte 1: Eventos em JavaScript

### O que são Eventos? 🎪

Eventos são ações ou ocorrências que acontecem no navegador, como cliques, teclas pressionadas, movimentos do mouse, etc.

### Tabela de Eventos Comuns 📋

| Evento         | Descrição                          | Exemplo de Uso                     |
|:--------------:|:----------------------------------:|:----------------------------------:|
| `click`        | Quando um elemento é clicado       | Botões, links                      |
| `dblclick`     | Duplo clique no elemento           | Edição rápida                      |
| `mouseover`    | Mouse sobre o elemento             | Efeitos hover                      |
| `mouseout`     | Mouse sai do elemento              | Reverter efeitos hover             |
| `mousemove`    | Mouse se move sobre o elemento     | Animações com mouse                |
| `keydown`      | Tecla pressionada                  | Controles de jogo, atalhos         |
| `keyup`        | Tecla liberada                     | Validação de formulário            |
| `submit`       | Formulário submetido               | Validação antes de enviar          |
| `change`       | Valor de input/select alterado     | Atualizações dinâmicas             |
| `focus`        | Elemento recebe foco               | Destacar campo ativo               |
| `blur`         | Elemento perde foco                | Validação ao sair do campo         |
| `load`         | Página/elemento carregado          | Inicializar após carregamento      |
| `scroll`       | Rolagem da página/elemento         | Efeitos parallax, lazy loading     |
| `resize`       | Janela redimensionada              | Layouts responsivos                |

### Como Usar Eventos? 🛠️

#### Método 1: Atributo HTML (não recomendado)
```html
<button onclick="alert('Clicado!')">Clique-me</button>
```

#### Método 2: Propriedade do elemento (pouco usado)

```javascript
const btn = document.querySelector('button');
btn.onclick = function() {
  console.log('Clicado!');
};
```

#### Método 3: `addEventListener` (recomendado)

```javascript
const btn = document.querySelector('button');
btn.addEventListener('click', function() {
  console.log('Clicado com addEventListener!');
});
```

### Exemplo Completo com Evento ✨

```html
<button id="meuBotao">Clique-me</button>
<p id="contador">0 cliques</p>

<script>
  const botao = document.getElementById('meuBotao');
  const contadorElemento = document.getElementById('contador');
  let contador = 0;

  botao.addEventListener('click', () => {
    contador++;
    contadorElemento.textContent = `${contador} cliques`;
    
    if (contador > 5) {
      botao.style.backgroundColor = 'red';
    }
  });
</script>
```

## 🌳 Parte 2: Manipulação do DOM

### O que é o DOM? 🌐

DOM (Document Object Model) é uma representação em árvore do documento HTML, onde cada elemento é um nó (node). O JavaScript pode manipular esses nós para alterar a página dinamicamente.

### Como Acessar Elementos? 🔍

| Método                         | Retorno                           | Exemplo                     |
|:------------------------------:|:---------------------------------:|:---------------------------:|
| `document.getElementById()`    | Elemento com ID específico        | `document.getElementById('header')` |
| `document.querySelector()`     | Primeiro elemento que casa com o seletor | `document.querySelector('.btn')` |
| `document.querySelectorAll()`  | NodeList de todos elementos que casam | `document.querySelectorAll('p')` |
| `document.getElementsByTagName()` | HTMLCollection de elementos pela tag | `document.getElementsByTagName('div')` |
| `document.getElementsByClassName()` | HTMLCollection de elementos pela classe | `document.getElementsByClassName('active')` |

### Manipulando Elementos ✂️

#### Alterando conteúdo

```javascript
// textContent (apenas texto)
elemento.textContent = 'Novo texto';

// innerHTML (permite HTML)
elemento.innerHTML = '<strong>Texto</strong> em negrito';
```

#### Alterando estilos

```javascript
elemento.style.backgroundColor = 'blue';
elemento.style.fontSize = '20px';
```

#### Adicionando/Removendo classes

```javascript
elemento.classList.add('ativo');
elemento.classList.remove('inativo');
elemento.classList.toggle('destaque'); // adiciona se não tem, remove se tem
```

#### Criando/Removendo elementos

```javascript
// Criar novo elemento
const novoParagrafo = document.createElement('p');
novoParagrafo.textContent = 'Sou novo aqui!';

// Adicionar ao DOM
document.body.appendChild(novoParagrafo);

// Remover elemento
const elementoParaRemover = document.getElementById('remover');
elementoParaRemover.remove();
```

### Exemplo Completo de Manipulação DOM 🏗️

```html
<div id="container">
  <button id="adicionar">Adicionar Item</button>
  <button id="remover">Remover Último</button>
  <ul id="lista"></ul>
</div>

<script>
  const adicionarBtn = document.getElementById('adicionar');
  const removerBtn = document.getElementById('remover');
  const lista = document.getElementById('lista');
  let contador = 1;

  adicionarBtn.addEventListener('click', () => {
    const novoItem = document.createElement('li');
    novoItem.textContent = `Item ${contador++}`;
    novoItem.classList.add('item-lista');
    lista.appendChild(novoItem);
  });

  removerBtn.addEventListener('click', () => {
    const ultimoItem = lista.lastElementChild;
    if (ultimoItem) {
      ultimoItem.remove();
      contador--;
    }
  });
</script>
```

### Event Delegation (Delegação de Eventos) 🎯
Ótimo para elementos dinâmicos ou muitos elementos similares:

```html
<ul id="lista-tarefas">
  <!-- Itens serão adicionados dinamicamente -->
</ul>

<script>
  const listaTarefas = document.getElementById('lista-tarefas');
  
  // Adiciona evento na lista (pai) em vez de cada item (filho)
  listaTarefas.addEventListener('click', (event) => {
    if (event.target.tagName === 'LI') {
      event.target.classList.toggle('completa');
    }
  });
  
  // Adicionando itens dinamicamente
  for (let i = 1; i <= 5; i++) {
    const item = document.createElement('li');
    item.textContent = `Tarefa ${i}`;
    listaTarefas.appendChild(item);
  }
</script>
```


## 🧠 **Exercícios - Parte 1: Eventos em JavaScript**

### 🔁 **Ex. 1 – Alternar Visibilidade de um Elemento**

Crie:

* Um botão com o texto "Mostrar/Esconder"
* Um parágrafo com um texto qualquer

**Objetivo:**

* Ao clicar no botão, o parágrafo deve ser escondido se estiver visível e mostrado se estiver escondido.

### 🎨 **Ex. 2 – Mudança de Cor com Mouse**

Crie um `<div>` com 200x200px de largura/altura e cor de fundo cinza.

Adicione eventos:

* Ao passar o mouse por cima (`mouseover`), mude a cor para azul
* Ao tirar o mouse (`mouseout`), volte para cinza

### 🔡 **Ex. 3 – Mostrar Texto ao Pressionar Tecla**

Adicione um `<input>` e um `<p>` vazio abaixo dele.

Ao digitar algo no input:

* Mostre em tempo real no parágrafo o que está sendo digitado (usando `keyup`).

---

## 🧠 **Exercícios - Parte 2: Manipulação do DOM**

### 🧾 **Ex. 4 – Lista de Tarefas Simples**

Crie:

* Um campo de texto
* Um botão "Adicionar"
* Uma `<ul>` vazia

Ao clicar no botão:

* Pegue o valor do campo de texto
* Crie um novo `<li>` com esse texto
* Adicione o `<li>` à lista

### 🌟 **Ex. 5 – Botão com Estilo Dinâmico**

Crie um botão com o texto "Mudar tema".

Ao clicar:

* Troque a cor de fundo da página entre branco e preto (modo claro/escuro)
* Troque a cor do texto também (para ficar visível)
* Use `classList.toggle()` para aplicar/remover uma classe CSS
