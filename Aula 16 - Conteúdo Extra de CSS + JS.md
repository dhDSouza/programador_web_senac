# Aula Extra — Variáveis com `:root`, Preferências de Cor com `@media` e CSS Modular

## 🎯 Objetivos da Aula

* Entender como criar e usar variáveis CSS com `:root`.
* Utilizar `@media` para capturar preferências de tema do sistema operacional.
* Organizar CSS de forma modular, separando responsabilidades e importando em um arquivo principal.

---

## 1. O que é `:root` e por que ele é tão útil?

O `:root` é basicamente o **elemento mais alto da árvore DOM**, equivalente ao `html`. A diferença é que `:root` possui maior **especificidade**, então é perfeito para declarar variáveis globais.

### 🧪 Exemplo simples de variáveis CSS

```css
:root {
  --cor-primaria: #4f46e5;
  --cor-secundaria: #64748b;
  --espacamento: 16px;
}

button {
  background: var(--cor-primaria);
  padding: var(--espacamento);
  color: #fff;
  border-radius: 8px;
}
```

### Por que usar variáveis?

* Facilita manutenção: troque um valor e toda a UI atualiza.
* Ajuda na criação de temas.
* Mantém consistência visual.

---

## 2. Detectando tema claro/escuro com `@media`

Hoje em dia, quase todo sistema operacional (Windows, macOS, Linux, Android, iOS) permite escolher entre **tema claro ou escuro**. Com CSS dá para acompanhar isso automaticamente:

### 🌓 Detectar tema escuro

```css
@media (prefers-color-scheme: dark) {
  :root {
    --cor-primaria: #0ea5e9;
    --cor-fundo: #0f172a;
    --cor-texto: #e2e8f0;
  }
}
```

### ☀️ Detectar tema claro

```css
@media (prefers-color-scheme: light) {
  :root {
    --cor-primaria: #2563eb;
    --cor-fundo: #f1f5f9;
    --cor-texto: #0f172a;
  }
}
```

### ✔️ Como funciona?

O navegador verifica a preferência do sistema e aplica o bloco correspondente. Essas variáveis podem ser usadas em qualquer lugar do CSS.

### 🧪 Usando as variáveis depois

```css
body {
  background: var(--cor-fundo);
  color: var(--cor-texto);
}
```

---

## 3. CSS Modular — Separando responsabilidades

Projetos profissionais não deixam tudo em um único arquivo **style.css** gigante. É comum separar o CSS em módulos menores.

### 🔧 Benefícios do CSS modular

* Organização mais clara.
* Reutilização de estilos.
* Escalabilidade para projetos grandes.
* Manutenção muito mais fácil.

### 📁 Exemplo de estrutura

```
css/
├── base.css        → reset, variáveis, fontes, regras gerais
├── layout.css      → grids, containers, estrutura
├── components.css  → botões, cards, inputs etc.
├── utils.css       → classes utilitárias (margens, paddings...)
└── main.css        → arquivo que importa todos os outros
```

### 📥 main.css importando os módulos

```css
@import "base.css";
@import "layout.css";
@import "components.css";
@import "utils.css";
```

### 🧱 Exemplo de divisão real

#### base.css

```css
:root {
  --cor-primaria: #4f46e5;
  --cor-fundo: #ffffff;
  --cor-texto: #111827;
}

@media (prefers-color-scheme: dark) {
  :root {
    --cor-fundo: #0f172a;
    --cor-texto: #e2e8f0;
  }
}
```

#### components.css

```css
.btn {
  background: var(--cor-primaria);
  border-radius: 8px;
  padding: 10px 16px;
  color: #fff;
  cursor: pointer;
}
```

#### layout.css

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}
```

E no **main.css**, você só importa tudo.

---

## 4. Demonstração prática completa

Aqui vai um exemplo funcional juntando tudo:

### main.css

```css
@import "base.css";
@import "layout.css";
@import "components.css";
```

### index.html

```html
<link rel="stylesheet" href="css/main.css">

<div class="container">
  <button class="btn">Clique aqui</button>
</div>
```

---

## 5. Entendendo melhor o `@media`

O `@media` é uma regra do CSS que permite aplicar estilos **somente quando certas condições forem atendidas**. Ele é muito usado para:

* Adaptar o layout a diferentes larguras de tela (**responsividade**)
* Detectar preferências do usuário (tema escuro/claro, redução de movimento etc.)
* Aplicar regras específicas para impressão

### 📏 Exemplo de responsividade básica

```css
/* Estilos gerais */
.container {
  width: 90%;
  margin: 0 auto;
}

/* Para telas maiores que 768px */
@media (min-width: 768px) {
  .container {
    width: 70%;
  }
}

/* Para telas maiores que 1024px */
@media (min-width: 1024px) {
  .container {
    width: 50%;
  }
}
```

> [!NOTE]
> Assim, o layout *cresce* conforme a largura disponível, mantendo estética e legibilidade.

---

## 6. Exemplo completo: HTML + CSS + JS com troca de tema light/dark

Abaixo um exemplo funcional que combina tudo visto na aula.

### 📄 index.html

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="css/main.css">
  <title>Tema Dinâmico</title>
</head>
<body>
  <div class="container">
    <h1>Exemplo de Tema Dinâmico</h1>
    <button id="toggleTheme" class="btn">Alternar Tema</button>
  </div>

  <script src="script.js"></script>
</body>
</html>
```

### 🎨 main.css

```css
@import "base.css";
@import "layout.css";
@import "components.css";
```

### 🎨 base.css

```css
/* Tema padrão (light) */
:root {
  --cor-fundo: #ffffff;
  --cor-texto: #111827;
  --cor-primaria: #2563eb;
}

/* Tema escuro automático pelo sistema */
@media (prefers-color-scheme: dark) {
  :root {
    --cor-fundo: #0f172a;
    --cor-texto: #e2e8f0;
    --cor-primaria: #0ea5e9;
  }
}

.dark {
  --cor-fundo: #0f172a;
  --cor-texto: #e2e8f0;
  --cor-primaria: #0ea5e9;
}

.light {
  --cor-fundo: #ffffff;
  --cor-texto: #111827;
  --cor-primaria: #2563eb;
}
```

### 📐 layout.css

```css
body {
  background: var(--cor-fundo);
  color: var(--cor-texto);
  font-family: Arial, sans-serif;
  transition: background 0.3s, color 0.3s;
}

.container {
  max-width: 600px;
  margin: 40px auto;
  padding: 20px;
  text-align: center;
}

/* Responsividade simples */
@media (max-width: 480px) {
  .container {
    padding: 10px;
  }
}
```

### 🧩 components.css

```css
.btn {
  background: var(--cor-primaria);
  color: #fff;
  border: none;
  padding: 12px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
}
```

### ⚙️ script.js

```javascript
document.addEventListener("DOMContentLoaded", () => {
    // Espera o DOM carregar antes de tentar acessar elementos.
    // Isso garante que elementos como o botão e o <body> já existam.
    document.addEventListener("DOMContentLoaded", () => {
        // Pega o botão com id="toggleTheme" (deve existir no HTML).
        const btn = document.getElementById("toggleTheme");

        // Referência ao elemento <body> da página — vamos alternar classes nele.
        const body = document.body;

        // Usa a API Window.matchMedia para checar a preferência de tema do sistema.
        // 'prefers-color-scheme: dark' é um media query CSS (mas aqui estamos usando via JS).
        // .matches retorna true se o usuário prefere esquema escuro no sistema.
        const initialPrefersDark = window.matchMedia('prefers-color-scheme: dark').matches;

        // Adiciona a classe inicial ao body — "dark" se o sistema prefere escuro,
        // caso contrário "light".
        // Essas classes devem existir no seu CSS para aplicar as cores correspondentes.
        body.classList.add(initialPrefersDark ? "dark" : "light");

        // Adiciona um listener para o clique do botão que alterna entre os temas.
        btn.addEventListener("click", () => {
            // classList.toggle alterna a presença de uma classe:
            // - se "dark" existe, remove; se não existe, adiciona.
            // Fazemos toggle nas duas classes para garantir que apenas uma esteja presente.
            body.classList.toggle("dark");
            body.classList.toggle("light");
        });
    });
});
```

---

## 🎓 Conclusão

Nesta aula extra, você viu:

* Como usar `:root` para criar variáveis globais.
* Como personalizar automaticamente cores usando `@media prefers-color-scheme`.
* Como organizar o CSS de forma limpa e modular.

> [!TIP]
> Essa combinação é padrão profissional em praticamente qualquer projeto sério hoje.
