# Calculator Frontend

The web front end of the calculator system. It only handles the UI and interaction —
no calculation here: type an expression, press equals, send it to the back end, and
display whatever the back end returns, along with the history.

## Tech stack

HTML + CSS + plain JavaScript. No framework, no build step.

## Layout

```text
index.html
css/style.css
js/config.js    back-end address
js/app.js       interaction and requests
```

## Run

Recommended: let the back end serve these files. Copy this folder into the back end's
`src/main/resources/webapp/`, start the back end, and open its URL.

You can also open `index.html` directly (or via any static server). In that case set the
back-end address in `js/config.js` first:

```js
window.API_BASE = 'http://localhost:8080';
```

The back end must be running.

## Features

- Basic arithmetic, parentheses, decimals, unary signs
- Power, square root, factorial, modulo, trig and inverse trig, log, exp, π, e, Ans
- DEG / RAD toggle
- History: list, delete one record, clear all
- Keyboard input (Enter to calculate, Backspace, Esc to clear)

## API used

| Action | Request |
|---|---|
| Calculate | `POST /api/calculate` |
| List history | `GET /api/history` |
| Delete one | `DELETE /api/history/{id}` |
| Clear all | `DELETE /api/history` |
