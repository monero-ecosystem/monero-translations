To translate [getmonero.org](http://getmonero.org) in your language follow this instructions. Remember that if you need help during any of these steps or with git GitHub, ask support on our chat `#monero-translations`(we are on IRC/Freenode, MatterMost and riot/matrix) or [send a PM to ErCiccione on reddit](https://www.reddit.com/message/compose/?to=erciccione), we will guide you through the whole process if necessary. Also, remember to take a look at our **[General guidlines for translators](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home)**

## Translate a page

### Get the repository

First of all you need your copy of the website. Go to [repo.getmonero.org/monero-project/monero-site](https://repo.getmonero.org/monero-project/monero-site) and click the "Fork" button on the top right. Now you have your personal copy of the repository and you can start working on it. Clone it locally and start translating

### Navigate to the correct file

Go to the /i18n folder and find the two letter code for the language you wish to translate into (if your language is not already listed, go to the section "Add a new language" of this guide). Enter that folder and find the file you wish to translate. The filenames are all in English and MUST NOT BE CHANGED.
&nbsp;

The .yml files are separated in sections. The first string of every section says `translated: "yes" [or "no"]`. After you have translated the whole section, change the value of this string from "no" to "yes". Doing so the snippet "This page is not translated" won't show.

### Translate the files

Here you can do your translation. Depending on the page, you may have to maneuver around some HTML or markdown. In general, anything between two tags (such as `<p>TRANSLATE THIS</p>`) should be fine.
Remember to check your page after translating it, to make sure nothing is broken


### Test your translation (not mandatory, ErCiccione will test every translation before it gets merged)

Build your website using jekyll serve if it's not rebuilding automatically.

If the build is successful, go to the correct page in the correct language and check to see that everything is translated, and that the page looks identical to the original English page (besides the translated text).

### Submit a Pull Request

You're all done. Submit a PR and wait for it to be reviewed and merged. Be sure to make any changes if requested.

## Add a new language

### _config.yml file

Navigate to the root folder of the whole website and find the file labeled `_config.yml`. Open it and find the line that says `languages:`. Add your two letter language code (Google it if you don't know it) in between the brackets after the others already present. You will need to put a comma after the previous last one.

Example:

```
languages: ["en", "es", "NEW LANG HERE"]
```

Save and exit the file.

### _data folder

Navigate to the `_data/lang` folder and copy the `en` folder. Paste it into the same folder and the copy renamed to the two letter language code of the language you will be translated to.
&nbsp;

Translate the content of the files. Do not touch anything labeled `url`, and in the roadmap.yml ONLY translate the `name:` content.

### _i18n folder

Navigate to the _i18n folder and duplicate the `en.yml` file. Rename the duplicate to the two letter language code of your language with a `.yml` at the end. Repeat this process with the `en` folder as well.
**The `en` folder and yml file themselves should still be there. They should not be renamed. There should be a new folder and yml file in addition to the ones that were already there.**

Enter the .yml file and translate everything there.

### File Priorities

the /i18n folder contains many files and folders and can take a fairly big amount of time to translate them all, so we need to work on the most important fist. The first files you see, with the extension `.yml`, are the highest priority and should be done first, so start editing the one with the code of your language.
When done with the .yml file, go inside the `resources` folder of your language and work on these files (from the highest priority):

1. Folder`user-guides` 
2. Folder `developer-guides`
3. Folder `moneropedia`

## Example

Let's say you want to add the German language

1.  Clone your forked repository locally
    2\. Edit the `_config.yml` file adding the two letter code for German: `de`
    3\. Navigate to the `_data` folder, then `lang`. Create a copy of the `en` folder and name it `de`
    4\. Go inside the `de` folder and translate all the documents as explained above
    5\. Go to the `_i18n` folder and make a copy of the files `en` and `en.yml`, then rename them to `de` and `de.yml`
    6\. Start translating the files according to their priority (as explained in the secion above "File Priorities")
    7\. Commit your changes and open a Merge Request on Gitlab

    Contact us as explained at the beginning of this wiki if you need help/info/support!
