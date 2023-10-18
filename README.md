Projeto Final - Python Coderhouse
Este é um projeto Python que importa dados de uma API, realiza transformações nesses dados usando a biblioteca Pandas e armazena os resultados em um banco de dados SQLite. Além disso, o projeto inclui notificações usando a biblioteca Plyer para informar o usuário sobre o status da importação.

📋 Pré-requisitos
- **Python 3.x**
- **Bibliotecas Python:** requests, pandas, sqlite3, Plyer

🔧 Funcionalidades

1. **Importação de Dados:**
   - O script faz uma solicitação GET para a API `https://brasilapi.com.br/api/cvm/corretoras/v1` para obter informações sobre corretoras.
   - Se a solicitação for bem-sucedida (status code 200), os dados são importados e transformados. Caso contrário, uma notificação é exibida informando sobre o erro na importação.

2. **Notificações:**
   - Após a importação, uma notificação é enviada para o sistema do usuário informando se a importação foi bem-sucedida ou se ocorreu um erro ao acessar a API.

3. **Transformação de Dados:**
   - Os dados da API são transformados em um DataFrame do pandas.
   - Algumas colunas do DataFrame são renomeadas para facilitar a compreensão.
   - Os dados são organizados e formatados conforme necessário.

4. **Armazenamento em Banco de Dados:**
   - Os dados transformados são armazenados em três tabelas separadas em um banco de dados SQLite chamado `coderhouse.db`:
     - **Tabela `corretoras_cadastro`:** Contém informações básicas sobre as corretoras.
     - **Tabela `corretoras_status`:** Contém informações sobre o status de funcionamento das corretoras.
     - **Tabela `corretoras_patrimonio`:** Contém informações sobre o patrimônio líquido das corretoras, com filtro aplicado para valores acima de 3.000.000.

⚙️ Executando os testes
Explicar como executar os testes automatizados para este sistema.

🔩 Execução do projeto
Para executar o projeto, você deve ter Python e as bibliotecas mencionadas instaladas. Em seguida, execute o script Python no seu ambiente de desenvolvimento.

```bash
python nome_do_script.py
```

⌨️ Estrutura do Banco de Dados
O banco de dados `coderhouse.db` contém as seguintes tabelas:

1. **Tabela `corretoras_cadastro`:**
   - `CNPJ` (Chave Primária)
   - `Nome` (Chave Primária)
   - `Nome Comercial`
   - `Código CVM`
   - `E-mail`
   - `Telefone`
   - `Endereço`
   - `Complemento`
   - `CEP`

2. **Tabela `corretoras_status`:**
   - `CNPJ` (Chave Primária)
   - `Data de Registro`
   - `Status`

3. **Tabela `corretoras_patrimonio`:**
   - `CNPJ` (Chave Primária)
   - `Patrimônio Líquido`

✒️ Autores
Ismael Cardoso
Diego da Silva
Henrique Berchielli

📄 Licença
Este projeto está sob licença livre.

