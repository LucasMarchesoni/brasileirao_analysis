1 - Quais jogadores têm consistentemente contribuído com gols e assistências, e como isso se correlaciona com o tempo de jogo que recebem? Existe uma relação entre a frequência de participação dos jogadores e sua produtividade?

- Os jogadores que mais participaram de gols com 4 participações foram Nico De La Cruz do Flamengo, Vitinho do Red Bull Bragantino e Gustavo Scarpa do Atlético MG. A minutagem não parece ter tanta relação com a produtividade, Nico possui 150 minutos a mais que o Scarpa e ambos possuem a mesma participações de gols.

```
SELECT
player AS jogador,
squad AS time,
G_plus_A,
min as minutagem
FROM
standard_stats
ORDER BY
G_plus_A
DESC
```

2 - Como a idade dos jogadores influencia seu desempenho em campo em relação aos objetivos esperados?

- Com relação ao xG, dos 10 primeiros em xG, 6 possuem acima de 30 anos. Porém, com relação ao xAG, dos 10 primeiros apenas 2 possuem mais de 30 anos. Não podemos afirmar que existe uma correlação clara entre a idade e criação de oportunidades.

```
SELECT
	player AS jogador,
	squad AS time,
	DATEDIFF(year, born, GETDATE()) AS idade,
	xG,
	xAG
FROM
	standard_stats
WHERE
	Pos != 'GK'
ORDER BY
	xG
DESC
```

3 - Quais jogadores demonstram maior progressão em termos de criação de oportunidades e eficácia no terço final do campo?

- Com relação a carregadas progressivas, Marquinhos do Fluminense lidera com 24, Wesley do Corinthians com 21 e Arias do Fluminense com 20. Com relação a passes progressivos, Fernandinho do CAP lidera com 51, Everton Ribeiro com 46 e Nico De La Cruz com 45.

```
SELECT
player AS jogador,
squad AS time,
PrgC,
PrgP
FROM
standard_stats
ORDER BY
PrgP
DESC
```

4 - Como a disciplina dos jogadores afeta sua disponibilidade e desempenho ao longo do tempo?

- Entre os 16 jogadores que mais tomaram cartoes amarelos, somam um total de 14 participações em gols. Dos 16 jogadores que já foram expulsos ao menos uma vez, somam um total de 10 participações em gols. Então podemos afirmar que indisciplina não tem uma correlação com a perfomance do jogador.

```
SELECT
	player AS jogador,
	squad AS time,
	CrdY,
	CrdR,
	min,
	G_plus_A
FROM
	standard_stats
ORDER BY
	CrdR
DESC
```

5 - Quais jogadores apresentam um desempenho acima ou abaixo das expectativas em termos de gols e assistências?

- Acima das expectativas em gols:
  - Danilo Barbosa (Botafogo): +2,10;
  - Felipe Mateus (Criciúma): +1,80;
  - Jean Carlos (Juventude): +1,70;

```
 SELECT
	player AS jogador,
	squad AS time,
	Gls,
	xG,
	Gls - xG as diferenca_esperado_real
FROM
	standard_stats
ORDER BY
	diferenca_esperado_real
DESC
```

- Abaixo das expectativas em gols:
  - Rafael Borré (Internacional): -2,90;
  - Raphael Veiga (Palmeiras): -1,20;
  - Endrick (Palmeiras): -1,10;

```
SELECT
	player AS jogador,
	squad AS time,
	Gls,
	xG,
	Gls - xG as diferenca_esperado_real
FROM
	standard_stats
ORDER BY
	diferenca_esperado_real
ASC
```

- Acima das expectativas em assistências:
  - Álvaro Barreal (Cruzeiro): +1,90;
  - Breno (Fortaleza): +1,90;
  - Yannick Bolasie (Criciúma): +1,80;

```
SELECT
	player AS jogador,
	squad AS time,
	Ast,
	xAG,
	Ast - xAG as diferenca_esperado_real
FROM
	standard_stats
ORDER BY
	diferenca_esperado_real
DESC
```

- Abaixo das expectativas em assistências:
  - Shaylon (Atlético Goianiense): -1,60;
  - Wesley (Corinthians): -1,40;
  - Tchê Tchê (Botafogo): -1,30;

```
SELECT
	player AS jogador,
	squad AS time,
	Ast,
	xAG,
	Ast - xAG as diferenca_esperado_real
FROM
	standard_stats
ORDER BY
	diferenca_esperado_real
ASC
```
