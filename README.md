# Classification Project (Credit Score)
 
Projeto criado com a intenção de desenvolver um modelo de **análise de score de crédito dos clientes de uma instituição financeira por meio de algoritmos de classificação de machine learning**. Dessa forma, o desafio é analisar o banco de dados e criar um modelo capaz de ler as informações do cliente e **avaliar de forma preditiva e automatizada se o score de crédito dele é descrito como “Ruim”, “Médio” ou “Bom”**. <br/>

1) Para tanto, os seguintes passos listados abaixo foram adotados:<br/>
2) Entendimento do desafio da empresa<br/>
3) Importação da base de dados<br/>
4) Preparação da base de dados para a inteligência artificial<br/>
5) Desenvolvimento e treinamento de um modelo de IA -> Score de crédito “Ruim”, “Médio” ou “Bom”<br/>
6) Escolher o melhor modelo<br/>
7) Usar o modelo desenvolvido em um cenário real<br/>

Com a lista de passos em mãos, o desenvolvimento do código seguiu o seguinte raciocínio:<br/>
I) importação das bibliotecas necessárias para a análise: Scikit-learn e Pandas<br/>
II) leitura do arquivo .csv<br/>
III) visualização da tabela<br/>
IV) identificação e remoção de valores vazios<br/>
V) para a utilização da Inteligência Artificial, são necessários 3 passos: importar, criar e treinar<br/>
VI) sabendo que a **IA apenas consegue entender números e não textos**, as colunas de texto, portanto, precisam ser alteradas para números. Dessa forma, deve-se ser atribuído um valor para cada informação de texto existente nas colunas<br/>
VII) transformação das colunas de texto em números, **excluindo-se apenas a coluna de Score de Crédito**, que é a coluna que se almeja calcular<br/>
VIII) **retirada das colunas que não serão usadas na previsão**: ID do cliente, por não trazer informações relevantes para o modelo, e de score_credito, por ser a que se deseja determinar<br/>
IX) **escolha das colunas a serem usadas no modelo** (y = score_credito, que é a coluna a ser prevista, e x = todas as outras colunas)<br/>
X) separação dos **dados em treino e teste**, sendo **70% de treino para os modelos aprenderem e 30%** de teste para testar se o modelo aprendeu corretamente<br/>
XI) os modelos selecionados para fazer esse teste foram:  **Random Forest, árvore de decisão e  KNN (k-Nearest Neighbors)**<br/>
XII) treinamentos dos modelos<br/>
XIII) cálculo das previsões<br/>
XIV) comparação das previsões com o y_teste (score_credito)<br/>
XV) determinação da **acurácia** do modelo<br/>
XVI) resultado: melhor modelo para esse projeto é o **Random Forest**, com **82,64% de acurácia** enquanto os modelos de árvore de decisão e KNN obtiveram respectivamente 73,51% e 73,24% <br/>

<table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>Acurácia (em %)</th>
    </tr>
    <tr>
        <th>Random Forest</th>
        <td>82.64%</td>
    </tr>
    <tr>
         <th>Árvore de Decisão</th>
        <td>73.51%</td>
    </tr>
    <tr>
        <th>KNN</th>
        <td>73.24%</td>
</table>

XVII) execução de previsões com a nova base dados de novos_clientes <br/>
XVIII) **análise preditiva** do score de crédito dos novos clientes<br/>
XIX) observação de quais colunas foram importantes no desenvolvimento do score de crédito<br/>

Com tais resultados, portanto, nota-se que as seguintes **variáveis foram determinantes** para o modelo Random Forest:<br/>
I) Total em dívidas<br/>
II) Mix de créditos<br/>
III) Total de juros em empréstimos<br/>
IV) Dias de atraso com o pagamento da fatura<br/>
