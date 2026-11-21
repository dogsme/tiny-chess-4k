[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dogsme/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dogsme/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# Tiny Chess — a chess engine in under 4 KB of Python

Built for the [make.fun bounty: Build the strongest chess engine in 4 KB of Python](https://make.fun/bounty/tiny-chess-01).

`main.py` is the whole engine: 3,433 bytes, Python 3.13, standard library only. It contains a complete legal move generator (castling, en passant, promotions, check evasion — perft-verified against the standard reference positions) built on precomputed attack and ray tables, a negamax alpha-beta search with iterative deepening, principal-variation search, a transposition table, quiescence, MVV-LVA and killer move ordering and a fixed node budget (deterministic: no clock, no randomness), and a material + piece-square-table evaluation with bishop-pair and pawn-structure terms. As the rules allow, the readable engine source (`engine.py`, kept beside the repo) is packed into `main.py` with the kit's own `makefun compress` (LZMA), which unpacks and execs it.

The engine plays through the make.fun env: it reads the game at `MAKEFUN_ENV_URL`, and for every position chooses a move with its search.

Run: the harness runs `python3 main.py` with `MAKEFUN_ENV_URL` set.
