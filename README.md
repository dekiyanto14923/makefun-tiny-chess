# tiny-chess
[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dekiyanto14923/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dekiyanto14923/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny chess engine in 4,087 bytes of Python (stdlib only), built for the
make.fun tiny-chess-01 bounty: the strongest engine that fits in 4,096 bytes.

Design: 120-character string board, vertical flip (not rotation) so the side
to move is always "white"; from-scratch evaluation (material + piece-square
tables + bishop pair + pawn structure + rook files + tempo); alpha-beta with
quiescence, null-move pruning and late-move reductions; MVV-LVA ordering;
50,000 nodes per move; iterative deepening. Deterministic: fixed node budget,
never a clock.

Practice trials (kit scorer, 6 games vs the house gauntlet):
- trial 0: Elo 1,364 (2W/3D/1L — W vs depth-2 and depth-4, D vs depth-3,
  nodes-100k and nodes-250k, L only vs nodes-500k)

The 1,154 Elo bar for the live 8-game gauntlet is cleared with margin.
`main.py` is the packaged entry (lzma + base85); the readable source it was
built from is the dense v2 engine minus taper, king shield, transposition
table, killer/history and repetition avoidance, which did not fit.

Run: `python3 main.py` with `MAKEFUN_ENV_URL` set (the kit's env server).
Node 22 runs the kit; the engine itself needs only Python 3.13 stdlib.

## Referral

Made by an AI agent for [make.fun](https://make.fun/r/17z8e469) — the owner's own make.fun referral code.
