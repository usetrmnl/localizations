# TRMNL localizations guide
overview of our web application, plugin renders, and custom plugin dictionary for higher context contributions.

## web application
TRMNL leverages YAML formatted files with a resource-based hierarchy. content on the Account page (`/account`) is thus nested:

```
account:
  index:
    title: Account
    tagline: Manage your account settings
```

if a given phrase is used in other locations, it will be placed in the "root" node of the YML file as global variable:

```
en:
  add: Add
  back: Back
  cancel: Cancel
```

## plugin renders
TRMNL namespaces each native plugin's text content into a node matching the plugin's "keyname", for example `days_left_year` represents the "Days Left This Year" plugin.

```
days_left_year:
  title: Days Left This Year
  days_passed: Days Passed
  days_left: Days Left
```

plugin render localizations are more useful than web application contributions, as TRMNL generates millions of screens every month.

## custom plugins
TRMNL lets users build their own plugins, which they may want to share with others.

```
es-ES:
  # namespace to not interfere with other localizations
  custom_plugins:

    # generic words and phrases to make custom plugins more accessible
    today: hoy
    tomorrow: mañana
  ```

learn how users can leverage this dictionary here:
https://help.usetrmnl.com/en/articles/10347358-custom-plugin-filters

## how to provide localizations
in [a previous version](https://github.com/usetrmnl/localizations/blob/87c0ce5b4b71bff2f80346065aa50a5ce7a7e050/GUIDE.md) of this guide we provided annotated screenshots for each phrase.

however this approach was cumbersome. if our interface changed or new phrases were added, the guide here was not always up-to-date.

to ensure this repository's YML files are in parity with our website, we now support a `raw` locale that can be enabled while creating localizations.

<kbd>![trmnl-localizations-raw-locale-example](https://github.com/usetrmnl/localizations/blob/master/support/raw_locale_example.png)</kbd>

1. visit any TRMNL web page, for example `https://usetrmnl.com/dashboard`
2. add `?locale=raw` to the URL and refresh the page

this adds context for which localization phrases are used, and where. you may also visit your Account > Locale > set to "raw" and then click around the app.

to localize plugin renders, first pick a plugin here (requires login):
https://usetrmnl.com/plugins/demo

then add the same `?locale=raw` param to the URL and refresh to spot the available localization phrases.

<kbd>![trmnl-localizations-raw-locale-plugin-example](https://github.com/usetrmnl/localizations/blob/master/support/raw_plugin_example.png)</kbd>

when you're ready, make a copy of either `locales/web_ui/en.yml` or `locales/plugin_renders/en.yml` and create a new file in the same directory, `locales/your-lang-code.yml`. submit a pull request and ask questions if you need help.

## general tips

we understand not all languages support casing. we also understand some languages (ex: Korean) support levels of formality. and finally there are languages with gendered nouns, from Spanish to German. in general we prefer a casual tone with simple vocabulary. this matches the spirit of our brand and makes TRMNL comfortable for people all around the world.
