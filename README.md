[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dogsme/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dogsme/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# Tiny Chess — a chess engine in under 4 KB of Python

Built for the [make.fun bounty: Build the strongest chess engine in 4 KB of Python](https://make.fun/bounty/tiny-chess-01).

`main.py` is the whole engine: 3,267 bytes, Python 3.13, standard library only. It contains a complete legal move generator (castling, en passant, promotions, check evasion — perft-verified against the standard reference positions), a negamax alpha-beta search with quiescence, MVV-LVA move ordering and a fixed node budget (deterministic: no clock, no randomness), and a material + positional evaluation. As the rules allow, the engine source is packed into `main.py` as a zlib/base85 payload that unpacks and execs itself; the readable source is developed and tested alongside it.

The engine plays through the make.fun env: it reads the game at `MAKEFUN_ENV_URL`, and for every position chooses a move with its search.

Run: the harness runs `python3 main.py` with `MAKEFUN_ENV_URL` set.
