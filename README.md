# Diagrama de Energia Livre de Gibbs - Conformações de Reação

Este repositório contém um script em Python para visualização de perfis de energia livre de Gibbs (diagramas de coordenada de reação). O código compara barreiras de ativação e energias de reação para quatro conformações distintas (B1, B2, D1 e D2).

## Metodologia e Origem dos Dados

As constantes termodinâmicas utilizadas neste script não são arbitrárias. Elas foram obtidas através de cálculos de química quântica utilizando o software **Gaussian**. 

Devido ao custo computacional do nível de teoria empregado (**R.nitrato/aug-cc-pVDZ**), as simulações foram executadas em um **cluster de computação de alto desempenho (HPC)**. Foram realizadas:
1.  Otimizações de geometria e cálculo de frequências para os Reagentes e Produtos.
2.  Busca e validação dos Estados de Transição (TS) para determinar as energias de ativação.

Os valores extraídos dos arquivos de saída (`.out` / `.log`) do Gaussian foram convertidos para kcal/mol e inseridos neste script para a geração do gráfico de alta qualidade.

## O Gráfico Gerado

O script modela a transição energética usando funções gaussianas emendadas, gerando curvas suaves:
*   **Círculos (o):** Reagentes (mínimo reagente)
*   **Quadrados (s):** Estado de Transição (máximo energético / Barreira)
*   **Triângulos (^):** Produtos (mínimo produto)

## Parâmetros Termodinâmicos Utilizados (kcal/mol)


| Conformação | Reagentes ($\Delta G$) | Ativação ($\Delta G^\ddagger$) | Produtos ($\Delta G$) |
| :--- | :---: | :---: | :---: |
| **B1** | 0.0 | 8.34 | -12.63 |
| **B2** | 0.0 | 11.12 | -5.79 |
| **D1** | 0.0 | 10.39 | -12.60 |
| **D2** | 0.0 | 11.22 | -1.33 |

## Como Executar o Script

### Pré-requisitos
Você precisará do Python 3 instalado e das bibliotecas listadas em `requirements.txt`.

### 1. Clonar o repositório
```bash
git clone https://github.com
cd nome-do-repositorio
```

### 2. Instalar as dependências
```bash
pip install -r requirements.txt
```

### 3. Executar o código
```bash
python plot_reaction.py
```

## Tecnologias Utilizadas
*   **Python 3**
*   **Matplotlib** (Plotagem gráfica)
*   **NumPy** (Cálculos vetoriais)
