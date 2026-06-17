# Caderno Temático: Inteligência Artificial e LLMs

Projeto feito para o desafio da [DIO](https://www.dio.me/), usando o NotebookLM para estudar um tema do zero e documentar o processo.

---

## Contexto e Objetivos

Escolhi IA e LLMs porque é um assunto que aparece em todo lugar e eu nunca tinha parado pra entender de verdade. Sei usar o ChatGPT, mas não fazia ideia do que acontecia por trás.

**O que eu queria aprender:**

- O que é um LLM e como ele difere de um programa comum
- Como a arquitetura Transformer funciona no básico
- O que são tokens e embeddings
- Como fazer boas perguntas pra uma IA
- Quais são os limites dessas ferramentas

---

## Curadoria de Fontes

| # | Fonte | Tipo | Link |
|---|-------|------|------|
| 1 | **Attention Is All You Need** — Vaswani et al. (2017) | Artigo (PDF) | [arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762) |
| 2 | **A Survey of Large Language Models** — Zhao et al. (2023) | Survey (PDF) | [arxiv.org/abs/2303.18223](https://arxiv.org/abs/2303.18223) |
| 3 | **Prompt Engineering Guide** — DAIR.AI | Guia web | [promptingguide.ai](https://www.promptingguide.ai/pt) |
| 4 | **Fundamentos de IA Generativa** — AWS Skill Builder | Material educacional | [explore.skillbuilder.aws](https://explore.skillbuilder.aws/learn/course/external/view/elearning/17763/fundamentos-de-ia-generativa) |
| 5 | **Introdução aos LLMs** — Google for Developers | Texto | [developers.google.com/machine-learning/resources/intro-llms](https://developers.google.com/machine-learning/resources/intro-llms) |

O artigo do Vaswani foi o mais difícil — muita matemática. O NotebookLM ajudou a extrair o que importava sem precisar entender tudo.

---

## Engenharia de Prompts e "Cicatrizes"

### Prompt 1 — O que é um LLM?

❌ `O que é LLM?` → resposta genérica, ignorou os documentos carregados.

✅ `Com base nos documentos que carreguei, o que é um LLM? Explica de forma simples, como se eu nunca tivesse estudado IA.` → muito melhor, passou a citar as fontes.

**Aprendizado:** prompt vago gera resposta vaga. Sempre especificar o nível e pedir pra usar as fontes.

---

### Prompt 2 — Como funciona o Transformer?

❌ `Explica o Transformer com um diagrama.` → NotebookLM é textual, não gera imagens. Resposta confusa.

✅ `Explica o mecanismo de atenção passo a passo, usando uma frase de exemplo.` → funcionou. Usou o exemplo da palavra "banco" pra mostrar como o contexto define o significado.

**Aprendizado:** trocar "diagrama" por "passo a passo" ou "com exemplo" resolve.

---

### Prompt 3 — Tokens e limites

✅ `O que são tokens em LLMs? Por que existe um limite e o que acontece quando ultrapassa?` → boa resposta desde o início. Aprendi que token não é igual a palavra e que o limite existe porque o modelo processa tudo de uma vez na memória.

---

### Prompt 4 — Riscos e limitações

❌ `Quais são os problemas dos LLMs?` → listou três coisas genéricas sem profundidade.

✅ `O que é alucinação em LLMs? Como acontece e como identificar quando a IA está inventando?` → muito mais útil.

**Aprendizado:** perguntas amplas geram respostas rasas. Melhor perguntar sobre um problema específico de cada vez.

---

## Miniguia de Estudo

### Resumos

**O que é um LLM?**
Um modelo treinado com enormes volumes de texto pra aprender padrões da linguagem humana. Ele não entende de verdade — prevê qual seria a continuação mais provável de um texto. É isso que o torna útil, e também o motivo pelo qual ele erra.

**Como funciona o Transformer?**
Arquitetura que usa **mecanismo de atenção**: ao processar uma palavra, o modelo olha pra todas as outras da frase ao mesmo tempo e decide quais são mais relevantes. Isso permite processar tudo em paralelo, sem perder contexto.

**Tokens e Embeddings**
Token é a unidade mínima processada — pode ser uma sílaba ou parte de uma palavra. Embedding é a representação numérica desse token, capturando seu significado no contexto.

**Limitações**
- **Alucinação:** inventa informações com confiança — sempre vale checar
- **Limite de contexto:** não "vê" documentos além de um certo tamanho
- **Data de corte:** não sabe o que aconteceu após o treino
- **Viés:** aprendeu com textos humanos, que têm preconceitos

---

### Glossário

| Termo | O que significa |
|-------|----------------|
| **LLM** | Modelo de linguagem grande, treinado pra gerar e entender texto |
| **Transformer** | Arquitetura de rede neural baseada em mecanismos de atenção |
| **Token** | Unidade mínima de texto processada pelo modelo |
| **Embedding** | Representação numérica de um token |
| **Self-Attention** | Mecanismo que relaciona cada token com todos os outros da sequência |
| **Prompt** | Texto enviado pra instruir o modelo |
| **Fine-tuning** | Ajuste de um modelo pré-treinado pra uma tarefa específica |
| **RLHF** | Treinamento com feedback humano pra alinhar o modelo |
| **Alucinação** | Quando o modelo gera informação falsa com confiança |
| **Zero-shot / Few-shot** | Tarefa sem exemplos / com poucos exemplos no prompt |
| **Chain-of-Thought** | Pedir pro modelo raciocinar passo a passo |
| **RAG** | Combina busca em documentos com geração de texto |
| **Knowledge Cutoff** | Data limite dos dados de treino |

---

### Prompts Reutilizáveis

```
// Conceito novo
"Explica [conceito] de forma simples, com um exemplo prático."

// Comparação
"Qual a diferença entre [A] e [B]? Quando cada um aparece na prática?"

// Aprofundamento
"Me explica passo a passo como [mecanismo] funciona, com uma frase de exemplo."

// Revisão
"Cria 5 perguntas sobre [tema] pra eu testar se entendi. Coloca as respostas no final."

// Resumo de fonte
"Com base nos documentos carregados, quais os 3 pontos mais importantes sobre [tema]?"

// Riscos
"Quais os principais problemas de usar [ferramenta] em [situação]?"
```

---

## Ferramentas Utilizadas

- [NotebookLM](https://notebooklm.google.com/) — organização das fontes e perguntas
- [GitHub](https://github.com/) — documentação e portfólio
- [Claude (Anthropic)](https://claude.ai/) — apoio na organização do material

---

**Italo** — estudante de Análise e Desenvolvimento de Sistemas  
Desafio de projeto da [DIO](https://www.dio.me/)
