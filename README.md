# 🚀 Apollo Cipher

Uma aplicação web simples, moderna e intuitiva para criptografar e descriptografar mensagens utilizando a clássica **Cifra de César** com uma chave de deslocamento fixa em **4**.

## 🎨 Funcionalidades e Características

- **Interface Dark Mode**: Design moderno e elegante com tons escuros, otimizado para conforto visual.
- **Criptografia e Descriptografia**: Suporte bidirecional para codificar e decodificar mensagens rapidamente.
- **Preservação de Caracteres**: O algoritmo diferencia letras maiúsculas de minúsculas e mantém intactos números, espaços e caracteres especiais/pontuação.
- **Zero Dependências**: Construído puramente com tecnologias nativas web (HTML5, CSS3 e JavaScript Vanilla), sem necessidade de frameworks ou bibliotecas externas.

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estruturação semântica da interface.
- **CSS3**: Estilização customizada, flexbox e transições suaves.
- **JavaScript**: Lógica matemática e manipulação do DOM para o cálculo da Cifra de César.

---

## ⚙️ Como Funciona o Algoritmo

A Cifra de César é uma técnica de substituição onde cada letra do texto é deslocada por um número fixo de posições no alfabeto. 

Neste projeto:
- **Chave (`shift`)**: `4`
- **Criptografar**: Move o caractere 4 posições à frente no alfabeto (ex: `A` → `E`, `B` → `F`).
- **Descriptografar**: Move o caractere 4 posições para trás (ex: `E` → `A`).

---

## 🚀 Como Executar o Projeto

1. Copie o código fonte da aplicação e salve-o em um arquivo com a extensão `.html` (por exemplo, `index.html`).
2. Dê um duplo clique no arquivo salvo para abri-lo em qualquer navegador web moderno (Google Chrome, Mozilla Firefox, Microsoft Edge, etc.).
3. Insira o texto desejado na caixa de texto e clique em **Criptografar** ou **Descriptografar**.

---

## 💻 Exemplo do Código JavaScript Principal

```javascript
const chave = 4;

function caesar(str, shift) {
  return str.split('').map(char => {
    const code = char.charCodeAt(0);
    // Maiúsculas A-Z
    if (code >= 65 && code <= 90) {
      return String.fromCharCode(((code - 65 + shift + 26) % 26) + 65);
    }
    // Minúsculas a-z
    if (code >= 97 && code <= 122) {
      return String.fromCharCode(((code - 97 + shift + 26) % 26) + 97);
    }
    // Outros caracteres ficam iguais
    return char;
  }).join('');
}
