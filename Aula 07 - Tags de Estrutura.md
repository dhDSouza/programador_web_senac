# 📌 Aula 7 - Introdução às Tags de Estrutura

### ✅ **Tag `<div>` – Organizando a página em blocos**

* **O que é?**
  A tag `<div>` é usada para **agrupar conteúdos** e organizar diferentes seções da página. É como uma "caixa invisível" que nos ajuda a estruturar melhor os elementos.

* **Exemplo:**

  ```html
  <div>
      <h1>Seção Principal</h1>
      <p>Este é um parágrafo dentro de uma div.</p>
  </div>
  ```

* **Por que usar?**
  Ela é muito útil para aplicar estilos ou layouts em partes específicas da página. Imagine que você quer colorir uma seção inteira — usar uma `<div>` facilita isso.

---

### ✏️ **Tag `<span>` – Estilizando partes do texto**

* **O que é?**
  A tag `<span>` é usada **dentro de linhas de texto** para aplicar estilos em **palavras ou trechos específicos**, sem quebrar a estrutura do parágrafo.

* **Exemplo:**

  ```html
  <p>Esta palavra é <span style="color: red;">vermelha</span>.</p>
  ```

* **Dica:** Use `<span>` quando quiser destacar uma parte do texto, como deixar uma palavra em negrito, colorida, ou com fonte diferente.

---

## 🎨 Introdução ao Atributo `style`

* **O que é?**
  O atributo `style` permite adicionar regras de **CSS** diretamente nos elementos HTML para **alterar sua aparência** (como cor, tamanho, alinhamento, etc.).

* **Exemplo:**

  ```html
  <h1 style="color: blue; text-align: center;">Título Centralizado em Azul</h1>
  <p style="font-size: 18px; color: green;">Este parágrafo é verde e tem tamanho de fonte 18px.</p>
  ```

* **Observação:**
  Embora seja possível estilizar diretamente no HTML com `style`, o ideal é usar **CSS externo** em projetos maiores, para manter o código mais organizado.

---

## 🌈 Trabalhando com Cores e Fontes

### 🎨 **Cores**

* **Como usar?**
  Você pode definir cores usando:

  * **Nomes** (como `red`, `blue`, `green`)
  * **Códigos Hexadecimais** (como `#ff0000` para vermelho)

* **Exemplo:**

  ```html
  <p style="color: #00ff00;">Este texto é verde (usando hexadecimal).</p>
  ```

---

### 🖋️ **Fontes**

* **Como alterar?**
  Usamos a propriedade `font-family` para definir o tipo de fonte, e `font-size` para o tamanho.

* **Exemplo:**

  ```html
  <p style="font-family: Arial, sans-serif;">Este texto usa a fonte Arial.</p>
  ```

* **Dica:** Sempre defina uma fonte de backup como `sans-serif` ou `serif`, caso a principal não esteja disponível.

---

## 🔗 Criando Links Internos e Âncoras

* **O que são?**
  Links internos servem para **navegar entre seções** da **mesma página**, usando IDs e âncoras.

* **Exemplo:**

  ```html
  <h2 id="seção1">Seção 1</h2>
  <p>Conteúdo da Seção 1.</p>

  <h2 id="seção2">Seção 2</h2>
  <p>Conteúdo da Seção 2.</p>

  <a href="#seção1">🔝 Voltar para a Seção 1</a>
  ```

* **Como funciona?**

  * O atributo `id` serve para **marcar um ponto** da página.
  * O `href="#id"` cria o link que leva até esse ponto.

---

## 🧪 Atividade Prática

### 🧱 1. Criar uma Página com Seções

* Crie 3 seções usando `<div>`, cada uma com:

  * Um título `<h2>`
  * Um parágrafo `<p>`
  * Um fundo diferente com o atributo `style`

* **Exemplo:**

  ```html
  <div style="background-color: #f0f0f0;">
      <h2>Seção 1</h2>
      <p>Conteúdo da primeira seção.</p>
  </div>

  <div style="background-color: #e0e0e0;">
      <h2>Seção 2</h2>
      <p>Conteúdo da segunda seção.</p>
  </div>

  <div style="background-color: #d0d0d0;">
      <h2>Seção 3</h2>
      <p>Conteúdo da terceira seção.</p>
  </div>
  ```

---

### 🎨 2. Estilizar Textos

* Aplique estilos diferentes aos títulos e textos:

  * Cores personalizadas
  * Tamanhos variados de fonte

* **Exemplo:**

  ```html
  <h2 style="color: #333; text-align: left;">Título Esquerdo</h2>
  <p style="color: #666; font-size: 14px;">Este texto é cinza e pequeno.</p>
  ```

---

### 🔗 3. Criar Links Internos

* Adicione links que levem a cada seção da página.

* **Exemplo:**

  ```html
  <a href="#seção1">Ir para a Seção 1</a> |
  <a href="#seção2">Ir para a Seção 2</a> |
  <a href="#seção3">Ir para a Seção 3</a>
  ```

---

## 🧠 Exercícios Finais

1. Crie uma seção adicional na página que inclua uma lista não ordenada de tópicos que você gostaria de aprender sobre HTML.
2. Adicione estilos personalizados à seção criada, mudando a cor de fundo e o tamanho do texto.
3. Crie um link interno que leva até essa nova seção a partir do topo da página.
