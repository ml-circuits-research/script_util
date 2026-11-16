# script_util

`bin/tmux_codex` pornește Codex în tmux și oferă un meniu pentru sesiuni active,
sesiuni oprite și conversațiile Codex din folderul curent.

```bash
./bin/tmux_codex
./bin/tmux_codex restart
```

Navighezi cu săgețile sau `j`/`k`, alegi cu Enter și ieși cu `q`.
Cu `x` poți închide o sesiune activă (cu confirmare) sau șterge o intrare oprită.
Te detașezi cu `Ctrl+b`, apoi `d`; rulezi din nou scriptul pentru reatașare.
Din interiorul tmux, alegerea unei sesiuni schimbă clientul curent la acea sesiune.
După ieșirea din Codex, sesiunea tmux rămâne deschisă cu un shell.

Conversațiile existente se reiau cu `codex resume ID`. Codex atribuie singur ID-ul
unei conversații noi, deci la repornirea unei sesiuni noi o alegi din lista folderului.
`restart` repornește sesiunile oprite pentru care ai ales deja o conversație.

Necesită `bash`, `tmux`, `codex` și `python3`. Istoricul tmux este separat de Claude,
în `~/.codex-tmux-sessions`. Poți configura `CODEX_BIN`, `CODEX_HOME`,
`CODEX_TMUX_SESSIONS_FILE` și `CODEX_TMUX_MAX_CONV` (implicit 10).
