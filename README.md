# amogus · on TON

A single-file interactive meme landing page built around an illustrated character,
animated emoji decorations, and a small persistent interaction counter.

**Status:** browser-only frontend experiment. The TON theme is part of the page identity;
this source does not implement a wallet, backend, shared leaderboard, or token contract.
Deployment availability has not been verified.

## Implementation highlights

- HTML, inline CSS, inline SVG, and vanilla JavaScript in one document.
- Responsive layout and CSS-animated decorative elements created in the browser.
- Click interactions that update a counter and display transient toast feedback.
- Persistence through `localStorage` under the `sus` key.
- A source-reference card linking to the Telegram-related post used by the page.

## Source map

| File | Responsibility |
| --- | --- |
| [index.html](index.html) | Complete layout, illustration, animation, counter, and page content |
| [.gitignore](.gitignore) | Local secret and session-file safeguards |

The counter belongs to the current browser storage. It is not a global usage metric.

## Local preview

Requirements: Python 3 and a browser. From the repository root:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Open `http://127.0.0.1:8000`. The source requires no package installation or build step.
Using an HTTP origin gives localStorage a consistent origin for repeatable checks.

## Quick manual check

1. Click the character and confirm that the visible counter changes.
2. Use the two action buttons and observe their counter / toast behavior.
3. Reload the same origin and confirm that the counter is retained.
4. Resize the viewport and inspect the illustration, action buttons, and reference card.

These are reproducible checks to run locally; automated browser coverage is not included.

## Content maintenance

The illustration, decorative emoji choices, feedback strings, and event handlers are in
`index.html`. Preserve the `stage`, `susBtn`, `tonBtn`, `count`, and `toast` element IDs when
editing markup because the script resolves those elements directly.

The page retains a [source post reference](https://x.com/i/status/2060382820548415878)
and a link to [TON](https://ton.org). Their inclusion is not a statement of endorsement.

## Verification and reuse

The existing [GitHub Pages demo](https://arar228.github.io/amogus-ton/) returned
HTTP 200 on 2026-09-07 and serves the root of `main`.

Documentation checks cover the static entrypoint and inline JavaScript syntax.
There is no test runner or deployment workflow file in the repository; browser behavior and
external content remain separate checks. Character references, logos, and third-party branding
retain their owners' rights. A repository license has not been provided.
