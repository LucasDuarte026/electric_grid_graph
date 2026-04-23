# Otimização de Rotas de Transmissão e Análise de Conectividade em Sistemas de Potência

Este projeto foi desenvolvido como parte de uma disciplina de **Inteligência Artificial**, focado especificamente no tema de **grafos e algoritmos de busca**. O objetivo central é modelar redes de transmissão de energia elétrica — utilizando os conhecidos sistemas de teste IEEE 14-Bus e IEEE 300-Bus — e aplicar algoritmos de busca para analisar conectividade, detectar ilhamentos e encontrar rotas de transmissão otimizadas.

## 📌 Sobre o Projeto

A infraestrutura elétrica exige ferramentas eficientes para garantir o fornecimento contínuo de energia, mesmo diante de falhas em componentes. Diante desse cenário, este projeto utiliza a linguagem Python para interpretar dados técnicos (`.raw`) e converter os sistemas em grafos matemáticos (onde os nós representam os barramentos de carga ou geração e as arestas representam as linhas de transmissão e transformadores).

Com a rede modelada como um grafo estruturado através da biblioteca `NetworkX`, foram implementados e comparados três algoritmos:

- **DFS (Busca em Profundidade):** Algoritmo de busca não informada utilizado para explorar a fundo a estrutura da rede, validar a conectividade entre barramentos e identificar com precisão a formação de ilhas elétricas após contingências.
- **BFS (Busca em Largura):** Algoritmo de busca não informada focado em encontrar caminhos topológicos mínimos, ou seja, rotas com o menor número de saltos (hops) ou componentes intermediários conectados.
- **A\* (Busca Informada):** Algoritmo heurístico avançado que pondera o custo real da transmissão (usando a reatância absoluta da linha como peso) e estima o custo restante com base na distância euclidiana. Assim, o A* encontra o caminho não apenas válido, mas mais estável fisicamente.

Para fins de validação e estudos experimentais, o projeto conta ainda com uma interface interativa diretamente no Notebook, permitindo que o usuário escolha os barramentos e algoritmos, gerando o cálculo do tempo de execução, custo do caminho e a representação visual na própria topologia elétrica gerada.

## 👨‍🎓 Estudantes

* Artur Zahn
* Matheus dos Santos Inês
* 1 - Lucas Duarte - 11734490 - Lider
* 2 - Isabela Sakomura Borges - 15460673 - vice lider
* 3 - Suellen Teodorico dos Santos Silva - 15489275
* 4 - Giovanna de Freitas Velasco - 13676346
* 5 - Gabriel Balbão Bazon - 13676408

## 🚀 Como Executar o Projeto (Exemplo no VSCode)

A forma recomendada de executar e interagir com o projeto é utilizando o **Visual Studio Code (VSCode)** com um ambiente virtual em **Python 3**.

### Siga os passos abaixo:

1. **Clone o repositório:**
   Abra seu terminal e clone o projeto:
   ```bash
   git clone https://github.com/LucasDuarte026/electric_grid_graph.git
   cd electric_grid_graph
   ```

2. **Crie um ambiente virtual:**
   Gere um ambiente isolado (virtual environment) para o Python 3:
   ```bash
   python3 -m venv .venv
   ```

3. **Ative o ambiente virtual:**
   * No **Linux/macOS**:
     ```bash
     source .venv/bin/activate
     ```
   * No **Windows** (PowerShell ou CMD):
     ```bash
     .venv\Scripts\activate
     ```

4. **Abra o projeto no VSCode:**
   ```bash
   code .
   ```

5. **Configure o kernel e instale as dependências:**
   * Certifique-se de que a extensão "Jupyter" e "Python" estão instaladas no VSCode.
   * Abra o arquivo `BusNetworkSearch.ipynb`.
   * No canto superior direito da janela do arquivo no VSCode, clique em **Select Kernel** (ou escolha o interpretador).
   * Selecione a opção **Python Environments** e escolha o caminho do `.venv` que você acabou de criar.
   * Na segunda célula do código há o comando `%pip install networkx matplotlib ipywidgets`. Ao executar esta célula (Shift+Enter), as dependências do projeto serão devidamente instaladas no seu ambiente virtual.

6. **Execute o sistema:**
   Prossiga rodando as células em sequência. O projeto irá fazer o download da base de dados se necessário, desenhar os gráficos na tela e carregar a interface interativa onde você pode simular os testes com os algoritmos DFS, BFS e A*.
