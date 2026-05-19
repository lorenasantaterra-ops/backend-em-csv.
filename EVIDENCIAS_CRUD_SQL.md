Evidências - INSERT, UPDATE e DELETE no banco db_em
Identificação

Nome: Deborah de Jesus Silva
Turma: 3º ANO B
Data: 19/05/2026

1. SELECT final - Leituras do dia 2026-04-04

Execute no DBeaver:

SELECT *
FROM leituras
WHERE timestamp >= '2026-04-04'
AND timestamp < '2026-04-05'
ORDER BY timestamp ASC;

Cole abaixo a saída obtida:

Tabela exibida na imagem:

id  station_id  timestamp   temperature_c   humidity_pct
9   EM-ARACATUBA-01 2026-04-04 08:00:00.000 -0300   23.4    76.2
10  EM-ARACATUBA-01 2026-04-04 09:00:00.000 -0300   25.2    72
11  EM-ARACATUBA-01 2026-04-04 10:00:00.000 -0300   25.9    70.5
12  EM-ARACATUBA-01 2026-04-04 11:00:00.000 -0300   27.1    67.4
2. SELECT final - Conferência do UPDATE

Execute no DBeaver:

SELECT *
FROM leituras
WHERE station_id = 'EM-ARACATUBA-01'
AND timestamp = '2026-04-04 09:00:00';

Cole abaixo a saída obtida:

Tabela exibida na imagem:

id  station_id  timestamp   temperature_c   humidity_pct
10  EM-ARACATUBA-01 2026-04-04 09:00:00.000 -0300   25.2    72
3. SELECT final - Conferência do DELETE

Execute no DBeaver:

SELECT *
FROM leituras
WHERE station_id = 'EM-ARACATUBA-01'
AND timestamp = '2026-04-04 11:00:00';

Cole abaixo a saída obtida:

A imagem mostra que não há registros retornados.

Texto do documento:

Se o DELETE foi feito corretamente, esse SELECT não deverá retornar registros.

4. SELECT final - Todas as leituras ordenadas

Execute no DBeaver:

SELECT *
FROM leituras
ORDER BY id ASC;

Cole abaixo a saída obtida:

Tabela mostrada na imagem:

id  station_id  timestamp   temperature_c
1   EM-ARACATUBA-01 2026-04-01 08:00:00.000 -0300   24.5
2   EM-ARACATUBA-01 2026-04-01 09:00:00.000 -0300   25.8
3   EM-ARACATUBA-01 2026-04-01 10:00:00.000 -0300   27.2
4   EM-ARACATUBA-01 2026-04-02 08:00:00.000 -0300   23.8
5   EM-ARACATUBA-01 2026-04-02 09:00:00.000 -0300   24.6
6   EM-ARACATUBA-01 2026-04-02 10:00:00.000 -0300   25.4
7   EM-ARACATUBA-01 2026-04-02 11:00:00.000 -0300   26.1
8   EM-ARACATUBA-01 2026-04-02 12:00:00.000 -0300   27
9   EM-ARACATUBA-01 2026-04-04 08:00:00.000 -0300   23.4
10  EM-ARACATUBA-01 2026-04-04 09:00:00.000 -0300   25.2
11  EM-ARACATUBA-01 2026-04-04 10:00:00.000 -0300   25.9
5. Teste pela API

Acesse no navegador:

http://localhost:3000/api/leituras/data/2026-04-04

Cole abaixo o resultado retornado pela API:

{
  "dataPesquisada": "2026-04-04",
  "total": 3,
  "leituras": [
    {
      "id": 9,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T11:00:00.000Z",
      "temperature_c": 23.4,
      "humidity_pct": 76.2
    },
    {
      "id": 10,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T12:00:00.000Z",
      "temperature_c": 25.2,
      "humidity_pct": 72
    },
    {
      "id": 11,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T13:00:00.000Z",
      "temperature_c": 25.9,
      "humidity_pct": 70.5
    }
  ]
}
6. Conclusão

Explique com suas palavras a diferença entre INSERT, UPDATE e DELETE.

Resposta:

INSERT = inserir
UPDATE = atualizar
DELETE = excluir