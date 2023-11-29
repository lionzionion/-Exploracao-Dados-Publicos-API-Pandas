#  Explorando Dados Públicos com Python: Uma Jornada com API e Pandas

## Introdução

Olá, comunidade! Recentemente, tive a oportunidade de mergulhar em uma fascinante jornada de exploração de dados públicos, utilizando Python, APIs (Application Programming Interfaces), e a poderosa biblioteca Pandas. Neste artigo, compartilharei minha experiência e os passos que segui para realizar análises específicas e interações com uma API.

## Objetivo do Trabalho

O objetivo principal era extrair dados de uma API governamental, realizar análises exploratórias e criar funcionalidades para entender melhor as informações disponíveis.

## Passo 1: Interagindo com a API

Comecei minha jornada realizando consultas a uma API pública que fornece dados sobre pedidos de verificação de limites. Construí uma função Python flexível que aceita parâmetros como UF (Unidade Federativa) e tipo de interessado ('Estado' ou 'Município') para buscar informações específicas.

# Código da função

```python
def consulta_api(uf, tipo_interessado):
    # ... (implementação detalhada no código)
```

## Passo 2: Análises Exploratórias

Explorando os dados, identifiquei os três status mais frequentes das solicitações e suas respectivas frequências. Além disso, criei uma nova variável para extrair o ano do status, permitindo análises temporais.

# Código para análises exploratórias

```python
top_status = df['status'].value_counts().head(3)
df['ano_status'] = df['data_status'].str.slice(0, 4)
freq_ano_status = df['ano_status'].value_counts()
```

## Passo 3: Consultas Específicas

Realizei consultas específicas, como contar o número de solicitações arquivadas por decurso de prazo para o estado de Minas Gerais.

# Código para contar solicitações arquivadas para Minas Gerais

```python
num_solic_arquivadas_minas = df_minas_gerais[df_minas_gerais['status'] == 'Arquivado por decurso de prazo'].shape[0]
```

## Passo 4: Salvando Resultados

Finalmente, salvei os resultados em arquivos CSV para compartilhar e revisitar as análises posteriormente.

# Código para salvar os dados em arquivo CSV

```python
df_bahia_estado.to_csv('solicitacoes_bahia_estado.csv', index=False)
```

## Conclusão

Esta jornada proporcionou uma compreensão mais profunda da interação entre Python, APIs e Pandas. A flexibilidade e poder dessas ferramentas oferecem inúmeras possibilidades para explorar e entender conjuntos de dados complexos.

Encorajo todos a explorar dados públicos, aplicar análises exploratórias e contribuir para a comunidade de ciência de dados. O código completo e os detalhes estão disponíveis no meu repositório do GitHub.

Espero que este artigo tenha sido informativo e inspirador para aqueles que desejam embarcar em jornadas semelhantes. Estou ansioso para receber feedback e sugestões da comunidade.

Obrigado pela leitura!

Atenciosamente,
Leandro Amadeu Lima Dias
