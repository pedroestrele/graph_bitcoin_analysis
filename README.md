# graph_bitcoin_analysis
# 🌐 Análise Estrutural e Topológica da Rede de Confiança Bitcoin Alpha


**Autor:** Pedro Marcos Nery Estrela Cordeiro  
**Instituição:** Universidade Federal da Bahia (UFBA) - Departamento de Ciência da Computação  
**Disciplina:** Teoria dos Grafos (2026.1)

## 📖 Sobre o Projeto
Este repositório contém o código-fonte, o *pipeline* de tratamento de dados e a análise matemática desenvolvida para o relatório final da disciplina de Teoria dos Grafos. 

O projeto investiga a topologia do **Bitcoin Alpha**, uma plataforma pioneira (balcão OTC) onde usuários negociavam criptomoedas e avaliavam a reputação uns dos outros para evitar fraudes em um ambiente descentralizado. O sistema foi modelado rigorosamente como um **grafo direcionado e ponderado**, avaliando desde métricas básicas de conectividade até propriedades avançadas de Redes Complexas (como *Small-World*, Lei de Potência e simulação de ataques).

grafo baixado em [+](https://snap.stanford.edu/data/soc-sign-bitcoin-alpha.html)

## 📂 Estrutura do Repositório

Os códigos foram divididos em *Jupyter Notebooks* focados em diferentes etapas:

* 🛠️ **`Tratamento_grafo.ipynb`**: *Pipeline* inicial de extração, transformação e carregamento (ETL). Removeu componentes cronológicos (*timestamps*) da base original e atestou a inexistência de arestas múltiplas, garantindo um grafo simples direcionado apropriado.
* 🧮 **`grafo_algoritmos.ipynb`**: Aplicação de algoritmos clássicos de grafos. Cálculo da ordem, tamanho, identificação de nós fontes/sumidouros, detecção de Componentes Fortemente/Fracamente Conexos (SCC/WCC) e refutação de Eulerianidade.
* 🕸️ **`analise_grafo_parte3.ipynb`**: O coração analítico do projeto. Focado no Maior SCC (Maior Componente Fortemente Conexo) para analisar distâncias, propriedades de Redes Complexas (*Small-World* e Lei de Potência) e simulação de robustez estrutural do Componente Gigante (GCC).
* 📊 **`graph_analysis.ipynb`**: Consolidação final e geração dos relatórios/ressalvas metodológicas (justificativa de contagem de saltos frente a pesos negativos e inviabilidade de algoritmos como Dijkstra).

### Datasets
* `soc-sign-bitcoinalpha.csv`: Base de dados bruta original.
* `grafo_sem_tempo.csv`: Base processada contendo a estrutura final `(Origem, Destino, Peso)` utilizada nas modelagens topológicas.
### COMO EXECUTAR? ###
# setup do ambiente virtual
python3 -m venv ~/grafo_env 
source ~/grafo_env/bin/activate
pip install numpy>=2 pandas networkx matplotlib
pip install jupyterlab
jupyter lab
#
além disso é intuitivo, apenas rodar as células de cada arquivo(individualmente ou em conjunto), alguns erros de biblioteca eventualmente aparecem, mas as partes que deram erro não foram as que foram usadas nos códigos(exemplo: Axes3D de Matplotlib)
