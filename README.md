# Resolução do Problema do Caixeiro Viajante (PCV) com Têmpera Simulada e Algoritmos Genéticos

Este repositório contém a implementação prática, os experimentos computacionais e o artigo acadêmico referente à **Tarefa 1 — Busca e Otimização Heurística**, desenvolvida na disciplina de **Sistemas Inteligentes**.

* **Autores:** Mário Cordeiro Júnior e André F. Maccarini
* **Instituição:** Universidade Tecnológica Federal do Paraná (UTFPR)

---

## 📁 Estrutura do Repositório

```text
.
├── artigo-tsp-mario.pdf            # Artigo final em PDF (5 págs. artigo + 5 págs. apêndices)
├── main.tex                        # Código-fonte principal em LaTeX (formato SBC)
├── sbc-template.sty                # Folha de estilo de artigos da SBC
├── sbc.bib                         # Referências bibliográficas (BibTeX)
├── sbc.bst                         # Estilo bibliográfico da SBC
├── TSP_Didatico_Exploratorio.ipynb # Notebook com formulação PEAS, código e experimentos
├── requirements.txt                # Dependências de bibliotecas Python
├── README.md                       # Documentação do repositório
└── figuras/                        # Gráficos de convergência e dados brutos
    ├── dados_experimentos.json
    ├── figura1_resfriamento.png
    ├── figura2_rotas_convergencia.png
    ├── rotas_e_convergencia.png
    └── tempoMedioXResfriamentoXHeuristica.png
```

---

## 🚀 Como Configurar o Ambiente e Executar o Projeto

Recomenda-se utilizar uma versão recente do Python (3.9 ou superior).

### 1. Criar e ativar o ambiente virtual (`venv`)

#### No Windows (PowerShell):
```powershell
# Criação do ambiente virtual
python -m venv venv

# Ativação do ambiente virtual
.\venv\Scripts\Activate.ps1
```
*(Nota: caso haja restrição de execução de scripts no PowerShell, execute antes: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process`)*

#### No Windows (Prompt de Comando - CMD):
```cmd
python -m venv venv
venv\Scripts\activate.bat
```

#### No Linux / macOS:
```bash
python3 -m venv venv
source venv/bin/activate
```

---

### 2. Instalar as Dependências

Com o ambiente virtual ativado, instale os pacotes necessários:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

### 3. Executar o Notebook de Experimentos

Para visualizar e reproduzir passo a passo a modelagem formal, os testes de convergência e a geração dos gráficos:

```bash
jupyter notebook TSP_Didatico_Exploratorio.ipynb
```
Ou, se preferir o Jupyter Lab:
```bash
jupyter lab TSP_Didatico_Exploratorio.ipynb
```

---

### 4. Compilação do Artigo em LaTeX (Opcional)

O arquivo `artigo-tsp-mario.pdf` já se encontra compilado na raiz. Caso deseje recompilá-lo a partir do código-fonte `main.tex`:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

---

## 🔬 Metodologia e Algoritmos

O trabalho aborda o Problema do Caixeiro Viajante com 20 cidades coordenadas em um espaço bidimensional $[0, 100]^2$:
1. **Modelagem Formal:** Representação por permutação com formalismo de Agentes Inteligentes (PEAS - *Performance, Environment, Actuators, Sensors*).
2. **Têmpera Simulada (Simulated Annealing):** Operador de vizinhança 2-opt com agendamentos de resfriamento geométrico ($\alpha = 0.995, 0.95$), linear e logarítmico.
3. **Algoritmo Genético:** Seleção por torneio ($k=3$), cruzamento OX (*Order Crossover*), mutação por troca (*swap mutation*) e elitismo estrito.
4. **Análise Comparativa:** Avaliação estatística de custo final, taxa de convergência e desvio-padrão ao longo de 30 rodadas independentes com sementes controladas.
