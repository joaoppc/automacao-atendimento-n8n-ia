# automacao-atendimento-n8n-ia
Atendimento automatizado de leads utilizando n8n e inteligencia artificial

## Objetivo
Criar um workflow automatizado no n8n que recebe mensagens via webhook, utiliza Inteligência Artificial para interpretar e classificar a intenção do cliente, executa regras de negócio baseadas na classificação e retorna uma resposta estruturada.

## Entregáveis

- **Workflow:** O fluxo exportado está no arquivo [`My workflow.json`](./My workflow.json).
- **Prompt da IA:** O texto exato utilizado para instruir o modelo está documentado no arquivo [`prompt.txt`](./prompt.txt).
- **Vídeo de Apresentação:** [Insira o link do seu vídeo aqui - YouTube/Loom/Drive].

## Payloads de teste
   {
     "nome": "Maria",
     "email": "maria@email.com",
     "mensagem": "Quero cancelar meu plano"
   }
   {
     "nome": "Maria",
     "email": "maria@email.com",
     "mensagem": "Quero comprar um plano"
   }
   {
     "nome": "Maria",
     "email": "maria@email.com",
     "mensagem": "Quero ajuda com o plano"
   }


## Raciocinio


Input: O Webhook recebe uma das opções de payload mostrados acima. Implementei uma validação inicial com o nó if para garantir que campos vitais (como mensagem) não cheguem vazios.

Processamento (IA): O modelo [gemini-flash-latest] avalia a mensagem. O prompt foi estruturado forçar a saída estritamente em formato JSON.

Roteamento (Switch): Com base na extração da IA, o fluxo se divide:

Vendas: Dados são enviados para o Google Sheets e geração de log de resposta através de webhook de resposta.

Suporte: Email enviado para email de suporte e geração de log de resposta através de webhook de resposta.

Cancelamento: geração de log de resposta através de webhook de resposta.


