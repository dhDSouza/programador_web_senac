# 🧩 Aula 2 – Levantamento de Requisitos e Protótipos

## 🎯 Objetivos da Aula

- Compreender profundamente a diferença entre requisitos funcionais e não funcionais
- Aprender a transformar necessidades do usuário em histórias bem estruturadas
- Desenvolver habilidades para criar protótipos que facilitem o desenvolvimento
- Estabelecer uma base sólida para o planejamento do projeto

## 📝 O que São Requisitos?

**Requisitos são declarações precisas** que definem o que um sistema deve fazer e como deve se comportar. Eles funcionam como um **contrato** entre o cliente e a equipe de desenvolvimento.

### 🔍 Por que são importantes?

- Evitam retrabalho e misunderstandings
- Servem como guia para toda a equipe
- Permitem validar se o sistema atende às expectativas

## 👉 Tipos de Requisitos

### 🎯 Requisitos Funcionais (RF)

**Definição:** Descrevem **o que o sistema deve fazer** - as funcionalidades específicas.   

**Características:**   

- São ações que o sistema executa
- Podem ser testados individualmente
- Geralmente começam com "O sistema deve..."

**Exemplos práticos:**   

- "O sistema deve permitir cadastro de usuários com e-mail e senha"
- "O sistema deve enviar e-mail de confirmação após cadastro"
- "O usuário deve poder filtrar produtos por categoria"

### ⚡ Requisitos Não Funcionais (RNF)

**Definição:** Descrevem **como o sistema deve funcionar** - atributos de qualidade.   

**Características:**   

- Afetam a experiência do usuário como um todo
- São frequentemente negligenciados, mas críticos para o sucesso
- Podem ser técnicos ou de usabilidade

## 📊 Tabela de Exemplos de Requisitos

| Tipo | Categoria | Exemplo | Por que é importante? |
|:----:|:---------:|:-------:|:---------------------:|
| **RF** | Cadastro | "O sistema deve validar e-mail único" | Evita duplicação de contas |
| **RF** | Pagamento | "O usuário deve poder salvar cartões" | Facilita compras futuras |
| **RF** | Busca | "O sistema deve sugerir termos relacionados" | Melhora a descoberta |
| **RNF** | Performance | "Páginas devem carregar em < 3s" | Reduz taxa de abandono |
| **RNF** | Segurança | "Dados sensíveis devem ser criptografados" | Protege informações |
| **RNF** | Usabilidade | "Site deve ser acessível para daltonismo" | Inclusão digital |

## 🧑‍🤝‍🧑 Histórias de Usuário - Da Teoria à Prática

### 📝 Estrutura Completa:

```
Como [persona], 
quero [ação específica] 
para [benefício claro/objetivo]

Critérios de Aceitação:

- Dado [contexto], quando [ação], então [resultado]
- [Condição específica que deve ser atendida]
```

### 💡 Exemplos Avançados:

**Exemplo 1 - E-commerce:**   

```
Como cliente frequente,
quero criar listas de compras salvadas
para agilizar minhas compras recorrentes

Critérios de Aceitação:

- Dado que estou logado, quando adicionar itens à lista, então os itens devem ser salvos mesmo após logout
- A lista deve permitir adicionar/remover itens facilmente
- Deve ser possível compartilhar a lista por link
```

**Exemplo 2 - Rede Social:**   

```
Como usuário novo,
quero importar contatos do Gmail
para encontrar amigos rapidamente

Critérios de Aceitação:

- O sistema deve solicitar permissão explícita
- Deve mostrar preview antes de importar
- Deve permitir seleção seletiva de contatos
```

## ✏️ Protótipo / Wireframe - Além do Básico

### 🎨 Níveis de Fidelidade:

**Baixa Fidelidade (Lo-Fi):**   

- Sketch no papel ou ferramentas simples
- Foco no fluxo e disposição básica
- Rápido de iterar

**Alta Fidelidade (Hi-Fi):**   

- Detalhes visuais próximos do final
- Inclui cores, tipografia, imagens
- Útil para validação com stakeholders

### 🛠️ Ferramentas Recomendadas:   

- **Iniciantes:** Figma (free), Balsamiq
- **Profissionais:** Adobe XD, Sketch
- **Rápido:** Papel e caneta + foto do celular

### 📱 Exemplo de Wireframe Detalhado:

<div align="center">
    <img src="https://assets.justinmind.com/wp-content/uploads/2019/04/mobile-wireframe-example-tenant-management-app.png" alt="Wireframes de um sistema">
    <p>
        Fonte: <em><a href="https://assets.justinmind.com/wp-content/uploads/2019/04/mobile-wireframe-example-tenant-management-app.png
" target="_blank">https://assets.justinmind.com/wp-content/uploads/2019/04/mobile-wireframe-example-tenant-management-app.png
</a></em>
    </p>
</div>

## 💡 Estudo de Caso Aprofundado: Pizzaria Online

### 🎯 Requisitos Detalhados:

**Requisitos Funcionais:**   

1. **RF001:** Sistema deve permitir montagem visual da pizza com arrastar e soltar
2. **RF002:** Deve calcular preço em tempo real conforme personalização
3. **RF003:** Deve sugerir combinações populares baseadas em histórico

**Requisitos Não Funcionais:**   

1. **RNF001:** Tempo de carregamento máximo de 2s em conexão 4G
2. **RNF002:** Interface deve ser utilizável com uma só mão no mobile

### 📖 Histórias de Usuário Completas:

**História 1 - Personalização:**   

```
Como cliente indeciso,
quero ver sugestões de combinações de ingredientes
para descobrir novos sabores populares

Critérios de Aceitação:

- Sugestões devem ser baseadas em pizzas mais vendidas
- Deve mostrar preço da sugestão
- Um clique deve aplicar a sugestão ao pedido
```

**História 2 - Agilidade:**   

```
Como cliente com pressa,
quero refazer meu último pedido com um clique
para não perder tempo refazendo escolhas

Critérios de Aceitação:

- Botão deve estar visível na homepage para usuários logados
- Deve mostrar resumo do último pedido antes de confirmar
- Deve permitir edição rápida antes do checkout
```

## 📝 Exercício Prático da Aula

### 🎯 Para o negócio escolhido na Aula 1:

**Parte 1 - Requisitos**   

1. Liste 5 requisitos funcionais priorizados (use a tabela como guia)
2. Especifique 3 requisitos não funcionais críticos para seu projeto
3. Classifique cada RF com nível de complexidade (baixa/média/alta)

**Parte 2 - Histórias de Usuário**   

1. Escreva 3 histórias de usuário com critérios de aceitação completos
2. Identifique para cada história: persona envolvida e valor gerado

**Parte 3 - Prototipagem**   

1. Esboce o wireframe da página principal (papel ou digital)
2. Inclua anotações sobre interações importantes
3. Pense na jornada do usuário a partir dessa tela

### 💡 Dica Profissional:

"Comece sempre pelas necessidades do usuário final, não pelas funcionalidades técnicas. Pergunte 'por que' essa funcionalidade é importante antes de implementar."

### ✅ Checklist de Validação:

- [ ] Meus requisitos são específicos e testáveis?
- [ ] As histórias de usuário têm benefício claro?
- [ ] O protótipo comunica claramente a ideia?

### 🔄 Fluxo do Projeto:
```
Requisitos → Histórias → Protótipos → Desenvolvimento
```

> [!TIP]
> Documentação clara economiza horas de desenvolvimento!   
> Invista tempo no planejamento para evitar retrabalho.
