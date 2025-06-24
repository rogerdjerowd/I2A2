# 🤖 Análise de Arquivos CSV com Agente Autônomo (n8n + OpenAI)

Este projeto foi desenvolvido como parte do curso **Agentes Autônomos com Redes Generativas** (I2A2), com o objetivo de criar um agente capaz de interpretar dados de notas fiscais (arquivos CSV) e responder perguntas em linguagem natural, utilizando a plataforma **n8n** integrada à **API da OpenAI (GPT-4-Turbo)**.

## 👤 Participante

- **Nome:** Rogério dos Santos Silva  
- **Grupo:** RogerioJob  
- **Instituição:** I2A2  
- **Ano:** 2025  

---

## 🚀 Tecnologias Utilizadas

- [n8n](https://n8n.io): Plataforma de automação LowCode/NoCode para criação de workflows.
- [OpenAI API](https://platform.openai.com): Utilizada para interpretar perguntas e gerar respostas.
- GitHub: Armazenamento do fluxo `.json` e dos dados de entrada.

---

## 🛠️ Estrutura da Solução

O agente foi implementado como um fluxo no n8n com os seguintes passos:

1. **Recebimento da Pergunta (Webhook):**  
   O processo inicia com a pergunta do usuário via webhook.

2. **Download do ZIP (GitHub):**  
   Um nó HTTP baixa automaticamente o arquivo `202401_NFs.zip` com os CSVs.

3. **Descompactação do ZIP:**  
   O arquivo ZIP é descompactado, extraindo os arquivos:
   - `202401_NFs_Cabecalho.csv`
   - `202401_NFs_Itens.csv`

4. **Preparação do Prompt:**  
   Os dados dos CSVs são formatados (com amostragem) e integrados à pergunta do usuário em um único prompt.

5. **Chamada à API da OpenAI:**  
   O prompt é enviado ao modelo **GPT-4-Turbo**, que retorna uma resposta textual com base nos dados.

6. **Resposta ao Usuário:**  
   A resposta é devolvida ao usuário via webhook, finalizando o fluxo.

---

## 💬 Exemplos de Perguntas e Respostas

- **Pergunta:** Qual o fornecedor que teve maior montante recebido?  
  **Resposta:** O fornecedor "EDITORA FTD S.A." teve o maior montante recebido, com um valor total de 285773.95.

- **Pergunta:** Qual o CPF/CNPJ do Emitente e a Razão Social da nota fiscal "3510129"?  
  **Resposta:** CNPJ: 06267630001509 – Razão Social: COMPANHIA BRASILEIRA DE EDUC. E SIST. DE ENS. S.A - PR OP.

- **Pergunta:** Quantas notas fiscais foram emitidas em 2024-01-15?  
  **Resposta:** Foram emitidas 15 notas fiscais nesse dia.

---

## 📂 Repositório

O repositório inclui:

- Fluxo n8n exportado (`.json`)
- Arquivo ZIP com os dados de teste
- Instruções de uso

🔗 Acesse: [https://github.com/rogerdjerowd/I2A2](https://github.com/rogerdjerowd/I2A2)

---

## ⚠️ Segurança

A chave de API da OpenAI **não está incluída** no repositório. Ela foi configurada diretamente pela interface do n8n via credenciais seguras.  
Para usar o fluxo, você deverá configurar sua própria credencial no n8n.

---

## 🧠 Considerações Finais

A construção desse agente representou um desafio, principalmente por ter sido desenvolvida **do zero** e **sem conhecimento prévio em agentes autônomos ou ferramentas LowCode**. A proposta inicial previa o uso de frameworks mais avançados como **LangChain**, **Langflow** ou **LlamaIndex**, mas devido ao tempo limitado, optou-se por uma abordagem funcional e acessível com o n8n.

O projeto cumpriu os objetivos propostos e demonstrou que é possível construir agentes eficientes com ferramentas simples, desde que bem estruturadas.

---

## 📧 Contato

Este projeto foi desenvolvido como parte do curso "Agentes Autônomos com Redes Generativas" do I2A2.  
Em caso de dúvidas, envie uma mensagem pelo GitHub ou diretamente ao autor: Rogério dos Santos Silva.

Atualiza README com descrição completa do projeto
