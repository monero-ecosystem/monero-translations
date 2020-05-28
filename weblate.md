## Step by step guide for Weblate

Translators can make two actions on weblate: translate new strings or Review other contributor's translations. This guide will give all the info you need to perform both tasks. 

### 0. Start!
Go to the [project page](https://translate.getmonero.org/projects/monero/),click on the tool you would like to contribute to (CLI or GUI wallet) and select the language. You will see some statistics and a series of lines in different colours:
![screenshot](/media/weblate/strings_status.png)

**Green:** You can ignore these, unless you would like to review already translated strings.  
**Red:** Untranslated srings or with failing checks. These should be the priority.  
**grey:** Strings that need some kind of action.  
**Yellow:** Strings with some issues that need to be reviewed.

After choosing the type of strings you want to work on (remember that strings higlighted red have precedence, especially ("Not translated strings" and "Strings needing action") you will be prompted to the string view, where you can finally start!

### 1. Check if a translation has been already suggested
![suggestion](/media/weblate/suggestion.png)  
If a translation has already been made, check the suggested string. If you think it's correct, upvote it and will be approved. If you think it's wrong, downvote it. (the voting proces is better explained in the [Review and vote strings](#review-and-vote-strings) section) If you think it's ok, but you want to suggest a better translation, got to next step.
You can also comment a string, this comes useful when you are not sure about a string and you want to ask the opinion of your fella translators.

### 2. Check out if your language has a glossary available
![glossary](/media/weblate/glossary.png)
Before adding a translation check out if the string you are working on matches a word of the language's glossary. If you are translating a word and that word is in the glossary, you should always use the translation suggested. (More info in the *What's a glossary? How to use it?* section). If there is no glossary available, the section in the screenshot will not appear.

### 3. Use the Translation Memory
![translation_memory](/media/weblate/translation-memory.png)

Check if there is a similar word/phrase in the translation memory (more accurate strings will have their bar colored green). If you think the suggested string is accurate, copy the string using the given button and submit your suggestion. Keep in mind that accurate suggestons by the translation memory must always be used, if present.  
Check the section *What's a translation memory? How to use it?* for more info.


### 4. Submit your translation and wait for a review
Click *Suggest string* to submit your translation. Now only needs to be approved, this can happen in two different ways:

- **By vote** Every user have the possibility to vote a suggested translation. When a translation has 1 addition approval (to be added to the automatic approval of the submitter) gets confirmed. To see how voting works check [the section "Review and vote strings"](#review-and-vote-strings)
- **By reviewers**: Strings can be confirmed/rejected/edited by a specific figure on Weblate, The "Reviewer". More info about the Reviewer role in the section *[The role of the Reviewer](#the-role-of-the-reviewer)*.

## General guidelines

- leave placeholders (like `%1`) and HTML tags as they are
- If the "needs edit" box is ticked, check the translation. If it's ok, unthick the box and "add suggestion"
- Use gender neutral words when possible

## Review and vote strings
For security reasons we cannot just accept every submitted translation by default, we have to check all strings before they get merged into the Monero code. Strings can be checked by a Reviewer (role explained in the next chapters) or by other translators.

Translators can vote translations made by other contributors simply using an upvote or downvote. If a string has at least 1 upvote from another translator, it will get confirmed.
![vote](/media/weblate/vote.png)

Voting a translation is extremely easy: 

1. Click on the string which contains a suggested translation. If you are translating, when opening the string you will see a warning in the top right of the page telling you a suggestion has already been made.
2. Click on the *Suggestions* tab.
3. Now you see the suggested translation. You can upvote it (button *Vote for*) or downvote it (button *Vote against*)

## The role of the Reviewer
See [reviewers.md](https://github.com/monero-ecosystem/monero-translations/blob/master/reviewers.md).

## What else can you do on Weblate?
We gave an overview of the main functions of Weblate, but this platform offers many more features that make the life of every contributor easier. On weblate you can:

- *Start discussions under any string*. This comes useful when you have some doubt about a string and you want an input from your fellow translators. Comments are saved and can be very useful to understand the process behind a translation.
- *Manage your profile* with many advanced settings. To make your experience more personalized.
- *Set up notifications* to receive an email every time the language of your choice has new strings or needs to be updated.
- *Link your weblate account to Gitlab and GitHub* to have yur commits visible on your accounts.
- *Much more*. Just play with Weblate for some time and you will find a lot of useful features. A link to the official guide for Weblate is at the bottom of this document.

## What's a translation memory? How to use it?
The translation memory is a very useful tool. If you already worked on Monero translations, you'll notice this is something we never used before. In fact, we used to keep consistency between translated projects only using glossaries and a lot of manual checking.  

Now it's more automatic. Every time a translation is submitted, Weblate remembers it and store it in a special database. If a word/string in another translation matches a word in the database, Weblate will tell you how it was translated in past and will suggest you to use it (saying first how similar is the sentence to translate with the one in its database). 

## What's a glossary? How to use it?
Glossaries are very useful for technical terms which are hard to translate. They will appear at the top right of the interface while you are translating a string. A glossary is the results of a consensus between translators of a given language about how to translate (or not translate) a word. **Glossaries should be always used and respected** when present in a language.

If you think a new word should be added to the glossary, or you want to edit an existent one, open an issue or directly a Pull Request on the [GitHub repository of the Localization workgroup](https://github.com/monero-ecosystem/monero-translations), where all the glossaries are stored. They are available only for few languages at the moment.

[More info about Glossaries](https://docs.weblate.org/en/weblate-3.8/user/translating.html#glossary)

## Support and contacts
Weblate has a very extensive and useful [user guide](https://docs.weblate.org/en/weblate-3.8/user/translating.html), which i absolutely raccomend to read and keep bookmarked.

The Localization workgroup at large usually discuss on `#monero-translation`. Chatroom on Freenode, Matrix and MatterMost. Additional contacts are [in the README on GitHub](https://github.com/monero-ecosystem/monero-translations#contacts)
