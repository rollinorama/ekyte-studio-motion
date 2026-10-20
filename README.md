# eKyte Studio Motion

Material da pipeline de vídeos do Marketing da eKyte (pronuncia-se "êcaite").

## Como este repo se encaixa

| Camada | Onde fica | O que define |
| --- | --- | --- |
| Processo | Instruções do projeto "eKyte motion" no Claude | Tarefa no eKyte, etapas, formulários, confirmações |
| Contrato do vídeo | `rules/motion-studio-rules.md` | Como um filme é feito: render, look, som, contact sheet |
| Material | Todo o resto deste repo | Logos, fontes, telas, referências, código de render |

**Regra do repo:** fora de `rules/motion-studio-rules.md`, nenhum arquivo traz regras novas. Os demais são só material. Arquivo novo entra quando um teste mostrar que faltou.

## Pastas

| Pasta | O que vai aqui |
| --- | --- |
| `rules/` | `motion-studio-rules.md` |
| `brand/` | `marca-ekyte.md`, logos em SVG (`logos/`) e fontes com licença (`fonts/`) |
| `screens/` | Telas do produto por módulo, sem dados reais de cliente |
| `reference/` | Os vídeos aprovados que são o padrão, uma pasta por vídeo (ver `reference/README.md`) |
| `render/` | O `render.mjs` e o template da pipeline local que já gerou os vídeos aprovados |
