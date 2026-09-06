# 🌐 Guia de Estudos: HTML5 & CSS3

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)


Este repositório contém anotações, exemplos de código e boas práticas sobre **HTML5** e **CSS3**, organizados de forma modular para consulta rápida.

---

## 📑 Módulos de Estudo


<details>
<summary><b><img src="../../img/HTML.webp" height="25" widht="25"> HTML5 </b></summary>

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