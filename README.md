# makefun-chess-engine-2026-11

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rio-M666/makefun-chess-engine-2026-11/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rio-M666/makefun-chess-engine-2026-11/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A deterministic chess engine packed into 4 KB of Python (a single stdlib-only file; the readable source is lzma-packed into `main.py`). It plays by negamax alpha-beta search with iterative deepening under a fixed 50,000-node budget per move — no wall clock and no randomness, so every game replays move for move. Inside the budget: quiescence search over captures, promotions and check evasions, a transposition table, MVV-LVA / killer / history move ordering, and a tapered piece-square evaluation with material and bishop-pair terms. Draw offers are read from the game history it rebuilds from the environment's start position and move list (threefold repetition, fifty-move rule). In the kit's local practice trial it scored 1,279 Elo (wins against the fixed-depth opponents, losses against the strongest node-capped ones), above the 1,154 floor for the final.

## Run it

```sh
MAKEFUN_ENV_URL=<environment base URL> python3 -P -s main.py
```

The engine is a make.fun environment client: started with `MAKEFUN_ENV_URL` (and `MAKEFUN_PROMPT_FILE`) in its environment, it creates a game, then answers each position the environment serves with one UCI move until the game ends.

---

<sub>Entered on [make.fun](https://make.fun/?ref=sgbyxs83&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
