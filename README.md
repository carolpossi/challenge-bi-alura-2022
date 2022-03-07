# [Alura Challenge BI: Edição #2 - Semana 1](https://www.alura.com.br/challenges/bi-2/semana-01-films)
Projeto de BI e Data Science desenvolvido para o Challenge BI: Edição #2 da [Alura](https://www.alura.com.br) em fevereiro de 2022.

**Desafio proposto**: construir um dashboard para a visualização e análise de dados sobre uma pesquisa de mercado para uma nova produção da Alura Films.
> A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de dados do IMDB com 1000 filmes. Use suas habilidades e conhecimentos para explorar, tratar e transformar os dados em informações relevantes que auxiliem na tomada de decisão da empresa.
 
Escolhi a plataforma **Microsoft Power BI** para este desafio.

## 🎲 Base de Dados

* [``` Filmes.csv ```](docs/Filmes.csv): Arquivo CSV com os top 1000 filmes de acordo com a classificação IMDB, com informações adicionais como ano de lançamento, gênero, atores e atrizes principais, avaliações, quantidade de votos, faturamento, entre outros.
* [``` Posters.csv```](docs/Posters.csv): Arquivo CSV com os URLs das imagens correspondentes aos pôsteres dos filmes listados em ``` Filmes.csv ```.

## 📐Métricas
Separei as métricas sugeridas (✔) em grupos, cada um em página do Dashboard, e tamblém inclui outras métricas (➕) que considerei relevantes ou interessantes. 
### Gêneros
* ✔ Gêneros mais rentáveis (Faturamento)
* ✔ Gêneros mais frequentes (Quantidade de filmes)
* ➕Relação entre duração e faturamento por gênero
* ➕Faturamento médio por gênero

🔻 Filtragem: hierarquia de gênero (principal, secundário e terciário)
### Avaliações
* ✔ Filmes mais votados
* ✔ Metascore, IMDB, Número de Votos
* ➕Relação entre faturamento e avaliação (Metascore e IMDB)
* ➕Média de avaliações por ano de lançamento

🔻 Filtragem: gênero principal, ano de lançamento, faturamento
### Estrelas
* ✔ Faturamento do Filmes por Estrela 1, 2 3 e 4
* ✔ Estrelas que mais aparecem nos filmes
* ➕Resumo das estrelas com avaliações médias, primeiro e último ano de lançamento, gêneros, faturamento e quantidade de filmes

## 🗨️Considerações e Aprendizados

## Progresso README
Tópicos do ```README.md```
- [x] Base de dados
- [ ] Tratamento dos dados
- [ ] Tabela de novas medidas e colunas
- Métricas por página
  - [x] Gêneros
  - [x] Estrelas
  - [x] Avaliações 
- Visuais e imagens por página
  - [ ] Gêneros
  - [ ] Estrelas
  - [ ] Avaliações 
   - [ ] Tooltip
- [ ] Considerações e Aprendizados

