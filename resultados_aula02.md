# Para a entrega completa deste LAB01 você precisa copiar a saída do código (output) e adicionar as repostas das perguntas abaixo:
# 1 - Avaliem os resultados e verifiquem se os resultados foram corretos ou incorretos. Coloque a resposta no arquivo do relatório do laboratório
# 2 - Detectado algum erro, qual seria a maneira mais correta de melhorar o resultado do algoritmo?
# 3 - Detalhe a função do LogisticRegression no algorítmo.

#========== PRODUÇÃO DO RELATÓRIO:==============

--- RESULTADOS DO LAB 01 ---
Mensagem: 'Quero consultar quanto dinheiro tenho' ==> Intenção Predita: [fazer_pix]
Mensagem: 'Pode me ajudar a fazer um pix?' ==> Intenção Predita: [fazer_pix]
Mensagem: 'Gostaria de cancelar meu cartão de crédito' ==> Intenção Predita: [cancelar_conta]

2 - O erro foi na primeira mensagem. Minha solução foi incluir mais uma frase no Dataset em mensagem, e incluir em intencao mais uma vez consultar_conta.

3 - A Logistc Regression ele cria um classificador e o modelo.fit ele treina, para depois poder ser usado.



# Para a entrega completa deste LAB02 você precisa copiar a saída do código (output) e adicionar as repostas das perguntas abaixo:
# 1 - Avaliem os resultados e verifiquem se os resultados foram corretos ou incorretos. Coloque a resposta no arquivo do relatório do laboratório
# 2 - Detectado algum erro, qual seria a maneira mais correta de melhorar o resultado do algoritmo?
# 3 - Detalhe a função do Naive Bayes no algorítmo.

--- RESULTADOS DO LAB 02 ---
Mensagem de Teste: 'Gostaria de devolver o produto que comprei'
Intenção Predita: troca_devolucao

--- Distribuição de Probabilidades por Classe ---
Classe [duvida_frete]: 27.99%
Classe [rastrear_pedido]: 24.54%
Classe [troca_devolucao]: 47.46%

2 - Não houve erro.

3 - O Naive Bayes no algoritmo é responsável por criar tarefa de classificação.



# Para a entrega completa deste LAB03 você precisa colar o código corrigido com os TODOs preenchidos, a acurácia obtida e responder:
# 1 - Qual foi a acurácia obtida pelo modelo no conjunto de teste e por que, em um dataset tão pequeno (9 exemplos), essa métrica pode ser enganosa?
# 2 - Como o modelo de Árvore de Decisão (DecisionTreeClassifier) toma a decisão de separar as intenções do usuário?
# 3 - Qual é o risco de utilizar uma Árvore de Decisão sem limite de profundidade (max_depth) em datasets de texto maiores?

--- RESULTADOS DO LAB 03 ---
Acurácia do Modelo: 33.33%
Eu acho que não deve ser enganosa, pelo fato de termos dado 9 opções para mensagem, em uma divisão de 100% o resultado para qualquer uma será sempre 33,33%.

2 - Ele toma decisões por meio de Sim e Não.

3 - pelo fato de gerar uma árvore muito grande pode ter o risco de não trazer respostas com tanta precisão.
