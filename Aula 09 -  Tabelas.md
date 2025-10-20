# 🧾 Aula 9 - Uso de Tabelas em HTML5

## 📚 **O que é uma Tabela no HTML?**

Uma **tabela** serve para organizar informações em **linhas e colunas**, como se fosse uma planilha do Excel. Ela é muito útil para exibir dados de forma clara e organizada.

## 🏛️ **Estrutura Semântica de uma Tabela**

No HTML, temos várias tags específicas para construir tabelas de forma **semântica** e bem organizada. Vamos entender cada uma:

* `<table>` → Cria a tabela.
* `<tr>` → Table Row → Linha da tabela.
* `<td>` → Table Data → Célula de dado.
* `<th>` → Table Header → Cabeçalho (título das colunas ou linhas).
* `<thead>` → Cabeçalho da tabela.
* `<tbody>` → Corpo da tabela.
* `<tfoot>` → Rodapé da tabela (opcional).

---

## 🔧 **Exemplo de uma Tabela Simples (Semântica)**

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tabela Simples</title>
</head>
<body>

<h2>🏆 Ranking de Vendas</h2>

<table border="1" style="border-collapse: collapse;">
  <thead>
    <tr>
      <th style="background-color: lightgray;">Posição</th>
      <th style="background-color: lightgray;">Vendedor</th>
      <th style="background-color: lightgray;">Vendas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1º</td>
      <td>Maria</td>
      <td>150</td>
    </tr>
    <tr>
      <td>2º</td>
      <td>João</td>
      <td>120</td>
    </tr>
    <tr>
      <td>3º</td>
      <td>Pedro</td>
      <td>100</td>
    </tr>
  </tbody>
</table>

</body>
</html>
```

### ▶️ **O que está acontecendo aqui?**

* `<thead>` → Agrupa o cabeçalho da tabela.
* `<tbody>` → Agrupa os dados principais.
* `<tr>` → Cada linha da tabela.
* `<th>` → Cabeçalhos com destaque (por padrão ficam em negrito e centralizados).
* `<td>` → Dados normais.

---

## 🪄 **Adicionando um Rodapé na Tabela**

```html
<table border="1" style="border-collapse: collapse;">
  <thead>
    <tr>
      <th>Produto</th>
      <th>Quantidade</th>
      <th>Preço (R$)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Camisa</td>
      <td>10</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Calça</td>
      <td>5</td>
      <td>100</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2" style="text-align: right;">Total</td>
      <td>750</td>
    </tr>
  </tfoot>
</table>
```

### ▶️ **Detalhes importantes:**

* `<tfoot>` → Fica no final da tabela, geralmente para totais ou resumos.
* `colspan="2"` → Essa célula ocupa 2 colunas, para alinhar corretamente o texto “Total”.

---

## 🎨 **Customizando com CSS Inline**

Se quiser destacar alguma linha ou célula:

```html
<tr style="background-color: lightyellow;">
  <td>Produto Especial</td>
  <td>2</td>
  <td>500</td>
</tr>
```

* Aqui aplicamos uma cor de fundo apenas nessa linha.

---

## ⚙️ **Outros Atributos Úteis**

* `border="1"` → Adiciona borda (não recomendado para projetos profissionais, mas bom para testes rápidos).
* `style="border-collapse: collapse;"` → Junta as bordas das células, deixando visualmente melhor.

---

# 🧠 **Exercícios Práticos**

### 1️⃣ **Tabela de Filmes**

Crie uma tabela com pelo menos 4 filmes. Cada filme deve ter:

* Nome
* Ano de lançamento
* Gênero
* Nota (de 0 a 10)

Inclua cabeçalho (`<thead>`) e corpo (`<tbody>`).

---

### 2️⃣ **Tabela de Horários de Aulas**

Monte uma tabela que simule os horários de uma turma com:

* Dias da semana
* Matérias
* Horário de início e fim

Inclua também um rodapé (`<tfoot>`) indicando o total de horas da semana.

---

### 3️⃣ **Tabela de Lista de Compras**

Crie uma tabela com:

* Item
* Quantidade
* Preço unitário
* Preço total do item

No rodapé some todos os preços para mostrar o valor total da compra.

---

### 4️⃣ **Desafio Extra**

Monte uma tabela de classificação de um campeonato de algum esporte que você goste, com pelo menos:

* Time / Jogador
* Jogos
* Vitórias
* Derrotas
* Pontos

Capriche no uso do `<thead>`, `<tbody>` e `<tfoot>`.

---

## 🚀 **Conclusão**

Tabelas são muito úteis para dados organizados, relatórios, rankings e listas. Aprender a fazer uma tabela bem estruturada com HTML5 é essencial para qualquer desenvolvedor web!
