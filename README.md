# script_util

Scripturi în `bin/` pentru gestionarea sesiunilor de agenți AI în `tmux`:

- `bin/tmux_claude` — Claude Code (`claude`)
- `bin/tmux_codex` — Codex (`codex`)
- `bin/tmux_omp` — Oh My Pi (`omp`)
- `bin/tmux_agy` — Google Antigravity CLI (`agy --dangerously-skip-permissions`)
- `bin/tmux_vibe` — Mistral Vibe (`vibe --auto-approve --trust`)

```bash
./bin/tmux_agy
./bin/tmux_vibe
./bin/tmux_claude
./bin/tmux_codex
./bin/tmux_omp
```

Navighezi cu săgețile sau `j`/`k`, alegi cu Enter și ieși cu `q`.
Cu `x` poți închide o sesiune activă (cu confirmare) sau șterge o intrare oprită.
Te detașezi cu `Ctrl+b`, apoi `d`; rulezi din nou scriptul pentru reatașare.
Din interiorul tmux, alegerea unei sesiuni schimbă clientul curent la acea sesiune.
După ieșirea din agent, sesiunea tmux rămâne deschisă cu un shell.
Sesiunile oprite sunt păstrate în istoric și pot fi repornite manual din meniu.
