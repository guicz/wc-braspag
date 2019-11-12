?> O plugin **Braspag para WooCommerce** é integrado ao plugin **Dokan Marketplace**. Possibilita que administradores de Marketplaces aceitem Pagamentos via Cartão de Crédito e Débito usando a modalidade de Split de Pagamento Braspag. 

O Split de Pagamento possibilita a divisão do valores de uma determinada venda entre diversos vendedores. No Split de Pagamento Braspag, existe o Master e os Subordinados:

* O **Master/Marketplace**, Possui acordos com os Subordinados. Define as taxas a serem descontadas sobre a venda de cada Subordinado. Também pode participar de uma venda fornecendo seus próprios produtos. 

* Os **Subordinados** são fornecedores dos produtos que compõem o carrinho. Recebem a maior parte do valor da venda, já descontadas as taxas acordadas com o Marketplace.

### Elegibilidade  do Subordinado

Para utilizar o Split de Pagamentos, o Marketplace deverá se cadastrar na Braspag juntamente com seus Subordinados. Após este processo, tanto o Marketplace quanto seus Subordinados possuirão um identificador único, conhecido como MerchantId (MID).

!> A elegibilidade do Subordinado em participar do processo de Split de Pagamento está condicionada ao Cadastro do Subordinado e Análise Braspag.

O processo de Análise Braspag do Subordinado para Split de Pagamentos ocorre da seguinte forma:

- O Master solicita o cadastro do subordinado.
- O subordinado será criado com status “Em análise” e estará bloqueado para participar da transação, até que o processo de Análise Braspag seja finalizado.
- Ao final da análise, o Master será notificado com o resultado do processo, juntamente com a identificação do subordinado.

### Links

- [Atendimento Braspag](https://suporte.braspag.com.br/hc/pt-br/articles/360018451052-Como-abrir-um-ticket-para-o-time-de-suporte-do-Split-de-Pagamentos-)
- [Cadastro do Subordinado](https://suporte.braspag.com.br/hc/pt-br/articles/360033735591-Processo-de-Cadastro-de-Subordinados)

### Instalação

1. Acesse o painel de administrador do WordPress.
2. Na barra lateral direita, vá para: Plugins > Adicionar novo.
3. Localize o botão "Enviar Plugin" no Topo da tela
4. Selecione os arquivos do nosso plugin dentro do seu computador.
4. Clique em "Instalar agora".
5. Por fim, clique no botão "Ativar" após a instalação.

### Requisitos

- Uma conta Braspag
- Credenciais de acesso para API. (As credenciais são obtidas pelo suporte Braspag)
- Certificado SSL. (É recomendado que sua loja possua um Certificado SSL)
- Plugin "WooCommerce" ativado e instalado.
- Plugin "Dokan" ativado e instalado.
- Plugin "Brazilian Market on WooCommerce" ativado e instalado.
- Versão mínima do PHP  7.0
- Versão mínima do WordPress  5.2

### Inserindo credenciais de acesso

1. Acesse o painel de administrador do WordPress.
2. Na barra lateral direita, vá para: Dokan > Configurações.
3. Na nova página aberta localize e selecione a aba "Braspag Gateway".
4. Localize e preecha os campos de "Integração" Client Secret, Merchant ID e Merchant Key.
5. Click em "Salvar" para guardar as alterações.

### Configuraçõs gerais

Na tela de configurções em Dokan > Configurações > Braspag Gateway, insira as demais informações:

- **Definições para Vendedores Inválido - Impedir a listagem de produtos** - Impede que vededores sem verificação tenham seus produtos listados na loja.
- **Definições para Vendedores Inválido - Impedir adicionar ao carrinho** - Impede que clientes adcionem produtos de vededores sem verificação.
- **Definições para Vendedores Inválido - Impedir o acesso a página do produto** - Impede que clientes acessem a página de produtos de vededores sem verificação.
- **Processo de Verificação - Ativar verificação do vededor** - Ativa o formlário do fornecedor para envio das inoformações de verificação. O formlário é encontrado no painel do fornecedor dentro da guia de configuração.
- **Processo de Verificação - Enviar verificação automaticamente** - Envia as infomações do vendedor diretamente para ánalise Braspag.
- **Contrato de adesão** - URL dos termos de uso e póliticas do Marketplace, deve ser um arquivo PDF.

### Ativando métodos de pagamento

1. Acesse o painel de administrador do WordPress.
2. Na barra lateral direita, vá para: WooCommerce > Configurações.
3. Na nova página aberta localize e selecione a aba "Pagamentos".
4. Marque o boão corresponente ao "Braspag - Split Cartão de Crédito" ou "Braspag - Split Cartão de Débito" para selecioná-lo como ativo no checkout.
5. Click em "Gerenciar" para abrir a tela principal de configurações da respectiva forma de pagamento.

### Configuraçõs para o cartão de crédito

Na tela de configurções para o método cartão de crédito, insira as demais informações:

- **Enable / Disable**  - Ativar para usar. Desativar para desligar.
- **Checkout Title**  - Escolha o título exibido aos clientes durante o checkout.
- **Checkout Description** - Adicionar informações mostradas aos clientes no checkout.
- **Texto da fatura** - O texto que aparecerá na fatura do cartão.
- **Menor Parcela** - O valor minínmo de cada parcela.
- **Número de Parcelas** - O limite para parcelamentos.
- **Aceitar as Bandeiras** - Bandeira de cartões elegíveis para o pagamento 
- **ProviderMerchantId** - Identificador único para a análise de fraude (Obtido através do suporte Braspag) 
- **Enable Log** - Quando estiver marcado ativa o registro de log para o método de pagamento.### Configuraçõs para o Cartão de Crédito

### Configuraçõs para o cartão de débito

Na tela de configurções para o método cartão de débito, insira as demais informações:

- **Enable / Disable**  - Ativar para usar. Desativar para desligar.
- **Checkout Title**  - Escolha o título exibido aos clientes durante o checkout.
- **Checkout Description** - Adicionar informações mostradas aos clientes no checkout.
- **Texto da fatura** - O texto que aparecerá na fatura do cartão.
- **Aceitar as Bandeiras** - Bandeira de cartões elegíveis para o pagamento 
- **Enable Log** - Quando estiver marcado ativa o registro de log para o método de pagamento.

------------

# Verificação do Subordinado

O processo de verificação do Subordinado consiste em coletar informações para ánalise Braspag. O envio das infomações coletas pode ser submetido para ánalise Braspag mediante a confirmação previa do Master/Marketplace ou automaticamente.

### Verificação com confirmação

Na Verificação com confirmação o Marketplace recebe os dados enviados pelo fornecedor e verifica por meio do Dashboard do Wordpress se os dados estão em conformidade com o exigido. Depois da avaliçao o Marketplace deve submeter as informações para ánalise Braspag.

!> O formulário de verificação é encontrado no dashboard do fornecedor em  Configurações > Verificação.

**Procedimentos:**

1. Por meio do dashboard Fornecedor preenche e envia as informações de verificações para análise interna do Marketplace.
2. Ao enviar um pedido de verificação, um email de notificação é enviado para o Marketplace.
3. O Marketplace deve acessar o dashboard WordPress e se direcionar para a tela de "Pedidos de Verificação" em Dokan > Verificações. 
4. Na tela de verificações o Marketplace pode filtar cada solicitação de verificação pelo seu status: Verificação Pendente | Verificação aprovada | Verificação Rejeitada | Em Verificação
5. Para novas solicitações o status da verificação é sempre "Verificação Pendente". Ao identificar uma "Verificação Pendente" o Marketplace deve fazer sua avaliçao interna antes de decidir se envia para ánalise Braspag ou rejeita os dados recebidos.
6. Ao final do processo de ánalise Braspag o Status da verificação é alterado automaticamente para "Verificação aprovada" ou "Verificação Rejeitada" e um email de notificação é enviado para o Marketplace.

### Verificação automatica

Na Verificação automatica os dados enviados pelo fornecedor são submetidos diretamente para ánalise Braspag.

!> O formulário de verificação é encontrado no dashboard do fornecedor em  Configurações > Verificação.

**Procedimentos:**

1. Na tela de configuração gerais em Dokan > Configurações > Braspag Gateway, localize e marque a opção "Enviar verificação automaticamente".
2. Por meio do dashboard o Fornecedor preenche e envia as sua informações diretamente para ánalise Braspag.
3. O registro do envio é encontado na tela de "Pedidos de Verificação" em Dokan > Verificações.
4. Para verificações automaticas enviadas para ánalise Braspag com sucesso o status da verificação é sempre "Em Verificação". Isso quer dizer que os dados enviados pelo fornecedor estão agora em processo de ánalise pela Braspag.
5. Ao final do processo de ánalise Braspag o Status da verificação é alterado automaticamente para "Verificação aprovada" ou "Verificação Rejeitada" e um email de notificação é enviado para o Marketplace.

------------

# Processos do Marketplace

### Captação do fornecedor

O processo de captação descreve as etapas necessárias para o cadastro de um fornecedor e um fluxo básico de vendas

### Cenário típico

1. Fornecedor toma conhecimento sobre os benefícios do Marketplace
2. Fornecedor acessa o site do Marketplace
3. Fornecedor efetua seu cadastro
4. Fornecedor preenche as informações de sua loja
5. Fornecedor configura seu meio de entrega
6. Fornecedor cadastra seus produtos
7. Fornecedor envia os dados para verificação
8. Com a verificação aprovada Fornecedor é liberado para a venda
9. Fornecedor começa a vender
9. Fornecedor recebe pedido
10. Status do pedido é atualizado automaticamente para pago, canceldo ou pendente
11. Fornecedor recebe confirmação de pagamento
12. O confere os dados do pedido 
13. Fornecedor despacha o pedido
14. Fornecedor finaliza o processo de venda
15. Fornecedor recebe em sua conta (cadastrada no processado de verificação) o valor do pedido descontado as taxas do Marketplace

### Fluxo do checkout

Os clientes podem adcionar varios produtos de fornecedores diferentes ao carrinho e realizar um unico processo de pagamento.

### Cenário típico

1. Consumidor toma conhecimento sobre os benefícios do Marketplace
2. Consumidor acessa o site do Marketplace
3. Consumidor realiza seu cadastro
4. Consumidor pesquisa produtos no shopping online
5. Consumidor efetua compras em mais de um Fornecedor
a. Consumidor adiciona produto do Fornecedor Y ao carrinho
b. Consumidor adiciona produto do Fornecedor XYZ ao carrinho
6. Consumidor efetua um único checkout transparente para o seu carrinho
(mesmo tendo produtos de mais de um Fornecedor)
7. Consumidor escolhe se quer pagar via cartão de crédito parcelado ou via cartão de débito
8. Gateway de pagamento aprova a transação
9. Consumidor conclui o checkout único
10. Fornecedor recebe o pedido
11. Status do pedido é alterado automaticamente para pagamento aprovado
12. Fornecedor recebe confirmação de pagamento
13. Fornecedor separa o pedido
14. Fornecedor confirma que o pedido está pronto para ser enviado
15. O pedido é despachado e um codigo de acompanhamento e enviado para o consumidor
16. Consumidor recebe seu pedido e finaliza o processo de compra
