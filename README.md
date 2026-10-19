🏦 CarolBank AI - Assistente Financeiro Inteligente com MCP & Open Finance

Projeto final desenvolvido para o Bootcamp Bradesco - Agentes de IA: Do Zero à Prática na plataforma da DIO
, sob orientação do Expert Bruno Lima.


🌐 Acesse a Aplicação Publicada ao Vivo:
👉 https://pixel-perfect-replay-988.lovable.app

📌 1. Sobre o Projeto

O CarolBank AI é um web app em formato de assistente conversacional inteligente que leva a experiência bancária para o chat. Utilizando o protocolo aberto MCP (Model Context Protocol), a aplicação simula a conexão entre Inteligência Artificial e ecossistemas de Open Finance:


Pluggy: Referência para a integração do ecossistema de Open Finance no Brasil (documentação e padronização regulatória).
Plaid (Sandbox): Fonte de dados fictícios estruturados para teste de contas correntes, saldos, faturas e transações.
Lovable: Plataforma de desenvolvimento ágil com IA para construção e publicação da interface visual do banco.


⚠️ Aviso de Segurança: Esta aplicação opera exclusivamente em ambiente de demonstração (Sandbox). Todos os dados de contas, saldos, estabelecimentos e valores são 100% fictícios. Nenhuma chave de API ou credencial sensível está versionada no projeto.

💬 2. Perguntas que o Assistente Responde & Origem dos Dados

O assistente foi projetado para responder de forma clara e visual às principais dúvidas financeiras do dia a dia:

Pergunta do Cliente	Dado Retornado	Origem do Dado (Simulação Open Finance)
"Qual é o meu saldo atual?"	Card visual com Saldo em Conta Corrente, Limite Especial e Total Disponível	Endpoint de Contas (Accounts/Balances)
"Ver extrato das últimas transações"	Lista com data, categoria (Alimentação, Transporte, Saúde) e valor colorido (entradas/saídas)	Endpoint de Transações (Transactions/Get)
"Análise de gastos por categoria"	Gráfico com divisão percentual de despesas	Agrupamento de categorias via IA
"Consultar fatura do cartão de crédito"	Valor fechado da fatura atual e data de vencimento	Saldo do Cartão de Crédito (Credit Balances)
"Planejar orçamento até a fatura vencer"	Cálculo da média diária recomendada de gastos com base no saldo livre	Lógica financeira do assistente
💡 Conceito Financeiro: Saldo do Cartão como Passivo (Dívida)

Na convenção do Open Finance e de APIs como a Plaid, valores positivos no cartão de crédito representam saídas ou saldo devedor (fatura a pagar), enquanto em contas de depósito representam ativos. O assistente traduz isso em linguagem simples para que o cliente não se confunda.

⚙️ 3. Arquitetura & Configuração dos Servidores MCP

O MCP (Model Context Protocol) funciona como a tomada universal entre a IA e serviços externos. A arquitetura foi desenhada com dois tipos de conexão:

1. Pluggy MCP (Streamable HTTP)
Tipo: Streamable HTTP
URL: https://mcp.pluggy.ai/mcp
Autenticação: Aberta para consulta de documentação do Open Finance Brasil.
Finalidade: Permite à IA consultar as regras, conceitos de consentimento e estrutura de Items do Open Finance brasileiro.
2. Plaid MCP (STDIO Server)
Tipo: STDIO
Pacote: mcp-server-plaid executado via gerenciador uv
Variáveis de Ambiente:
PLAID_CLIENT_ID: Identificador de Sandbox
PLAID_SECRET: Chave secreta de ambiente Sandbox
PLAID_ENV: sandbox
Finalidade: Fornecer dados mockados de instituições financeiras de teste para alimentar o assistente.
🎨 4. Especificação OpenSpec enviada ao Lovable

O aplicativo foi gerado no Lovable utilizando o seguinte prompt estruturado no padrão OpenSpec:

text
Crie um aplicativo web moderno e responsivo em formato de Chat de Assistente Financeiro Pessoal, inspirado em bancos digitais e fintechs de alta tecnologia.
### Identidade do App:
- Nome da Aplicação: CarolBank AI - Assistente Financeiro Inteligente
- Autora: Carolina Fernanda
- Tema Visual: Cores modernas em tons de azul escuro/índigo com detalhes em ciano e branco, transmitindo segurança bancária, tecnologia e clareza. Suporte a tema escuro/claro.
### Estrutura da Interface:
1. Header:
   - Logotipo e nome: "CarolBank AI" com subtítulo "Open Finance & Inteligência Financeira".
   - Banner de Alerta (Obrigatório): "⚠️ Ambiente de Demonstração: Dados fictícios simulados via Sandbox (Open Finance / Plaid / Pluggy)."
   - Indicador de status: "🟢 Conectado ao Open Finance Sandbox".
2. Área Principal do Chat:
   - Boas-vindas personalizadas e botões de atalho rápido (Saldo, Extrato, Gastos por Categoria, Fatura do Cartão e Planejamento).
3. Respostas Interativas:
   - Cards visuais para saldo e limite, extrato com ícones e cores, e divisão de orçamento diário.
🚀 5. Melhorias Implementadas Além do Básico
Card de Planejamento Diário: O assistente calcula automaticamente quanto o usuário pode gastar por dia até a data de vencimento da fatura (regra dos 20% de reserva).
Tema Dark / Light Integrado: Alternador rápido no canto superior direito para conforto visual.
Avisos de Governança e Transparência: Faixa fixa informando a natureza de teste dos dados, em conformidade com as diretrizes do Banco Central para Open Finance.
👩‍💻 Autora

Desenvolvido por Carolina Fernanda

💼 LinkedIn
🐙 GitHub

Projeto acadêmico desenvolvido para avaliação no Bootcamp Bradesco - Agentes de IA da Digital Innovation One (DIO).
