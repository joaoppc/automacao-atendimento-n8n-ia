# automacao-atendimento-n8n-ia
Atendimento automatizado de leads utilizando n8n e inteligencia artificial

## Objetivo
Criar um workflow automatizado no n8n que recebe mensagens via webhook, utiliza Inteligência Artificial para interpretar e classificar a intenção do cliente, executa regras de negócio baseadas na classificação e retorna uma resposta estruturada.

## Entregáveis

- [cite_start]**Workflow:** O fluxo exportado está no arquivo [`My workflow.json`](./My workflow.json)[cite: 7].
- [cite_start]**Prompt da IA:** O texto exato utilizado para instruir o modelo está documentado no arquivo [`prompt.txt`](./prompt.txt)[cite: 7].
- [cite_start]**Vídeo de Apresentação:** [Insira o link do seu vídeo aqui - YouTube/Loom/Drive][cite: 7].

## ⚙️ Como importar e testar

1. Copie o conteúdo do arquivo `workflow_n8n.json`.
2. No seu ambiente n8n, crie um novo workflow e cole o conteúdo (Ctrl+V / Cmd+V) diretamente na tela.
3. Configure as credenciais no nó da IA (ex: OpenAI API Key).
4. Ative o fluxo e envie um `POST` para a URL de teste do Webhook utilizando o seguinte payload:
   ```json
   {
     "nome": "Maria",
     "email": "maria@email.com",
     "mensagem": "Quero cancelar meu plano"
   }
