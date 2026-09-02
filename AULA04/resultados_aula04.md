-------------- RESULTADOS ----------------

1-   precision    recall  f1-score   support

     consultas       1.00      0.88      0.93         8
financiamentos       0.88      1.00      0.93         7
 investimentos       1.00      1.00      1.00         8
    pagamentos       1.00      1.00      1.00         7

      accuracy                           0.97        30
     macro avg       0.97      0.97      0.97        30
  weighted avg       0.97      0.97      0.97        30

[[7 1 0 0]
 [0 7 0 0]
 [0 0 8 0]
 [0 0 0 7]]

=== INICIANDO BATERIA DE TESTES (10 INPUTS OBRIGATÓRIOS) ===

[Teste 1/10]
Digite a frase do cliente: Corinthians é maior que o Palmeiras?
Fallback: encaminhando para atendimento humano.

[Teste 2/10]
Digite a frase do cliente: Ferrari é melhor que Mercedes?
Fallback: encaminhando para atendimento humano.

[Teste 3/10]
Digite a frase do cliente: Senna é maior que Hamilton 
Fallback: encaminhando para atendimento humano.

[Teste 4/10]
Digite a frase do cliente: Neymar é melhor que messi?
Fallback: encaminhando para atendimento humano.

[Teste 5/10]
Digite a frase do cliente: Luis é Gay ?
Fallback: encaminhando para atendimento humano.

[Teste 6/10]
Digite a frase do cliente: Champions ou Libertadores ? 
Fallback: encaminhando para atendimento humano.

[Teste 7/10]
Digite a frase do cliente: Free Fire ou Fortnite ? 
Fallback: encaminhando para atendimento humano.

[Teste 8/10]
Digite a frase do cliente: futebol ou basquete ?
Fallback: encaminhando para atendimento humano.

[Teste 9/10]
Digite a frase do cliente: Brasil ou Argentina ? 
Fallback: encaminhando para atendimento humano.

[Teste 10/10]
Digite a frase do cliente: Coca ou Pepsi ? 
Fallback: encaminhando para atendimento humano.

2 - Dataset de móveis criado com sucesso!

Distribuição das intenções:
intencao
vendas                20
suporte               20
trocas_devolucoes     20
reclamacoes           20
logistica_entregas    20
Name: count, dtype: int64

========================================
MATRIZ DE CONFUSÃO
========================================
[[4 0 0 0 2]
 [1 4 1 0 0]
 [0 0 6 0 0]
 [0 0 1 5 0]
 [0 0 0 1 5]]

========================================
RELATÓRIO DE CLASSIFICAÇÃO
========================================
                    precision    recall  f1-score   support

logistica_entregas       0.80      0.67      0.73         6
       reclamacoes       1.00      0.67      0.80         6
           suporte       0.75      1.00      0.86         6
 trocas_devolucoes       0.83      0.83      0.83         6
            vendas       0.71      0.83      0.77         6

          accuracy                           0.80        30
         macro avg       0.82      0.80      0.80        30
      weighted avg       0.82      0.80      0.80        30


========================================
TESTES MANUAIS - 8 FRASES
========================================

[Teste 1/8]
Digite a frase do cliente: Quero comprar um sofá
Intenção identificada: trocas_devolucoes
Confiança: 100.00%

[Teste 2/8]
Digite a frase do cliente: Como montar meu armário?
Intenção identificada: logistica_entregas
Confiança: 100.00%

[Teste 3/8]
Digite a frase do cliente: Quero devolver minha mesa
Intenção identificada: reclamacoes
Confiança: 100.00%

[Teste 4/8]
Digite a frase do cliente: Minha cadeira veio quebrada.
Intenção identificada: reclamacoes
Confiança: 100.00%

[Teste 5/8]
Digite a frase do cliente: Quero reclamar do serviço
Intenção identificada: trocas_devolucoes
Confiança: 100.00%

[Teste 6/8]
Digite a frase do cliente: Onde está meu pedido?
Intenção identificada: logistica_entregas
Confiança: 100.00%

[Teste 7/8]
Digite a frase do cliente: Preciso do meu boleto
Intenção identificada: logistica_entregas
Confiança: 100.00%

[Teste 8/8]
Digite a frase do cliente: Boleto com valor errado 
Intenção identificada: trocas_devolucoes
Confiança: 100.00%

2.1 - O KNN lidou bem com as frases diferentes das usadas no treinamento. Quando não reconheceu uma intenção, o sistema acionou o fallback e encaminhou para atendimento humano. Nos 10 testes, acertou em 100% dos casos.

2.2 - O KNN teve 80% de acurácia e apresentou alguns erros. Para saber se a Árvore de Decisão foi melhor, é preciso comparar os resultados dos dois modelos.

3 - O melhor modelo é o KNN, pois obteve 97% de acurácia no primeiro teste e 80% no dataset de móveis. Além disso, o fallback funcionou bem, encaminhando corretamente as frases que estavam fora das categorias. Por isso, o KNN se mostrou uma boa opção para este projeto.
