---
layout: section
---

# LLM como Agentes

---

# Tool Calling

Hoje um LLM não responde apenas texto. Ele pode:

- pesquisar
- executar código
- usar APIs
- controlar computadores
- gerar imagens

---

# Harness

```mermaid
graph TB
    U[Usuário] --> H[Harness]
    H --> L[LLM]
    H --> W[Web]
    H --> F[Arquivos]
    H --> A[APIs]
    H --> C[Código]
    L --> H
    H --> U
```

> O harness orquestra o fluxo entre o usuário, o modelo e as ferramentas.

---
layout: image-right
image: 'https://commons.wikimedia.org/wiki/Special:FilePath/Ameca_Generation_1.jpg'
---

# Agentes

Estamos entrando em outra etapa: não apenas responder, mas executar tarefas completas.

- Planejamento.
- Ferramentas.
- Memória.
- Execução.

---

# Desenvolvimento de Software

A programação foi uma das áreas mais impactadas. Hoje temos:

- autocomplete
- geração de código
- testes
- documentação
- revisão
- debugging

Mudou a forma de desenvolver software.

---

# A mudança de paradigma

**Antes:** Programador → Código

**Agora:** Programador → IA → Código

**Cada vez mais:** Programador → Especificação · IA → Implementação