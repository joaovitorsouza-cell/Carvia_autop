# Car Via Auto Peças — projeto

Site com catálogo de exemplos, busca por nome/código, filtros, detalhes, carrinho persistido no navegador e integração preparada para Mercado Pago.

## Abrir no Windows / VS Code
1. Extraia o ZIP (não execute dentro do arquivo compactado).
2. Instale Node.js 22.13 ou superior.
3. No VS Code, use Arquivo > Abrir Pasta e selecione Car_Via_Auto_Pecas.
4. Abra Terminal > Novo Terminal e execute:

```sh
npx pnpm@11.25.0 install
npx pnpm@11.25.0 dev
```

Abra http://localhost:5173 no navegador. A instalação precisa de internet.

## Arquivos principais
- app/page.tsx: interface e carrinho.
- app/globals.css: aparência e responsividade.
- lib/catalog.ts: produtos, códigos e preços (em centavos).
- app/api/checkout/route.ts: validação e checkout Mercado Pago no servidor.
- app/api/orders/route.ts: consulta de pedidos e verificação de pagamento.
- db/schema.ts e drizzle/: banco de pedidos e migração.

## Estado atual
Produtos, preços, estoque e imagens são ilustrativos. Vendas reais estão desativadas. É necessário cadastrar o catálogo real, implementar controle de estoque persistente e definir entrega/retirada antes de ativar vendas. A integração de pagamento não foi testada com credenciais reais.

O carrinho funciona localmente. Pedidos dependem do banco D1 com a migração aplicada. A autenticação hospedada usa o login do ChatGPT/Sites; o ambiente de desenvolvimento pode usar identidade simulada. O projeto não inclui login independente por senha, painel administrativo, cálculo de frete ou emissão de nota fiscal.

Credenciais de pagamento devem ficar apenas no servidor: MERCADO_PAGO_ACCESS_TOKEN. SALES_ENABLED é a chave de ativação. Nunca coloque tokens em app/page.tsx ou no catálogo. Não é preciso configurar pagamentos para visualizar a loja.

## Verificações feitas
Compilação de produção e TypeScript passaram. Testes simulados verificaram autenticação, origem, bloqueio de pagamentos sem configuração, quantidades e preços calculados no servidor. Esta cópia não foi executada no Windows; não houve revisão visual em navegador.

## Site de referência
https://car-via-auto-pecas.frostytetra64.chatgpt.site
O site hospedado está privado. Este ZIP contém o código, sem credenciais, dependências instaladas ou dados pessoais. O identificador de hospedagem foi removido da cópia.
