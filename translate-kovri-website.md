# Translate Kovri website (kovri.io)

Before starting to translate, read our [general guidlines for translators](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home) here on Taiga. If you find any issue or need help with any of the following steps, Click the 'MEET UP' button on the menu on the left, to be redirected on our support chat, or feel free to contact ErCiccione anytime.

Kovri website is based on two repositories: [kovri-site](https://github.com/monero-project/kovri-site) and [kovri-docs](https://github.com/monero-project/kovri-docs), we will need to work on both of them. If you need help with any of these steps, contact ErCiccione, he can help you get the work done and can do the most tricky parts for you.

## Update a translation

Let's start from `kovri-site`, where the core of the website is. To update a translation navigate to the `kovri-site/kovri.i2p/_i18n` folder. There you'll find a list of folders and `.yml` files. The folders contain the actual documents which need to be translated, the `.yml` files are the voices of the menus.

What you have to do is just find the folder of the language relevant to you and start translating the text you find. For the `.yml` files, translate only the text on the right (e.g: in `building: Building Instructions`, only `building instructions` must be translated.)

Same procedure for `kovri-docs`: just navigate to the [i18n section](https://github.com/monero-project/kovri-docs/tree/master/i18n), open the folder with the language code relevant to you and start translating the untranslated strings/files.

### example

You are an Italian translator. Navigate to the `/_i18n/` folder in `kovri-site`. You'll find the `it.yml` file, open it and translate all the strings on the right, as explained in the section above. When done, it's time to translate the actual files! go inside the `/it/` folder and check which files need to be translated. If any text is still in English, translate it. That's it.

Same for `kovri-docs`: navigate to the `/i18n/it/` section and check which files need to be translated.

## Add a new language

Adding a new language is very easy. What you need to do is navigate to [kovri-site/kovri.i2p/_i18n](https://github.com/monero-project/kovri-site/tree/master/kovri.i2p/_i18n), make a copy of the `en.yml` file and rename it with the language code corresponding to the language you want to translate into. Same for the `en` folder: copy it and rename it.    
When done you need to edit your new `[LANG].yml` file and also edit the other ones, so that your language will be correctly listed on every localized page. What you have to do is add your language at the end of the `langs` section inside the `.yml` file, along with the respective language code (see the example in the next section).

Now navigate to `_data/lang`, copy the folder `en`, rename it using the code of the language you are working on and translate the strings.

That's it. All the files you need are ready and you only need to start translating!

### example

You are a Japanese speaker. Go to kovri-site/kovri.i2p/_i18n/ and make a copy of the `en.yml` file, rename it to `ja.yml` and translate it. At the end of the `langs` section add `ja: Japanese`. The section should look like this:

```
en: English
  es: Español
  ru: Русский
  fr: Français
  it: Italiano
  de: Deutsch
  da: Dansk
  ja: Japanese      <-- You shuld use the corresponding translation for 'Japanese'
```

Remember to add `ja: Japanese` also in all the other `.yml` files. 

Make a copy of the `en` folder and rename it `ja` (leaving the original `en` intact). Translate all the files inside. 
Now navigate to `_data/lang`, copy the `en` folder, rename it `ja` and translate the strings cointained in `navigation.yml`.

That's it, your translations are ready!
