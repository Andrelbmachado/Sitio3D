# PLANO — Sítio 3D

Plano por fases para sair de "só documentação" até um modelo 3D do sítio, consultável e versionado.

**Estado em 21/10/2026:** só existem `README.md` e este `PLANO.md`. Nenhuma fase abaixo foi iniciada.

Cada fase tem: objetivo, tarefas (checklist), entregável e critério de pronto. Uma fase só começa quando a anterior cumprir o critério de pronto.

---

## Fase 0 — Base do repositório

**Objetivo:** repositório pronto para receber arquivos sem bagunça.

- [ ] Criar pastas `modelos/`, `medidas/`, `fotos/`, `anotacoes/` (cada uma com um `README.md` curto explicando o conteúdo)
- [ ] Criar `.gitignore` (ignorar `*.blend1`, `.DS_Store`, `log.txt`, arquivos temporários)
- [ ] Decidir sobre Git LFS para `*.jpg`, `*.png`, `*.blend`, `*.glb` (recomendado se fotos passarem de ~50 MB no total)
- [ ] Registrar a convenção de nomes (seção abaixo) nos READMEs das pastas

**Entregável:** estrutura de pastas commitada.
**Pronto quando:** clonar o repo mostra as 4 pastas e o `.gitignore`; `git lfs track` configurado (ou decisão de não usar registrada aqui).

## Fase 1 — Levantamento (dados brutos)

**Objetivo:** ter os dados reais do sítio antes de modelar qualquer coisa.

- [ ] Dividir o sítio em áreas nomeadas (ex.: `casa`, `galpao`, `pomar`, `acude`, `divisa-norte`) e listar em `anotacoes/areas.md`
- [ ] Medidas do perímetro do terreno → `medidas/medidas.csv`
- [ ] Medidas de cada construção (comprimento, largura, altura, posição relativa) → mesmo CSV
- [ ] Fotos de cada área (mínimo 4 por área: N, S, L, O) → `fotos/`
- [ ] Uma nota por área em `anotacoes/<area>.md` (uso atual, problemas, ideias)
- [ ] Opcional: coordenadas GPS dos cantos do terreno (celular ou Google Earth)

Formato do `medidas.csv`:

```csv
area,elemento,medida,valor,unidade,data,fonte
casa,parede-frente,comprimento,12.40,m,2026-10-21,trena
```

**Entregável:** CSV + fotos + notas cobrindo todas as áreas da lista.
**Pronto quando:** toda área de `areas.md` tem pelo menos 1 medida, 4 fotos e 1 nota.

## Fase 2 — Modelo 3D simples (blocos)

**Objetivo:** primeira versão 3D em escala, sem detalhe.

- [ ] Escolher ferramenta (recomendado: Blender, gratuito) e registrar aqui
- [ ] Modelar terreno plano com o perímetro da Fase 1, em metros, escala 1:1
- [ ] Construções como caixas nas dimensões e posições do CSV
- [ ] Salvar `modelos/sitio.blend` e exportar `modelos/sitio.glb`

**Entregável:** `sitio.blend` + `sitio.glb`.
**Pronto quando:** 3 medidas conferidas no modelo batem com o CSV (erro < 5%).

## Fase 3 — Detalhamento

**Objetivo:** modelo reconhecível por quem conhece o sítio.

- [ ] Relevo do terreno (curvas de nível, se houver dados; senão, aproximação pelas fotos)
- [ ] Telhados, portas, janelas das construções principais
- [ ] Árvores, cercas, açude/caminhos como objetos simples
- [ ] Texturas básicas a partir das fotos

**Pronto quando:** alguém da família identifica cada área no modelo sem ajuda.

## Fase 4 — Visualização e uso (opcional)

**Objetivo:** ver o modelo sem instalar nada.

- [ ] Página HTML simples com `<model-viewer>` carregando `sitio.glb`
- [ ] Publicar via GitHub Pages
- [ ] Usar o modelo para planejar (ex.: nova construção, plantio) registrando cenários em `anotacoes/`

**Pronto quando:** link público abre o modelo no celular.

---

## Convenções

- **Fotos:** `AAAA-MM-DD_area_descricao.jpg` (ex.: `2026-10-21_acude_vista-norte.jpg`)
- **Áreas:** minúsculas, sem acento, hífen no lugar de espaço
- **Unidades:** metros, sempre
- **Commits:** `<pasta>: <o que mudou>` (ex.: `medidas: perímetro divisa norte`)

## Decisões em aberto

| Decisão | Opções | Quando decidir |
|---|---|---|
| Git LFS | usar / não usar | Fase 0 |
| Ferramenta 3D | Blender / SketchUp / outra | início da Fase 2 |
| Fonte do relevo | GPS / topografia / estimativa | início da Fase 3 |
| Publicação | GitHub Pages / privado | Fase 4 |
