ï»¿# O loop que aprende ê¢â¬â FormaêÂ§êÂ£o LOOP-R Engenharia (curso 5 de 6, o êÂºltimo)

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


Curso aberto e gratuito do INEMA.CLUB no formato INEMA Learning v7.2, em portuguêÂªs, inglêÂªs e espanhol:
**https://inematds.github.io/loop-r-eng-aprende-v72/** êÂ· [EN](https://inematds.github.io/loop-r-eng-aprende-v72/en/) êÂ· [ES](https://inematds.github.io/loop-r-eng-aprende-v72/es/)

Oito aulas para quem jêÂ¡ usa Claude Code ou Codex no terminal: hipêÂ³tese com nêÂºmero, experimento keep/discard com git (desenho do autoresearch), veredito A/B com guarda-corpos, cartêÂ£o de decisêÂ£o, promoêÂ§êÂ£o e rollback (LOOP-R), liêÂ§êÂµes com aprovaêÂ§êÂ£o em lote e revisêÂ£o (SIL Loop R), regra vinculante no AGENTS.md, o risco de otimizar contra o prêÂ³prio medidor, rastro e custo por ciclo, e a montagem das oito peêÂ§as no seu sistema.

## O kit (`kit/`)

Scripts pequenos (python3 + bash + git, sem pip). Os ensaios nêÂ£o chamam modelo; `agente-claude.sh` êÂ© o êÂºnico que chama (`claude -p --tools "" --output-format json`, pela sua assinatura). O kit lêÂª os repositêÂ³rios pêÂºblicos [loop-r](https://github.com/inematds/loop-r) e [sil-loop-r](https://github.com/inematds/sil-loop-r) em `~/projetos`, e nunca grava neles.

| arquivo | aula | o que faz |
|---|---|---|
| `hipotese.py`, `hipoteses/` | 1 | confere os sete campos da hipêÂ³tese e calcula a amostra mêÂ­nima de um A/B |
| `triagem/`, `novo-sistema.sh`, `medir.py` | 2, 6 | sistema de ensaio (classificador de triagem, 40 casos + 30 escondidos, sintêÂ©ticos) e a mêÂ©trica êÂºnica |
| `experimento.sh`, `agente-falso.sh`, `agente-claude.sh` | 2, 6, 7 | um ciclo keep/discard com git; `GUARDA`, `ESCONDIDOS` e `RASTRO` opcionais; `MEDIR`/`MEDIDOR` para o medidor do seu repo (o results.tsv nasce sozinho, fora do git) |
| `loopr.py` | 3 | veredito (teste z), cartêÂ£o, decidir, promover, reverter |
| `contar-licoes.py` | 4 | mede o loop de liêÂ§êÂµes em prosa (LESSONS/FALHAS/LIMITES), sêÂ³ contagens |
| `hooks/settings-sessionstart.json` | 5 | hook que injeta `sil.py context --brief` em cada sessêÂ£o |
| `hashes.py` | 6 | congela e confere o medidor (formato do sha256sum) |
| `custo-ciclo.py` | 7 | custo por ciclo, custo por keep e alertas a partir do rastro |
| `conferir-loop.py`, `montar.sh`, `loop.conf.exemplo` | 8 | confere as oito peêÂ§as do loop |
| `blocos/`, `saidas/`, `capturar.sh` | ê¢â¬â | cada bloco "Terminal" das aulas e a saêÂ­da capturada em 19/10/2026 |

```bash
git clone https://github.com/inematds/loop-r-eng-aprende-v72 ~/projetos/loop-r-eng-aprende-v72
git clone https://github.com/inematds/loop-r ~/projetos/loop-r
git clone https://github.com/inematds/sil-loop-r ~/projetos/sil-loop-r
bash ~/projetos/loop-r-eng-aprende-v72/kit/blocos/a2-ensaio.sh
```

Os dados de vendas do exemplo do LOOP-R sêÂ£o sintêÂ©ticos (gerador com seeds escolhidos); os dados de triagem do kit tambêÂ©m.

## Gerar o site

ConteêÂºdo em `conteudo/<idioma>/` (JSON). O HTML êÂ© gerado: `python3 gerar.py && python3 validar.py --links` (e `--lang en|es`). NêÂ£o edite o HTML êÂ  mêÂ£o. Depois de mexer num bloco de terminal: `TMPDIR=<pasta> bash kit/capturar.sh` e `python3 ~/.claude/skills/formato-curso-v72/scripts/resolver-kit.py . --conferir`.

---

**EN** ê¢â¬â *The Loop That Learns*, course 5 of 6 of the LOOP-R Engineering Track: numeric hypotheses, keep/discard experiments with git, A/B verdicts with guardrails, promotion and rollback, lessons that become binding rules, Goodhart, cost per cycle. Open and free (INEMA.CLUB).

**ES** ê¢â¬â *El loop que aprende*, curso 5 de 6 de la FormaciêÂ³n LOOP-R IngenierêÂ­a: hipêÂ³tesis con nêÂºmero, experimentos keep/discard con git, veredictos A/B con barandillas, promociêÂ³n y rollback, lecciones que se vuelven reglas vinculantes, Goodhart y costo por ciclo. Abierto y gratuito (INEMA.CLUB).

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>