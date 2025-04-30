Estrutura do Projeto
pgsql
Copiar
Editar
ObservabilidadeBancoDados/
├── db/
│   ├── Dockerfile
│   ├── northwind.sql
│   └── README.md
├── postgres-exporter/
│   ├── Dockerfile
│   └── README.md
├── prometheus/
│   ├── Dockerfile
│   ├── prometheus.yml
│   └── README.md
├── grafana/
│   ├── Dockerfile
│   ├── dashboards/
│   │   └── example-dashboard.json
│   ├── provisioning/
│   │   ├── datasources/
│   │   │   └── datasource.yml
│   │   └── dashboards/
│   │       └── dashboard.yml
│   └── README.md
├── docker-compose.yml
└── README.md
Primeiros Passos
Para colocar toda a stack de observabilidade em funcionamento, siga as instruções abaixo:

Clone o repositório:

bash
Copiar
Editar
git clone https://github.com/AleTavares/ObservabilidadeBancoDados.git
cd observability-project
Construa e inicie os containers:

bash
Copiar
Editar
docker-compose up --build -d
Acesso aos serviços:

PostgreSQL: Utilize um cliente de sua preferência para se conectar ao banco de dados.

Prometheus: A interface está disponível em http://localhost:9090.

Grafana: Acesse o painel em http://localhost:3000. As credenciais padrão são admin / admin.

Configurando o Grafana
O Grafana serve como ferramenta de visualização dos dados coletados pelo Prometheus. Após iniciar o serviço, siga os passos abaixo:

Vá até http://localhost:3000.

Faça login com:

Usuário: admin

Senha: admin (será solicitada a troca da senha no primeiro login).

Clique no ícone de "+" na barra lateral e selecione "Importar".

Na opção "Importar via ID do Dashboard", insira um ID válido. Exemplo:

ID do Dashboard: 9628

Clique em "Carregar".

Escolha a fonte de dados do Prometheus e confirme clicando em "Importar".

O painel estará pronto para exibir as métricas do banco PostgreSQL.

Mais Informações
Cada pasta contém um arquivo README.md com instruções específicas de configuração.

O banco de dados Northwind vem carregado por padrão no PostgreSQL para facilitar testes.

O arquivo prometheus/prometheus.yml pode ser ajustado para adaptar a coleta de dados conforme necessário.

Este projeto oferece uma abordagem prática para monitoramento de bancos de dados PostgreSQL, promovendo visibilidade sobre o desempenho e auxiliando na identificação de gargalos.
