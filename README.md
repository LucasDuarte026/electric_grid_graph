# Transmission Route Optimization and Connectivity Analysis in Power Systems

This project was developed as part of an **Artificial Intelligence** course, specifically focused on the theme of **graphs and search algorithms**. The central objective is to model electrical power transmission networks — using the well-known IEEE 14-Bus and IEEE 300-Bus test systems — and apply search algorithms to analyze connectivity, detect islanding, and find optimized transmission routes.

## 📌 About the Project

The electrical infrastructure requires efficient tools to ensure the continuous supply of energy, even in the event of component failures. Given this scenario, this project uses the Python language to interpret technical data (`.raw`) and convert the systems into mathematical graphs (where nodes represent load or generation buses and edges represent transmission lines and transformers).

With the network modeled as a structured graph using the `NetworkX` library, three algorithms were implemented and compared:

- **DFS (Depth-First Search):** Uninformed search algorithm used to deeply explore the network structure, validate connectivity between buses, and accurately identify the formation of electrical islands after contingencies.
- **BFS (Breadth-First Search):** Uninformed search algorithm focused on finding minimal topological paths, that is, routes with the fewest number of hops or intermediate connected components.
- **A\* (Informed Search):** Advanced heuristic algorithm that weighs the real transmission cost (using the line's absolute reactance as a weight) and estimates the remaining cost based on Euclidean distance. Thus, A* finds a path that is not only valid but physically more stable.

For validation and experimental study purposes, the project also features an interactive interface directly in the Notebook, allowing the user to choose the buses and algorithms, generating the calculation of execution time, path cost, and visual representation within the generated electrical topology itself.

## 👨‍🎓 Students

* Lucas Duarte - Lider
* Isabela Sakomura Borges - Vice lider
* Artur Zahn
* Matheus dos Santos Inês
* Suellen Teodorico dos Santos Silva
* Giovanna de Freitas Velasco
* Gabriel Balbão Bazon

## 🚀 How to Run the Project (VSCode Example)

The recommended way to run and interact with the project is by using **Visual Studio Code (VSCode)** with a virtual environment in **Python 3**.

### Follow the steps below:

1. **Clone the repository:**
   Open your terminal and clone the project:
   ```bash
   git clone https://github.com/LucasDuarte026/electric_grid_graph.git
   cd electric_grid_graph
   ```

2. **Create a virtual environment:**
   Generate an isolated environment (virtual environment) for Python 3:
   ```bash
   python3 -m venv .venv
   ```

3. **Activate the virtual environment:**
   * On **Linux/macOS**:
     ```bash
     source .venv/bin/activate
     ```
   * On **Windows** (PowerShell or CMD):
     ```bash
     .venv\Scripts\activate
     ```

4. **Open the project in VSCode:**
   ```bash
   code .
   ```

5. **Set up the kernel and install dependencies:**
   * Ensure that the "Jupyter" and "Python" extensions are installed in VSCode.
   * Open the `BusNetworkSearch.ipynb` file.
   * In the upper right corner of the file window in VSCode, click on **Select Kernel** (or choose the interpreter).
   * Select the **Python Environments** option and choose the path of the `.venv` you just created.
   * In the second code cell, there is the command `%pip install networkx matplotlib ipywidgets`. By executing this cell (Shift+Enter), the project dependencies will be properly installed in your virtual environment.

6. **Run the system:**
   Proceed by running the cells in sequence. The project will download the database if necessary, draw the graphs on the screen, and load the interactive interface where you can simulate tests with the DFS, BFS, and A* algorithms.
