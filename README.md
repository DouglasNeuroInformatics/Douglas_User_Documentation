# Douglas Neuroinformatics Platform Documentation
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-7-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

This repository contains documentation for the Douglas Neuroinformatics Platform, including guidance on getting started, using the system, research methods, available services, and getting help.  The docs can be found here: https://docs.douglasneuroinformatics.ca

## To build locally

Follow these steps.
1. `uv venv`
2. `cd docs`
3. `uv pip install -r requirements.txt`
4. `uv run make html`
5. `open _build/html/index.html`

To make changes, edit the markdown files.
If you have done a major refactor (renaming files or directory structures), 
you can use `make clean html` to create a fresh build directory for local testing.

Also check out

- [MyST docs](https://myst-parser.readthedocs.io/en/latest/)
- [SPHINX docs](https://www.sphinx-doc.org/en/master/usage/quickstart.html)

## Translations (French)

English markdown files are the source. French translations use the standard
[Sphinx gettext workflow](https://www.sphinx-doc.org/en/master/usage/advanced/intl.html):
each page has a matching `.po` file under `docs/locales/fr/LC_MESSAGES/`
(e.g. `docs/available_services/chatdnp.md` ->
`docs/locales/fr/LC_MESSAGES/available_services/chatdnp.po`).
Any string that has no translation falls back to English, so pages can be translated one at a time.

1. `cd docs`
2. `pip install sphinx-intl`
3. Extract the English strings: `make gettext`
4. Create or update the French `.po` files: `sphinx-intl update -p _build/gettext -l fr`.
5. Fill in the `msgstr ""` entries in the `.po` file. Remove any `#, fuzzy` flag once a string is checked.
6. Build both languages side by side:
   - `sphinx-build -b html . _build/html/en`
   - `sphinx-build -b html -D language=fr . _build/html/fr`
7. Open `docs/_build/html/en/index.html` and use the **Français** / **English** link
   at the bottom of the sidebar menu to switch languages.

When the English text of a page changes, re-run steps 3 and 4.
Changed strings are marked `#, fuzzy` and show in English until the translation is reviewed.

### Switching languages

The **Français** / **English** link in the sidebar (`docs/_templates/layout.html`) swaps the
`/en/` or `/fr/` part of the current page's URL, so it opens the same page in the other language.
It matches the Read the Docs URL layout (`/en/latest/...` and `/fr/latest/...`)
and the local `_build/html/en` and `_build/html/fr` layout above.
The link is hidden when the URL has no language part (e.g. a plain `make html` build).

On Read the Docs, French is published as a separate translation project
(language `fr`) that points to this same repository and is linked to the main project
under *Admin > Translations*. Read the Docs then also lists both languages in its flyout menu.

## Contributing

If you want to contribute your expertise to this documentation,
the best place to start would be to 
[create a new issue](https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/issues)
and describe the content you plan on adding. 
This will allow other contributors to discuss with you 
and is a good way to check if someone else is already working on a similar idea that you can collaborate on.

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/isabelbacellar"><img src="https://avatars.githubusercontent.com/u/87087618?v=4?s=100" width="100px;" alt=""/><br /><sub><b>isabelbacellar</b></sub></a><br /><a href="#ideas-isabelbacellar" title="Ideas, Planning, & Feedback">🤔</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/pulls?q=is%3Apr+reviewed-by%3Aisabelbacellar" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="https://github.com/gdevenyi"><img src="https://avatars.githubusercontent.com/u/3001850?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Gabriel A. Devenyi</b></sub></a><br /><a href="#ideas-gdevenyi" title="Ideas, Planning, & Feedback">🤔</a> <a href="#content-gdevenyi" title="Content">🖋</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/commits?author=gdevenyi" title="Documentation">📖</a> <a href="#projectManagement-gdevenyi" title="Project Management">📆</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/commits?author=gdevenyi" title="Tests">⚠️</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/pulls?q=is%3Apr+reviewed-by%3Agdevenyi" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="https://github.com/surchs"><img src="https://avatars.githubusercontent.com/u/1302022?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Sebastian Urchs</b></sub></a><br /><a href="#ideas-surchs" title="Ideas, Planning, & Feedback">🤔</a> <a href="#content-surchs" title="Content">🖋</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/commits?author=surchs" title="Documentation">📖</a> <a href="#projectManagement-surchs" title="Project Management">📆</a></td>
    <td align="center"><a href="https://github.com/jeremie-fouquet"><img src="https://avatars.githubusercontent.com/u/6575734?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Jeremie Fouquet</b></sub></a><br /><a href="#content-jeremie-fouquet" title="Content">🖋</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/commits?author=jeremie-fouquet" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/LuceroGG"><img src="https://avatars.githubusercontent.com/u/43321220?v=4?s=100" width="100px;" alt=""/><br /><sub><b>LuceroGG</b></sub></a><br /><a href="#userTesting-LuceroGG" title="User Testing">📓</a> <a href="#ideas-LuceroGG" title="Ideas, Planning, & Feedback">🤔</a></td>
    <td align="center"><a href="https://github.com/devdinie"><img src="https://avatars.githubusercontent.com/u/54685871?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Swapna</b></sub></a><br /><a href="#userTesting-devdinie" title="User Testing">📓</a> <a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/issues?q=author%3Adevdinie" title="Bug reports">🐛</a> <a href="#ideas-devdinie" title="Ideas, Planning, & Feedback">🤔</a></td>
    <td align="center"><a href="https://github.com/raihaan"><img src="https://avatars.githubusercontent.com/u/7913859?v=4?s=100" width="100px;" alt=""/><br /><sub><b>raihaan</b></sub></a><br /><a href="#ideas-raihaan" title="Ideas, Planning, & Feedback">🤔</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/thomasbeaudry"><img src="https://avatars.githubusercontent.com/u/7085398?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Thomas Beaudry</b></sub></a><br /><a href="https://github.com/DouglasNeuroInformatics/Douglas_User_Documentation/commits?author=thomasbeaudry" title="Documentation">📖</a> <a href="#content-thomasbeaudry" title="Content">🖋</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
