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
| local daemon startup flags | | |
| signing address | | recherchieren |
| Spendable Wallet | | recherchieren |
| Tx descriptions | | |
| wallet creation height | | |

## New

| English | German | Notes |
| --- | --- | --- |
| **cache** | Cache | |
| **daemon log path** | Daemon-Log-Pfad | |
| **hidden** | versteckt | |
| **QrCode(Qr Code)** ^1 | QR-Code | |
| **spent outputs** | verbrauchte Outputs | |
| **view key** | View-Key | really new? |
| **wallet log path** | Wallet-Log-Pfad | |

**^1** : Inconsistent in upstream?

## Discuss Change

| English | German | Notes |
| --- | --- | --- |
| clear | | is: _leeren_ |
| Generate | _erzeugen_ | was: _generieren/erstellen_ |
| money | | is: _Geld/Guthaben_ |
| Tracking | | is: _Nachverfolgen_ |

## Changed

Less ambiguous/incoherent: Former translation was found to be ambiguous
technically or in meaning, or the term was translated differently throughout the
GUI. This can and will always happen, understandability > consistency :)

*   funds: case-by-case
*   key : Schlüssel, ausser >
    view-key, spend-key

| English | German | Notes |
| --- | --- | --- |
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
| **spend key** | Spend-Key | was: Spend-Schlüssel |
| **spend proof** | Sendenachweis | was: _Ausgabennachweis_ |
| | | |
| ReadOnly Wallet | _view-only Wallet_ | is: _Schreibgeschütztes Wallet_ |
| View Only Wallet | _view-only Wallet_ | is: _schreibgeschütztes Wallet_ |

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
| confirmations | Bestätigungen | |
| daemon | Daemon | |
| entry | Eintrag | |
| error | Fehler | |
| fee | Gebühr | |
| funds | Geld/Guthaben | contextual |
| integrated address | integrierte Adresse | |
| mine | minen | |
| miner | Miner | |
| mining | Mining | |
| node | Node (m/f/n?) | |
| Note: | Info: | |
| payment | Zahlung | |
| payment ID | Zahlungs-ID | |
| proof | Nachweis | |
| ringsize | Ringgröße | |
| security level | Sicherheitslevel | |
| transaction | Transaktion | |
| testnet | | |
| Tx ID | Tx-ID | |
| Tx key | Tx-Schlüssel | |
| Tx note | Tx-Notiz | |
| unlocked balance | verfügbares Guthaben | |
| wallet | Wallet | |

## Not in GUI

| English | German | Notes |
| --- | --- | --- |
| _anonymity set_ | | |
| block reward | Blockbelohnung | |
| block time | Blockzeit | |
| change | Rückgeld | |
| _coinbase transaction_ | _Coinbase-Transaktion?_ | |
| confidential transaction | vertrauliche Transaktion | |
| cryptocurrency | Kryptowährung | |
| dust | Dust | |
| emission | Emission | |
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
| stealth address | Schattenadresse | _FB appreciated!_, alt: Tarnadresse |
| _tail_ | | |
| _tail emission_ | | |
| _transaction unlock time_ | | |
