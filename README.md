# acc-calc-data

Banco de referência **Assetto Corsa Competizione (ACC)** — curadoria comunitária em YAML versionado.

Este repositório alimenta a calculadora [acc-calc](https://github.com/jgbmiranda/acc-calc) com dados confiáveis sobre:

- **Carros** (massa, consumo base, BoP, classes GT3/GT4/GTC/TCX)
- **Pistas** (layout, comprimento, voltas-base, degradação)
- **Pneus** (compostos, faixa de temperatura, degradação por composto)

## Estrutura

```
acc-data/
├── schema/       # JSON Schema dos formatos YAML (validação automática no CI)
│   ├── car.schema.json
│   ├── track.schema.json
│   └── tire.schema.json
├── cars/         # Um YAML por carro, sub-pasta por classe (gt3/, gt4/, ...)
├── tracks/       # Um YAML por pista (ex: monza.yaml)
└── tires/        # Compostos de pneu (ex: dhe2.yaml)
```

## Contribuindo

1. Fork este repo
2. Edite ou adicione YAMLs em `acc-data/`
3. Abra PR — o workflow `validate` valida YAMLs contra os JSON Schemas automaticamente

## Convenções

- **Slugs** em kebab-case ASCII (`bmw-m4-gt3`, não `BMW M4 GT3`)
- **Unidades** sempre explícitas no campo (`fuel_liters`, `mass_kg`, `pressure_psi`)
- **Localização** em pt-BR no campo `display_name`; chaves técnicas em inglês

## Licença

Conteúdo de domínio público / CC0 — dados factuais sobre o jogo.

Marcas: "Assetto Corsa Competizione" é marca registrada da Kunos Simulazioni. Este projeto não é oficial.
