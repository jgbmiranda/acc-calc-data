# acc-calc-data

> Banco de dados de referência do Assetto Corsa Competizione para o app `acc-calc`. Fonte da verdade do **princípio #0 (Fidelidade Física ACC)**.

## Estrutura

```
acc-data/
├── schema/         # JSON Schemas (Draft 2020-12) — validação
├── cars/<class>/   # Carros por classe (gt3, gt4, etc)
├── tracks/         # Pistas
├── tires/          # Compostos de pneu
└── README.md
```

## Versionamento (NFR-13)

- **package.json `version`** define semver do banco
- **Tag git** por release: `v2025.3.1`
- **Patch (X.X.+1):** correção de erro de dados ou ajuste fino
- **Minor (X.+1.0):** novo carro, nova pista, BoP update da Kunos
- **Major (+1.0.0):** mudança de schema (rebuild do app)

## Validação

Toda PR roda CI com:
1. JSON Schema validation contra `schema/*.schema.json`
2. Sanity ranges (BoP plausível, lap times razoáveis, etc)
3. Cross-references (composto referenciado em car existe em tires/)

## Como contribuir

1. Fork
2. Edite YAML respeitando o schema
3. PR com source dos dados (link para changelog Kunos, leaderboard, etc)
4. CODEOWNER aprova
5. Após merge, app recebe webhook e invalida cache em ≤ 5min

## Glossário

- **BoP:** Balance of Performance — ajuste de peso/potência por pista
- **DHE2:** composto seco GT3 default
- **Pit time:** tempo mínimo estacionado no pit obrigatório

## Update SLA

NFR-14: atualização ≤ 7 dias após patch oficial Kunos com mudança relevante.
