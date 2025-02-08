## Exercício:

Chegou a hora de você testar os conhecimentos desenvolvidos durante a aula. Continuando com o projeto das laranjas/toranjas agora você deve selecionar parte dos dados. As colunas que iremos avaliar são as de diâmetro e peso. Crie arrays específicos para guardar o diâmetro e peso da laranja e toranja. O diâmetro está na coluna zero e o peso na coluna 1. Os dados referentes a laranja vão até a linha 4999 e os referentes à toranja iniciam na linha 5000 do arquivo.

Após fazer a seleção de dados, importe a biblioteca matplotlib e crie um gráfico para a laranja e para a toranja do peso pelo diâmetro.


import numpy as np # Importação da biblioteca NumPy

url = "https://raw.githubusercontent.com/Marina-Falcao-DEV/Dataset_Citrus_Alura_Numpy/refs/heads/main/citrus.csv"

dados_total_citrus = np.loadtxt(url, delimiter = ",", skiprows = 1, usecols = np.arange(1, 6, 1)) # Ajustes para criação do array com os valores (excluindo a primeira coluna e a primeira linha)
print(dados_total_citrus)

# Verificando as características do array completo:
print("-"*20, "CARACTERÍSTICAS DO ARRAY (COMPLETO)","-"*20)
print(f"\nEste é um dataset com {dados_total_citrus.ndim} dimensões.") # Verificando quantas dimensões tem o array
print(f"Este é um dataset com {dados_total_citrus.shape[0]} linhas e {dados_total_citrus.shape[1]} colunas.") # Verificando a quantidade e linhas e colunas do array
print(f"Este é um dataset com {dados_total_citrus.size} elementos.") # Verificando o número de itens do array
print("="*77)

# Filtrando as colunas de diâmetro [posição 0] e peso [posição 1] do array total e criação de arrays específicos para laranjas e toranjas:
diametro_laranja = dados_total_citrus[:5000, 0]
diametro_toranja = dados_total_citrus[5000: , 0]
peso_laranja = dados_total_citrus[ :5000, 1]
peso_toranja = dados_total_citrus[5000: , 1]

# Criação do gráfico diâmetro X peso [laranjas X toranjas]:
import matplotlib.pyplot as plt
plt.plot(diametro_laranja, peso_laranja)
plt.plot(diametro_toranja, peso_toranja)
plt.legend(["Laranjas", "Toranjas"])


