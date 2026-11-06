# Relatório de Preparação da Base de Dados — LifeSync

## 1. Fonte dos dados
Avaliações públicas do aplicativo Mobills (Finanças Pessoais), concorrente do LifeSync, disponibilizadas na Google Play Store. O detalhamento está em `fonte-dos-dados.md`.

## 2. Coleta
- Data da coleta: 06/11/2026
- Ferramenta: biblioteca google-play-scraper (Python), executada no Google Colab
- Critério: 200 avaliações mais recentes
- Período coberto: 13/09/2026 a 05/11/2026
- Variáveis coletadas: nota, comentário, data e curtidas
- Arquivo original preservado, sem alterações: `dados-brutos/mobills_avaliacoes_originais.csv`

## 3. Diagnóstico de qualidade
- Registros: 200
- Valores nulos: 0 em todas as colunas
- Registros duplicados: 0
- Comentários vazios: 0
- Distribuição das notas: 1★ = 53 | 2★ = 14 | 3★ = 11 | 4★ = 13 | 5★ = 109

## 4. Tratamento aplicado
- Padronização do texto dos comentários (minúsculas e remoção de espaços repetidos)
- Nova verificação de duplicados após a padronização (0 encontrados)
- Criação de variáveis: `comentario_limpo`, `tamanho_comentario`, `comentario_curto`, `mes` e `classe_nota`
- Classificação das notas: 1 e 2 = negativa, 3 = neutra, 4 e 5 = positiva
- Nenhum registro foi removido
- Base tratada salva em arquivo separado: `dados-tratados/mobills_avaliacoes_tratadas.csv`

## 5. Validação
Verificações feitas no Google Colab (registradas em `validacao-da-base.md`):
- 200 registros no original e no tratado
- 0 nulos e 0 duplicados
- Notas entre 1 e 5 e curtidas sem valores negativos
- Classes coerentes com as notas
- Notas do arquivo tratado iguais às do original

## 6. Resumo da base tratada
- Positivas: 122 (61%)
- Negativas: 67 (33,5%)
- Neutras: 11 (5,5%)
- Comentários curtos (menos de 5 palavras): 57 (28,5%)
- Nota média da amostra: cerca de 3,56

## 7. Limitações
- A amostra cobre cerca de 7 semanas, então pode não representar todo o histórico do aplicativo.
- A nota média da amostra (cerca de 3,56) é menor que a nota geral do app na loja (4,17).
- Há muitos comentários curtos, com pouca informação textual.
- Em alguns casos a nota não combina com o texto do comentário.
- Avaliações da Play Store refletem usuários que decidiram avaliar, o que pode não representar todos os usuários.

## 8. Dicionário de dados
Disponível em `dicionario-de-dados.md`.

## 9. Conclusão
A base de avaliações do Mobills foi coletada, tratada e validada, e está pronta para a etapa de análise (KPIs, estatística e gráficos).

## 10. Responsáveis
Coordenação: Vinicius | Coleta: Vinicius | Diagnóstico: Vinicius | Limpeza: Vinicius | Dicionário e validação: Vinicius
