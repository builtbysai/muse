# muse

Study notes and research behind the work. Deep dives into generative art,
printmaking, composition, and the techniques that feed the gallery pieces.

## Reading room

`build_index.py` generates a self-contained static reading room from the notes:

```sh
python3 build_index.py   # reads study/, writes site/
```

Stdlib only, no dependencies. Renders `site/index.html` (search, themed shelves,
catalogue), `site/notes/*.html` (one page per note, prev/next), and
`site/before.html` (plain baseline list). Everything is inlined; the site works
from file:// with no network access. Served live at https://builtbysai.com/muse/.
