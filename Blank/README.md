# Installation

First, clone this repo at `app/design/frontend`

```bash
cd app/design/frontend
git clone https://github.com/kevinruscoe/magento-theme-kevinruscoe-blank/
```

Then install snowdogs blank sass theme with

```bash
composer require snowdog/theme-blank-sass
```

Then install snowdogs frontend tools

```bash
composer require snowdog/frontools
cd vendor/snowdog/frontools
yarn install
yarn setup
```

Snowdogs frontend tools requires a `themes.json` file, so make this at `dev/tools/frontools/config/themes.json`.

```json
{
  "theme-blank-sass": {
    "src": "vendor/snowdog/theme-blank-sass",
    "dest": "pub/static/frontend/Snowdog/blank",
    "locale": ["en_US"],
    "ignore": [".test"]
  },
  "kevinruscoe-theme": {
    "parent": "theme-blank-sass",
    "src": "app/design/frontend/KevinRuscoe/Theme",
    "dest": "pub/static/frontend/KevinRuscoe/Theme",
    "locale": ["en_US", "en_GB"]
  }
}
```

Finally, set your theme to the new theme and clear cache.