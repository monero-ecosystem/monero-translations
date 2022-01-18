*This file is intended for future translation coordinators or anyone that can manage our Weblate instance.*

## Instructions on how to keep `monero` and `monero-gui` updated:

1. Contributors translate strings on Weblate
2. Their translations get automatically committed after 24 hours. There's a setting for that [here](https://translate.getmonero.org/settings/monero/gui-wallet/#vcs) and the [docs are here](https://docs.weblate.org/en/weblate-4.8/admin/projects.html#component-commit-pending-age)
3. When it's time to update (generally once a month)

    a. Lock the component (https://translate.getmonero.org/projects/monero/gui-wallet/#repository)
    
    b. Clone Weblate's internal repo locally (`git clone https://translate.getmonero.org/git/monero/gui-wallet/`) using your Weblate username and API token as password (https://translate.getmonero.org/access/monero/#api)
    
    c. Fetch upstream and rebase (`git fetch upstream` and `git rebase upstream/master`) assuming upstream is https://github.com/monero-project/monero-gui.git
    
    d. Run the command `lupdate qml.qrc -ts translations/monero-core.ts -no-obsolete && lupdate qml.qrc -ts translations/monero-core_*.ts -no-obsolete` to update strings
    
    e. Push the commit with the updated strings to the Weblate's internal repo (make sure you are synced with the upstream repo first, see step 3.c above)
   
    f. Open a PR from `monero-weblate`'s repo against `monero-project`'s
    
    g. Wait until the PR is merged and the binaries released
    
    h. Unlock component
4. Contributors will start translating the updated strings

## Instructions on how to keep `monero-site/userguides` and `monero-site/moneropedia` updated:

This is the script for the user guides (and can be used to moneropedia by changing the updatelangs function): https://github.com/monero-project/monero-site/blob/master/po/po-update.sh 

### Script for reference

```bash
#!/bin/bash

# SCRIPT
#
# This script loops through all the .config files in this folder and run po4a on them. The config files are one for each user guide.
# See the next section for instructions about adding new config files.
#
# CONFIG FILES
#
# The config files give a set of instructions to po4a, which will update all translations files (.pot and .po) and documents (.md) at the same time.
# we use --keep=0 to transfer all translated content directly to the original markdown file, but would be good to switch to a more reasonable thresold
# (maybe the standard 80%?) in the future, when the guides will be mostly translated.
#
# To avoid spamming unnecessary diffs, we didn't add all config files for all guides. A new config file should be added
# when the translation files and the guides themselves need to be updated (so, when the original document got changed and 
# the changes need to be transferred to the translation files). To add a new config file to be managed by po4a:
#
# 1. Copy one of the other .config files and rename it to the filename of the guide it's going to point to (for example, for the user guide
# 'verification-allos-advanced.md' we will create a config file named 'verification-allos-advanced.config').
# 2.change the strings starting with [po4a_paths] and [type: markdown] using this structure:
# [po4a_paths] ../_i18n/en/resources/user-guides/weblate/<GUIDE.pot> $lang:../_i18n/$lang/resources/user-guides/weblate/<GUIDE.po>
# 3. At the bottom of the file, change the '[type: markdown]' instruction:
# [type: markdown] ../_i18n/en/resources/user-guides/<GUIDE.md> $lang:../_i18n/$lang/resources/user-guides/<GUIDE.md>

checkpo() {
  if ! command -v po4a &> /dev/null
  then
    echo "po4a is not installed"
    exit
  else
    echo "Updating language files.."
  fi
}

updatelangs() {
  for guide in user-guides/*.config; do
    echo "-> Running po4a on ${guide}"
    po4a $guide || echo "ERROR: something went wrong, po4a didn't run succesfully on ${guide}"
  done
}

while true; do
  checkpo
  updatelangs
  echo "Done."
  break
done
```
### Adding new user guides or moneropedia terms

Please read https://github.com/monero-project/monero-site/issues/1780#issuecomment-907117317 if adding new terms/guides.

1. Gettextize translated and untranslated documents. This will generate `.po` and `.pot` files for all languages
2. Add `<name>.config` file to be parsed by po4a for each moneropedia entry in `po/moneropedia/<name>.config` or `po/user-guides/<name>.config`
3. When the structure of all entries matches the original English file, run po4a against the config file added above. This will change the structure of all `.po/.pot` files in a smarter way, which recognizes the different markdown structures
4. Manually tweak the template `.pot` file and fix any weirdness found (remove fuzzy for each block or po4a will ignore it when it's time to transfer it back to the `.md` file, the actual guide)
5. Manually fix all incongruences and inconsistencies in each `.po` file
6. Run po4a again against the config file (see item 3 above)
7. Visually check the resulting markdown file to make sure everything went fine
