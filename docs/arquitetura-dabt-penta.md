# Arquitetura DABT+ com Penta Central

## Documento conceitual para o Livro Cruzado e o Motor Borges

**Autor do projeto:** SOUNAVY  
**Versão:** 1.0 — conceito de pesquisa  
**Status:** hipótese de arquitetura; não é prova científica nem sistema autônomo

---

## 1. Ideia central

A arquitetura reúne cinco forças em uma forma pentagonal. Todas as ações passam pelo **Penta (Π)**, colocado no centro como observador, medidor e roteador de rodadas.

O Penta não precisa decidir sempre. Em algumas rodadas ele apenas registra, em outras permite a passagem, e em situações de dúvida solicita uma nova medição. A decisão final pode depender do autor, de uma regra explícita ou de uma terceira rodada de análise.

```text
                 Alfa (α)
                    /\\
                   /  \\
          Beta (β)      Teta (θ)
                   \\  /
                    \\/
                 Penta (Π)
                    ||
                Delta (Δ)
```

A forma pode ser lida de duas maneiras:

- **Pentágono de forças:** cinco nós em tensão complementar;
- **Penta central:** todas as leituras passam por um centro de observação antes de avançar.

---

## 2. Nós e responsabilidades

### Delta (Δ) — ação

Delta é a ação que movimenta o processo. Ele não gera uma nota para si mesmo. Recebe os resultados dos outros nós e pode:

- avançar;
- manter o estado;
- suspender a decisão;
- solicitar nova rodada;
- propor uma bifurcação;
- executar uma ação autorizada pelo autor.

Delta não é obrigado a decidir em toda rodada.

### Alfa (α) — aproximação

Alfa coleta sinais de confirmação, evidência, continuidade, materialidade e razão.

### Beta (β) — resistência

Beta coleta sinais de perda, ausência, contradição, risco, tradição, preservação e resistência.

**Alfa e Beta começam com o mesmo peso.** A diferença entre eles vem dos dados observados, não de uma superioridade fixa.

### Teta (θ) — confiança e dispersão

Teta mede:

- quantidade de evidências;
- proximidade entre Alfa e Beta;
- estabilidade do resultado;
- dispersão entre rodadas;
- confiança suficiente para uma bifurcação.

Um limiar, como 80%, é uma regra configurável, não uma verdade universal.

### Penta (Π) — observador central

Penta observa as interações, a memória e os padrões. Pode detectar:

- ciclos repetitivos;
- retornos temporais;
- amostras do início, meio e fim;
- padrões associados a Fibonacci ou à razão áurea;
- divergências entre rodadas;
- necessidade de buscar mais dados.

Penta sugere e roteia. Não deve bloquear o livre-arbítrio do autor.

---

## 3. Três famílias de equações

Não existe uma única fórmula para todos os usos. O mesmo núcleo pode ter fórmulas diferentes para objetivos diferentes.

### 3.1 Equação de contagem e equilíbrio

Para um conjunto de observações:

\[
S = \frac{A-B}{A+B+\varepsilon}
\]

Onde:

- `A` é a quantidade de sinais Alfa;
- `B` é a quantidade de sinais Beta;
- `ε` evita divisão por zero;
- `S` varia aproximadamente entre -1 e +1.

Interpretação:

- `S > 0`: predominância de Alfa;
- `S < 0`: predominância de Beta;
- `S ≈ 0`: equilíbrio ou ambiguidade.

Essa é a fórmula adequada para contar algo como “manga verde” e “manga amarela”: ela descreve a amostra, não inventa uma conclusão.

A força da evidência também precisa considerar o tamanho da amostra:

\[
C = |S| \cdot \frac{A+B}{A+B+k}
\]

`k` é um fator de cautela. Uma única observação não deve produzir a mesma confiança que cinquenta observações.

### 3.2 Equação de caos histórico humano

O caos, neste projeto, não significa aleatoriedade absoluta. Significa ruptura de um padrão que ficou previsível.

\[
K = R \cdot C \cdot (1-N)
\]

Onde:

- `R` é a repetição do padrão;
- `C` é a confiança de que o padrão foi detectado;
- `N` é o índice de novidade;
- `K` é o índice de ruptura.

Quando `K` ultrapassa o limiar definido pelo autor, o sistema **sugere** uma alternativa. Não a executa automaticamente.

Exemplo:

```text
manga → banana → manga → banana → manga
```

O Penta detecta baixa novidade e repetição alta. Se a confiança for suficiente, Delta pode sugerir:

```text
ruptura: experimentar melancia
```

No livro, a “melancia” pode ser uma cidade nova, um narrador inesperado, uma data distante ou uma contradição.

### 3.3 Equação de decisão por rodadas

Uma rodada reúne as leituras e passa pelo Penta:

\[
R_i = \Pi(\alpha_i, \beta_i, \theta_i, M_i, K_i, Q_i)
\]

Onde:

- `M` é a memória das rodadas anteriores;
- `K` é a ruptura possível;
- `Q` é a pergunta atual;
- `Rᵢ` pode ser avançar, manter, suspender, buscar ou bifurcar.

A decisão pode usar até três passadas:

1. **Primeira passada:** medir o material inicial;
2. **Segunda passada:** buscar amostras melhores ou verificar divergências;
3. **Terceira passada:** consolidar, suspender ou devolver ao autor.

Se as três passadas divergirem muito, o resultado correto pode ser **não decidir**.

---

## 4. Amostragem de artigos e fontes

Para uma pesquisa com milhares de artigos, o sistema não deve fingir que “leu tudo” se apenas consultou uma amostra.

Um procedimento transparente seria:

1. definir o conjunto de artigos e os critérios de inclusão;
2. separar por data, tema, método ou fonte;
3. escolher amostras do começo, meio e fim da lista;
4. registrar quais itens foram realmente consultados;
5. classificar os sinais Alfa, Beta e neutros;
6. calcular o resultado da primeira rodada;
7. solicitar uma segunda busca onde a evidência estiver mais forte ou contraditória;
8. registrar o que mudou entre as rodadas.

O sistema deve guardar fonte, título, autores, ano, trecho analisado e motivo da classificação. Sem isso, a equação produz apenas um número sem rastreabilidade.

---

## 5. Criptografia e número oculto na borda

A ideia de um número secreto na borda pode ser útil, mas precisa ser separada da metáfora narrativa.

### O que é seguro

Para criptografia real, use algoritmos padronizados, como AES-GCM ou ChaCha20-Poly1305, com uma chave aleatória mantida em segredo. Um número como `33`, um primo ou um número imaginário, sozinho, não é uma chave segura.

Um hash com uma constante pública também não é criptografia. Ele identifica ou verifica integridade, mas não esconde o conteúdo.

### O que o número secreto pode fazer

Um segredo na borda pode servir como:

- salt ou nonce, quando usado corretamente;
- chave derivada por KDF;
- identificador privado de um dispositivo;
- semente de um gerador, se houver análise de segurança;
- componente de um lacre de integridade.

A implementação não deve publicar o segredo no HTML ou no JavaScript do GitHub Pages. Tudo que chega ao navegador pode ser inspecionado pelo usuário.

### Número imaginário

Números complexos podem aparecer em sinais, áudio, controle e processamento de Fourier. Porém, usar `i` ou um número imaginário não torna uma cifra segura. A segurança vem do algoritmo, do tamanho da chave, da aleatoriedade e do gerenciamento do segredo.

Portanto:

> A borda pode usar um número secreto como parte de um protocolo criptográfico; ela não deve tratar um número oculto como segurança por si só.

---

## 6. Aplicação ao Livro Cruzado

Cada fragmento do livro pode conter:

```json
{
  "historia_ancora": "A Deusa",
  "fatia": "A aparição",
  "ano": 1921,
  "local": "Cidade A",
  "eixo": "horizontal",
  "alfa": 4,
  "beta": 3,
  "tet a": 0.62,
  "penta": "mesmo símbolo reaparece em 1924",
  "delta": "manter a hipótese aberta"
}
```

O campo deve ser escrito como `teta` no software; o espaço acima é apenas um erro tipográfico a ser evitado na implementação.

A montagem pode alternar:

```text
A Deusa — 1921 — aparição
Outra linhagem — 1924 — testemunho
A Deusa — 1931 — retorno
Outra linhagem — 1976 — documento
Presente — pergunta ainda aberta
```

Nenhuma história é apagada. O Penta apenas mostra quando uma linha está repetindo, quando outra precisa ser retomada e quando uma ruptura pode enriquecer o livro.

---

## 7. Limites e compromisso de pesquisa

Este modelo é uma ferramenta de organização e exploração. Ele não prova causalidade histórica, não conhece a mente de uma pessoa e não transforma correlação em verdade.

Toda saída deve ser acompanhada de:

- fonte;
- quantidade de observações;
- regra utilizada;
- rodada em que foi produzida;
- incerteza;
- decisão do autor.

A interação com inteligência artificial pode ajudar a comparar, resumir, classificar e sugerir caminhos. A autoria, a interpretação final, a verificação das fontes e a decisão de publicar permanecem humanas.

## 8. Fechamento

O sistema não existe para eliminar a dúvida. Ele existe para tornar a dúvida visível e trabalhável. Alfa e Beta têm o mesmo ponto de partida; Teta mede a estabilidade; Penta observa os retornos; Delta escolhe se deve avançar, esperar ou abrir uma ruptura.

Quando a repetição fica rígida, o caos oferece uma passagem. Quando a evidência é fraca, a suspensão protege a pesquisa. Quando várias linhas se aproximam, a montagem permite que elas convivam sem que uma seja abandonada.

Essa é a proposta: uma arquitetura capaz de contar, comparar, lembrar, divergir e retornar — sem confundir um cálculo com a verdade final.
