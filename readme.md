# Campeonato brasileiro - ETL e Análise

O projeto consiste na extração dos dados do campeonato brasileiro, no tratamento e na carga dos dados. Por fim, foi realizado uma análise dos dados.

Para realizar o projeto fazendo o ETL utilizei o Python para extração e tratamento, o SSIS (SQL Server Integration Services) para carga, SQL Server para análise e Power BI para o dashbioard.

## Sobre os dados

A análise foi realizada retirando os dados do site **[fbref](https://fbref.com/en/)**.

## Carga

Para carregar os dados no banco de dados, foi utilizado o SSIS. É necessário abrir a pasta carga_brasileirão com direitos de administrador, configurar a conexão com o banco e rodar o projeto para a carga ser feita.

![Carga](/assets/carga.jpeg)

## Dashboard:

No dashboard, pode-se conferir quais os indicadores existem para um melhor entendimento.

![Dashboard](/assets/dashboard.jpeg)

**[Clique para ver o dashboard](https://app.powerbi.com/view?r=eyJrIjoiNTY1M2FiNGEtMjY0Mi00MjcxLWFiMGUtM2RlNGM4ZTgyZGM0IiwidCI6ImE5NjgwMmM4LTA0OTAtNDI3NC1iZDVmLTA5NzIxYWQzOWRjNiJ9)**

## Ferramentas

Utilizei as seguintes ferramentas:

- **Python**: Foi utilizado para realizar a extração e tratamento dos dados.
- **SSIS**: Foi utilizado para a carga dos dados.
- **SQL Server**: Foi utilizado para análise dos dados.
- **Power BI**: Foi utilizado para o dashboard.

## Perguntas respondidas

**Qual goleiro tem a melhor taxa de defesa esperada ajustada (PSxG+/-), indicando sua eficácia em relação às expectativas de gols sofridos com base nas oportunidades concedidas?**

- O goleiro com a melhor taxa de defesa esperada ajustada é o João Ricardo do Fortaleza com 3,60.

**Qual goleiro tem a maior porcentagem de saídas bem-sucedidas (Stp%)?**

- O goleiro com a melhor taxa de cruzamentos é o Augustín Rossi do Flamengo com 13,60%.

**Quais goleiros têm o maior número médio de lançamentos (Att) e a maior média de distância de lançamento (AvgLen)?**

- Os goleiros com mais lançamentos completos em média são:

  - Gustavo (Criciúma): 66,70%;
  - Bento (CAP): 53,30%;
  - Éverson (Atlético MG): 52,50%;

- Os goleiros com a média de passes mais longos são:
  - João Ricardo (Fortaleza): 39,80m;
  - Cleiton (Red Bull Bragantino): 39,10m;
  - Ronaldo (Atlético GO): 39m;

**Qual é a relação entre a quantidade de tempo de jogo (Playing Time) de um goleiro e sua eficácia em defesas durante penalidades (Penalty Kicks)? Existe uma correlação significativa entre a experiência de jogo e a capacidade de defender penalidades?**

- Não podemos afirmar isso, já que os únicos goleiros que defenderam penâltis possuem diferença significativa no tempo em campo.

**Como a taxa de sucesso de defesas (Save%) de um goleiro afeta o desempenho geral da equipe? Há evidências de que um alto índice de defesas está correlacionado com um aumento nas vitórias (W) ou uma redução nas derrotas (L)?**

- Um goleiro com mais defesas deixa o time mais próximo de vencer mas isso né o único fator. Os goleiros com mais vitórias possuem mais de 80% de aproveitamento nas defesas. Porém um goleiro com apenas uma vitória também possui um índice de aproveitamento maior que 80%, indicando que o goleiro pode ser um fator mas existem outros fatores que influenciam.

**Quais jogadores têm a melhor taxa de conversão de chutes em gols (G/Sh)?**

- Com pelo menos 10 chutes no gol, os jogadores com a melhor taxa de conversão em gols são:
  - Cannobio (CAP): 20%;
  - Sasha (Red Bull Bragantino): 20%;
  - Everaldo (Bahia) e Pablo (CAP): 18%;

**Quais jogadores têm o maior número médio de chutes por jogo (Sh/90) e a maior média de chutes no alvo por jogo (SoT/90)?**

- Com pelo menos 10 chutes no gol, os jogadores com mais chutes a gol por 90 min são:

  - Rafael Borré (Internacional): 4,25;
  - Vegetti (Vasco): 3,97;
  - Everaldo (Bahia): 3,88

- Com pelo menos 10 chutes no gol, os jogadores com mais chutes certos a gol por 90 min são:
  - Cano (Fluminense): 1,76;
  - Everaldo (Bahia): 1,76;
  - Rafael Borré (Internacional): 1,5;

**Quais jogadores superam consistentemente as expectativas de gols (G-xG) e as expectativas de gols não penalizados (np:G-xG), indicando uma capacidade excepcional de finalização?**

- Com pelo menos 10 chutes, os jogadores que mais superam as expectativas de gols e as expecatativas de gols não penalizados são:
  - Wesley (Internacional): 1,3;
  - Pablo (CAP): 1,2;
  - Matheus Pereira (Cruzeiro): 0,8;

**Quais jogadores têm consistentemente contribuído com gols e assistências, e como isso se correlaciona com o tempo de jogo que recebem? Existe uma relação entre a frequência de participação dos jogadores e sua produtividade?**

- Os jogadores que mais participaram de gols com 4 participações foram Nico De La Cruz do Flamengo, Vitinho do Red Bull Bragantino e Gustavo Scarpa do Atlético MG. A minutagem não parece ter tanta relação com a produtividade, Nico possui 150 minutos a mais que o Scarpa e ambos possuem a mesma participações de gols.

**Como a idade dos jogadores influencia seu desempenho em campo em relação aos objetivos esperados?**

- Com relação ao xG, dos 10 primeiros em xG, 6 possuem acima de 30 anos. Porém, com relação ao xAG, dos 10 primeiros apenas 2 possuem mais de 30 anos. Não podemos afirmar que existe uma correlação clara entre a idade e criação de oportunidades.

**Quais jogadores demonstram maior progressão em termos de criação de oportunidades e eficácia no terço final do campo?**

- Com relação a carregadas progressivas, Marquinhos do Fluminense lidera com 24, Wesley do Corinthians com 21 e Arias do Fluminense com 20. Com relação a passes progressivos, Fernandinho do CAP lidera com 51, Everton Ribeiro com 46 e Nico De La Cruz com 45.

**Como a disciplina dos jogadores afeta sua disponibilidade e desempenho ao longo do tempo?**

- Entre os 16 jogadores que mais tomaram cartoes amarelos, somam um total de 14 participações em gols. Dos 16 jogadores que já foram expulsos ao menos uma vez, somam um total de 10 participações em gols. Então podemos afirmar que indisciplina não tem uma correlação com a perfomance do jogador.

**Quais jogadores apresentam um desempenho acima ou abaixo das expectativas em termos de gols e assistências?**

- Acima das expectativas em gols:

  - Danilo Barbosa (Botafogo): +2,10;
  - Felipe Mateus (Criciúma): +1,80;
  - Jean Carlos (Juventude): +1,70;

- Abaixo das expectativas em gols:

  - Rafael Borré (Internacional): -2,90;
  - Raphael Veiga (Palmeiras): -1,20;
  - Endrick (Palmeiras): -1,10;

- Acima das expectativas em assistências:

  - Álvaro Barreal (Cruzeiro): +1,90;
  - Breno (Fortaleza): +1,90;
  - Yannick Bolasie (Criciúma): +1,80;

- Abaixo das expectativas em assistências:
  - Shaylon (Atlético Goianiense): -1,60;
  - Wesley (Corinthians): -1,40;
  - Tchê Tchê (Botafogo): -1,30;
