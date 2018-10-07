Follow the instructions to translate Monerujo, the android wallet developed by the Monero community.

Monerujo's repository can be found [here](https://github.com/m2049r/xmrwallet), the 3 files that need to be translated are inside [this](https://github.com/m2049r/xmrwallet/tree/master/app/src/main/res/values) folder.

Also, remember to take a look at our **[General guidlines for translators](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/home)**

## Add a new language

Follow these steps to add a new translation:

1.  Create an account on github
2.  create a new folder under `xmrwallet/app/src/main/res` named `values-LANGCODE` (e.g the Italian folder will be named `values-it`)
3.  copy from the folder `xmrwallet/app/src/main/res/values` the 3 needed files: `about.xml` `help.xml` `strings.xml` and put them in the `values-LANGCODE` folder
4.  Now everything is ready and you only need to translate the files inside the folder

## Update an already existing language

Monerujo is actively developed which means that sometimes new strings are added to the codebase. When a new string is added it will be enclosed in squared brackets (e.g `<string name="menu_changepw">[Change Passphrase]</string>`) so that a translator can easily find it by searching for `]</string>`. See [this issue](https://github.com/m2049r/xmrwallet/pull/234#issuecomment-383051195) on GitHub for reference.

_Example:_
You speak Spanish and you want to make sure all strings in `values-es/strings.xml` are translated. So you open the file, open the 'search' field and paste `]</string>`and you'll see some highlighted fields. Those need to be translated, and the square brackets `[ ]` removed.
Also, remember to check the other localizable file: `help.xml`, if you find some english parts, those need to be translated

## Note

There are a couple of things to keep in mind when working on a translation:

*   **Do not** translate Monerujo's license, but the 'privacy policy' should be translated
*   Keep the translated strings as short as possible. _Remember monerujo is a mobile wallet, the space is very limited_
*   some strings have the attribute `translatable="false">`, they must **not** be translated. You **have to remove them** (the entire <string `translatable="false">text</string> + newline) from the translated file
