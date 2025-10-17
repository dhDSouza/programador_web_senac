# 🧑‍🏫 Aula 8 - **Formulários em HTML5**

### 🎯 **Objetivos de Aprendizagem**

* Compreender a função e estrutura de um formulário HTML.
* Utilizar corretamente os principais elementos de formulário (`<form>`, `<input>`, `<textarea>`, `<select>`, etc).
* Aplicar novos tipos de inputs do HTML5 (como `email`, `number`, `date`, `color`, etc).
* Usar atributos de validação e acessibilidade (`required`, `placeholder`, `pattern`, `aria-*`).
* Criar um formulário funcional e semântico para uma aplicação web.

---

### 🧩 **1. Introdução**

Formulários são a **principal forma de interação entre o usuário e a aplicação web**.
É através deles que o usuário envia dados — seja pra se cadastrar, logar, pesquisar, fazer upload de arquivos, etc.

O elemento base de um formulário é o `<form>`, e dentro dele ficam os campos (`<input>`, `<select>`, `<textarea>`, etc).

```html
<form action="/cadastro" method="post">
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome" required>

  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>

  <button type="submit">Enviar</button>
</form>
```

---

### ⚙️ **2. Estrutura de um Formulário**

| Elemento                | Função                                                          |
| ----------------------- | --------------------------------------------------------------- |
| `<form>`                | Define o início e o fim do formulário.                          |
| `action`                | Endereço (URL) para onde os dados serão enviados.               |
| `method`                | Define o método HTTP usado: `get` ou `post`.                    |
| `<label>`               | Rótulo descritivo de um campo (importante para acessibilidade). |
| `<input>`               | Campo de entrada de dados.                                      |
| `<textarea>`            | Campo de texto de múltiplas linhas.                             |
| `<select>` / `<option>` | Campo de seleção (lista suspensa).                              |
| `<button>`              | Botão para envio ou ação.                                       |

---

### 🧱 **3. Tipos de Input mais usados**

HTML5 trouxe vários tipos novos de campos que facilitam validação e melhoram a experiência do usuário.

| Tipo       | Descrição                    | Exemplo                                  |
| ---------- | ---------------------------- | ---------------------------------------- |
| `text`     | Texto simples                | `<input type="text">`                    |
| `email`    | Valida formato de e-mail     | `<input type="email">`                   |
| `password` | Oculta o texto digitado      | `<input type="password">`                |
| `number`   | Somente números              | `<input type="number" min="0" max="10">` |
| `date`     | Seleciona data               | `<input type="date">`                    |
| `color`    | Escolhe cor                  | `<input type="color">`                   |
| `file`     | Upload de arquivo            | `<input type="file">`                    |
| `checkbox` | Seleção múltipla             | `<input type="checkbox">`                |
| `radio`    | Seleção única entre opções   | `<input type="radio" name="sexo">`       |
| `range`    | Controle deslizante numérico | `<input type="range" min="0" max="100">` |

---

### 💬 **4. Validação e Atributos Úteis**

HTML5 inclui validações automáticas e atributos para controlar o comportamento dos campos.

| Atributo                | Função                                             |
| ----------------------- | -------------------------------------------------- |
| `required`              | Campo obrigatório                                  |
| `placeholder`           | Texto exibido dentro do campo                      |
| `pattern`               | Expressão regular para validar formato             |
| `min`, `max`, `step`    | Limites e intervalos numéricos                     |
| `maxlength`             | Número máximo de caracteres                        |
| `disabled` / `readonly` | Impede a edição do campo                           |
| `autofocus`             | Foca automaticamente no campo ao carregar a página |

---

### 🌐 **5. Envio de Dados**

* `method="get"` → Envia os dados na **URL** (usado para buscas ou consultas).
* `method="post"` → Envia os dados de forma **oculta no corpo da requisição** (usado para cadastros, login, etc).

Exemplo:

```html
<form action="/login" method="post">
  <input type="text" name="usuario" placeholder="Usuário">
  <input type="password" name="senha" placeholder="Senha">
  <button type="submit">Entrar</button>
</form>
```

---

### 🧠 **6. Atividade Prática**

Crie um formulário de **cadastro de usuário** contendo:

* Nome completo
* E-mail
* Senha
* Data de nascimento
* Gênero (radio)
* Interesses (checkbox)
* Campo de texto para “Sobre você”
* Botão “Enviar”

💡 *Desafio extra:* adicionar validações com `pattern`, `required`, `min`, `max`, e estilizar o formulário com CSS.
