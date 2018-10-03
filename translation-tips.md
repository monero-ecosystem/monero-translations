# Translation tips for Monero translators

Thank you for contributing! Your translation will help people across the world achieve financial privacy and use fungible money on the internet.

The policy of the Monero project is that we accept any useful contribution if it doesn't break anything. And maybe we'll improve it later if necessary. That's how we've managed to recruit more than 400 contributors. So it's safe to assume that your contribution will be welcome. In some cases, like the getmonero.org website which contains a huge amount of information, it's expected that a translation won't be complete. 

Since you may not be a professional translator, this guide will tell you some of the tricks of the trade, to help you create better translations. It also gives some pointers about how to deal with the technology that makes Monero work.


## Contents

1. [How to edit files in Monero projects](#1-how-to-edit-files-in-monero-projects)
2. [People](#2-people)
3. [Consistency](#3-consistency)
4. [Context](#4-context)
5. [Special types of text](#5-special-types-of-text)
6. [English is weird](#6-english-is-weird)
7. [Reference materials](#7-reference-materials)
8. [Spelling and proofreading](#8-spelling-and-proofreading)
9. [Reviewing and testing](#9-reviewing-and-testing)

![Monero](media/translation-tips/people.png)


## 1. How to edit files in Monero projects

The Monero project is a collection of different repositories on GitHub and GitLab. You can find general information about translation procedures in the [Monero Localization Wiki](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home) in Taiga, our planning and tracking tool.

More specific translation instructions are available for the following projects:

- [Monero graphical user interface (GUI)](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/translating-the-gui)
- [Monero website](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/translating-monero-website)
- [Monero daemon and command-line interface (CLI)](https://github.com/monero-project/monero/blob/master/README.i18n.md)
- [Documentation and website for Kovri (anonymous router)](https://gitlab.com/kovri-project/kovri-docs)
- [Monerujo (Android wallet)](https://taiga.getmonero.org/project/erciccione-monero-localization/taskboard/monerujo-android-wallet)

Other Monero-related projects, created by community members, are collected in the [Monero Ecosystem](https://github.com/monero-ecosystem/meta).

We're planning to set up a localization platform called [pootle](https://pootle.translatehouse.org/). But for now, the default workflow is entering the translations in a text editor and making a pull request in Git or on Github to upload your work.

The TS files containing source text and translation strings for the actual software (Monero GUI, CLI and daemon) can be translated in [Qt Linguist](http://doc.qt.io/archives/qt-4.8/linguist-translators.html), which offers some limited computer-assisted translation (CAT) features, like copying repeated strings. You won't have to worry about keeping the XML tags intact. And if you use a text editor instead, you'll have to remove the label `type="unfinished"` manually after translating each string.

![GUI version 0.12 in Dutch](media/translation-tips/gui.png)


## 2. People

Don't hesitate to ask our localization coordinator @erciccione for technical help and planning advice. We know the current system isn't easy to use for people who are experts in language rather than software. You can reach him on the #monero-translations channel on IRC (Freenode) or [on Reddit](https://www.reddit.com/user/ErCiccione/). 

The original version of this guide was written by Dutch translator Edwin den Boer (@ProkhorZ), who worked as a freelance translator specialized in software localization for 15 years. You can contact him for linguistic advice on [Reddit](https://www.reddit.com/user/edbwtf/) or [Twitter](https://twitter.com/edbwt/).

![TS file with Italian translations](media/translation-tips/ts.png)


## 3. Consistency

Consistency is even more important than choosing the best translation. For example, a user who wants to know what the view key does, needs to find the same term that's used in Monero wallets on the Monero website.

Before you search in dictionaries (see paragraph 7 below), don't forget to search in projects that have already been translated. For example, if you're adding translations to the GUI, look for the existing translations in the monero-core repository, or in other repositories like the monero.org website if they have been translated. Or [use a phrase book in QtLinguist](http://doc.qt.io/qt-4.8/linguist-translators.html#phrase-books).

To help different translators to use the same terminology, lists of terms are shared [on Taiga](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home). At the moment (May 2018), glossaries are available for Swedish, Italian, German, French and Spanish.

Consistency isn't just a matter of terminology. Sticking to a consistent **style**, **grammar** and **spelling** will make the translation look professional and will help avoid confusion, even when it means making a random choice between equally valid options. Such choices will probably depend on the target language only. For example: Do you use polite pronouns? Which plural form do you use if your language has more than one? Which gender do you use when you're not sure which noun you're referring to?

Eventually, each language should have a language-specific style guide, and/or adopt a general-purpose style guide from an authoritative source.

![Stalagmites/Stalagtites](media/translation-tips/stalagtmites.jpg)


## 4. Context

On the other hand, it may be better to translate non-technical terms differently in different contexts. For example, you could use different words for *work* and *working* in the explanation of mining in the GUI: 

> Mining secures the Monero network, and also pays a small reward for the work done. (...) It will stop mining when you continue working.

Of course it's important to look at the actual user interface you're translating. But sometimes it helps to go a step further and look at the code. 

In the TS translation files, you'll find a reference to a file and a line number for every string. (Note that line numbers may change frequently during development.) This tells you where to find the source code on Github - QML code for the GUI, C++ code for the CLI and daemon.

For example, in the GUI, the %1 placeholder in the string `%1 blocks remaining: ` seemed to refer to a number of blocks. But the [ProgressBar code](https://github.com/monero-project/monero-gui/blob/master/components/ProgressBar.qml) showed that %1 actually was a string variable, to be filled with the text "Wallet" or "Daemon".

Another important source for finding out what the text actually means is the [Monero StackExchange](https://monero.stackexchange.com/), where technical questions are answered. And don't forget to consult the [Moneropedia](https://getmonero.org/resources/moneropedia/) for definitions of key terms.

![Parsing a sentence](media/translation-tips/parsing.gif)


## 5. Special types of text

### Hotkeys

The Monero GUI includes hotkeys in the navigation pane on the left, so you can navigate without using a mouse - for example, S for Send or D for Advanced. Press the Alt key (maybe the one on the right side of your keyboard) to show which letters are used. When you see strings consisting of just one upper case letter in the LeftPanel section of the GUI, those are hotkeys. You'll want to translate them with a letter that occurs in the translated string - but you should use a unique letter for every menu option.

### Step-by-step instructions

When we're telling the user what to do, mention the required actions in the order in which they need to be performed. For example: "Click *Save* and enter the filename". It would be confusing to write "Enter the filename after clicking *Save*".

### Untranslatable text

Some parts of the source text shouldn't be translated:
- commands in the command-line interface
- tags in HTML or XML
- code examples in documentation 

On the other hand, comments in code examples should be translated. Here's an example from the Kovri documentation:
```bash
$ brew install cmake boost openssl # clang installed by default
```
The # is a comment character in Bash, so the text "clang installed by default" is a comment that should be translated.

When translating text containing code or XML/HTML tags, the safest option is usually to copy the source text in order to keep the tags intact. But make sure that you don't accidentally leave part of the source text untranslated.

### Mnemonic seeds

A very special type of text is the word list for mnemonic seeds (the recovery text that encodes your private key in 25 words). This list is not translated. Versions in other languages than English are created according to certain criteria. The list needs to contain exactly 1626 words. The first part, the prefix, needs to be unique for every word, so that users can ignore or change the rest of the word. The prefix is 1 character for Chinese, 3 for English, Japanese and Esperanto, and 4 for other languages. You might be able to use an existing word list or corpus in your language as source material. Ideally, the words should also be as common as possible, so that users are able to write them down correctly. 

Check the [src/mnemonics](https://github.com/monero-project/monero/tree/master/src/mnemonics) folder in the monero repository to see for which languages a word list is available. You'll need help from a developer to add the code necessary to active the mnemonic seed language. Open an issue in the monero repo on Github or ask for help on IRC.

Unlike translations, the word list needs to be perfect the first time. When you change it, you could make some users' recovery text invalid. That's why we still support an old list for English.

![Dictionary Cat](media/translation-tips/verbing.jpg)


## 6. English is weird

Please avoid translating literally. Translating means expressing the same meaning in another language - it's more than replacing words. Ask yourself: If I didn't know that this text was translated from English, would I notice that it was? 

English grammar and style have some peculiarities that you don't need to follow, even in related languages:

- It's not always clear whether a word is a noun or a verb, and when it's a verb, whether it's an infinitive or an imperative. Does *Print* describe the printing process (infinitive), or is it a command or instruction (imperative)? Menu options are usually translated as an infinitive, and instructions to users as an imperative.

- In instructions and especially in marketing copy, the imperative may imply 'for your convenience'. For example: "On Linux systems, use snapcraft for easy deployment." In that case, I'd prefer to use the equivalent of 'you can' in the translation.

- English speakers like to joke about the length of compound words in German, but compound nouns can be just as long in English. They're just less noticeable, because the parts are written as separate words. In your translation, you may have to make the relation between words more explicit by adding prepositions. So you'll have to understand what it means! For example, *failed password security question answer attempts limit* could be explained as a *limit on the number of answer attempts for security questions after failed passwords*. Note that the first part of a compound will often hide a plural: a *transaction counter* will count multiple transactions.

- *All Words In Titles Start With Upper Case Letters.* This is not the preferred style in many other languages that use an alphabet.

When your translation is longer than the English text, some of these peculiarities may have the side-effect of making the translation shorter without losing any information:

- Quantifiers like 'some' and 'any' in the previous sentence are not needed in many languages.

- Subclauses can be short in English and they're used more often than in other languages. But they can lead to complex layers of statements that are hard to parse. Simplify the translation by splitting sentences or by replacing a subclause with a preposition: *that contains* becomes *with*.

- General categories are often mentioned explicitly where they would be implied in other languages: depending on the context, *the monero.org website* could be simply called *monero.org* in your translation. 

- Double negatives are popular in English. Try to avoid confusions by turning them into positive statements: *Don't do this unless...* = *Only do this if...*

![She always smiled when she saw a dog](media/translation-tips/smile.jpg)


## 7. Reference materials

Professional translators search for everything - especially simple words like *set* that have hundreds of different meanings. When deciding which word to use in the translation, knowing what the source text means is just the first step.

Translation memories and terminology databases are more useful sources than dictionaries. In translation memories, you can see how a term is translated in a particular context. A good terminology database will also include contextual information such as definitions, longer strings and a label for the product.

Luckily, there are plenty of reference sources available on the Internet. But take into account that the source might use a term in a different way than Monero developers do.

* The [Microsoft Language Portal](https://www.microsoft.com/Language/en-US/Search.aspx) offers an extensive terminology database for the many languages Microsoft products have been translated in. There's no freely available equivalent for iOS or MacOS. If you're looking for an Apple-specific term, your best bet is to search apple.com and then to change the language code on the page you find.

* [Linguee](http://www.linguee.com/) is an online dictionary that displays examples and definitions from multilingual websites. Linguee offers translations between all official EU languages except Irish, as well as between English and Chinese, Russian and Japanese. It's very user-friendly: you can enter a word from the source or target language without explicitly changing the direction.

For difficult terms, other options include:

* [TAUS data](http://www.tausdata.org/), a collection of translation memories with a wider selection of languages than Linguee.

* [IATE](http://iate.europa.eu/), the European Union's multilingual termbase, compiled from various technical dictionaries and termbases.

* Searching on [Wikipedia](https://en.wikipedia.org/wiki/Main_Page) and changing the language may help you find an explanation as well as a translation.

* Of course, you could use a search engine like [DuckDuckGo](https://duckduckgo.com/) or [StartPage](https://www.startpage.com/) to find the meaning of a term, or to check which translation is used more often. 

* The official Monero Channels: some terms are specific to cryptocurrencies and can be difficult to find a correct translation, feel free to ask in our chats like #monero-translations, #monero, or #monero-community, somebody will gladly help you.

Google Translate is not recommended for any translation that you want to publish.

![Warnings in Qt Linguist](media/translation-tips/qt.png)


## 8. Spelling and proofreading

Did you finish the translation? Congratulations! Now it's time to check the spelling manually as well as automatically. This may require pasting the text into a browser, text editor or word processor. Take into account that spell checkers are bad at applying rules for compounding. A red squiggle is a warning, not necessarily an error. And on the other hand, spell checkers won't always notice misspellings that happen to be correct words, like *pubic key*.

Don't use search engines to check the spelling! The most common errors might be more popular than the correct spelling. Or you might find more hits for "you're right" than "your right" when you're trying to spell "on your right".

It's also useful to check for double spaces, double periods, spaces before punctuation etc. QT Linguist does a few automated checks, like checking whether the punctuation at the end of a string is the same as in the source text.

For long-form text like a web page, people used to print the text to read more carefully and catch errors. That method might be outdated. The modern equivalent would be having a text-to-speech app read it out loud. The app will struggle with typos that your brain might correct automatically.

![Quotation Marks](media/translation-tips/quotes.jpg)


## 9. Reviewing and testing

The best practice would be to compile and test the translated version of the software before submitting a pull request. If you're not able to do this, maybe you can find someone who can?

As a translator, the least you could do for testing is to actually use your translation. Please don't think: "I don't need it, I speak English."

Translations are reviewed by ErCiccione and volunteers on Github before they are merged. If you don't have time to translate, please consider reviewing other people's translations. 

Don't worry about failed building checks on Github; it may happen that the code in the master branch won't compile correctly while it's being updated. This can be caused by reasons not related to your translation. If in doubt, ask ErCiccione.

![Monero.org in Polish](media/translation-tips/website.png)
