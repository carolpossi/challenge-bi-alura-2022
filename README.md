# [Alura Challenge BI: Edição #2 - Semana 1](https://www.alura.com.br/challenges/bi-2/semana-01-films)
Projeto de BI e Data Science desenvolvido para o Challenge BI: Edição #2 da [Alura](https://www.alura.com.br) em fevereiro de 2022.

**Desafio proposto**: construir um dashboard para a visualização e análise de dados sobre uma pesquisa de mercado para uma nova produção da Alura Films.
> A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de dados do IMDB com 1000 filmes. Use suas habilidades e conhecimentos para explorar, tratar e transformar os dados em informações relevantes que auxiliem na tomada de decisão da empresa.
 
Escolhi a plataforma **Microsoft Power BI** para este desafio. [Clique aqui](https://app.powerbi.com/view?r=eyJrIjoiNDhiMjE1NDQtZjRiMS00ZGIwLWEwYzQtNThlMDc1ZTYzMDlmIiwidCI6ImZkYzJlZjNkLWEzZDEtNDA1OC1hOTA4LTAxMWMxMTcxZTYxNiJ9&pageName=ReportSection) para acessar o dashboard na web.

## 🎲 Base de Dados

* [``` Filmes.csv ```](docs/Filmes.csv): Arquivo CSV com os top 1000 filmes de acordo com a classificação IMDB, com informações adicionais como ano de lançamento, gênero, atores e atrizes principais, avaliações, quantidade de votos, faturamento, entre outros.
* [``` Posters.csv```](docs/Posters.csv): Arquivo CSV com os URLs das imagens correspondentes aos pôsteres dos filmes listados em ``` Filmes.csv ```.

## 📊 Páginas 
Separei as métricas sugeridas(✔) em grupos, cada um em uma página do Dashboard, e tamblém inclui outras métricas(➕) que considerei relevantes ou interessantes. 
### Gêneros
<img src="https://user-images.githubusercontent.com/43648611/157265454-e27da05f-9e39-46fb-921c-3e9f60aa0f4f.png" width="800">

* ✔ Gêneros mais rentáveis (Faturamento)
* ✔ Gêneros mais frequentes (Quantidade de filmes)
* ➕Relação entre duração e faturamento por gênero
* ➕Faturamento médio por gênero

🔻 Filtragem: hierarquia de gênero (principal, secundário e terciário)
### Avaliações
<img src="https://user-images.githubusercontent.com/43648611/157265717-e938d961-ce9d-4c0f-be1c-a26a58061a90.png" width="800">

* ✔ Filmes mais votados
* ✔ Metascore, IMDB, Número de Votos
* ➕Relação entre faturamento e avaliação (Metascore e IMDB)
* ➕Média de avaliações por ano de lançamento

🔻 Filtragem: gênero principal, ano de lançamento, faturamento

A tabela de filmes, à direita da página, possui a seguinte dica de ferramenta habilitada:

![Tooltop Filmes (Página Avaliações)](https://user-images.githubusercontent.com/43648611/157266049-fca3a009-4260-40f4-b87a-ea6257c22199.png)

### Estrelas
<img src="https://user-images.githubusercontent.com/43648611/157265780-cfb40a9f-8eea-4e5c-92b5-af63e38e6db7.png" width="800">

* ✔ Faturamento do Filmes por Estrela 1, 2 3 e 4
* ✔ Estrelas que mais aparecem nos filmes
* ➕Resumo das estrelas com avaliações médias, primeiro e último ano de lançamento, gêneros, faturamento e quantidade de filmes

## 📐Cálculos e Transformação de Dados
### Novas Tabelas
<img src="https://user-images.githubusercontent.com/43648611/157269393-fa89f963-4a99-4db1-87da-58ef17585f8f.png" width="400">

Além das tabelas fonte, ``` Filmes ``` e ``` Posters ``` , criei outras duas tabelas, ```Estrelas``` e ```Genre``` , pois a fonte possui múltiplos valores para descrever o gênero do filme, assim como múltiplas estrelas (atores e atrizes) por filme. Separando os valores em colunas e transformando as colunas em linhas, foram obtidas as tabelas desejadas, com as quais foi possível construir os gráficos e filtros apresentados anteriormente.
Este processo foi necessário para evitar a duplicação de valores desnecessários na tabela fonte.


| ![Tabela Estrelas - Cabeçalho](https://user-images.githubusercontent.com/43648611/157271126-af763dad-e9e7-42a8-a9eb-3a09abe1b69b.png) | ![Tabela Gênero - Cabeçalho](https://user-images.githubusercontent.com/43648611/157271270-6187abea-4b19-4190-8a01-b826830b4663.png) |
|:--:|:--:|
| <i>Cabeçlho Tabela ```Estrelas```</i>  | <i>Cabeçlho Tabela ```Genre```</i> |

A coluna ```Id_Title``` serve como chave para todas as relações. 

### Novas Colunas

Para montar a tabela de filmes na página de [Avaliações](#avaliações), criei as colunas abaixo:
* ``` Filme e Ano = Filmes[Series_Title] & " (" & Filmes[Released_Year] & ")" ```
  * Concatenação de duas informações relevantes sobre o filme
* ``` Diferença Avaliações = IF(Filmes[IMDB_Rating] <> 0 && Filmes[Meta_score] <> 0,ABS(Filmes[Meta_score]-Filmes[IMDB_Rating]),0) ```
  * Representa o grau de controvérsia de um filme com base nas diferença entre as avaliações das duas fontes disponibilizadas.


## 🗨️Considerações e Aprendizados

## Progresso README
Tópicos do ```README.md```
- [x] Base de dados
- [x] Tratamento dos dados
- [x] Tabela de novas medidas e colunas
- Métricas por página
  - [x] Gêneros
  - [x] Estrelas
  - [x] Avaliações 
- Visuais e imagens por página
  - [x] Gêneros
  - [x] Estrelas
  - [x] Avaliações 
   - [x] Tooltip
- [ ] Considerações e Aprendizados
- [x] Inserir link para dashboard na web

