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

    Quando o modelo aprende demais os dados de treinamento ou de forma muito específica, incluindo o "ruído". O modelo irá memorizar ao invés de generalizar.

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
