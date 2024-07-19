# TRMNL localizations
collection of in-app labels, toast messages, and help messages to make [TRMNL](https://usetrmnl.com) comfortable for everyone.

## How it Works

1. the TRMNL web app is built in Ruby on Rails (v7) and follows the [I18n conventions](https://guides.rubyonrails.org/i18n.html)
2. all language-specific content is read from a "dictionary" file, not hard-coded in the frontend views
3. adding support for a new language is as simple as creating a dictionary file with a valid [i18n language code](https://github.com/ladjs/i18n-locales)

## How to Contribute

1. fork this repo
2. make a copy of `locales/en.yml` and create a new file, `locales/your-lang-code.yml`
3. submit a pull request and ask questions if you need help
