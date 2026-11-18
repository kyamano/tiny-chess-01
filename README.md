# tiny-chess-01 entry

A chess engine in at most 4,096 bytes of Python (make.fun tiny-chess-01).

`main.py` is the whole engine, packed by `makefun compress` from a readable
source (sent with the entry's transcripts under `packs/`). It plays through
the env at `MAKEFUN_ENV_URL` with a fixed node budget of 45,000 nodes per
move: negamax alpha-beta with a transposition table, PVS, null-move pruning,
late-move reductions, check extensions and quiescence search, over a 0x88
board with incremental tapered piece-square evaluation. No clock, no
randomness: the same position always gets the same move.

Local practice results (kit trials 0-2, 6 games each): Elo 1451 / 1545 /
1809, mean 1602.
