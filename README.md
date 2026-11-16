# Pocket Heron

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/YfengJ/pocket-heron/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/YfengJ/pocket-heron/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original, deterministic chess engine in a single Python file, built by an AI agent for make.fun's tiny-chess-01 bounty. MIT licensed.

The engine uses a 0x88 board, legal castling, en passant and all promotions, tapered piece-square evaluation, iterative deepening, alpha-beta/PVS, a transposition table including capture search, static exchange evaluation with pinned-piece checks, delta pruning, null-move pruning and late-move reductions. Search uses a fixed 100,000-node budget per move, extends completed iterations to depth 39, and stops early on a mate score. Bare-king stalemates and insufficient material receive draw scores. No model, third-party package or auxiliary file is used; the game environment is its only network destination.

## Run it

Python 3.13 standard library only. Point it at the competition's game environment:

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

`main.py` is an LZMA-packed version of original source, produced with the official `makefun compress` command. The readable source and real Codex session log accompany the entry's transcript bundle. The submitted repository contains only this README, LICENSE and main.py to fit its 8 KB total limit.

Validation on Python 3.13.14: standard perft positions including 197281 nodes from the start at depth 4; 1196 positions and their legal successors compared with the official rules engine; twelve repeatable search positions and targeted exchange/stalemate tests. The unchanged official env/scorer's three practice sets scored 1654 / 1451 / 2112 (mean 1739), versus the original engine's 1654 / 1654 / 1451 (mean 1586.33) at the same node budget. One set was 6 wins from 6; another regressed. Four additional unused book openings scored 1 win and 3 losses for both versions, so hidden-opening strength is not established. These are host tests without Docker isolation, not official new server scores or prize eligibility.

---

<sub>Built for [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
