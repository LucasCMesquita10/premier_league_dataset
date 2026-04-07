⚽ Análise Estatística da Premier League
📝 Descrição do Projeto
Este projeto realiza uma análise de dados e estatística profunda do histórico de jogos da Premier League, desde a sua criação na temporada de 1993/1994 até o primeiro semestre da temporada 2024/2025. O objetivo principal é extrair insights e compreender o comportamento da liga inglesa ao longo das décadas usando técnicas de ciência de dados.

🎓 Contexto Acadêmico
O projeto foi desenvolvido como parte prática da disciplina de Modelagem Estatística. Ele consolida conceitos de estatística e manipulação de dados aplicando testes de hipótese e visualização de dados para desmistificar comportamentos e tendências do futebol do campeonato inglês.

🧠 Tratamento de Dados e Decisões de Projeto
Durante a análise exploratória e limpeza dos dados, algumas decisões metodológicas importantes foram tomadas para garantir a integridade da análise:

Concentração de Valores Nulos: Observou-se que os dados nulos (referentes a cartões, faltas, chutes, escanteios, etc.) se acumulam quase inteiramente antes do ano de 2001. Isso se deve ao fato de que não era comum coletar dados tão granulares na época.

Preservação de Colunas: Optou-se por não remover (dropar) essas colunas ou as linhas afetadas. Fazer isso resultaria na perda de informações históricas cruciais (por exemplo, podemos não ter as estatísticas de posse ou placar exato de certos momentos, mas sabemos o resultado final e quem venceu a partida).

Não Preenchimento de Nulos (Imputação): Também decidi não preencher os valores nulos com médias ou medianas de épocas posteriores. O futebol mudou drasticamente ao longo das décadas e aplicar médias modernas em jogos dos anos 90 seria estatisticamente perigoso e distorceria a realidade. Além disso, no futebol as dinâmicas são únicas e nem sempre são previsíveis.

📁 Estrutura do Repositório
O projeto é composto pelos seguintes arquivos principais:

England CSV.csv: A base de dados principal contendo informações detalhadas sobre os jogos, como os times, árbitros, placar no intervalo (HT) e final (FT), chutes ao gol, faltas, escanteios e cartões.

premierLeague.ipynb: Um notebook Jupyter utilizado para a etapa de pré-processamento. Nele, foi realizada a tradução e renomeação de colunas, o tratamento de dados faltantes e as validações estatísticas e gráficas iniciais com a criação de novas métricas.

app.py: Aplicação interativa em Python que armazena um Dashboard web contendo todas as visualizações dinâmicas e painéis analíticos desenvolvidos para o usuário final.

🚀 Funcionalidades do Dashboard (app.py)
O Dashboard foi desenhado utilizando a biblioteca Streamlit e conta com um menu de navegação lateral rico em recursos.

Filtro de Escopo de Tempo:
Devido à ausência de certos dados antes de 2001, implementei um filtro mestre no topo do Dashboard, onde o usuário pode escolher a profundidade da sua análise:

Análise Histórica Completa (1993 - 2025): Focada em resultados, pontos e tendências gerais ao longo de toda a história da Premier League.

Análise Estatística Refinada (2001 - 2025): Focada em métricas profundas (faltas, chutes, cartões, escanteios) usando apenas o período em que a coleta de dados era completa.

Abas Analíticas:

📊 Visão Geral: Apresentação principal do painel interativo.

📈 Análise Exploratória: Focada na exibição de gráficos que exploram o comportamento dos dados.

🧪 Testes de Hipótese: Seção dedicada à modelagem estatística profunda, que utiliza as bibliotecas Scipy e Statsmodels para realizar testes matemáticos rigorosos.

🔍 Análise por Time: Uma aba para filtrar e focar nas tendências e métricas de desempenho de uma equipe em específico.

⚔️ Comparação entre Times: Ferramenta projetada para selecionar duas equipes diferentes e colocar seus dados lado a lado para um embate de estatísticas.

🛠️ Tecnologias e Bibliotecas Utilizadas
Linguagem: Python

Manipulação de Dados: Pandas, NumPy

Modelagem e Estatística: Scikit-Learn, SciPy, Statsmodels

Visualização de Dados: Plotly Express, Plotly Graph Objects, Seaborn, Matplotlib

Interface Web: Streamlit, Dash

⚙️ Como Executar o Projeto Localmente
Clone este repositório:

git clone https://seu-repositorio.git
cd seu-repositorio
Crie e ative um ambiente virtual (Recomendado):

python -m venv venv
# No Windows:
venv\Scripts\activate
# No Linux/Mac:
source venv/bin/activate
Instale as dependências:
Você pode instalar os pacotes utilizados rodando o seguinte comando no terminal:

pip install streamlit pandas plotly numpy scikit-learn scipy statsmodels seaborn matplotlib dash
Execute o Dashboard:
Para inicializar a interface web, digite no terminal:

streamlit run app.py
O aplicativo será aberto automaticamente em seu navegador, geralmente rodando no endereço http://localhost:8501.