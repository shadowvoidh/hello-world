### 🌐 Estudos de Programação de HTML5 & CSS3

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)


Este repositório contém anotações, exemplos de código e boas práticas sobre **HTML5** e **CSS3**, organizados de forma modular para consulta rápida.

---

## 📑 Módulos de Estudo

<div align="center">
<details>
<summary><b><img src="../../../assets/logo/html.svg" height="50" width="50"> HTML5 </b></summary>

<br>

O HTML (HyperText Markup Language) é a linguagem de marcação responsável pela estrutura e conteúdo de uma página web.

### 1. Estrutura Básica de um Documento
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Página</title>
</head>
<body>
    <h1>Olá, Mundo!</h1>
</body>
</html>
```

### 2. Tags Semânticas Principais

A semântica melhora a acessibilidade e o SEO (otimização para motores de busca).

| Tag | Finalidade |
| :--- | :--- |
| `<header>` | Cabeçalho da página ou de uma seção |
| `<nav>` | Conjunto de links de navegação principal |
| `<main>` | Conteúdo principal e exclusivo do documento |
| `<section>` | Seção genérica de conteúdo agrupado por tema |
| `<article>` | Conteúdo independente e reutilizável (ex: post, notícia) |
| `<aside>` | Conteúdo lateral ou relacionado (sidebar) |
| `<footer>` | Rodapé com direitos, contatos e links úteis |
| `<img>` | Incorpora e exibe uma imagem na página |
| `<source>` | Define múltiplos recursos de mídia para `<picture>`, `<audio>` ou `<video>` |
| `<button>` | Cria um botão clicável para ações ou envio de formulários |
| `<label>` | Define um rótulo/legenda de texto para um elemento de formulário (como um `<input>`) |
| `<video>` | Incorpora e exibe um reprodutor de vídeo na página |
| `<center>` | Centraliza Horizontalmente todo o seu conteúdo da pagina |



### 3. Formulários e Acessibilidade
```HTML
<form action="/enviar" method="POST">
    <!-- O atributo 'for' do label deve corresponder ao 'id' do input -->
    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" placeholder="seuemail@exemplo.com" required>

    <label for="mensagem">Mensagem:</label>
    <textarea id="mensagem" name="mensagem" rows="4" required></textarea>

    <button type="submit">Enviar Formulário</button>
</form>
```
---

### 4. Mídia e Elementos Interativos
```HTML
<!-- Imagem com acessibilidade (alt obrigatório) -->
<img src="imagem.png" alt="Descrição detalhada da imagem para leitores de tela">

<!-- Vídeo Nativo -->
<video controls width="600">
    <source src="video.mp4" type="video/mp4">
    Seu navegador não suporta a tag de vídeo.
</video>
```



</details>

<details>
<summary><b><img src="../../../assets/logo/css3.svg" height="50" widht="50"> CSS3 </b></summary>

### O CSS (Cascading Style Sheets) é responsável pela apresentação visual, estilização, cores, tipografia e layout responsivo da página.

### 1. Seletores, Especificidade e Variáveis

```CSS
/* Declaração de Variáveis Globais */
:root {
    --cor-primaria: #2563eb;
    --cor-fundo: #f8fafc;
    --fonte-principal: 'Inter', sans-serif;
}

/* Estilização Geral */
body {
    background-color: var(--cor-fundo);
    font-family: var(--fonte-principal);
    margin: 0;
}

/* Seletores de Classe e Pseudo-classes */
.botao {
    background-color: var(--cor-primaria);
    color: white;
    padding: 10px 20px;
    border-radius: 6px;
    transition: background-color 0.3s ease;
}

.botao:hover {
    background-color: #1d4ed8;
}
```

### 2. Box Model (Modelo de Caixa)
Tudo no CSS é uma caixa composta por Conteúdo, Padding (espaçamento interno), Border (borda) e Margin (espaçamento externo).

```CSS
* {
    /* Garante que padding e border não aumentem a largura total do elemento */
    box-sizing: border-box;
}

.caixa {
    width: 300px;
    padding: 20px;
    border: 2px solid #333;
    margin: 15px auto; /* Centraliza horizontalmente */
}
```


### 3. Layouts Modernos: Flexbox & CSS Grid
Flexbox (1D - Alinhamento em Linha ou Coluna)
```CSS
.container-flex {
    display: flex;
    justify-content: space-between; /* Alinhamento no eixo principal */
    align-items: center;            /* Alinhamento no eixo transversal */
    gap: 16px;                     /* Espaçamento entre os itens */
}
```
CSS Grid (2D - Linhas e Colunas)
```CSS
.container-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```


### 4. Responsividade e Media Queries
Adapta o layout para diferentes tamanhos de tela (Mobile-First).

```CSS
/* Estilo base para dispositivos móveis */
.menu {
    display: block;
}

/* Regra para telas maiores (Desktops / Laptops) */
@media (min-width: 768px) {
    .menu {
        display: flex;
        justify-content: flex-end;
    }
}
```


### Tags CSS
## 1. Mídia e Recursos (`<img>`, `<video>`, `<source>`)

| Propriedade | Finalidade | Exemplo |
| :--- | :--- | :--- |
| `object-fit` | Define como o conteúdo de uma imagem ou vídeo se ajusta ao seu container | `object-fit: cover;` |
| `object-position` | Ajusta o alinhamento do conteúdo recortado dentro do container | `object-position: center top;` |
| `aspect-ratio` | Define uma proporção de aspecto preferencial (ex: 16/9, 1/1) | `aspect-ratio: 16 / 9;` |
| `max-width` | Garante que o elemento não ultrapasse certo limite (torna imagens responsivas) | `max-width: 100%;` |
| `height` | Define a altura do elemento | `height: auto;` |

---

## 2. Formulários e Botões (`<button>`, `<label>`)

| Propriedade | Finalidade | Exemplo |
| :--- | :--- | :--- |
| `cursor` | Altera o tipo de ponteiro do mouse ao passar por cima | `cursor: pointer;` |
| `outline` | Controla a borda de foco (muito usado em acessibilidade ao focar botões/inputs) | `outline: 2px solid blue;` |
| `user-select` | Define se o texto do elemento pode ser selecionado pelo usuário | `user-select: none;` |
| `appearance` | Altera o estilo nativo do sistema operacional para botões/inputs | `appearance: none;` |
| `pointer-events` | Define se o elemento responde a eventos do mouse/clique | `pointer-events: none;` |

---

## 3. Layout e Estrutura Semântica (`<header>`, `<main>`, `<section>`, etc.)

| Propriedade | Finalidade | Exemplo |
| :--- | :--- | :--- |
| `display` | Define o tipo de renderização do elemento (ex: `flex`, `grid`, `block`, `inline-block`) | `display: flex;` |
| `flex-direction` | Define a direção dos itens em um container Flexbox | `flex-direction: column;` |
| `justify-content` | Alinha os itens ao longo do eixo principal (horizontal por padrão) | `justify-content: space-between;` |
| `align-items` | Alinha os itens ao longo do eixo transversal (vertical por padrão) | `align-items: center;` |
| `grid-template-columns` | Define a estrutura de colunas em um layout CSS Grid | `grid-template-columns: repeat(3, 1fr);` |
| `gap` | Define o espaçamento entre elementos em um container Flexbox ou Grid | `gap: 16px;` |

---

## 4. Estilização Geral, Cores e Espaçamento

| Propriedade | Finalidade | Exemplo |
| :--- | :--- | :--- |
| `margin` | Define o espaçamento externo ao redor do elemento | `margin: 20px auto;` |
| `padding` | Define o espaçamento interno entre a borda e o conteúdo | `padding: 12px 24px;` |
| `background-color` | Define a cor de fundo do elemento | `background-color: #0d1117;` |
| `color` | Define a cor do texto | `color: #ffffff;` |
| `border-radius` | Arredonda os cantos da borda do elemento | `border-radius: 8px;` |
| `box-shadow` | Adiciona efeitos de sombra ao redor do elemento | `box-shadow: 0 4px 6px rgba(0,0,0,0.1);` |

</details>

</div>
