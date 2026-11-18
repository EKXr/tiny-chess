# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/EKXr/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/EKXr/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python: negamax alpha-beta search with a transposition table, MVV-LVA move ordering, check extensions and quiescence over captures, promotions and check evasions, evaluating material plus piece-square tables with a phase-blended king table. It searches to a fixed node budget (60,000 nodes a move), never to a clock, so every replay plays the same moves.

## Run it

```sh
MAKEFUN_ENV_URL=<env url from the kit> python3 main.py
```

Grade it with the kit: `makefun grade-local --kit . --bot <this repo> --driver docker` (or `--driver process` without Docker).

---
<sub>Entered on [make.fun](https://make.fun/?ref=zs90sebx&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

## Source and packaging

`main.py` is the packaged entry point, generated from the readable source `engine.py` with the kit's compress step: `node cli/makefun.mjs compress engine.py --out main.py`, run on its own after the last change to the source.
`engine.py` is kept in this repository folder alongside `main.py` so the readable source travels with the submission bundle, but it is not committed: the repository as a whole is capped at 8,192 bytes, and `main.py` alone already uses 4,079 of them.
