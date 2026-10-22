# 🏡 Sítio 3D

Um lugar só para guardar **tudo sobre o sítio em 3D**: modelos, medidas, fotos e anotações — organizado, versionado e fácil de achar.

> **Status atual:** fase inicial. O repositório tem só a documentação (este README e o [PLANO.md](PLANO.md)).
> Ainda **não existe código, modelo 3D nem arquivo de dados**. Tudo abaixo marcado como _planejado_ é intenção, não algo pronto.

---

## Por que este projeto existe

Informação sobre um terreno costuma ficar espalhada: fotos no celular, medidas num caderno, croquis em papel, ideias em mensagens. O Sítio 3D quer juntar tudo num só lugar, com histórico de mudanças (Git), para:

- consultar rápido uma medida ou foto de qualquer parte do sítio;
- planejar obras, plantios e reformas em cima de um modelo 3D fiel;
- não perder nada com o tempo.

## O que vai ter aqui

| Item | Descrição | Situação |
|---|---|---|
| Documentação | README e plano por fases | ✅ existe |
| Estrutura de pastas | `modelos/`, `medidas/`, `fotos/`, `anotacoes/` | 🕓 planejado |
| Medidas | Tabela com dimensões de terreno e construções (CSV) | 🕓 planejado |
| Fotos | Fotos organizadas por área e data | 🕓 planejado |
| Anotações | Notas em Markdown por área do sítio | 🕓 planejado |
| Modelo 3D | Modelo do terreno e construções (ex.: Blender `.blend` + exportação `.glb`) | 🕓 planejado |
| Visualização | Forma simples de ver o modelo no navegador | 🕓 planejado |

## Estrutura de pastas (planejada)

```text
Sitio3D/
├── README.md
├── PLANO.md
├── modelos/      # arquivos 3D (.blend, .glb)
├── medidas/      # medidas.csv e croquis
├── fotos/        # AAAA-MM-DD_area_descricao.jpg
└── anotacoes/    # uma nota .md por área
```

## Como contribuir / usar

Hoje o uso é só leitura da documentação. Quando as pastas existirem:

1. Coloque o arquivo na pasta certa, seguindo a convenção de nomes do [PLANO.md](PLANO.md).
2. Faça commit com uma mensagem clara (ex.: `fotos: açude, vista norte`).
3. Arquivos grandes (fotos, modelos) — ver a decisão sobre Git LFS no plano.

## Próximos passos

O roteiro detalhado, com tarefas e critérios de pronto, está em **[PLANO.md](PLANO.md)**.

---

_Documentação revisada em 21/10/2026. Itens marcados como **planejado** ainda não existem no repositório._
