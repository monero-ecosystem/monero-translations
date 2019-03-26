# German translation

## This is a page for collaboration on terminology between German translators

Let's build a coherent dictionary for the translation of technical and other
Monero-related terms, providing consistency and ease of maintainability for
future translators/contributers. The initial wordlist was branched off from
[the swedish collab](https://taiga.getmonero.org/project/erciccione-monero-localization/wiki/swedish-terminology).

Everything in this document should be treated as a request for comment, so it
can and probably will change in the future upon further input.

## Guidelines (WIP)

### Translation of terms

Whenever possible, the terms from the 'agreed-upon' list should be used.

### Handling of placeholder text

Placeholder text should not be translated, so that upstream changes are
automatically displayed in the gui.
Examples: '4...', '78.9239845', '[2324.9239845](tel:23249239845)'.
This assumes that numeric value input defaults to US throughout localizations.

**TODO: Compile and check assumption**

## Workflow (WIP)

### 1\. Setup

*   Fork the [monero-gui repository](https://github.com/monero-project/monero-gui) on GitHub
*   TODO: QT Linguist
*   TODO: PR

* * *

## Not translated

| English | German | Notes |
| --- | --- | --- |


## New

| English | German | Notes |
| --- | --- | --- |
| | | |
| **Not in GUI** | | |
| ring confidential transaction | vertrauliche Ringtransaktion | |
| (Ring CT) | Ring-CT | |
| block emission | Verteilung(skurve) | |
| main (block) emission | Hauptverteilung | |
| tail (block) emission | Anschlussverteilung | |
| testnet | Testnet | |
| transaction unlock time | Freigabedauer von Transaktionen | |

## Discuss Change

| English | German | Notes |
| --- | --- | --- |
| clear | zurücksetzen | is: _leeren_ |
| daemon log path | Hintergrunddienst-Log-Pfad | |
| money | Geld | is: _Geld/Guthaben_ |
| node | der/das Node | please discuss which article should be used; use _der Node_ for now |
| local daemon startup flags | Startparameter für lokalen Hintergrunddienst |  |
| signing address | signierende Adresse | |
| Spendable Wallet | Wallet mit Vollzugriff | |
| spent outputs | ausgegebene Outputs | |
| Tracking | | is: _Nachverfolgen_ |
| Tx descriptions | Transaktionsbeschreibungen | |
| wallet | die/das Wallet | please discuss which article should be used; use _das Wallet_ for now |
| wallet creation height | Wallet-Erstellungshöhe | |
| wallet log path | Wallet-Log-Pfad | |
| | | |
| **Not in GUI** | | |
| fork | Fork/Upgrade | prefer to use _Upgrade_ or _Netzwerkupgrade_ when referring to Monero's scheduled hardforks (?) |
| _ledger_ | Kassenbuch/Ledger | use _Ledger_ if the sentence refers to the Hardware-Wallet |

## Changed

Less ambiguous/incoherent: Former translation was found to be ambiguous
technically or in meaning, or the term was translated differently throughout the
GUI. This can and will always happen, understandability > consistency :)

*   funds: case-by-case
*   key : Schlüssel, ausser >
    view-key, spend-key

| English | German | Notes |
| --- | --- | --- |
| **daemon** | Hintergrunddienst | was: _Daemon_ |
| **Generate** | erzeugen | was: _generieren/erstellen_ |
| **log** | Log | was: _Log/Bericht/Protokoll_ |
| **log level** | Log-Level | was: _Detailgrad des Berichts_ |
| **mnemonic seed** | mnemonischer Seed | was: _mnemonischer Code_ |
| **output** | Output | was: _Ausgang_ |
| **public spend key** ^1 | öffentlicher Spend-Key | was: _Spend-Schlüssel (öffentlich)_ |
| **private spend key** ^1 | privater Spend-Key | was: _Spend-Schlüssel (privat)_ |
| **quick transfer** | Schnelltransfer | was: _Schnellüberweisung_ |
| **read-only** | schreibgeschützt | was: _nicht beschreibbar_ (FS access) |
| **reward** | Belohnung | was: inconsistent |
| **seed** | Seed | was: _(mnemonischer) Code_ |
| **spend key** | Spend-Key | was: _Spend-Schlüssel_ |
| **spend proof** | Sendenachweis | was: _Ausgabennachweis_ |
| **Tx ID** | Transaktions-ID | |
| **Tx key** | Transaktionsschlüssel | |
| **Tx note** | Transaktionsnotiz | |
| | | |
| ReadOnly Wallet | View-Only-Wallet | was: _Schreibgeschütztes Wallet_ |
| View Only Wallet | View-Only-Wallet | was: _schreibgeschütztes Wallet_ |

viewOnly == readOnly?

**^1** : Inconsistent in upstream?

## Unchanged

Consistent: Leaving the existing translation made sense.

| English | German | Notes |
| --- | --- | --- |
| amount | Betrag | |
| balance | Guthaben | |
| blockchain | Blockchain | |
| block height | Blockhöhe | |
| cache | Cache | |
| confirmations | Bestätigungen | |
| entry | Eintrag | |
| error | Fehler | |
| fee | Gebühr | |
| funds | Geld/Guthaben | contextual |
| hidden | versteckt | |
| integrated address | integrierte Adresse | |
| mine | minen | |
| miner | Miner | |
| mining | Mining | |
| Note: | Info: | |
| payment | Zahlung | |
| payment ID | Zahlungs-ID | |
| proof | Nachweis | |
| QrCode(Qr Code) **^1** | QR-Code | |
| ringsize | Ringgröße | |
| security level | Sicherheitslevel | |
| transaction | Transaktion | |
| unlocked balance | verfügbares Guthaben | |
| view key | View-Key | |

**^1** : Inconsistent in upstream?

## Not in GUI

| English | German | Notes |
| --- | --- | --- |
| _anonymity set_ | | |
| block reward | Blockbelohnung | |
| block time | Blockzeit | |
| change | Wechselgeld | was: _Rückgeld_ |
| coinbase transaction | Coinbase-Transaktion | |
| confidential transaction | vertrauliche Transaktion | |
| cryptocurrency | Kryptowährung | |
| dust | Dust | |
| fork | Fork | |
| fungible | Fungibel | |
| fungibility | Fungibilität | |
| _ledger_ | | |
| _proof-of-work_ | _Proof-of-Work_ | |
| public key | öffentlicher Schlüssel | |
| private key | privater Schlüssel | |
| public view key | öffentlicher View-Key | |
| private view key | privater View-Key | |
| _(Ring CT)_ | | |
| _ring confidential transaction_ | | |
| ring signature | Ringsignatur | |
| scalable | skalierbar | |
| scalability | Skalierbarkeit | |
| stealth address | Schattenadresse | |
| _tail_ | | |
| _tail emission_ | | |
| _transaction unlock time_ | | |
