# Estatística Descritiva Aplicada à Engenharia Química
Este script utiliza Python para realizar análises estatísticas básicas de parâmetros de processos químicos, como temperatura, pressão e eficiência.

## Funcionalidades
- Cálculo de estatísticas descritivas: média, mediana, moda, desvio padrão e variância.
- Análise de correlação entre variáveis.
- Visualização de dados com gráficos interativos.

## Como Usar
1. Certifique-se de ter Python instalado (versão 3.8 ou superior).

##########################################################CODIGO##########################################################
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats

def estatistica_eng_quimica():
    print("Bem-vindo à Estatística Descritiva Aplicada à Engenharia Química!")
    print("Vamos analisar os dados operacionais de um processo químico fictício.\n")

    # Simular dados de um processo químico
    np.random.seed(42)  # Garantir reprodutibilidade
    temperatura = np.random.normal(200, 5, 30)  # Temperatura em °C
    pressao = np.random.normal(10, 1, 30)       # Pressão em atm
    eficiencia = np.random.uniform(80, 95, 30)  # Eficiência em %

    # Criar um DataFrame com os dados
    df = pd.DataFrame({
        "Temperatura (°C)": temperatura,
        "Pressão (atm)": pressao,
        "Eficiência (%)": eficiencia
    })
    print("Dados Operacionais (Amostras):\n", df.head())

    # Calcular medidas estatísticas
    medidas = df.describe()
    print("\nResumo Estatístico:")
    print(medidas)

    # Analisar correlação
    correlacao = df.corr()
    print("\nMatriz de Correlação:")
    print(correlacao)

    # Gráficos
    print("\nGerando gráficos para visualização dos dados...")
    plt.figure(figsize=(12, 6))

    # Histograma de Temperatura
    plt.subplot(1, 3, 1)
    plt.hist(temperatura, bins=10, color='blue', alpha=0.7, edgecolor='black')
    plt.title("Distribuição de Temperatura")
    plt.xlabel("Temperatura (°C)")
    plt.ylabel("Frequência")

    # Gráfico de dispersão: Pressão x Temperatura
    plt.subplot(1, 3, 2)
    plt.scatter(temperatura, pressao, color='green', alpha=0.7)
    plt.title("Pressão vs. Temperatura")
    plt.xlabel("Temperatura (°C)")
    plt.ylabel("Pressão (atm)")

    # Histograma de Eficiência
    plt.subplot(1, 3, 3)
    plt.hist(eficiencia, bins=10, color='orange', alpha=0.7, edgecolor='black')
    plt.title("Distribuição de Eficiência")
    plt.xlabel("Eficiência (%)")
    plt.ylabel("Frequência")

    plt.tight_layout()
    plt.show()

    # Explicação
    print("\nInterpretação:")
    print("1. Estatísticas como média e desvio padrão ajudam a entender a estabilidade do processo.")
    print("2. A matriz de correlação indica relações entre variáveis, como temperatura e pressão.")
    print("3. Histogramas ajudam a visualizar a distribuição e detectar anomalias.")

if __name__ == "__main__":
    estatistica_eng_quimica()


########################################################## GERANDO DADOS ##########################################################
![image](https://github.com/user-attachments/assets/40a622ed-03aa-4b41-8078-7fe804ab324d)


########################################################## GERANDO TABELAS ##########################################################
![image](https://github.com/user-attachments/assets/bdd94b42-e54d-40ba-a4e6-13cba0e80759)

########################################################## INTERPRETAÇÃO ##########################################################
![image](https://github.com/user-attachments/assets/cb4a5035-d8cf-418d-bf12-47b9efae1d78)





