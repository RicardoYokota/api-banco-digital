# Banco Digital

Esta aplicação simula um sistema bancário digital com operações básicas, como depósito, saque, transferência e consulta de saldo.

## Estrutura

- **Banco:** Armazena informações básicas como nome, número, agência e senha.
- **Contas:** Armazena as contas criadas.
- **Saques, Depósitos e Transferências:** Controla as transações realizadas.

## Funcionalidades

- **Criar Contas:** Permite que um usuário crie uma conta bancária, fornecendo um nome, número da conta, agência e senha. A conta é armazenada no banco de dados e está pronta para ser usada em transações.
- **Realizar Depósitos:** Os usuários podem depositar valores em suas contas bancárias. O valor do depósito é somado ao saldo atual da conta, e o sistema garante que o depósito seja positivo.
- **Realizar Saques:** Permite que um usuário retire um valor de sua conta, desde que haja saldo suficiente. O sistema valida se o saldo é suficiente para cobrir o saque e, se for, subtrai o valor do saldo da conta.
- **Realizar Transferências:** Os usuários podem transferir valores de sua conta para outra conta bancária, respeitando o saldo e as credenciais de ambas as contas. A transferência será registrada como uma subtração no saldo da conta de origem e uma adição no saldo da conta de destino.
- **Consultar Saldo:** Permite que o usuário consulte o saldo de sua conta. A consulta pode ser feita a qualquer momento, desde que o número da conta e a senha sejam fornecidos corretamente.
- **Consultar Extrato:** O extrato da conta pode ser consultado, mostrando todas as transações realizadas, como saques, depósitos e transferências, com detalhes de data e valor. O extrato também requer que o número da conta e a senha sejam fornecidos.

## Estrutura do Banco Digital

- **Banco:** Armazena as informações do banco, como nome, número e agência. Pode conter uma senha geral de acesso administrativo (se necessário).
- **Contas:** Cada conta possui informações como o número da conta, saldo, senha, agência e histórico de transações. As contas podem ser criadas, excluídas ou modificadas conforme necessário.
- **Transações:** São registradas em um histórico de transações, incluindo saques, depósitos e transferências. Cada transação contém informações como tipo (depósito, saque, transferência), valor, data e contas envolvidas.

## Exemplos de Endpoints

- **POST /contas** – Criar uma nova conta bancária.
- **POST /transacoes/depositar** – Realizar um depósito em uma conta.
- **POST /transacoes/sacar** – Realizar um saque de uma conta.
- **POST /transacoes/transferir** – Transferir valores entre duas contas.
- **GET /contas/saldo** – Consultar o saldo de uma conta.
- **GET /contas/extrato** – Consultar o extrato de uma conta.

## Segurança

- **Autenticação:** As operações sensíveis (saques, transferências, etc.) exigem autenticação com senha. O sistema valida a senha fornecida antes de permitir qualquer transação.
- **Validação de Dados:** Todos os valores inseridos (como valores de depósitos, saques e transferências) são validados para garantir que sejam positivos. As contas e transações devem ser verificadas para garantir que estão corretas e que as contas envolvidas existem.
