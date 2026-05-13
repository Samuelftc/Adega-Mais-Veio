<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Poppins&color=FF982D&size=24&center=true&vCenter=true&width=600&lines=Adega+Mais+Véio;Bar+%26+Restaurante;Cardápio+Digital+Interativo;Sistema+de+Agendamento+de+Narguilé" />
</p>

---

# Adega Mais Véio — Site Institucional e Cardápio Digital

Site completo de um bar e restaurante fictício desenvolvido como projeto pessoal para testar e consolidar habilidades em desenvolvimento web front-end. O projeto conta com múltiplas páginas, carrinho de compras persistente, sistema de agendamento de narguilé e filtros de cardápio dinâmicos.

---

> **Aviso**
>
> Este é um **projeto pessoal em andamento**, desenvolvido intencionalmente de forma incremental para testar conhecimentos.
> O código pode conter seções incompletas, comentários de desenvolvimento e implementações que ainda serão refinadas.
> O projeto está disponível publicamente pois representa de forma honesta a evolução prática no desenvolvimento web.

---

## Deploy

Acesse o site em produção: [https://adega-mais-veio.netlify.app](https://adega-mais-veio.netlify.app)

## Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Páginas](#páginas)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Estrutura de Arquivos](#estrutura-de-arquivos)
- [Como Executar](#como-executar)
- [Detalhamento Técnico](#detalhamento-técnico)
- [Aprendizados](#aprendizados)
- [Autor](#autor)

---

## Sobre o Projeto

A Adega Mais Véio é um projeto pessoal que simula o site completo de um bar e restaurante localizado em São Paulo. A proposta foi construir algo além de exercícios simples — um sistema com múltiplas páginas interligadas, carrinho de compras funcional com persistência de dados, catálogo de produtos gerado dinamicamente e um sistema de agendamento de narguilé com formulário modal.

O projeto foi desenvolvido inteiramente com HTML, CSS e JavaScript puros, sem frameworks, com foco em praticar manipulação avançada do DOM, gerenciamento de estado com `localStorage`, e organização de código em múltiplos arquivos com responsabilidades separadas.

---

## Páginas

| Página | Arquivo | Descrição |
|---|---|---|
| Início | `index.html` | Hero, destaques do cardápio, seção de espaço, aluguel de narguilé e contato rápido |
| Cardápio | `cardapio.html` | Catálogo completo com filtros por categoria (Tudo, Bebidas, Comidas, Combos) |
| Espaço | `espaco.html` | Galeria do ambiente, cards de diferenciais, horários e reserva |
| Narguilé | `narguile.html` | Acessórios com filtros por categoria e seção de aluguel com agendamento |
| Sobre Nós | `sobreNos.html` | História, timeline, valores, equipe e missão/visão |
| Contato | `contato.html` | Formulário de contato, informações, mapa, FAQ com animação e redes sociais |

---

## Funcionalidades

- Navegação entre 6 páginas com header e footer reutilizados
- Cardápio gerado dinamicamente via JavaScript a partir de array de objetos
- Filtros de categoria com botão ativo destacado (Bebidas, Comidas, Combos)
- Carrinho de compras lateral com controle de quantidade por item (+ e -)
- Carrinho persistente entre páginas e recarregamentos via `localStorage`
- Contador de itens no ícone do carrinho atualizado em tempo real
- Toast notifications para adição e remoção de itens do carrinho
- Catálogo de acessórios de narguilé com filtros (Essências, Carvões, Diversos, Combos)
- Sistema de aluguel de narguilé com formulário de agendamento em modal/overlay
- Confirmação visual de agendamento realizado
- FAQ interativo com animação de abrir e fechar via `<details>` nativo
- Linha decorativa animada no hover dos links do header
- Seção de timeline na página Sobre Nós
- Layout responsivo com scroll suave entre seções

---

## Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura semântica das 6 páginas |
| CSS3 | Estilização completa, animações, variáveis CSS e responsividade |
| JavaScript (ES6) | Manipulação do DOM, eventos, arrays, objetos e `localStorage` |
| Font Awesome 6 | Ícones da interface (header, contato, cards, redes sociais) |
| Google Fonts | Famílias tipográficas Poppins e Raleway |

---

## Estrutura de Arquivos

```
adega-mais-veio/
│
├── index.html
├── cardapio.html
├── espaco.html
├── narguile.html
├── sobreNos.html
├── contato.html
│
└── assets/
    ├── css/
    │   └── style.css
    │
    └── js/
        ├── produtos.js
        ├── carrinho.js
        ├── cardapio.js
        ├── narguile.js
        └── agendamentos.js
```

### Responsabilidade de cada arquivo

| Arquivo | Responsabilidade |
|---|---|
| `produtos.js` | Arrays de dados: `produtos` (cardápio), `narguileAcessorios` e `narguilesAluguel` |
| `carrinho.js` | Abrir/fechar carrinho, renderizar itens, controlar quantidade, calcular total e persistir no `localStorage` |
| `cardapio.js` | Renderizar cardápio, filtrar por categoria e destacar botão ativo |
| `narguile.js` | Renderizar acessórios com filtros, exibir narguilés para aluguel e gerenciar formulário de agendamento |
| `agendamentos.js` | Abrir/fechar painel de agendamentos e armazenar dados de agendamentos realizados |
| `style.css` | Todo o CSS do projeto: layout, componentes, animações e responsividade |

---

## Como Executar

Não há dependências de instalação. O projeto roda diretamente no navegador.

**1. Clone o repositório**
```bash
git clone https://github.com/Samuelftc/Adega-Mais-Veio.git
```

**2. Acesse a pasta do projeto**
```bash
cd Adega-Mais-Veio
```

**3. Abra no navegador**

Abra o arquivo `index.html` diretamente no navegador, ou use a extensão **Live Server** no VS Code para melhor experiência de desenvolvimento.

> As imagens do projeto são carregadas via URLs externas (Unsplash, Google, etc.), portanto é necessário conexão com a internet para visualizá-las corretamente.

---

## Detalhamento Técnico

### Carrinho com localStorage

O carrinho persiste os dados entre páginas e recarregamentos. Ao adicionar ou remover um item, o array `produtosCarrinho` é salvo no `localStorage` como JSON. Ao carregar qualquer página, o carrinho é recuperado e renderizado automaticamente.

```javascript
// Salvar
localStorage.setItem('carrinho', JSON.stringify(produtosCarrinho))

// Recuperar
let produtosCarrinho = JSON.parse(localStorage.getItem('carrinho')) || []
```

### Geração dinâmica do cardápio

Os produtos não estão escritos no HTML. Eles ficam em `produtos.js` como array de objetos e são renderizados via JavaScript com `createElement`, garantindo que adicionar novos produtos ao cardápio seja simples.

### Filtro de categorias

Cada produto tem uma propriedade `categoria`. Ao clicar em um filtro, o array é filtrado com `.filter()` e o cardápio é re-renderizado mostrando apenas os itens da categoria selecionada.

### Sistema de agendamento de narguilé

Ao clicar em "Agendar" em um narguilé, um overlay com formulário é criado dinamicamente no DOM. Ao confirmar, os dados do formulário são capturados com `FormData` e armazenados em array. Uma tela de confirmação é exibida antes de fechar o modal.

### Toast notifications

Ao adicionar ou remover itens do carrinho, um elemento `div` é criado, inserido no `body` e removido após 3 segundos com `setTimeout`, simulando notificações em tempo real.

### FAQ animado

A página de contato usa o elemento `<details>` nativo do HTML5. JavaScript foi adicionado para animar a abertura e fechamento com transição de altura, e o ícone de seta rotaciona via CSS ao expandir.

---

## Aprendizados

Este projeto consolidou e expandiu os seguintes conceitos:

- **Múltiplas páginas interligadas** com header, footer e carrinho reutilizados em cada uma
- **`localStorage`** para persistência de estado do carrinho entre páginas e sessões
- **Geração dinâmica de listas completas** com `createElement` e `appendChild` em escala real
- **Filtros com `.filter()`** para exibição condicional de produtos por categoria
- **Spread operator (`...`)** para clonar objetos ao adicionar ao carrinho
- **`FormData` e `Object.fromEntries()`** para captura de dados de formulário
- **Overlay/modal criado dinamicamente** sem HTML estático, só com JavaScript
- **Toast notifications** com criação e remoção de elementos via `setTimeout`
- **Variáveis CSS (`:root`)** para centralizar a paleta de cores do projeto
- **Animações CSS** com `@keyframes`, `transition` e `transform` em vários componentes
- **Pseudo-elementos (`::after`)** para criar linhas decorativas animadas no menu
- **`<details>` e `<summary>`** nativos do HTML5 com animação customizada via JavaScript
- **Organização de dados em arrays de objetos** separados da lógica de renderização

---

## Autor

Desenvolvido por **Samuel Ferreira**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Samuelftc)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:samuelferreiradev08@gmail.com)

---

> Projeto pessoal desenvolvido para prática avançada de desenvolvimento web front-end.
