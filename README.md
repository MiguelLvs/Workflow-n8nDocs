# 📊 Workflow n8n: n8n - Docs

## 🔍 Descrição
Este workflow realiza [explique o objetivo principal].  
Exemplo: envia lembretes automáticos via WhatsApp para pacientes com base em uma planilha de horários.

---

## 🧩 Nodes utilizados

| Nome do Node        | Tipo                         | Descrição                                         |
|---------------------|------------------------------|---------------------------------------------------|
| Webhook             | gatilho                      | Recebe dados externos via requisição HTTP         |
| Google Sheets       | leitura de dados             | Acessa planilha com informações de pacientes      |
| WhatsApp (HTTP)     | envio de mensagem            | Envia notificação via API externa                 |
| Set                 | manipulação de dados         | Prepara os dados antes de enviar a mensagem       |
| If                  | condicional                  | Verifica se o paciente já respondeu               |

---

## 🔄 Fluxo de execução

1. **Gatilho:** O webhook recebe dados ou inicia automaticamente via Schedule Trigger.
2. **Leitura de dados:** O workflow acessa uma planilha (Google Sheets) com dados relevantes.
3. **Processamento:** Compara, filtra ou estrutura as informações.
4. **Ação final:** Envia a mensagem ao paciente via WhatsApp.
5. **Confirmação:** Opcionalmente, espera resposta do usuário para marcar como "concluído".

---

## ⚙️ Requisitos

- Conta n8n (self-hosted ou cloud)
- Integração com [Google Sheets, API WhatsApp, etc.]
- Credenciais configuradas (ex: Google OAuth, Webhook URL)

---

## 🚀 Como importar no n8n

1. Acesse o painel do n8n
2. Clique em **Import > From File**
3. Selecione o arquivo `n8n-Docs.json`
4. Clique em **Save**

---

## 🗃️ Arquivos

- [n8n - Docs.json`](./n8n-Docs.json) – Arquivo do workflow para importação no n8n.

---

## 📌 Observações

- Este fluxo pode ser facilmente adaptado para outras fontes de dados.
- Verifique as permissões da API e o limite de requisições da plataforma utilizada.
