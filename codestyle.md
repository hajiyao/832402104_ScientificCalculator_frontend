# Front-end Code Style (codestyle.md)

**Base standards: [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) and
[Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html).**
A few project-specific conventions are added below.

## 1. General

- Files are UTF-8. Indent with 4 spaces; never tabs.
- End every file with one blank line. Keep lines under 100 characters.
- End every statement with a semicolon.
- No front-end framework. Plain HTML / CSS / JavaScript only.

## 2. HTML

- Tag and attribute names are lowercase; attribute values use double quotes.
- Always declare `<!DOCTYPE html>`, `lang`, `charset`, and `viewport`.
- Use semantic structure: `h1`~`h3` for headings, `ul/li` for lists, `header/main/section` for blocks.
- No inline styles or inline event handlers (`onclick=""`). All styling and behavior live in separate files.

## 3. CSS

- Class names are lowercase with hyphens, e.g. `history-item`, `screen-result`.
- Group declarations per selector in this order: layout/positioning → box model → typography/color → the rest.
- Use hex or `rgba()` consistently; don't mix notations.
- No `!important` unless unavoidable.
- Responsive behavior is handled with media queries at a single 760px breakpoint.

## 4. JavaScript

- Variables use `var` (this project targets ES5). Names are `lowerCamelCase`.
- Constants are `UPPER_SNAKE_CASE`, e.g. `OPERATOR_TOKENS`.
- Strings use single quotes, except when building HTML attributes.
- Use strict mode (`'use strict'`) and wrap the code in an IIFE to avoid polluting globals.
- Always compare with `===` / `!==`, never `==`.
- Cache DOM queries in variables instead of re-querying.
- Render dynamic content with `textContent` / `createElement`. Never build `innerHTML` strings from user or back-end data, to prevent injection.
- All API calls go through one helper function, and errors are displayed in one place — no repeated `fetch` calls scattered around.

## 5. Responsibility boundaries

- The front end only handles interaction and display. **No expression evaluation on the client side.** No `eval`.
- History is never cached in `localStorage` or memory. It is always fetched from the back-end API.
- The back-end address is configured in exactly one place: `js/config.js`.
