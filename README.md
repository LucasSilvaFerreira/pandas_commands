
#Comandos do Pandas

```python
df_criado_com_hash = pd.DataFrame({'nome_da_col1':[1,2,3,4], 'nome_da_col2':['a','b', 'c', 'd']}) 
```
  Criar um dataframe é simples. É só utilizar as chaves como nome das colunas e um array de valores como o valor da chave

```python
table_df = pd.read_table('path/da/tabela', delimiter='\t')  
```
 Abrindo a tabela usando arquivo

```python
table_df_sem_duas_ultimas_colunas =  table_df.iloc[:, 0:-2]      
```
 Retirando  as duas ultimas colunas

```python
table.df.apply(lambda x:len([y for y in x if y>1]) ,axis=1)  
```
Passa a linha como entrada de uma funcãoe retorna quantos elementos são maiores do que 1.

```python
table_df = table_df.iloc[np.random.permutation(len(table_df))]   
```
 Fazendo um embaralhamento nos valores da tabela

```python
table_df.shape[1] 
```
 Retorna o numero de colunas (1 ou linhas 0)


```python
table_df.columns.values 
```
 retorna nome das colunas


```python
del table_df['nome_da_coluna_a_deletar']  
```
 deleta uma coluna do dataframe


```python
table_df['nova_coluna'] = 'valor default da nova coluna' 
```
 cria uma nova coluna no df e adiciona o valor a todos os campos


```python
table_df['nova_coluna'] = [1,2,3,4,5]    
```
 Cria uma nova coluna e adiciona valores de um array com a mesma quantidade de linha que o dataframe


```python
table_df['nome_da_coluna'].max(axis=1, numeric_one = True) 
```
 Retorna o maior valor de cada linha (igonorando valores não numéricos). Obs esse valor pode ser adicionado a uma nova coluna usando essa saida com o comando de cima


```python
table_df[['coluna1', 'coluna2', 'coluna3']].apply(minha_funcao, axis=1) 
```
 Passa como parametro de minha_funcao as n colunas escolhidas . axis= Faz com que table_df seja lido por linhas.


```python
table_df.apply(minha_funcao, axis=0) 
```
Passa como parametro de minha_funcao cada coluna.


```python
np.array_split(table_df[['coluna1', 'coluna2', 'coluna3']], 10)  
```
 Divide table_df em 10 dataframes diferentes. Cada array contem apenas os valores das colunas indicadas.


```python
tabela_filtrada = tabela.query('idade < 20 and peso == 70')
```
Filtrando um Data Frame utilizando o comando query

```python
table_df[table_df['coluna_com_flag_desejada'].isin(['YES'])] 
```
 retorna apenas as colunas com 'YES' na coluna 'coluna_com_flag_desejada'


```python
table_df['coluna_com_valores_desejados'].groupby([table_df['coluna_com_flags_dos_grupos_diferentes_1'], table_df['coluna_com_flags_dos_grupos_diferentes_2']])  
```
 retorna n arrays separados. sendo n o numero de possiveis flags dentro da coluna (nesse caso da coluna 'coluna_com_flags_dos_grupos_diferentes')


```python
pd.melt(pd.DataFrame({'a':{1,2,3,4}, 'b':{1,2,3,4}, 'c':{1,2,3,4}})) 
```
 faz um melt na hash possibilitando o plot de multiplos graficos no ggplot


```python
pd.DataFrame.to_csv(table_df, 'tabela.txt' , sep='\t', index=False) 
```
 salvando dataframe inteiro






