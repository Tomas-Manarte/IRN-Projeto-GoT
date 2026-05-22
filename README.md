# Análise da Rede Social de Game of Thrones

Projeto GRC & IRN | ISCTE-Sintra | 2025/2026

Análise da rede de coocorrências das personagens de Game of Thrones (T1–T8)
usando teoria de grafos, redes complexas e Graph Convolutional Networks.

## Estrutura do repositório

```
IRN-Projeto-GoT/
├── data/                    # dataset (não incluído)
│   ├── nodes/               # got-s1-nodes.csv ... got-s8-nodes.csv
│   └── edges/               # got-s1-edges.csv ... got-s8-edges.csv
├── entregavel_3/
│   └── IRN_projeto_fase3_V2.ipynb   # notebook principal
├── requirements.txt
└── README.md
```

## Setup

### 1. Deszipar e abrir no VSCode

Descompacta a pasta e abre-a no VSCode:

```
File → Open Folder → seleciona a pasta IRN-Projeto-GoT
```

### 2. Criar o ambiente virtual

Abre o terminal no VSCode (`Ctrl + '`) e corre:

```bash
python -m venv .venv
```

Ativar:

- **Windows (PowerShell):** `.venv\Scripts\Activate.ps1`
- **Windows (CMD):** `.venv\Scripts\activate.bat`
- **Mac/Linux:** `source .venv/bin/activate`

### 3. Instalar dependências

```bash
pip install -r requirements.txt
```

Para a versão PyTorch Geometric (opcional):

```bash
pip install torch-geometric
```

Se não instalares o torch-geometric, o notebook funciona na mesma
— usa apenas a GCN from-scratch.

### 4. Adicionar o dataset

O dataset não está incluído. Descarrega de:

https://github.com/mathbeveridge/gameofthrones

Copia os ficheiros para dentro da pasta `data/` com esta estrutura:

```
data/
├── nodes/
│   ├── got-s1-nodes.csv
│   ├── got-s2-nodes.csv
│   └── ... (até s8)
└── edges/
    ├── got-s1-edges.csv
    ├── got-s2-edges.csv
    └── ... (até s8)
```

### 5. Correr o notebook

Abre o ficheiro `entregavel_3/IRN_projeto_fase3_V2.ipynb` no VSCode
(precisa da extensão Jupyter instalada) e seleciona o kernel `.venv`
quando pedido.

**Importante:** usa sempre `Kernel → Restart & Run All` para garantir
que os resultados são reprodutíveis e os execution counts ficam sequenciais.

## O que o notebook faz

- **Etapa 1** — Carrega e valida os dados das 8 temporadas
- **Etapa 2** — Métricas de rede (mundo pequeno, lei de potência, comunidades, centralidades)
- **Etapa 3** — GCN from-scratch para prever sobrevivência + ablation study
- **Etapa 4** — Simulação de robustez (remoção de hubs, Max-Flow, Mann-Whitney)
- **Etapa 5** — Avaliação final (curva de loss, matriz de confusão, AUC)

## Grupo

Ilie Iftime (112779) · Inês Cruz (123557) · Sofia Quintino (123554) · Tomás Manarte (122090)
