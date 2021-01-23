# airbnb_rj
airbnb Rio de Janeiro analysis

a. Como foi a definição da sua estratégia de modelagem?
A predição do preço parece a opção mais desafiadora, com preços não podendo ser negativos e com a presença de outliers.
b. Como foi definida a função de custo utilizada?
Com a restrição de não negatividade uma distribuição adequada é a gamma (ou tweedie), sendo minimizado o deviance. 
c. Qual foi o critério utilizado na seleção do modelo final?
Para comparar os modelos o deviance (gamma) médio foi comparado no banco de teste.
d. Qual foi o critério utilizado para validação do modelo?
- No modelo gamma um grid search foi feito com 5-fold-CV e no finalista não foi realizado uma busca de hiperparâmetros.
De qualquer modo, o banco foi separado 60% para treino dos modelos (validação cruzada feita sobre o treino no caso da gamma),
20% para validação dos modelos, seleção do finalista e 20% final para estimar métricas de erro/diagnosticar.
Por que escolheu utilizar este método?
- A separação de uma parcela da amostra para validação é uma metodologia bem difundida e adequada para estimar métricas de erro.
e. Quais evidências você possui de que seu modelo é suficientemente bom?
- Comparando o modelo finalista com um modelo Dummy(mediana), Benchmark(gamma-poucas variáveis) e um Gamma(vários parâmetors + grid search) o modelo final um boosting, apresentou uma melhora significativa no deviance médio perante os demais modelos. Além disso, a média está bem calibrada e um gráfico de dispersão dos preditos X atuais mostra boa aderência dos valores no banco Hold-Out.
