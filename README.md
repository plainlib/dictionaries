# Flat Hunspell Dictionaries

A flat collection of Hunspell spelling dictionaries (`.aff` + `.dic` pairs) for 120+ languages and regional variants, aggregated from multiple upstream projects and placed together in a single directory.

## Sources and priority

Dictionaries were collected from three upstream projects and merged in the following order (higher overrides lower):

1. **LibreOffice/dictionaries** (highest priority) — https://github.com/LibreOffice/dictionaries
2. **JetBrains/hunspell-dictionaries** — https://github.com/JetBrains/hunspell-dictionaries
3. **wooorm/dictionaries** (lowest priority) — https://github.com/wooorm/dictionaries

If a language is present in more than one source, the file from the higher‑priority source is kept. This means the final set uses LibreOffice dictionaries wherever available, then fills the gaps from JetBrains, and finally from wooorm.

## What is included

* Only spelling dictionaries: `.aff` and `.dic` files.
* Hyphenation dictionaries (`hyph_*`), thesaurus files (`th_*`), and test fixtures are excluded.
* All files are placed flat in the repository root. There are no subdirectories.
* File names follow the original upstream naming. Hyphenated names such as `be-official.aff`, `ca-valencia.dic`, `el-polyton.aff`, `fa-IR.dic`, `sr-Latn.aff`, and `tlh-Latn.aff` are kept as is.

## Licensing

**This repository is an aggregation. It does not relicense any dictionary.**

Each `.aff` and `.dic` file remains under the license assigned by its original author(s) and upstream project. Because dictionaries were merged from multiple sources, **the license varies from file to file**.

### Source‑wide license notes

* **LibreOffice/dictionaries** — the repository as a whole is distributed under **MPL‑2.0**, but individual dictionaries carry different licenses: LGPL‑2.1+, GPL‑2+, GPL‑3+, MPL‑1.1, CC‑BY‑SA‑3.0, CC0‑1.0, and others. See the Debian copyright file for a detailed per‑language breakdown:  
  https://tracker.debian.org/media/packages/libr/libreoffice-dictionaries/copyright-17.1.0rc3-3
* **wooorm/dictionaries** — each dictionary has its own license declared in the package metadata (`package.json`) and in a per‑dictionary `LICENSE` file. Licenses include MIT, BSD‑2‑Clause, GPL‑2.0, GPL‑2.0 OR GPL‑3.0, GPL‑2.0 OR LGPL‑2.1 OR MPL‑1.1, LGPL‑2.1, and others.
* **JetBrains/hunspell-dictionaries** — dictionaries are generally distributed under **LGPLv3** and/or **MPL**, with some files under MIT. The exact license is stated in the README file shipped with each dictionary.

### What this means for you

* If you use a dictionary in a context where the license matters (redistribution, commercial product, SaaS), **check the license of that specific dictionary** before using it.
* Attribution requirements from the original license still apply. Where a dictionary requires attribution, credit the original authors as stated in the upstream repository.
* This repository does not claim any copyright over the dictionary content. It only collects and renames files.

## How to find the license of a specific dictionary

Because licenses differ, the most reliable way is to check the upstream source:

| If the file came from… | Look here |
|---|---|
| LibreOffice | `dictionaries/<lang>/` in https://github.com/LibreOffice/dictionaries, or the Debian copyright file linked above |
| JetBrains | `README` or `LICENSE` file in the corresponding folder at https://github.com/JetBrains/hunspell-dictionaries |
| wooorm | `dictionaries/<lang>/package.json` or `dictionaries/<lang>/LICENSE` at https://github.com/wooorm/dictionaries |

If you need a machine‑readable per‑file license list, it can be generated from the upstream metadata, but this repository does not currently include such a list.

## Finnish dictionary (fi_FI)

The Finnish dictionary (`fi_FI.aff` + `fi_FI.dic`) was not taken from the three main sources above. It was obtained from a **sailfishos-chum** community repository and **modified locally** (header/`.aff` directives adjusted, file renamed to the flat `fi_FI` scheme; the word list itself was not changed).

The dictionary originates from the **Voikko** project (https://voikko.puimula.org/) and is distributed under the **LGPL‑2.1 or later**. Because the file was modified, this notice documents the change as required by LGPL‑2.1 § 2. When redistributing `fi_FI`, keep this notice alongside the file and credit Voikko and the sailfishos-chum repository.

## Disclaimer

* This repository is **not affiliated with** The Document Foundation, LibreOffice, JetBrains, or Titus Wormer.
* No dictionary has been modified in content. Only file names and locations have been changed to produce a flat layout.
* The aggregation script and the layout are provided as‑is. The dictionary files themselves are subject to their respective upstream licenses.
* If you are the rights holder of a dictionary and believe it is included here incorrectly, open an issue and it will be removed or updated.

## Naming conventions

* Language codes follow the common `xx_YY` form when the upstream provides it (`en_US`, `ru_RU`, `es_AR`).
* Some upstream names use hyphens (`fa-IR`, `sr-Latn`, `tlh-Latn`) or lack a region (`ca`, `fr`, `is`). These are kept as‑is.
* Two Belarusian variants exist: `be_BY` and `be-official`. Both are separate dictionaries.

## Source repositories

* https://github.com/LibreOffice/dictionaries
* https://github.com/JetBrains/hunspell-dictionaries
* https://github.com/wooorm/dictionaries

## License of this repository

The collection as a whole, including the README and any aggregation scripts, is provided under the **MIT License**, **except for the dictionary files themselves**, which remain under their original upstream licenses as described above.