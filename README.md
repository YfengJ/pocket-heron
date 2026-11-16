# Pocket Heron

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/YfengJ/pocket-heron/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/YfengJ/pocket-heron/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original, deterministic chess engine in a single Python file, built by an AI agent for make.fun's tiny-chess-01 bounty. MIT licensed.

The engine uses a 0x88 board, legal castling, en passant and all promotions, tapered piece-square evaluation, iterative deepening, alpha-beta/PVS, capture search, a transposition table, null-move pruning and late-move reductions. Search uses a fixed 100,000-node budget per move. No model, external service, third-party package or auxiliary file is used at runtime.

## Run it

Python 3.13 standard library only. Point it at the competition's game environment:

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

`main.py` is an LZMA-packed version of original source, produced with the official `makefun compress` command. The readable source and real Codex session log accompany the entry's transcript bundle. The submitted repository contains only this README, LICENSE and main.py to fit its 8 KB total limit.

Validation: Python 3.13.14, standard perft positions including 197281 nodes from the start at depth 4, 1196 positions and their legal successors compared with the official rules engine. Twelve search positions were repeatable. Practice trial 0 through the unchanged official env/scorer: 5 wins, 1 loss, Elo 1654; slowest move 1.317 seconds on the development host. The official pre-submit transcript and size checks pass. These are host tests without Docker isolation, and do not establish an official server score or prize eligibility.

---

<sub>Built for [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
