
# Predição de TEA com Rastreamento Ocular, GRU e Bi-LSTM

Este projeto faz parte de um Trabalho de Conclusão de Curso sobre a aplicação de modelos de aprendizado profundo em dados temporais de rastreamento ocular.

O objetivo é desenvolver e avaliar modelos GRU e Bi-LSTM para identificar padrões associados ao Transtorno do Espectro Autista (TEA) em crianças, comparando participantes classificados como:

- `ASD`: Transtorno do Espectro Autista;
- `TD`: desenvolvimento típico.

O projeto utiliza notebooks Jupyter para executar as etapas de análise exploratória, pré-processamento, treinamento e avaliação dos modelos.

> Os modelos possuem finalidade acadêmica e não substituem o diagnóstico clínico realizado por profissionais especializados.

---

## Estrutura do projeto

```text
CODIGO_TCC/
│
├── data/
│   └── raw/
│       ├── Eye-tracking Output/
│       └── Metadata_Participants.csv
│
├── notebooks/
│   ├── 00_eda_baseline.ipynb
│   ├── 01_preprocess_baseline.ipynb
│   ├── 02_bilstm_baseline.ipynb
│   └── 02_gru_baseline.ipynb
│
├── venv/
├── .gitignore
├── README.md
└── requirements.txt
````

---

# Como executar o projeto

## 1. Abrir a pasta do projeto

No PowerShell, acesse a pasta principal:

```powershell
cd C:\Users\joao\Documents\codigo_tcc
```

Ajuste o caminho caso o projeto esteja armazenado em outro local.

---

## 2. Criar o ambiente virtual

Dentro da pasta principal do projeto, execute:

```powershell
python -m venv venv
```

---

## 3. Ativar o ambiente virtual

No PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Quando o ambiente estiver ativo, o terminal deverá apresentar algo semelhante a:

```text
(venv) PS C:\Users\joao\Documents\codigo_tcc>
```

Caso o PowerShell bloqueie a ativação, execute:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

Depois, ative novamente:

```powershell
.\venv\Scripts\Activate.ps1
```

---

## 4. Instalar as dependências

Com o ambiente virtual ativado:

```powershell
python -m pip install -r requirements.txt
```

---

## 5. Registrar o ambiente no Jupyter

Instale o suporte ao kernel:

```powershell
python -m pip install ipykernel
```

Depois, registre o ambiente:

```powershell
python -m ipykernel install --user --name codigo_tcc --display-name "Python (codigo_tcc)"
```

---

## 6. Preparar o conjunto de dados

Baixe o conjunto de dados disponível em:

```text
https://www.kaggle.com/datasets/imtkaggleteam/eye-tracking-autism
```

Organize os arquivos da seguinte forma:

```text
data/
└── raw/
    ├── Eye-tracking Output/
    │   ├── arquivo_01.csv
    │   ├── arquivo_02.csv
    │   └── ...
    └── Metadata_Participants.csv
```

Os arquivos de rastreamento ocular devem ficar em:

```text
data/raw/Eye-tracking Output/
```

O arquivo de metadados deve ficar em:

```text
data/raw/Metadata_Participants.csv
```

---

## 7. Selecionar o kernel no VS Code

Abra um dos notebooks no Visual Studio Code.

No canto superior direito:

1. clique em `Select Kernel`;
2. selecione `Python (codigo_tcc)`;
3. confirme que o interpretador utilizado corresponde ao ambiente virtual:

```text
CODIGO_TCC\venv\Scripts\python.exe
```

---

## 8. Executar os notebooks

Os notebooks devem ser executados nesta ordem:

```text
1. notebooks/00_eda_baseline.ipynb
2. notebooks/01_preprocess_baseline.ipynb
3. notebooks/02_bilstm_baseline.ipynb
4. notebooks/02_gru_baseline.ipynb
```

Para executar uma célula:

```text
Shift + Enter
```

Para executar o notebook completo, utilize o botão:

```text
Run All
```

---

## Etapas executadas

### `00_eda_baseline.ipynb`

Realiza:

* leitura dos arquivos de rastreamento ocular;
* integração dos arquivos CSV;
* remoção de participantes não identificados;
* integração com os metadados;
* análise inicial da base;
* geração da base consolidada.

### `01_preprocess_baseline.ipynb`

Realiza:

* limpeza dos dados;
* tratamento de valores ausentes;
* conversão das variáveis;
* engenharia de atributos;
* organização temporal;
* padronização;
* geração da base utilizada pelos modelos.

### `02_bilstm_baseline.ipynb`

Realiza:

* criação das janelas temporais;
* divisão dos participantes;
* treinamento da Bi-LSTM;
* avaliação por janela e participante;
* geração de métricas e gráficos.

### `02_gru_baseline.ipynb`

Realiza:

* criação das janelas temporais;
* divisão dos participantes;
* treinamento da GRU;
* avaliação por janela e participante;
* geração de métricas e gráficos.

---

## Ordem geral do pipeline

```text
Dados brutos
    ↓
Análise exploratória
    ↓
Integração com os metadados
    ↓
Pré-processamento
    ↓
Engenharia de atributos
    ↓
Construção das janelas temporais
    ↓
Treinamento da Bi-LSTM
    ↓
Treinamento da GRU
    ↓
Avaliação dos modelos
```

---

## Autor

**João Pasip**

Projeto desenvolvido para fins acadêmicos nas áreas de inteligência artificial, aprendizado profundo, rastreamento ocular e saúde digital.

```

