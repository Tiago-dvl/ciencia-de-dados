# Principais Conceitos de Machine Learn (Aprendizado de Máquina)

---

**<mark>O que é um Modelo em Machine Learn?</mark>**

    Modelo é o **resultado de um processo de treinamento** e teste de um algorítimo com dados. O algorítimo, após ter aprendido a executar a tarefa específica na qual foi designinada, se torna um modelo.

<u>Exemplo:</u> Uma criança que aprendeu a diferença entre um cachorro e um gato. 

* <u>Obs:</u> Um modelo de Machine Learn é utilizado para: fazer previsões, classificação, regressão e tomar decisões sobre os novos dados, com base no que já aprendeu.

**<mark>O que são Parâmetros?</mark>**

    São os **valores internos que são ajustados** durante o processo de treinamento de um modelo. Durante o processo de aprendizado de um algorítimo, os parâmetros internos são ajustados, de forma a minimizar os erros da previsão. 

* <u>Obs:</u> Após encontrar os valores adequados, estes se tornam os parâmetros do modelo.

**<mark>O que é Subajuste (Underfiting)?</mark>**

     Quando o modelo foi **treinado de forma superficial**, sem identificar detalhes nos dados. O modelo é **simples demais** para capturar os padrões dos dados, mesmo nos dados de treino.

* <u>Obs:</u> Um modelo subajustado não aprende nem os dados de treino, o que significa que ele não está conseguindo representar a relação entre as variáveis.

* <u>Exemplo:</u> Uma criança viu **poucas fotos** e aprendeu uma regra **muito simples**, como: "Todo animal de 4 patas é um cachorro."

* <u>Como identificar...</u>
  
  * Baixa acurácia, tanto no treino quanto no teste.   
  
  * O erro é alto, mesmo com muitos dados.

* <u>Como Corrigir...</u>
  
  * Usar um modelo Mais complexo (ex: árvore de decisão).
  
  * Adicionar mais variáveis (features).
  
  * Aumentar o tempo de treinamento.
  
  * Remover regularizações excessivas.

    

**<mark>O que é Sobreajuste (Overfiting)?</mark>**

    Quando **o modelo aprende demais os dados de treinamento** ou de forma muito específica, incluindo o "ruído". O modelo irá memorizar ao invés de generalizar.

* Obs: O modelo sobreajustado terá um ótimo desempenho nos dados de treino, mas irá fracassar em dados novos (teste ou produção), por quê nao irá generalizar bem os novos dados.

* Exemplo: Uma criança viu **100 fotos** de cães e gatos, e aprendeu regras muito específicas, como: **"Se o animal tem um laço rosa e está em cima de um tapete azul, é um gato."**

* Como identificar...
  
  * Alta acurácia no treinamento
  
  * Baixa acurácia no teste/validação

* Como Evitar...
  
  * Usar mais dados
  
  * Podar a complexidade do modelo
  
  * Cross-validation

Continuar (precisão e sensibilizade)..



## Métricas Para Análise de Desempenho



**<mark>O que é uma Matriz de Confusão?</mark>**
    É uma tabela que resume o desempenho de um algorítimo de classificação, mostrando os acertos e erros em relação ás classes reais. De forma resumida, a tabela mostra o que o modelo previo com o que era real.

Estrutura da Matriz...

| Classe        | Previsto Positivo        | Previsto Negativo        |
| ------------- | ------------------------ | ------------------------ |
| Real Positivo | Verdadeiro Positivo (VP) | Falso Negativo (FN)      |
| Real Negativo | Falso Positivo (FP)      | Verdadeiro Negativo (VN) |

- **VP (Verdadeiro Positivo)**: o modelo acertou um **positivo**.

- **VN (Verdadeiro Negativo)**: o modelo acertou um **negativo**.

- **FP (Falso Positivo)**: o modelo **errou**, dizendo que era positivo.

- **FN (Falso Negativo)**: o modelo **errou**, dizendo que era negativo.



 ****Exemplo simples (gatos vs não-gatos):****

|                | Previsto Gato | Previsto Não-Gato |
| -------------- | ------------- | ----------------- |
| **É Gato**     | 8 (VP)        | 2 (FN)            |
| **Não é Gato** | 1 (FP)        | 9 (VN)            |

O modelo acertou **8 gatos** e **9 nao-gatos**, erro **1 não-gato** como gato, e deixou **2 gatos** passarem.



* A matriz de confusão ajuda a calcular as métricas:
  
  * Acurácia
  
  * Precisão
  
  * Sensibilidade (Recall)
  
  * F1-Score



**<mark>O que é Precisão(Precision)?</mark>**

    É a **qualidade das previsões positivas** do modelo. Mede **quantos dos ítens** que o modelo previo **como positivos realmente são positivos**.

**Fórmula:** Precisão = Verdadeiros Positivos  / (Verdadeiros positivos +                                      Falsos Positivos)

**Exemplo**: Um modelo para detectar **gatos em fotos**:

- O modelo disse que havia **10 gatos**

- Mas só **7 realmente eram gatos** (3 eram cachorros)

    Então:  Precisão = 7 / (7+3)​ = 7 / 10 = 0,7 ou **70% de Precisão**



**<mark>O que é Sensibilidade(Recall)?</mark>**

    É a capacidade do modelo de encontrar todos os casos positivos reais. Mede quantos dos ítens realmente positivo foram identificados pelo modelo.

**Fórmula:** Sensibilidade = Verdadeiros Positivos / (Verdadeiros                                               positivos + Falsos Negativos)

**Exemplo:** Um modelo para **detecção de gatos em fotos**:

- Havia **15 gatos reais** nas imagens

- O modelo encontrou **9 gatos**, mas **errou 6** (não detectou)

Então:

Sensibilidade = 9 + (6 + 9) ​= 0,6 ou **60% de Sensibilidade**



<mark>**O que são as Features?**</mark>

    As features, ou **entradas específicas**, são as informações fornecidas ao modelo, as **variáveis de entrada** que o modelo usa para **aprender e fazer previsões**.

Exemplo: 

    Um modelo treinando para **classificar animais** em fotos:

- **Features**: número de patas, presença de pelos, tamanho, etc.



**<mark>O que são os Rótulos?</mark>**

    São os **valores reais** que o modelo precisa **aprender a prever**.  Eles representam a **resposta correta** para cada exemplo de treino.

Exemplo:

Um modelo treinando para **classificar animais** em fotos:

- **Rótulos**: gato ou cachorro.



**<mark>O que é Generalização?</mark>**

    É a **capacidade do modelo de fazer boas previsões em dados novos**, que ele nunca viu antes.

Comparação:

| Situação                  | Generaliza bem? |
| ------------------------- | --------------- |
| Vai bem só no treino      | ❌ Não           |
| Vai bem no treino e teste | ✅ Sim           |

**Como melhorar a generalização:**

- Usar mais dados de treino

- Evitar modelos muito complexos

- Usar validação cruzada

 O que é Classificação Binária?

    É um tipo de problema de prendizado de máquina onde o modelo deve escolher entre duas classes possíveis.

    **Obs:** O modelo responde: **“Sim ou Não”**, **“Verdadeiro ou Falso”**, **“1 ou 0”**, **“Positivo ou Negativo”**.

**Exemplo:** 

- **E-mail**: spam ou não spam

- **Doença**: doente ou saudável

- **Pagamento**: será feito ou não

- **Foto**: é um gato ou não é?

Saída do Modelo:

### Saída do modelo:

- Pode ser **direta** (ex: `1` ou `0`)

- Ou uma **probabilidade** (ex: `0.87` de ser spam)

---
