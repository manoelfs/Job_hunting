# 🧠 Guia e Prompt para Análise de Aderência com Inteligência Artificial

Este documento contém as diretrizes e o prompt otimizado para que uma inteligência artificial (ChatGPT, Claude, Gemini, etc.) cruze com máxima precisão o seu currículo profissional com a lista de vagas gerada pelo robô.

---

## 📝 Como usar este Guia

1. Abra sua ferramenta de Inteligência Artificial de preferência.
2. Copie o bloco de **Prompt** fornecido abaixo.
3. Substitua os marcadores `[Cole o texto do seu Currículo aqui]` e `[Cole a tabela/conteúdo do CSV consolidado aqui]` pelos seus dados correspondentes.
4. Envie a mensagem para obter o relatório analítico estruturado.

---

## 💬 PROMPT PARA COPIAR E COLAR

```text
Você é um Headhunter Executivo e Analista de Carreira Especialista.

Sua tarefa é analisar uma lista de vagas de emprego recentes (fornecidas na tabela/arquivo anexo) e compará-las detalhadamente com o meu Currículo (também fornecido em anexo/texto).

---

### 📥 DADOS DE ENTRADA:
1. CURRÍCULO PROFISSIONAL:
[Cole o texto do seu Currículo aqui]

2. ARQUIVO DE VAGAS COLETADAS:
[Cole a tabela/conteúdo do CSV consolidado aqui]

---

### ⚙️ REGRA DE ANÁLISE DE ADERÊNCIA:
Para cada vaga presente na lista, você deve realizar um cruzamento minucioso considerando:
- Senioridade e Nível de Cargo (Ex: Gestão/Liderança vs. Especialista Hands-on)
- Hard Skills e Tecnologias exigidas vs. Histórico de uso real
- Metodologias, Processos e Governança (Ex: SRE, ITIL, FinOps, Agile)
- Atribuições do dia a dia e responsabilidades orçamentárias/de pessoas

Atribua uma nota de Grau de Aderência (%) de 0% a 100%:
- 90% a 100%: Vaga ideal (Atende liderança, stack e processos perfeitamente).
- 75% a 89%: Alta aderência (Atende aos principais requisitos, pequenos desvios de stack ou senioridade).
- 50% a 74%: Média aderência (Atende parte dos requisitos, mas exige transição técnica ou de nível).
- Abaixo de 50%: Baixa aderência (Fora do escopo profissional ou perfil muito distante).

---

### 📊 FORMATO DA RESPOSTA (SAÍDA):
Monte uma tabela organizada no formato Markdown contendo as seguintes colunas:

| Cargo e Empresa | Fonte / Link | Aderência (%) | Justificativa de Aderência (Requisitos Atendidos vs. Faltantes) |
| :--- | :--- | :---: | :--- |
| **[Título da Vaga]** <br> *[Nome da Empresa]* | [Acessar Vaga](URL_LINK) | **XX%** | **Pontos Atendidos:** [Listar 2-3 pontos fortes]. <br>**Pontos Faltantes:** [Listar pontos divergentes ou não citados no CV]. |

---

Ao final da tabela, forneça um resumo com 2 a 3 recomendações estratégicas sobre as vagas em que devo focar minhas candidaturas primeiro.
```
