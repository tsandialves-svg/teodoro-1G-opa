# Exercícios - Introdução ao JavaScript (Etapas 0 a 4)

## Etapa 0 - Preparando o ambiente

### Checkpoint
1. **Em qual aba das ferramentas do desenvolvedor a mensagem apareceu?**
   Na aba **Console**.

2. **O atributo `defer` faz o navegador esperar o HTML ser lido antes de executar o script. Por que isso será importante mais adiante, quando o script precisar mexer em elementos da página?**
   Porque garante que todos os elementos HTML já estejam carregados e disponíveis na página antes que o JavaScript tente acessá-los ou modificá-los, evitando erros de elemento não encontrado.

3. **Se você escrevesse `<script src="codigo.js" defer>` no HTML, mas o arquivo se chamasse `script.js`, o que aconteceria?**
   O navegador não encontraria o arquivo `codigo.js`, exibiria um erro de arquivo não encontrado no Console e o código JavaScript não seria executado.

---

## Etapa 1 - O que é JavaScript

### Tabela - Experimente
| Expressão | Resultado observado |
| :--- | :--- |
| `2 + 3` | `5` |
| `"Web" + " I"` | `"Web I"` |
| `"5" + 3` | `"53"` |
| `"5" - 3` | `2` |
| `2 + 3 * 4` | `14` |
| `(2 + 3) * 4` | `20` |

### Checkpoint
1. **Por que `"5" + 3` e `"5" - 3` dão resultados tão diferentes?**
   O operador `+` realiza concatenação quando um dos valores é texto (`string`), juntando `"5"` e `3` em `"53"`. Já o operador `-` é exclusivo para subtração matemática, forçando o JavaScript a converter o texto `"5"` no número `5` antes de calcular `5 - 3 = 2`.

2. **Por que `2 + 3 * 4` e `(2 + 3) * 4` dão resultados diferentes?**
   Pela ordem de precedência matemática: na primeira expressão a multiplicação é feita antes da soma (`2 + 12 = 14`), enquanto na segunda os parênteses priorizam a soma (`5 * 4 = 20`).

---

## Etapa 2 - Variáveis e tipos

### Checkpoint
1. **Antes de executar, escreva o que as quatro linhas com `typeof` vão imprimir:**
   * `string`
   * `number`
   * `boolean`
   * `undefined`

2. **Qual erro apareceu no console na última linha? Por que ele ocorre?**
   Aparece o erro `TypeError: Assignment to constant variable.` porque a variável `escola` foi criada com `const`, o que impede a alteração do seu valor após a declaração.

3. **Quais destes nomes de variável são válidos? Marque e justifique os inválidos.**
   * `nota_final`: **Válido** (permite letras e sublinhado).
   * `3nota`: **Inválido** (não pode começar com número).
   * `nota-final`: **Inválido** (hífen não é permitido em nomes de variáveis).
   * `$total`: **Válido** (o símbolo `$` é permitido).
   * `class`: **Inválido** (`class` é uma palavra reservada do JavaScript).

4. **Observe o código abaixo e diga o que será impresso. Depois confira no console.**
   Será impresso **`16`**.

---

## Etapa 3 - Operadores, conversão e texto com variáveis

### Checkpoint
1. **Escreva a saída prevista de cada `console.log` (são 8 linhas de saída):**
   * `9 5 14`
   * `3.5`
   * `1`
   * `49`
   * `Olá, Ana! 7 dividido por 2 é 3.5.`
   * `8.5`
   * `"7.51"`
   * `NaN`

2. **Qual é a diferença entre `Number("7.5") + 1` e `"7.5" + 1`? O que isso significa para quem lê um número digitado em um campo de formulário?**
   `Number("7.5") + 1` converte o texto para número e realiza a soma matemática (`8.5`), enquanto `"7.5" + 1` concatena os valores como texto (`"7.51"`). Como valores vindos de formulários chegam como texto (`string`), é indispensável convertê-los com `Number()` antes de realizar cálculos.

3. **Sem executar, calcule: `10 % 3`, `2 ** 3` e `10 / 4`.**
   * `10 % 3` = **`1`**
   * `2 ** 3` = **`8`**
   * `10 / 4` = **`2.5`**

---

## Etapa 4 - Condicionais

### Checkpoint
1. **Com `temperatura = 20`, qual mensagem aparece? E com `30`? Por quê?**
   Com `20`, aparece **`Agradável`**, pois falha no primeiro teste (`20 >= 30`), mas passa no segundo (`20 >= 20`). Com `30`, aparece **`Calor`**, pois a primeira condição (`30 >= 30`) já é verdadeira e encerra a verificação.

2. **Quais as saídas das quatro últimas linhas? Por que recomendamos `===`?**
   * `5 == "5"` → `true`
   * `5 === "5"` → `false`
   * `0 == false` → `true`
   * `0 === false` → `false`
   Recomendamos `===` porque ele compara tanto o valor quanto o tipo do dado, evitando conversões implícitas que causam erros lógicos.

3. **Escreva uma condição que seja verdadeira apenas quando a variável `nota` estiver entre 0 e 10 (inclusive):**
   ```javascript
   nota >= 0 && nota <= 10
   ```