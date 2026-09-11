<div align="center">
<img src="../../../assets/logo/js.svg" height="50" width="50">
</div>

### 🏵 Estudos de Programação de JavaScript (ES6+)

O **JavaScript** é a linguagem de programação de alto nível, dinamicamente tipada e multiparadigma que executa no navegador e em ambientes de servidor (Node.js).

---

## 1. Variáveis e Escopo

| Palavra-chave | Escopo | Reatribuível? | Redeclarável? |
| :--- | :--- | :--- | :--- |
| `let` | Bloco (`{}`) | Sim | Não |
| `const` | Bloco (`{}`) | Não | Não |
| `var` *(obsoleto)* | Função/Global | Sim | Sim |

```javascript
const NOME_DO_APP = "MeuProjeto"; // Constante (não altera o valor)
let contador = 0;                  // Permite reatribuição

if (true) {
  let escopoFechado = "Visível apenas neste bloco";
}
```

---

## 2. Tipos de Dados

### 2.1 Tipos Primitivos
* **String:** `"Texto"` ou `'Texto'` ou `` `Interpolação` ``
* **Number:** `42`, `3.14`
* **Boolean:** `true` ou `false`
* **Null:** Ausência intencional de valor (`null`)
* **Undefined:** Variável declarada mas sem valor inicial (`undefined`)
* **Symbol / BigInt:** Identificadores únicos e números inteiros de alta precisão

### 2.2 Objetos e Arrays
```javascript
// Array (Lista de elementos)
const frutas = ["Maçã", "Banana", "Laranja"];

// Objeto (Par de Chave/Valor)
const usuario = {
  nome: "Lucas",
  idade: 25,
  ativo: true
};
```

---

## 3. Funções e Arrow Functions

### 3.1 Função Tradicional vs Arrow Function
```javascript
// Função Tradicional
function somar(a, b) {
  return a + b;
}

// Arrow Function (Sintaxe enxuta)
const subtrair = (a, b) => a - b;

// Arrow Function com um parâmetro (sem parênteses necessários)
const dobrar = n => n * 2;
```

---

## 4. Métodos Principais de Arrays (Iteração e Transformação)

| Método | Finalidade | Retorno |
| :--- | :--- | :--- |
| `.map()` | Transforma cada elemento e gera um novo array | Novo Array |
| `.filter()` | Filtra elementos com base em uma condição | Novo Array filtrado |
| `.find()` | Busca o **primeiro** elemento que atende à condição | O elemento ou `undefined` |
| `.forEach()` | Executa uma função para cada elemento | Nenhum (`undefined`) |
| `.reduce()` | Reduz o array a um único valor acumulado | Um único valor |

```javascript
const numeros = [1, 2, 3, 4, 5];

// Map
const dobrados = numeros.map(n => n * 2); // [2, 4, 6, 8, 10]

// Filter
const pares = numeros.filter(n => n % 2 === 0); // [2, 4]

// Find
const busca = numeros.find(n => n > 3); // 4
```

---

## 5. Desestruturação e Operator Spread/Rest

```javascript
// 5.1 Desestruturação de Objetos
const { nome, idade } = usuario;

// 5.2 Desestruturação de Arrays
const [primeiraFruta, segundaFruta] = frutas;

// 5.3 Operator Spread (...) - Clonar ou juntar
const novosNumeros = [...numeros, 6, 7];
const usuarioAtualizado = { ...usuario, cidade: "São Paulo" };
```

---

## 6. Manipulação de DOM (Navegador)

```javascript
// Seleção de Elementos
const botao = document.querySelector("#meuBotao");
const lista = document.querySelectorAll(".item-lista");

// Event Listener (Ouvinte de Eventos)
botao.addEventListener("click", (event) => {
  console.log("Botão clicado!");
  document.body.classList.toggle("dark-mode");
});
```

---

## 7. Assincronismo (`Promises` e `Async/Await`)

### 7.1 Consumindo APIs com `fetch` e `async/await`
```javascript
async function buscarDados() {
  try {
    const resposta = await fetch("https://api.exemplo.com/dados");
    
    if (!resposta.ok) throw new Error("Erro na requisição");
    
    const dados = await resposta.json();
    console.log(dados);
  } catch (erro) {
    console.error("Falha ao buscar dados:", erro);
  }
}

buscarDados();
```

---

## 8. Módulos (`ES Modules`)

```javascript
// exportar.js
export const API_URL = "https://api.exemplo.com";
export function autenticar() { /* ... */ }

// importar.js
import { API_URL, autenticar } from "./exportar.js";
```
