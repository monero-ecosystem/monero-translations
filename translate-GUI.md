# How to translate the GUI

Before starting tranlating, take a look at the general guidelines and the available glossaries on the [main page](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home) of this wiki

## Add a new language

Adding a new language requires some more steps compared to updating one.
1\. Check if your language is [already listed](https://github.com/monero-project/monero-gui/tree/master/translations)
2\. if it's not, fork the repository, so that you get a perfect clone of it
3\. now use the file [monero-core.ts](https://github.com/monero-project/monero-gui/blob/master/translations/monero-core.ts "monero-core.ts") as base for your translation
You will find a document containing many blocks with this structure:

```
<message>
<location filename="../pages/AddressBook.qml" line="52"/>
<source>Add new entry</source>
<translation type="unfinished"></translation>
</message>
```

You need to make a copy of this file and rename it adding your language's code (eg. the Italian translation is named _monero-core_it.ts_).
4\. Now that you have the copy ready for your language, it's time to start!
Between `<source></source>` there is the original sentence, you have to put the translation between `<translation>/<translation>`. Be careful, if you forget to remove `type="unfinished"` the source text will be used. Make sure you are sticking as much as possible to the structure of the original line (eg. if a sentence is ending with a `.` your translation should end with `.`)
5\. Check and double check everything
6\. Upload the translation in your remote repository on GitHub
7\. Before making the Pull Request we need to edit a couple of files. At the end your PR [must look similar to this one](https://github.com/monero-project/monero-gui/pull/836/files) to work, this means you need to add the same lines in the same files, but referred to your language(you also need to add a round flag 100x100 px , [Open a Issue](https://taiga.getmonero.org/project/erciccione-monero-localization/issues) or contact us on #monero-translations if you don't know where to find one)
8\. Make the PR and open a new task here with the status "ready for tests" , remember to include the link of your PR in the description. If you prefer you can open a new task while still working on the translation, this can be useful if you wish to receive feedbacks or attract collaborators. In this case use the status "in progress"

**Note:** You can use a GUI to edit the file instead of doing it manually. One of the most common is _linguist_ of the QT package (installed by default in some Linux distro, like Ubuntu. to use it just type on terminal `linguist monero-core_[languagecode].ts`)

If you never used GitHub or need some help, please [Open a Issue asking for help](https://taiga.getmonero.org/project/erciccione-monero-localization/issues) or contact us on #monero-translations (IRC channel we use for coordination and support)

## Refresh a language
The Monero codebase is in constant developement, this means sometimes new strings will be added and some will be removed from the GUI. To keep your language file syncronized with the code, you can run this command when inside the monero-gui repository:    
`lupdate -pro monero-wallet-gui.pro -ts translations/monero-core_[languagecode].ts -no-obsolete`.   
ErCiccione will try to keep all language files updated so you generally won't need to use it, but some advanced users may want to make sure they are working on an updated file. If you don't know how to run this command, but want to make sure you are working on an update language file, ask ErCiccione to update it for you.
