1 - Qual é a relação entre a quantidade de tempo de jogo (Playing Time) de um goleiro e sua eficácia em defesas durante penalidades (Penalty Kicks)? Existe uma correlação significativa entre a experiência de jogo e a capacidade de defender penalidades?

- Não podemos afirmar isso, já que os únicos goleiros que defenderam penâltis possuem diferença significativa no tempo em campo.

```
SELECT
	player AS jogador,
	squad AS time,
	min AS minutagem,
	PKsv
FROM
	goalkeeping
WHERE
	PKsv >  0
```

2 - Como a taxa de sucesso de defesas (Save%) de um goleiro afeta o desempenho geral da equipe? Há evidências de que um alto índice de defesas está correlacionado com um aumento nas vitórias (W) ou uma redução nas derrotas (L)?

- Um goleiro com mais defesas deixa o time mais próximo de vencer mas isso né o único fator. Os goleiros com mais vitórias possuem mais de 80% de aproveitamento nas defesas. Porém um goleiro com apenas uma vitória também possui um índice de aproveitamento maior que
  80%, indicando que o goleiro pode ser um fator mas existem outros fatores que influenciam.

```
SELECT
	player AS jogador,
	squad AS time,
	Save_Pct / 10 AS pct_defesas,
	W,
	D,
	L
FROM
	goalkeeping
ORDER BY
	W
ASC
```
