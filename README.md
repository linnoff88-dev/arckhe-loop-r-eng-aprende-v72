# O loop que aprende â€” FormaÃ§Ã£o LOOP-R Engenharia (curso 5 de 6, o Ãºltimo)

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


Curso aberto e gratuito do INEMA.CLUB no formato INEMA Learning v7.2, em portuguÃªs, inglÃªs e espanhol:
**https://inematds.github.io/loop-r-eng-aprende-v72/** Â· [EN](https://inematds.github.io/loop-r-eng-aprende-v72/en/) Â· [ES](https://inematds.github.io/loop-r-eng-aprende-v72/es/)

Oito aulas para quem jÃ¡ usa Claude Code ou Codex no terminal: hipÃ³tese com nÃºmero, experimento keep/discard com git (desenho do autoresearch), veredito A/B com guarda-corpos, cartÃ£o de decisÃ£o, promoÃ§Ã£o e rollback (LOOP-R), liÃ§Ãµes com aprovaÃ§Ã£o em lote e revisÃ£o (SIL Loop R), regra vinculante no AGENTS.md, o risco de otimizar contra o prÃ³prio medidor, rastro e custo por ciclo, e a montagem das oito peÃ§as no seu sistema.

## O kit (`kit/`)

Scripts pequenos (python3 + bash + git, sem pip). Os ensaios nÃ£o chamam modelo; `agente-claude.sh` Ã© o Ãºnico que chama (`claude -p --tools "" --output-format json`, pela sua assinatura). O kit lÃª os repositÃ³rios pÃºblicos [loop-r](https://github.com/inematds/loop-r) e [sil-loop-r](https://github.com/inematds/sil-loop-r) em `~/projetos`, e nunca grava neles.

| arquivo | aula | o que faz |
|---|---|---|
| `hipotese.py`, `hipoteses/` | 1 | confere os sete campos da hipÃ³tese e calcula a amostra mÃ­nima de um A/B |
| `triagem/`, `novo-sistema.sh`, `medir.py` | 2, 6 | sistema de ensaio (classificador de triagem, 40 casos + 30 escondidos, sintÃ©ticos) e a mÃ©trica Ãºnica |
| `experimento.sh`, `agente-falso.sh`, `agente-claude.sh` | 2, 6, 7 | um ciclo keep/discard com git; `GUARDA`, `ESCONDIDOS` e `RASTRO` opcionais; `MEDIR`/`MEDIDOR` para o medidor do seu repo (o results.tsv nasce sozinho, fora do git) |
| `loopr.py` | 3 | veredito (teste z), cartÃ£o, decidir, promover, reverter |
| `contar-licoes.py` | 4 | mede o loop de liÃ§Ãµes em prosa (LESSONS/FALHAS/LIMITES), sÃ³ contagens |
| `hooks/settings-sessionstart.json` | 5 | hook que injeta `sil.py context --brief` em cada sessÃ£o |
| `hashes.py` | 6 | congela e confere o medidor (formato do sha256sum) |
| `custo-ciclo.py` | 7 | custo por ciclo, custo por keep e alertas a partir do rastro |
| `conferir-loop.py`, `montar.sh`, `loop.conf.exemplo` | 8 | confere as oito peÃ§as do loop |
| `blocos/`, `saidas/`, `capturar.sh` | â€” | cada bloco "Terminal" das aulas e a saÃ­da capturada em 19/10/2026 |

```bash
git clone https://github.com/inematds/loop-r-eng-aprende-v72 ~/projetos/loop-r-eng-aprende-v72
git clone https://github.com/inematds/loop-r ~/projetos/loop-r
git clone https://github.com/inematds/sil-loop-r ~/projetos/sil-loop-r
bash ~/projetos/loop-r-eng-aprende-v72/kit/blocos/a2-ensaio.sh
```

Os dados de vendas do exemplo do LOOP-R sÃ£o sintÃ©ticos (gerador com seeds escolhidos); os dados de triagem do kit tambÃ©m.

## Gerar o site

ConteÃºdo em `conteudo/<idioma>/` (JSON). O HTML Ã© gerado: `python3 gerar.py && python3 validar.py --links` (e `--lang en|es`). NÃ£o edite o HTML Ã  mÃ£o. Depois de mexer num bloco de terminal: `TMPDIR=<pasta> bash kit/capturar.sh` e `python3 ~/.claude/skills/formato-curso-v72/scripts/resolver-kit.py . --conferir`.

---

**EN** â€” *The Loop That Learns*, course 5 of 6 of the LOOP-R Engineering Track: numeric hypotheses, keep/discard experiments with git, A/B verdicts with guardrails, promotion and rollback, lessons that become binding rules, Goodhart, cost per cycle. Open and free (INEMA.CLUB).

**ES** â€” *El loop que aprende*, curso 5 de 6 de la FormaciÃ³n LOOP-R IngenierÃ­a: hipÃ³tesis con nÃºmero, experimentos keep/discard con git, veredictos A/B con barandillas, promociÃ³n y rollback, lecciones que se vuelven reglas vinculantes, Goodhart y costo por ciclo. Abierto y gratuito (INEMA.CLUB).

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>