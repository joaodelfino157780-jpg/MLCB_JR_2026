#========== PRODUÇÃO DO RELATÓRIO AULA 01 ==============
# 1 - Com a remoção dos stopwords no vocabulário, os resultados finais terão menos assertividades.
# 2 - Ele serve para auxiliar na sequência de palavras do stopwords, garantindo maior número de assertividade.
# 3 - Não, ela não ajuda pelo fato das stopwords estarem auxiliando na classificação das intenções.


#========== PRODUÇÃO DO RELATÓRIO AULA 02 ==============
# 1 - A métrica PRECISION representa precisão no número de acerto referente aos dados. A métrica 
RECALL representa a quantidade de acertos encontrados, garantindo assim sua média. A métrica F1-Score representa equilíbrio que há entre elas, ou seja, se a quantidade de acertos for de 90%, e a de erros for de 10%, haverá um desequilíbrio, então o F1_SCORE serve para captar esse desbalanceamento.
# 2 - Ela serve como a linha de acertos, onde na tabela os valores de acerto tem que ser maior do que os valores de erro, e isso deve ser medido na linha diagonal. Onde a matriz Principal representa os verdadeiros positivos.
# 3 - Pois ela mostra apenas os acertos reais, ignorando completamente a quantidade de erros.



#========== PRODUÇÃO DO RELATÓRIO AULA 03 ==============
# 1 - import pandas as pd
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# 1. Seus dados (Fechando a chave que faltava no seu dicionário)
dados_rh = {
    'mensagem': [
        'Como solicitar minhas ferias?', 'Quero agendar meu periodo de ferias',
        'Onde baixo meu holerite do mes?', 'Preciso do comprovante de rendimentos',
        'Como cadastrar meu atestado medico?', 'Onde envio o atestado de consulta?',
        "Como Solicito a carta de demissão?", "Quero pedir meu aviso-Prévio"
    ],
    'intencao': [
        'solicitar_ferias', 'solicitar_ferias',
        'obter_holerite', 'obter_holerite',
        'enviar_atestado', 'enviar_atestado',
        "Carta_demissão", "Solicitação_Aviso-Prévio"
    ]
}

# 2. Criando o DataFrame
df = pd.DataFrame(dados_rh)
X = df['mensagem']
y = df['intencao']

# 3. Montando o Pipeline
pipeline = Pipeline([
    ('vectorizer', TfidfVectorizer(stop_words=['de', 'o', 'meu', 'minhas'])),
    ('classifier', LogisticRegression())
])

# 4. Treinando com TODOS os dados (já que a base é minúscula)
pipeline.fit(X, y)

# 5. Avaliando as predições nos mesmos dados
y_pred = pipeline.predict(X)
acuracia = accuracy_score(y, y_pred)

print(f"Acurácia do modelo: {acuracia * 100:.2f}%")


df3 = pd.DataFrame(dados_rh)

# TODO 1: Separe o dataset em X ('mensagem') e y ('intencao')
X = df3['mensagem']
y = df3['intencao']

# TODO 2: Realize a divisão em treino (70%) e teste (30%) com random_state=42
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# TODO 3: Monte o Pipeline encapsulando o TfidfVectorizer e a LogisticRegression
pipeline = Pipeline([
    ('vectorizer', TfidfVectorizer(stop_words=['de', 'o', 'meu', 'minhas'])),
    ('classifier', LogisticRegression())
])

# TODO 4: Treine o pipeline completo com .fit() usando os dados de treino brutos
pipeline.fit(X_train, y_train)


# TODO 5: Faca a predicao nos dados de teste brutos e exiba a acuracia
predicoes = pipeline.predict(X_test)
print(f"Acuracia via Pipeline: {accuracy_score(y_test, predicoes) * 100:.2f}%")

Acurácia do modelo: 100.00%
Acuracia via Pipeline: 0.00%

# 2 - Diminui o vazamento de dados dentro do resultado.

# 3 - Pois eles mesmo já servem para filtrar as mensagens e garantir via treino e teste que elas sejam filtradas corretamente. 
