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

Fiecare meniu afișează doar sesiunile tmux ale agentului său. Sesiunile sunt
grupate în „Directorul curent” și „Globale (alte directoare)”, separat pentru
cele active și cele oprite. Directorul este folderul de pornire al sesiunii.

Sesiunile noi primesc marcajul tmux `@agent`; un marcaj al altui agent are
prioritate față de nume sau istoricul vechi. Sesiunile vechi sunt recunoscute
după prefixul agentului, conversația salvată sau executabilul agentului din panou.
Intrările vechi fără indicii despre agent sunt ascunse. Istoricul nou păstrează
și agentul, inclusiv pentru sesiunile cu nume personalizat.

Sub fiecare sesiune tmux apare timpul relativ: de exemplu,
`started 2 hours ago · active 5 minutes ago`. Activitatea este cea raportată
de tmux, inclusiv output-ul agentului, nu doar interacțiunea utilizatorului.
Pentru sesiunile oprite se afișează ultimele valori observate când meniul
a fost deschis. Pentru istoricul vechi fără timpi salvați apare `unknown`.

Dacă agentul s-a închis și panoul a rămas la shell, sesiunea apare la oprite.
La reluare, agentul pornește într-o fereastră nouă a aceleiași sesiuni tmux,
păstrând fereastra veche și output-ul ei. Dacă sesiunea tmux nu mai există,
este recreată. O conversație salvată este reluată direct; în Codex, dacă ID-ul
nu este cunoscut, poți continua ultima conversație din folder sau alege alta.
Erorile de lansare/atașare permit revenirea la meniu.
