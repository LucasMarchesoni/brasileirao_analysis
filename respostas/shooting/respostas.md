1 - Quais jogadores têm a melhor taxa de conversão de chutes em gols (G/Sh)?

- Com pelo menos 10 chutes no gol, os jogadores com a melhor taxa de conversão em gols são:
  - Cannobio (CAP): 20%;
  - Sasha (Red Bull Bragantino): 20%;
  - Everaldo (Bahia) e Pablo (CAP): 18%;

```
SELECT
	player AS jogador,
	squad AS time,
	G_per_Sh
FROM
	shooting
WHERE
	Sh >= 10
ORDER BY
	G_per_Sh
DESC
```

2 - Quais jogadores têm o maior número médio de chutes por jogo (Sh/90) e a maior média de chutes no alvo por jogo (SoT/90)?

- Com pelo menos 10 chutes no gol, os jogadores com mais chutes a gol por 90 min são:
  - Rafael Borré (Internacional): 4,25;
  - Vegetti (Vasco): 3,97;
  - Everaldo (Bahia): 3,88

```
SELECT
	player AS jogador,
	squad AS time,
	Sh_per_90 / 100 AS chutes_por_90_min
FROM
	shooting
WHERE
	Sh > 10
ORDER BY
	Sh_per_90
DESC
```

- Com pelo menos 10 chutes no gol, os jogadores com mais chutes certos a gol por 90 min são:
  - Cano (Fluminense): 1,76;
  - Everaldo (Bahia): 1,76;
  - Rafael Borré (Internacional): 1,5;

```
SELECT
	player AS jogador,
	squad AS time,
	Sot_per_90 / 100 AS chutes_por_90_min
FROM
	shooting
WHERE
	Sh > 10
ORDER BY
	Sot_per_90
DESC
```

3 - Quais jogadores superam consistentemente as expectativas de gols (G-xG) e as expectativas de gols não penalizados (np:G-xG), indicando uma capacidade excepcional de finalização?

- Com pelo menos 10 chutes, os jogadores que mais superam as expectativas de gols e as expecatativas de gols não penalizados são:
  - Wesley (Internacional): 1,3;
  - Pablo (CAP): 1,2;
  - Matheus Pereira (Cruzeiro): 0,8;

```
SELECT
	player AS jogador,
	squad AS time,
	G_minus_xG / 10 AS G_minus_xG
FROM
	shooting
WHERE
	Sh > 10
ORDER BY
	G_minus_xG
DESC
```
