# Pesquisa Operacional — LifeSync

## 1. Objetivo

Esta documentação apresenta a pesquisa de campo e os modelos de Pesquisa Operacional elaborados para o LifeSync. O trabalho investiga a organização do tempo e o planejamento pessoal e usa modelos matemáticos para simular diferentes distribuições de horas e alternativas para cumprir metas semanais.

A análise está organizada em três partes: pesquisa de campo com respostas obtidas pelo Google Forms; modelo de maximização da pontuação estimada de produtividade e bem-estar; modelo de minimização de custos, com uma variante que minimiza o tempo.

## 2. Fontes e tratamento dos dados

A pesquisa de campo foi baseada na planilha exportada do Google Forms, com 15 respostas válidas para 15 perguntas. A coluna de carimbo de data e hora foi retirada da análise por não ser necessária aos cálculos. O notebook contém uma cópia das respostas sem esses horários, de modo que a análise possa ser executada sem carregar a planilha original.

As respostas da pesquisa são dados observados. Já os pontos, custos, eficiências, metas e limites usados nos modelos matemáticos são premissas definidas pelo grupo. Eles não foram medidos diretamente com os participantes.

## 3. Pesquisa de campo

A análise descritiva calculou frequências e percentuais para as respostas categóricas. Na pergunta sobre funcionalidades, cada participante podia selecionar mais de uma opção; por isso, as porcentagens dessa questão não precisam somar 100%.

### Principais resultados

- 11 participantes (73,3%) tinham entre 18 e 24 anos.
- 8 (53,3%) estudavam e trabalhavam.
- 9 (60%) responderam que só conseguiam organizar bem o tempo às vezes ou que tinham bastante dificuldade.
- 6 (40%) apontaram administrar o tempo disponível como a maior dificuldade; 4 (26,7%) indicaram conciliar trabalho e estudos.
- 7 (46,7%) disseram que memorizavam as tarefas; 4 (26,7%) não usavam um método específico.
- 12 (80%) disseram que algumas vezes deixavam de realizar uma atividade importante por falta de organização ou planejamento.
- 8 (53,3%) disseram que utilizariam um aplicativo que reunisse áreas diferentes da rotina; 3 (20%) responderam talvez e 4 (26,7%) responderam não.

As funcionalidades mais selecionadas foram organização de tarefas e compromissos (12 participantes; 80%), planejamento de estudos (10; 66,7%), organização de descanso e lazer (8; 53,3%), controle financeiro (8; 53,3%) e metas e acompanhamento de progresso (8; 53,3%). Nas respostas abertas, também apareceram sugestões de agenda, lembretes, notificações, simplicidade, personalização e acesso em diferentes dispositivos.

Esses resultados descrevem somente as 15 pessoas que responderam ao formulário. A amostra é pequena e não probabilística, portanto não representa necessariamente todos os usuários potenciais do LifeSync.

## 4. Modelo 1 — Maximização da pontuação

### Objetivo e variáveis

O modelo distribui 140 horas por semana entre seis atividades, buscando maximizar uma pontuação estimada:

- x1: trabalho (horas por semana);
- x2: estudo;
- x3: exercício;
- x4: sono e descanso;
- x5: lazer;
- x6: organização pessoal e financeira.

A função objetivo usada no notebook é:

**Maximizar Z = 6x1 + 7x2 + 8x3 + 9x4 + 7,5x5 + 6,5x6.**

Os coeficientes representam pontos estimados por hora, numa escala definida pelo grupo. Não são medidas clínicas nem avaliações dos participantes.

### Restrições

- **Tempo semanal disponível:** x1 + x2 + x3 + x4 + x5 + x6 = 140. O grupo considerou 168 horas na semana, das quais 28 ficam reservadas para refeições, deslocamento e higiene.
- **Carga conjunta de trabalho e estudo:** x1 + x2 ≤ 60.
- **Limites por atividade:** cada cenário estabelece valores mínimos e máximos para as seis variáveis.
- **Não negatividade:** todas as horas devem ser iguais ou maiores que zero.

Os limites por cenário são premissas do grupo e estão especificados no notebook.

### Resultados dos cenários

| Atividade (h/semana) | Estudante | Trabalhador | Equilibrado |
|---|---:|---:|---:|
| Trabalho | 10 | 40 | 30 |
| Estudo | 32 | 5 | 12 |
| Exercício | 8 | 8 | 8 |
| Sono e descanso | 63 | 63 | 63 |
| Lazer | 25 | 22 | 25 |
| Organização pessoal/financeira | 2 | 2 | 2 |
| **Pontuação estimada (Z)** | **1.115,5** | **1.084,0** | **1.095,5** |

A solução apresenta a combinação que maximiza a pontuação dentro dos limites escolhidos para cada cenário. Ela não deve ser interpretada como uma recomendação individual de rotina: o resultado depende dos coeficientes e limites inseridos pelo grupo.

### Sensibilidade apresentada

No cenário equilibrado, o notebook também altera o limite máximo de sono e descanso e a pontuação atribuída ao lazer:

| Alteração simulada | Pontuação ótima | Resultado associado |
|---|---:|---|
| Máximo de sono = 49 h | 1.063,0 | Cenário viável |
| Máximo de sono = 56 h | 1.081,5 | Cenário viável |
| Máximo de sono = 63 h | 1.095,5 | Cenário viável |
| Pontos do lazer = 6,0 por hora | 1.067,5 | 14 h de lazer |
| Pontos do lazer = 7,5 por hora | 1.095,5 | 25 h de lazer |
| Pontos do lazer = 9,5 por hora | 1.145,5 | 25 h de lazer |

Essa análise mostra como a solução matemática muda quando parâmetros estimados são alterados; não comprova que a pontuação corresponda a produtividade ou bem-estar observados na prática.

## 5. Modelo 2 — Minimização de custo

### Objetivo e variáveis

O segundo modelo escolhe quantas horas semanais dedicar a diferentes formas de cumprir quatro metas: estudo, saúde, finanças e lazer. O objetivo principal é minimizar o custo estimado.

Para cada alternativa, a variável representa horas por semana. O modelo usa um custo por hora e uma eficiência estimada, expressa em unidades de benefício por hora.

| Categoria | Alternativa | Custo estimado (R$/h) | Eficiência estimada (unidades/h) | Limite (h/semana) |
|---|---|---:|---:|---:|
| Estudo | Aula presencial | 12 | 1,0 | 0–8 |
| Estudo | Videoaula | 3 | 0,7 | 0–10 |
| Estudo | Grupo de estudo | 5 | 0,9 | 0–6 |
| Saúde | Academia | 6 | 1,0 | 0–5 |
| Saúde | Caminhada ao ar livre | 0 | 0,6 | 0–6 |
| Finanças | Planilha manual | 0 | 0,5 | 0–6 |
| Finanças | Aplicativo (tipo LifeSync) | 2 | 1,2 | 0–4 |
| Lazer | Fora de casa | 20 | 1,0 | 0–6 |
| Lazer | Em casa | 2 | 0,8 | 0–10 |

### Restrições

- **Metas mínimas semanais:** 12 unidades de estudo, 4 de saúde, 3 de finanças e 6 de lazer.
- **Tempo total:** no máximo 40 horas por semana.
- **Limites por alternativa:** cada forma de execução respeita os limites da tabela.
- **Não negatividade:** nenhuma alternativa pode ter horas negativas.

As unidades de benefício, os custos e os limites são estimativas feitas pelo grupo para fins didáticos.

### Resultado de custo mínimo

O plano de custo mínimo encontrado usa aproximadamente **35,5 horas por semana** e tem custo estimado de **R$ 75,18 por semana**:

| Alternativa escolhida | Horas/semana | Custo semanal estimado |
|---|---:|---:|
| Videoaula | 10,00 | R$ 30,00 |
| Grupo de estudo | 5,56 | R$ 27,78 |
| Academia | 0,40 | R$ 2,40 |
| Caminhada ao ar livre | 6,00 | R$ 0,00 |
| Planilha manual | 6,00 | R$ 0,00 |
| Lazer em casa | 7,50 | R$ 15,00 |
| **Total** | **35,46** | **R$ 75,18** |

Os valores apresentados dependem diretamente dos custos e eficiências definidos pelo grupo. Por exemplo, o custo zero atribuído a caminhada e planilha manual é uma premissa do modelo.

### Variante: minimização de tempo com orçamento limitado

O notebook inclui uma segunda formulação que minimiza o total de horas, mantendo as metas por categoria e limitando o custo a **R$ 120 por semana**. A comparação simulada foi:

| Cenário | Tempo mínimo estimado | Orçamento usado |
|---|---:|---:|
| Com a opção de aplicativo | 28,4 h/semana | R$ 120,00 |
| Sem a opção de aplicativo | 31,7 h/semana | R$ 120,00 |

A diferença é de aproximadamente **3,2 horas por semana** nas condições simuladas. Isso não é uma economia observada na pesquisa nem uma garantia de que o LifeSync reduzirá o tempo real de uma pessoa. O resultado representa apenas o efeito dos custos, eficiências, metas, limites e orçamento escolhidos para a simulação.

## 6. Ferramentas e reprodução

O notebook foi desenvolvido em Python e utiliza numpy, pandas, scipy.optimize.linprog, matplotlib e seaborn. O solver linprog resolve os modelos lineares. Para reproduzir os cálculos, abra o notebook do projeto no Google Colab e execute as células em ordem. A seção de pesquisa de campo já incorpora as respostas sem os carimbos de data e hora.

O notebook salva gráficos na pasta graficos/ durante a execução. Esses arquivos podem ser mantidos nessa pasta se a equipe quiser versionar os gráficos no GitHub.

## 7. Limitações e interpretação

- A pesquisa tem 15 participantes e não representa necessariamente a população em geral.
- Os modelos usam premissas estimadas pelo grupo, não medições dos participantes.
- Os modelos são lineares e tratam os ganhos por hora como constantes dentro dos limites definidos.
- A maximização não representa horários específicos nem dependências entre atividades.
- As soluções mudam se os pontos, custos, eficiências, metas ou limites forem alterados.
- A comparação com a opção de aplicativo é hipotética; não demonstra que o LifeSync já gere economia de tempo ou dinheiro.

Assim, a pesquisa de campo oferece indicações para pensar funcionalidades do LifeSync, enquanto os modelos servem como demonstrações quantitativas de otimização sob premissas explícitas.

## 8. Arquivo relacionado

O notebook com a análise da pesquisa de campo e os modelos matemáticos está em [cadernos/LifeSync_Pesquisa_Campo_e_Operacional.ipynb](../cadernos/LifeSync_Pesquisa_Campo_e_Operacional.ipynb).
