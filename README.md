# 🧠 Workflow n8n – IA com Memória e Envio para Google Docs

## 📌 Descrição

Este workflow utiliza inteligência artificial (IA) com memória de conversação para responder a perguntas recebidas via chat e, em seguida, **salva automaticamente as perguntas e respostas em um documento do Google Docs**.

É ideal para aplicações como:
- Atendimento automático com registro das conversas.
- Geração de relatórios de perguntas e respostas.
- Assistentes que consultam a Wikipedia e mantêm contexto entre mensagens.

---

## 🧩 Estrutura do Workflow

| Etapa | Node                          | Função                                                                 |
|-------|-------------------------------|------------------------------------------------------------------------|
| 1     | `When chat message received`  | Gatilho que recebe uma nova mensagem do usuário.                      |
| 2     | `Groq Chat Model`             | Modelo de linguagem (LLM) que responde à pergunta.                    |
| 3     | `Simple Memory`               | Armazena o histórico das últimas 10 interações.                       |
| 4     | `Wikipedia`                   | Ferramenta que permite consultas à Wikipedia pela IA.                 |
| 5     | `AI Agent`                    | Agente LangChain que coordena o LLM, memória e ferramenta externa.    |
| 6     | `Per/Res` (Set)               | Prepara os dados em formato JSON com a pergunta e a resposta.         |
| 7     | `Code - "Envio"`              | Constrói o corpo da requisição HTTP para envio ao Google Docs.        |
| 8     | `HTTP Request`                | Envia o texto formatado para o Google Docs usando a API oficial.      |

---

## 🔄 Fluxo de Execução

1. Usuário envia uma pergunta via chat.
2. O `AI Agent`, usando o `Groq Chat Model`, responde com base na pergunta, contexto anterior e consultas à Wikipedia.
3. A resposta é combinada com a pergunta em formato JSON.
4. O conteúdo é formatado e enviado para um documento no Google Docs por meio de requisição HTTP.

---

## ⚙️ Requisitos

- **Conta no Google** com permissões para usar a [Google Docs API](https://developers.google.com/docs/api).
- Credencial OAuth2 configurada no n8n para o Google Drive (`googleDriveOAuth2Api`).
- Conta e credencial ativa na [Groq](https://groq.com/) conectada ao n8n.
- Permissão para escrita no documento Google Docs especificado:
