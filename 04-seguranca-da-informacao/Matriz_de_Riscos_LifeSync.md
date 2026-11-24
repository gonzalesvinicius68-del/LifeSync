# MATRIZ DE RISCOS
## Projeto LifeSync — Segurança da Informação

---

## 1. Introdução

Este documento apresenta uma análise preliminar dos riscos de segurança da informação relacionados ao projeto **LifeSync**, um sistema proposto para auxiliar na organização e no gerenciamento da vida pessoal dos usuários. A matriz considera os ativos identificados no inventário do projeto e possíveis ameaças e vulnerabilidades que podem afetar suas informações.

Como o LifeSync está em fase de planejamento e documentação, os riscos e controles descritos são **hipóteses e recomendações acadêmicas**. Não indicam que medidas de segurança já tenham sido implementadas ou testadas.

## 2. Objetivos

- Identificar riscos que possam comprometer os ativos previstos para o LifeSync.
- Avaliar a probabilidade de ocorrência e o impacto de cada risco.
- Classificar os riscos para apoiar a definição de prioridades.
- Indicar medidas de tratamento e proteção que poderão ser consideradas no desenvolvimento.

## 3. Critérios de avaliação

Cada risco recebe uma nota de **1 a 5** para probabilidade e impacto. A pontuação é calculada pela multiplicação desses valores:

> **Risco = Probabilidade × Impacto**

### 3.1 Escalas utilizadas

| Critério | Escala |
|---|---|
| **Probabilidade** | 1 – Rara; 2 – Improvável; 3 – Possível; 4 – Provável; 5 – Quase certa. |
| **Impacto** | 1 – Insignificante; 2 – Pequeno; 3 – Moderado; 4 – Grande; 5 – Crítico. |

### 3.2 Faixas de classificação

| Classificação | Pontuação | Interpretação |
|---|:---:|---|
| 🟢 **Baixo** | 1 a 7 | Risco de menor prioridade no contexto da matriz. |
| 🟡 **Médio** | 8 a 14 | Risco que requer acompanhamento e medidas de tratamento. |
| 🔴 **Alto** | 15 a 25 | Risco que merece atenção prioritária no planejamento. |

## 4. Matriz de riscos

A tabela a seguir relaciona os principais riscos preliminares identificados para os ativos do LifeSync.

| ID | Ativo | Ameaça / risco | Prob. | Impacto | Pontuação | Nível |
|:---:|---|---|:---:|:---:|:---:|:---:|
| R01 | Dados pessoais | Acesso não autorizado ou vazamento de dados | 4 | 5 | **20** | 🔴 Alto |
| R02 | Credenciais de acesso | Roubo ou descoberta de senhas | 4 | 5 | **20** | 🔴 Alto |
| R03 | Dados financeiros | Exposição ou alteração indevida de registros | 3 | 5 | **15** | 🔴 Alto |
| R04 | Tarefas e calendário | Perda, indisponibilidade ou alteração de informações | 3 | 3 | **9** | 🟡 Médio |
| R05 | Anotações pessoais | Divulgação de conteúdo privado | 3 | 4 | **12** | 🟡 Médio |
| R06 | Banco de dados | Perda ou corrupção de informações | 3 | 5 | **15** | 🔴 Alto |
| R07 | Código-fonte / GitHub | Exposição de senhas, tokens ou chaves no repositório | 3 | 4 | **12** | 🟡 Médio |
| R08 | Documentação e protótipos | Acesso ou divulgação não autorizada | 2 | 3 | **6** | 🟢 Baixo |
| R09 | Cópias de segurança | Backup inexistente, indisponível ou sem possibilidade de restauração | 3 | 5 | **15** | 🔴 Alto |
| R10 | Aplicação / comunicação | Interceptação de dados durante a transmissão | 2 | 4 | **8** | 🟡 Médio |

## 5. Tratamento e controles propostos

Os controles a seguir são recomendações preliminares para o tratamento dos riscos identificados.

| ID | Ativo | Controles propostos |
|:---:|---|---|
| **R01** | Dados pessoais | Propor controle de acesso por usuário, autenticação segura, comunicação protegida por HTTPS e revisão de permissões. |
| **R02** | Credenciais | Armazenar senhas com algoritmo de hash apropriado; prever requisitos de senha e recuperação segura de conta. |
| **R03** | Dados financeiros | Restringir o acesso aos próprios registros do usuário, validar operações no servidor e avaliar registros de auditoria. |
| **R04** | Tarefas e calendário | Prever validação dos dados, controle de alterações e procedimentos para recuperação de informações. |
| **R05** | Anotações pessoais | Aplicar o princípio do menor privilégio e impedir que um usuário acesse anotações de outro. |
| **R06** | Banco de dados | Restringir privilégios, planejar backups e prever testes periódicos de restauração. |
| **R07** | Código-fonte / GitHub | Não publicar senhas, tokens ou chaves; utilizar variáveis de ambiente e revisar permissões e alterações no repositório. |
| **R08** | Documentação | Revisar os arquivos antes de compartilhá-los, controlar permissões quando necessário e usar dados fictícios em exemplos. |
| **R09** | Cópias de segurança | Definir frequência de cópias, proteger os arquivos de backup e documentar testes de restauração. |
| **R10** | Aplicação / comunicação | Prever HTTPS/TLS e configurações seguras para a transmissão de informações. |

## 6. Relação com a segurança da informação e a LGPD

A análise considera os seguintes princípios da segurança da informação:

- **Confidencialidade:** evitar acesso e divulgação não autorizados.
- **Integridade:** evitar alteração ou destruição indevida.
- **Disponibilidade:** manter as informações acessíveis quando necessário.

Como o sistema poderá tratar dados pessoais, o projeto também deverá considerar a **Lei Geral de Proteção de Dados Pessoais (LGPD)**, incluindo cuidados com finalidade, necessidade, transparência e segurança no tratamento.

## 7. Considerações finais

A matriz de riscos permite visualizar os principais eventos que podem afetar os ativos previstos para o LifeSync e organizar prioridades de tratamento. Os riscos classificados como altos merecem atenção prioritária no planejamento.

As avaliações são preliminares e deverão ser revistas quando a arquitetura, as tecnologias e os requisitos do sistema estiverem definidos.

As medidas apresentadas são propostas acadêmicas. Sua implementação, validação e eficácia deverão ser verificadas em etapas futuras, caso sejam realizadas.

## 8. Referências e base normativa

BRASIL. **Lei nº 13.709, de 14 de agosto de 2018.** Lei Geral de Proteção de Dados Pessoais (LGPD).

---

> **Observação:** as escalas e faixas de classificação desta matriz foram adotadas como critérios simplificados para fins acadêmicos; não constituem, isoladamente, uma certificação ou auditoria.
