# Identificação da Fonte de Dados — LifeSync

## 1. Fonte dos dados
A base de dados utilizada no projeto LifeSync é composta por avaliações públicas de usuários do aplicativo Mobills, disponibilizadas na Google Play Store.

## 2. Objetivo da coleta
Coletar avaliações para identificar a percepção dos usuários sobre o aplicativo, seus principais pontos positivos, dificuldades e oportunidades de melhoria.

## 3. Variáveis previstas
- Nota atribuída pelo usuário;
- Comentário da avaliação;
- Data da publicação;
- Quantidade de curtidas da avaliação.

## 4. Método de coleta
A coleta foi realizada por meio de uma ferramenta de extração de avaliações públicas da Google Play Store, utilizando Python.

## 5. Formato de armazenamento
Os dados foram organizados em um arquivo CSV, preservando os registros originais coletados.

## 6. Finalidade acadêmica
Os dados serão utilizados exclusivamente para fins acadêmicos, buscando identificar oportunidades de melhoria para o projeto LifeSync.

## 7. Resultado da coleta
- Data da coleta: 06/11/2026
- Quantidade coletada: 200 avaliações
- Período das avaliações: 13/09/2026 a 05/11/2026
- Ferramenta: biblioteca google-play-scraper (Python), executada no Google Colab
- Critério de seleção: 200 avaliações mais recentes (ordenação por data)
- Arquivo original: mobills_avaliacoes_originais.csv (preservado sem alterações)
- Limitação: a amostra cobre apenas cerca de 7 semanas, então pode não representar todo o histórico do aplicativo.
