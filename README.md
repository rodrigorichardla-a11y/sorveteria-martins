# Sorveteria Martins — Loja virtual

Projeto responsivo preparado para publicação na Netlify. O site usa as fotografias reais e o logotipo fornecidos, catálogo com os cinco açaís, tamanhos, adicionais, carrinho persistente, formulário de finalização e integração com WhatsApp.

## Publicar na Netlify
1. Descompacte o ZIP e envie a pasta do projeto para um repositório GitHub.
2. Na Netlify, crie um novo site conectado a esse repositório. (As funções de servidor precisam ser publicadas por Git ou Netlify CLI; o simples arrastar-e-soltar dos arquivos estáticos não publica as funções.)
3. Em **Site configuration → Environment variables**, configure:
   - `ADMIN_PASSWORD`: senha forte para entrar em `/admin.html`.
   - `SESSION_SECRET`: segredo aleatório longo (mínimo recomendado: 32 caracteres), diferente da senha.
4. Faça um novo deploy. As funções usam Netlify Blobs para armazenar catálogo, configurações e pedidos de forma persistente.
5. Abra `/admin.html` para entrar no painel e gerenciar produtos, preços, adicionais e status dos pedidos.

## Publicação via Netlify CLI (alternativa ao Git)
Requer Node.js 18+ e Netlify CLI. Na pasta do projeto, execute `npm install`, `netlify login`, `netlify link` e `netlify deploy --prod`.

## Desenvolvimento local
Execute `npm install` e `npx netlify dev` para testar as funções localmente. Para testar login local, defina `ADMIN_PASSWORD` e `SESSION_SECRET` no ambiente.

## Observações importantes
- O checkout abre o WhatsApp oficial `553191161291` com a mensagem preenchida; o cliente ainda precisa tocar em **Enviar** no WhatsApp.
- A taxa de entrega não é estimada nem somada. É indicada como “a confirmar pelo WhatsApp”.
- O pagamento disponível é somente PIX.
- O carrinho fica salvo no navegador (LocalStorage). Os pedidos preparados são registrados com status **Aguardando envio**; a equipe deve alterar manualmente para **Recebido** depois de confirmar o recebimento no WhatsApp.
- O painel administrativo e o armazenamento persistente dependem da publicação na Netlify e das variáveis de ambiente acima. A visualização estática local não substitui o backend implantado.
