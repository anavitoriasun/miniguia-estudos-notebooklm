# 📚 Miniguia de Estudos: Engenharia de Prompts para IA Generativa

&gt; **Projeto Prático - Desafio DIO**  
&gt; *Uso do NotebookLM como ferramenta de aprendizagem ativa e curadoria do conhecimento.*

---

## 🎯 Contexto e Objetivos

### Contexto

A Engenharia de Prompts (ou *Prompt Engineering*) é o processo de projetar, estruturar e otimizar entradas de texto em linguagem natural para guiar modelos de linguagem (LLMs) e soluções de IA generativa no alcance dos resultados desejados. Com o avanço de modelos pré-treinados baseados em arquiteturas Transformer, a qualidade do conteúdo gerado depende diretamente da precisão, do contexto e do tom das instruções fornecidas. Este repositório documenta a curadoria e a síntese desse conhecimento a partir de referências técnicas oficiais.

### Objetivos de Estudo

* **Compreender** o papel da engenharia de prompts como ponte entre a intenção humana e a execução da máquina.
* **Mapear** as principais técnicas de prompting (como *zero-shot*, *few-shot*, *Chain-of-Thought* e *Tree-of-Thought*).
* **Analisar** os principais modos de falha e desafios de segurança (como alucinações, ambiguidades e injeção de prompts).
* **Construir** um miniguia de estudo e um acervo de prompts reutilizáveis para apoiar revisões futuras.

---

## 📚 Curadoria de Fontes

O estudo foi fundamentado e estruturado em 3 fontes abertas de grandes provedores de tecnologia e infraestrutura:

1. 📄 **O que é Engenharia de Prompt? | Databricks**

  * **Descrição:** Explora definições fundamentais, técnicas de raciocínio (cadeia de pensamentos), ciclo de vida do prompt, rastreamento de experimentos com MLflow, modos de falha e implicações éticas.
  * **Link:** [Databricks Blog](https://www.google.com/url?sa=E&amp;q=https%3A%2F%2Fwww.databricks.com%2Fbr%2Fblog%2Fwhat-is-prompt-engineering)
2. 📄 **O que é Engenharia de Prompt? | IBM**

  * **Descrição:** Aborda a importância dos modelos de base, competências do engenheiro de prompts (comunicação, Python, linguística), técnicas de otimização e casos de uso em setores como saúde e desenvolvimento de software.
  * **Link:** [IBM Think Topics](https://www.google.com/url?sa=E&amp;q=https%3A%2F%2Fwww.ibm.com%2Fbr-pt%2Fthink%2Ftopics%2Fprompt-engineering)
3. 📄 **O que é Engenharia por Prompt? | AWS**

  * **Descrição:** Detalha a importância dos prompts para desenvolvedores e experiência do usuário, além de técnicas avançadas como prompting maiêutico, conhecimento gerado, estímulo direcional e do menor para o maior.
  * **Link:** [AWS Concept Hub](https://www.google.com/url?sa=E&amp;q=https%3A%2F%2Faws.amazon.com%2Fpt%2Fwhat-is%2Fprompt-engineering%2F)

---

## 🧪 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Abaixo estão registrados exemplos de refinamento de instruções e os modos de falha documentados durante o processo de testes com o NotebookLM.

### Evolução de Prompts (Antes vs. Depois)

* **Prompt V1 (Inexistente/Genérico):**  
&gt; *"Me fale sobre engenharia de prompt."*

  * **Problema:** Resposta vaga, abrangente demais e sem estrutura definida para revisão técnica.
* **Prompt V2 (Refinado com Papel, Formato, Restrições e Escopo):**  
&gt; *"Atue como um Especialista em IA Generativa. Com base exclusivamente nas 3 fontes fornecidas (Databricks, IBM e AWS), elabore um resumo comparativo das técnicas de prompting (Zero-shot, Few-shot e Chain-of-Thought). Apresente o resultado em uma tabela Markdown indicando: Técnica, Descrição e Caso de Uso Recomendado."*

  * **Resultado:** Resposta direta, altamente estruturada, sem alucinações e diretamente aplicável ao estudo.

---

### 🩹 Cicatrizes e Troubleshooting (Modos de Falha)

| Problema / Modo de Falha                 | Causa Identificada nas Fontes                                                  | Solução Aplicada no Prompt                                                                                         |
| ---------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| **Ambiguidade e má interpretação**       | Prompts vagos ou genéricos que geram saídas desconexas.                        | Especificar claramente a função (persona), o contexto, o formato desejado (tabelas/listas) e o escopo da resposta. |
| **Alucinação (Informação Falsa)**        | Prompts excessivamente amplos ou sem amarração em dados de entrada.            | Aplicar a instrução estrita: *"Responda utilizando exclusivamente o conteúdo das fontes fornecidas"*.              |
| **Injeção de Prompt (Prompt Injection)** | Entradas maliciosas que tentam sobrepor instruções iniciais do sistema.        | Encapsular as entradas de usuário em blocos de contexto bem delimitados e definir regras de restrição.             |
| **Especificação Excessiva**              | Prompts rígidos em demasia que travam a capacidade de resposta útil do modelo. | Equilibrar o detalhamento de instrução sem limitar a capacidade analítica da IA.                                   |

---

## 📖 Miniguia de Estudo (Entrega Final)

### 1\. Resumos Estruturados do Assunto

#### A. Conceito e Importância

A Engenharia de Prompts consiste na criação e no refinamento sistemático de instruções em linguagem natural enviadas aos modelos de linguagem. Ela atua como ponte entre a intenção humana e a compreensão da máquina, garantindo respostas de alta qualidade, reduzindo a necessidade de pós-processamento manual e otimizando o uso de recursos computacionais.

#### B. Principais Técnicas de Prompting

* **Zero-Shot Prompting:** Fornece a instrução da tarefa ao modelo sem apresentar nenhum exemplo prévio no prompt.
* **Few-Shot Prompting:** Oferece pequenos exemplos de entrada e saída no próprio prompt para orientar o formato e o padrão esperado.
* **Chain-of-Thought (Cadeia de Pensamentos - CoT):** Divide tarefas complexas em etapas intermediárias de raciocínio lógico antes de gerar a conclusão.
* **Tree-of-Thoughts (Árvore de Pensamentos - ToT):** Explora múltiplos caminhos lógicos de raciocínio em formato de ramificações ou árvores de busca.
* **Conhecimento Gerado (Generated Knowledge):** Solicita que o modelo liste primeiramente os fatos relevantes para só então concluir a resposta principal.
* **Estímulo Direcional (Directional Stimulus):** Inclui palavras-chave ou dicas específicas no prompt para direcionar o tom, o estilo ou o foco.

#### C. Boas Práticas Recomendadas

* **Clareza e Especificidade:** Evite ambiguidades e defina explicitamente o formato de saída (tabelas, listas, JSON).
* **Fornecimento de Contexto:** Adicione dados de fundo, limitações e orientações de conduta.
* **Processo Iterativo:** Teste variações de formulação, avalie os resultados e faça ajustes contínuos.
* **Decomposição de Tarefas:** Quebre problemas grandes e complexos em etapas ou subproblemas menores.

---

### 2\. Glossário de Conceitos

* **Prompt:** Entrada de texto em linguagem natural fornecida a um modelo de IA generativa para solicitar uma tarefa.
* **LLM (Large Language Model):** Modelo de aprendizado de máquina pré-treinado em grandes volumes de dados para processamento e geração de linguagem natural.
* **Zero-Shot:** Abordagem onde o modelo responde a uma solicitação sem ter recebido nenhum exemplo no prompt.
* **Few-Shot:** Abordagem em que amostras do resultado esperado são fornecidas junto com a instrução.
* **Chain-of-Thought (CoT):** Técnica que induz o modelo a resolver problemas através de passos lógicos intermediários.
* **Alucinação:** Situação em que o modelo gera informações incorretas ou sem fundamentação nos dados fornecidos.
* **Prompt Injection:** Ataque ou tentativa maliciosa de manipular as instruções originais de um sistema de IA por meio do texto de entrada.

---

### 3\. 🔄 Prompts Reutilizáveis para Futuras Revisões

```
PROMPT 1 - Síntese Estruturada:
"Com base exclusivamente nas fontes do meu caderno, crie um resumo em 5 tópicos principais sobre [Subtema de Engenharia de Prompts], citando de onde o conhecimento foi extraído."

```

```
PROMPT 2 - Gerador de Quiz de Fixação:
"Atue como um tutor técnico em IA. Elabore um questionário com 4 perguntas de múltipla escolha sobre técnicas de prompting (Zero-shot, Few-shot e CoT) e inclua o gabarito comentado ao final."

```

```
PROMPT 3 - Mapeamento Comparativo:
"Crie uma tabela Markdown comparando as técnicas Chain-of-Thought, Tree-of-Thought e Conhecimento Gerado com as colunas: Técnica, Como Funciona, Vantagens e Quando Utilizar."
```
