1 - Qual goleiro tem a melhor taxa de defesa esperada ajustada (PSxG+/-), indicando sua eficácia em relação às expectativas de gols sofridos com base nas oportunidades concedidas?

- O goleiro com a melhor taxa de defesa esperada ajustada é o João Ricardo do Fortaleza com 3,60.

```
SELECT
	player AS jogador,
	squad AS time,
	[PSxG+/-]
FROM
	advanced_goalkeeping
ORDER BY
	[PSxG+/-]
DESC
```

2 - Qual goleiro tem a maior porcentagem de saídas bem-sucedidas (Stp%)?

- O goleiro com a melhor taxa de cruzamentos é o Augustín Rossi do Flamengo com 13,60%.

```
SELECT
	player AS jogador,
	squad AS time,
	[Stp%]
FROM
	advanced_goalkeeping
ORDER BY
	[Stp%]
DESC
```

3 - Quais goleiros têm o maior número médio de lançamentos (Att) e a maior média de distância de lançamento (AvgLen)?

- Os goleiros com mais lançamentos completos em média são:
  - Gustavo (Criciúma): 66,70%;
  - Bento (CAP): 53,30%;
  - Éverson (Atlético MG): 52,50%;

```
SELECT
	player AS jogador,
	squad AS time,
	[Cmp%]
FROM
	advanced_goalkeeping
ORDER BY
	[Cmp%]
DESC
```

- Os goleiros com a média de passes mais longos são:
  - João Ricardo (Fortaleza): 39,80m;
  - Cleiton (Red Bull Bragantino): 39,10m;
  - Ronaldo (Atlético GO): 39m;

```
SELECT
	player AS jogador,
	squad AS time,
	AvgLen
FROM
	advanced_goalkeeping
ORDER BY
	AvgLen
DESC
```
