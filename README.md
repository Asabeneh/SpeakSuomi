# Finnish Flow

Finnish Flow is a static, content-rich single-page site for English speakers to learn Finnish (A1→B2). It combines bite-sized lessons, grammar notes, vocabulary, reading passages, and an interactive placement quiz embedded in `index.html`.

## Features

- Single-file static site: `index.html` contains the UI, styles, content, and the placement quiz script.
- Interactive placement quiz (50 items) that parses the hidden assessment tables and scores the user.
- Clear learning roadmap from A1 to B2, grammar ladder, and practice materials.

## Quick start

1. Open the site in a browser:

   - Double-click `index.html`, or run a simple local server:

```bash
# Python 3
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

2. Navigate to the Placement test section or the anchor `#placement-test`.

## Files

- [index.html](index.html) — The complete site.
- [README.md](README.md) — This file.
- [CONTRIBUTING.md](CONTRIBUTING.md) — Contribution guidelines.
- [docs/QUIZ.md](docs/QUIZ.md) — Technical notes for the interactive quiz.

## Quiz internals (quick links)

- Quiz UI container: [index.html](index.html#L1702)
- Quiz parsing & scoring engine: [index.html](index.html#L2276)
- Hidden answer-key tables: [index.html](index.html#L921)

## CEFR mapping

- 0–25%: A1
- 26–50%: A2
- 51–75%: B1
- 76–100%: B2

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for code style and how to edit assessment items.

## License

Add a license file if you want to publish this project publicly.
