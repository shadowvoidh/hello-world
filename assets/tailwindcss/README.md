<div align="center">
<img src="../../img/Tailwind.webp" height="50" widht="50">
</div>

### Tailwind CSS

![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

Este repositório contém anotações, exemplos de componentes e padrões práticos sobre **Tailwind CSS**, o framework CSS utilitário (*Utility-First*).

---

## 📑 Módulos de Estudo

<details>
<summary><b>⚙️ Módulo 1: Instalação e Configuração</b></summary>

<br>

O Tailwind CSS pode ser integrado via CLI, Vite, Frameworks (Next.js, React, Vue) ou CDN (apenas para testes).

### 1.1 Instalação via Tailwind CLI
```bash
# 1. Instalar pacotes de desenvolvimento
npm install -D tailwindcss postcss autoprefixer

# 2. Gerar o arquivo de configuração (tailwind.config.js)
npx tailwindcss init -p


# Classes Tailwind CSS Principais

O Tailwind CSS é um framework utilitário que permite estilizar elementos HTML aplicando classes prontas diretamente nas tags.
```
---
## 2. Configurar o tailwind.config.js
Mapeie os caminhos de todos os seus arquivos que utilizarão as classes do Tailwind:

```JavaScript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js,jsx,ts,tsx}"],
  theme: {
    extend: {
      colors: {
        brand: '#3b82f6', // Cor personalizada
      },
    },
  },
  plugins: [],
}
```
### 3. Adicionar as Diretivas ao CSS Principal
No arquivo de estilo principal (ex: src/input.css):

```CSS
@tailwind base;
@tailwind components;
@tailwind utilities;
```
</details>

<details>
<summary><b>🌊 Módulo 2: Customização CSS </b></summary>


## 2.1 Espaçamento e Dimensões

| Categoria | Sintaxe / Classes | Descrição |
| :--- | :--- | :--- |
| **Padding** | `p-4` (16px), `px-2` (horizontal), `py-6` (vertical), `pt-2` (topo) | Define o espaçamento interno do elemento |
| **Margin** | `m-auto`, `mx-4`, `-mt-2` (margem negativa) | Define o espaçamento externo do elemento |
| **Largura e Altura** | `w-full` (100%), `w-screen` (100vw), `w-64` (256px), `h-12` (48px), `max-w-md` | Controla dimensões e limites de largura e altura |

---

## 2.2 Cores e Opacidade

### Exemplo: Fundo, texto e borda com opacidade
```html
<div class="bg-slate-900 text-white border border-slate-700/50 p-6 rounded-xl">
    <h2 class="text-emerald-400 font-bold text-xl">Card Ativo</h2>
    <p class="text-slate-400 text-sm mt-2">Exemplo de combinação de cores e opacidades.</p>
</div>
```

---

## 3. Layout e Posicionamento

### 3.1 Flexbox
```html
<div class="flex items-center justify-between gap-4 p-4 bg-gray-100 rounded-lg">
    <span class="font-medium">Item 1</span>
    <span class="font-medium">Item 2</span>
    <button class="bg-blue-600 text-white px-4 py-2 rounded-md">Ação</button>
</div>
```

### 3.2 CSS Grid
```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    <div class="bg-white p-4 shadow-md rounded-lg">Coluna 1</div>
    <div class="bg-white p-4 shadow-md rounded-lg">Coluna 2</div>
    <div class="bg-white p-4 shadow-md rounded-lg">Coluna 3</div>
</div>
```

### 3.3 Posicionamento

| Categoria | Classes Utilitárias | Descrição |
| :--- | :--- | :--- |
| **Posição** | `relative`, `absolute`, `fixed`, `sticky` | Controla o tipo de posicionamento CSS |
| **Deslocamento** | `top-0`, `right-4`, `inset-0` | Define coordenadas (`inset-0` = top/right/bottom/left zero) |
| **Camadas (z-index)** | `z-10`, `z-50` | Define a ordem de sobreposição no eixo Z |

---

## 4. Recursos Avançados e Modificadores

### 4.1 Modificadores de Estado (Hover, Focus, Group)

#### Hover e Transições
```html
<button class="bg-indigo-600 hover:bg-indigo-700 transition-colors duration-200 text-white font-medium px-4 py-2 rounded-lg">
    Clique Aqui
</button>
```

#### Group Hover (Efeito no filho ao passar o mouse no pai)
```html
<div class="group p-4 bg-white border rounded-lg hover:border-indigo-500 cursor-pointer">
    <h3 class="group-hover:text-indigo-600 transition-colors font-bold">Título do Card</h3>
    <p class="text-gray-500">Passe o mouse no card para alterar a cor do título.</p>
</div>
```

---

### 4.2 Breakpoints Responsivos (Mobile-First)

O Tailwind aplica o estilo padrão para telas menores e requer prefixos para telas maiores:

* `sm:` (≥ 640px)
* `md:` (≥ 768px)
* `lg:` (≥ 1024px)
* `xl:` (≥ 1280px)

```html
<!-- Em mobile: 1 coluna | Tablet (md): 2 colunas | Desktop (lg): 4 colunas -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
    <!-- Conteúdo -->
</div>
```

---

### 4.3 Dark Mode

> **Nota:** Ativado com o prefixo `dark:` quando a classe `dark` estiver configurada no elemento `<html>` ou `<body>`.

```html
<div class="bg-white dark:bg-zinc-900 text-zinc-900 dark:text-zinc-100 p-6">
    <p>Este bloco se adapta automaticamente ao Modo Escuro!</p>
</div>
```

---

## 5. Customização e Abstração

### 5.1 Valores Arbitrários (JIT Compiler)
Utilize colchetes `[...]` quando precisar de uma medida ou cor exata fora do tema padrão:

```html
<div class="w-[347px] h-[calc(100vh-80px)] bg-[#1a1a1a] top-[12px]">
    Valores exatos personalizados
</div>
```

### 5.2 Abstração com `@apply`
Útil para evitar duplicação em elementos altamente reutilizados:

```css
@layer components {
  .btn-primary {
    @apply bg-blue-600 hover:bg-blue-700 text-white font-semibold px-4 py-2 rounded-lg transition-all duration-200 shadow-sm;
  }
}
```
</details>







<details>
<summary><b>🔥 Módulo 3: Tags do Tailwind</b></summary>



## 1. Mídia e Recursos (`<img>`, `<video>`, `<source>`)

| Propriedade CSS equivalente | Classe Tailwind | Finalidade | Exemplo de Uso |
| :--- | :--- | :--- | :--- |
| `object-fit: cover;` | `object-cover` | Ajusta o conteúdo da mídia para preencher o container sem distorcer | `<img class="object-cover h-48 w-full">` |
| `object-position: center;` | `object-center` | Centraliza o alinhamento do conteúdo recortado | `<img class="object-center">` |
| `aspect-ratio: 16 / 9;` | `aspect-video` | Define a proporção de tela de vídeo padrão (16/9) | `<video class="aspect-video w-full">` |
| `max-width: 100%;` | `max-w-full` | Impede que a imagem ultrapasse o tamanho do pai (responsividade) | `<img class="max-w-full h-auto">` |
| `height: auto;` | `h-auto` | Ajusta a altura automaticamente proporcional à largura | `<img class="w-32 h-auto">` |

---

## 2. Formulários e Botões (`<button>`, `<label>`)

| Propriedade CSS equivalente | Classe Tailwind | Finalidade | Exemplo de Uso |
| :--- | :--- | :--- | :--- |
| `cursor: pointer;` | `cursor-pointer` | Altera o cursor para a mãozinha de clique | `<button class="cursor-pointer">` |
| `outline: none;` / `focus:...` | `focus:outline-none` / `focus:ring-2` | Controla e estiliza o anel de foco ao clicar ou navegar via teclado | `<button class="focus:ring-2 focus:ring-blue-500">` |
| `user-select: none;` | `select-none` | Impede a seleção acidental de texto | `<label class="select-none">` |
| `appearance: none;` | `appearance-none` | Remove os estilos nativos do sistema operacional em campos | `<input class="appearance-none">` |
| `pointer-events: none;` | `pointer-events-none` | Desativa cliques e interações do mouse sobre o elemento | `<div class="pointer-events-none">` |

---

## 3. Layout e Estrutura Semântica (`<header>`, `<main>`, `<section>`, etc.)

| Propriedade CSS equivalente | Classe Tailwind | Finalidade | Exemplo de Uso |
| :--- | :--- | :--- | :--- |
| `display: flex;` | `flex` | Transforma o container em um layout Flexbox | `<header class="flex">` |
| `flex-direction: column;` | `flex-col` | Organiza os itens em coluna (vertical) | `<main class="flex flex-col">` |
| `justify-content: space-between;` | `justify-between` | Distribui os itens com espaço igual entre eles | `<nav class="flex justify-between">` |
| `align-items: center;` | `items-center` | Alinha os itens verticalmente ao centro | `<div class="flex items-center">` |
| `grid-template-columns: repeat(3, 1fr);` | `grid-cols-3` | Cria um layout de Grid com 3 colunas de tamanhos iguais | `<section class="grid grid-cols-3">` |
| `gap: 16px;` | `gap-4` | Espaçamento de 16px (1rem) entre itens Flex ou Grid | `<div class="flex gap-4">` |

---

## 4. Estilização Geral, Cores e Espaçamento

| Propriedade CSS equivalente | Classe Tailwind | Finalidade | Exemplo de Uso |
| :--- | :--- | :--- | :--- |
| `margin: 16px;` | `m-4` / `mx-auto` | Define margem externa (ou centraliza na horizontal com `mx-auto`) | `<div class="mx-auto max-w-sm">` |
| `padding: 12px 24px;` | `px-6 py-3` | Define o espaçamento interno (horizontal de 24px e vertical de 12px) | `<button class="px-6 py-3">` |
| `background-color: #0d1117;` | `bg-slate-900` | Define a cor de fundo usando a paleta do Tailwind | `<footer class="bg-slate-900">` |
| `color: #ffffff;` | `text-white` | Define a cor do texto para branco | `<p class="text-white">` |
| `border-radius: 8px;` | `rounded-lg` | Arredonda os cantos do elemento (8px por padrão) | `<div class="rounded-lg">` |
| `box-shadow: ...` | `shadow-md` | Adiciona sombra suave ao redor do elemento | `<article class="shadow-md">` |

</details>