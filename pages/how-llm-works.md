# O que realmente é um LLM?

Um modelo treinado para prever o próximo token.

A partir disso ele aprende:

- linguagem
- programação
- matemática
- raciocínio aproximado
- conhecimento factual

---

# Tokenização

O modelo não lê palavras. Ele lê **tokens**.

Exemplo:

```
Computadores
```

↓

```
Comp
ut
adores
```

Cada modelo possui seu próprio vocabulário.

---
layout: center
---

# Como um LLM responde?

<Flow :steps="['Entrada', 'Tokenização', 'Embeddings', 'Transformer', 'Próximo token', 'Repete centenas de vezes']" />

---
layout: fact
---

# Então ele pensa?
<br/>

## Não exatamente!

---
layout: statement
---

Ele prevê probabilidades. É como jogar com dados.

Mas essa previsão gera comportamentos extremamente sofisticados.

É um exemplo clássico de comportamento emergente.

---

# Scaling Laws

Quanto maior:

- modelo
- dados
- computação

Melhor tende a ser o desempenho — até certo limite.

---

# In-Context Learning

Modelos aprenderam algo inesperado: não precisam de novo treinamento para toda tarefa.

Basta fornecer exemplos no prompt.

---

# RLHF

Depois do pré-treinamento, humanos avaliam respostas.

O modelo aprende preferências humanas. Isso torna o chat muito mais útil.