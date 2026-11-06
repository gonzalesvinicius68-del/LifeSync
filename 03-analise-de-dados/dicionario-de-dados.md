# Dicionário de Dados — LifeSync

Base: avaliações públicas do Mobills (Google Play Store), coletadas em 06/11/2026.
Arquivo original: mobills_avaliacoes_originais.csv (200 registros, 4 colunas).
Arquivo tratado: mobills_avaliacoes_tratadas.csv (200 registros, 9 colunas).

## Variáveis originais

| Variável | Tipo | Descrição | Valores possíveis |
|---|---|---|---|
| nota | inteiro | Nota dada pelo usuário ao aplicativo | 1 a 5 |
| comentario | texto | Comentário original do usuário, sem alteração | texto livre |
| data | data e hora | Data e hora da publicação da avaliação | 13/09/2026 a 05/11/2026 |
| curtidas | inteiro | Quantidade de curtidas recebidas pela avaliação | 0 ou mais |

## Variáveis criadas na limpeza

| Variável | Tipo | Descrição | Valores possíveis |
|---|---|---|---|
| comentario_limpo | texto | Comentário em minúsculas e sem espaços extras | texto livre |
| tamanho_comentario | inteiro | Número de palavras do comentário | 1 ou mais |
| comentario_curto | booleano | Verdadeiro se o comentário tem menos de 5 palavras | True / False |
| mes | texto | Mês da avaliação, no formato AAAA-MM | 2026-09, 2026-10, 2026-11 |
| classe_nota | texto | Nota 1 ou 2 = negativa, 3 = neutra, 4 ou 5 = positiva | negativa / neutra / positiva |

## Regras de tratamento
- Texto padronizado: minúsculas e espaços repetidos removidos.
- Duplicados verificados após a padronização (0 encontrados).
- Nenhum registro foi removido.
- O arquivo original foi preservado sem alterações.
