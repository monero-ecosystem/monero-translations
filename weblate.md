This page you instruct you how to use our Weblate instance to translate many Monero projects.

<a href="https://translate.getmonero.org/engage/monero/">
<img src="https://translate.getmonero.org/widgets/monero/-/open-graph.png" alt="Translation status" />
</a>

## Step by step guide for Weblate

Translators can perform two actions on Weblate: translate new strings or review the translations of others. This guide will give all the info you need to perform both tasks. 

### 1. Start!

Go to the [project page](https://translate.getmonero.org/projects/), click on the tool you would like to contribute to (for example the CLI or GUI wallet) and select the language. You will see some statistics and a series of lines in different colours:

![screenshot](/media/weblate/strings_status.png)

- **Green:** These represents already translated strings. You can safely ignore them, unless you would like to review the work already done by others;
- **Red:** Untranslated strings or with failing checks. These should be the priority;
- **Grey:** Strings that need some kind of action;
- **Yellow:** Strings with some issues that need to be reviewed;

After choosing the type of strings you want to work on (remember that strings higlighted in red are preferred, especially (**Not translated strings** and **Strings needing action**) you will be prompted to the string view, where you can finally start!

### 2. Check if a translation has been already suggested

![suggestion](/media/weblate/suggestion.png)  

If a translation has already been made, check the suggested string. If you think it is correct, upvote it and it will be approved. If you think it is wrong, downvote it. (the voting process is better explained in the [Review and vote strings](#review-and-vote-strings) section)

If you think the translation can be improved and you want to suggest a better translation, go to next step. You can also comment on a string. This comes in handy when you are not sure about a string and you want to ask the opinion of your fellow translators.

### 3. Check out if your language has a glossary available

![glossary](/media/weblate/glossary.png)

Before adding a translation check if the string you are translating matches a word of the language's glossary. If you are translating a word and that word is in the glossary, you should always use the suggested translation. If there is no glossary available, the section in the screenshot will not appear.

> More info in the [What is a glossary? How to use it?](#what-is-a-glossary-how-to-use-it) section.

### 4. Use the Translation Memory

![translation_memory](/media/weblate/translation-memory.png)

Check if there is a similar word/phrase in the translation memory (more accurate strings will have their bar colored green). If you think the suggested string is accurate, copy the string using the given button and submit your suggestion. Keep in mind accurate suggestons by the translation memory must always be used, if present.  

> Check the section [What is a translation memory? How to use it?](#what-is-a-translation-memory-how-to-use-it) for more info.

### 3. Submit your translation and wait for a review

Click **Suggest string** to submit your translation. Now it only needs to be approved and this can happen in two different ways:

- **By vote:** Every user has the possibility to vote for or against a suggested translation. When a translation has 1 additional approval (to be added to the automatic approval of the submitter) it gets confirmed. To see how voting works check the section [Review and vote strings](#review-and-vote-strings);
- **By reviewers:**: Strings can be confirmed/rejected/edited by a specific figure on Weblate, the "Reviewer". More info about the Reviewer role in the section [The role of the Reviewer](#the-role-of-the-reviewer).

## General guidelines

- Leave placeholders (like `%1`) and HTML tags as they are
- If the **needs edit** box is ticked, check the translation. If the translation is OK, untick the box and then click at **add suggestion**

## Review and vote strings

For security reasons, translations can not be submitted by default. All strings have to be checked before they are merged into different Monero projects.
Strings can be checked by a Reviewer (role explained in the next chapters) or by other translators.

Translators can vote on translations made by other contributors simply using an up- or downvote. If a string has at least 1 upvote from another translator, it will get confirmed.

![vote](/media/weblate/vote.png)

Voting a translation is extremely easy: 

1. Click on the string containing a suggested translation. If you are translating, when opening the string you will see a warning in the top right of the page telling you a suggestion has already been made.
2. Click the **Suggestions** tab.
3. Now you see the suggested translation. You can upvote it (**Vote for** button) or downvote it (**Vote against** button).

## The role of the Reviewer

See [reviewers.md](https://github.com/monero-ecosystem/monero-translations/blob/master/reviewers.md).

## What is a glossary? How to use it?

Glossaries are very useful for technical terms which are hard to translate. They will appear at the top right of the interface while you are translating a string. A glossary is the results of a consensus between translators of a given language about how to translate (or not translate) a word. **Always use and respect glossaries** when present in a language.

If you think a new word should be added to the glossary, or you want to edit an existing one, open an issue, or send a pull request to the GitHub repository of the Localization Workgroup.

The glossaries are stored in the [terminology-guides](https://github.com/monero-ecosystem/monero-translations/tree/master/terminology-guides) folder available for these languages:

  - [French](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/french-terminology.md)
  - [German](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/german-terminology.md)
  - [Italian](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/italian-terminology.md)
  - [Spanish](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/spanish-terminology.md)
  - [Swedish](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/swedish-terminology.md)
  - [Brazilian Portuguese](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/portuguese-br-terminology.md)
  - [Chinese simplified](https://github.com/monero-ecosystem/monero-translations/blob/master/terminology-guides/zh%20rCN-terminology)

All terms are meant to give consistency and stability to the terminology used in a given language, that is why they should not be easily edited directly. For this reason all glossaries are stored in this repository and can be edited only after the changes are discussed at lenght in a pull request or issue.

> More info about [Glossaries](https://docs.weblate.org/en/weblate-3.8/user/translating.html#glossary) can be found at Weblate's official documentation.

## What is a translation memory? How to use it?

The translation memory is a very useful tool. We used to keep consistency between translated projects using only glossaries and a lot of manual checking. Now it is more automatic.

Every time a translation is submitted, Weblate remembers it and stores it in a special database. If a word/string in another translation matches a word in the database, Weblate will tell you how it was translated in the past and suggest you to use it (saying first how similar the translated sentence is in relation to the one in its database).

## What else can you do on Weblate?

That was a breif overview of the main Weblate functionality, but this platform offers many more features that make the life of every contributor easier. On Weblate you can:

- **Start discussions under any string**. This comes in handy when you have some doubt about a string and want input from your fellow translators. Comments are saved and can be very useful to understand the process behind a translation. Mention people with @username.
- **Manage your profile** with many advanced settings. To make your experience more personalized.
- **Set up notifications** to receive an e-mail every time the language of your choice has new strings or needs to be updated.
- **Link your weblate account to GitLab and GitHub** to have your commits visible on your accounts.
- **Much more**. Just play with Weblate for some time and you will find a lot of useful features. A link to the official guide for Weblate is at the bottom of this document.

## Additional resources

Weblate has a very extensive and useful [user guide](https://docs.weblate.org/en/weblate-3.8/user/translating.html) which we absolutely recommend to read and keep bookmarked.
