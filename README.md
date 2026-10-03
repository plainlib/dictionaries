# Flat Hunspell Dictionaries

A flat collection of Hunspell spelling dictionaries (`.aff` + `.dic` pairs) for 120+ languages and regional variants, aggregated from multiple upstream projects and placed together in a single directory.

## What is included

* Only spelling dictionaries: `.aff` and `.dic` files.
* Hyphenation dictionaries (`hyph_*`), thesaurus files (`th_*`), and test fixtures are excluded.
* All files are placed flat in the repository root. There are no subdirectories.
* File names follow the original upstream naming. Hyphenated names such as `be-official.aff`, `ca-valencia.dic`, `el-polyton.aff`, `fa-IR.dic`, `sr-Latn.aff`, and `tlh-Latn.aff` are kept as is.

## Sources and priority

Dictionaries were collected from three upstream projects and merged in the following order (higher overrides lower):

1. **LibreOffice/dictionaries** (highest priority) — https://github.com/LibreOffice/dictionaries
2. **JetBrains/hunspell-dictionaries** — https://github.com/JetBrains/hunspell-dictionaries
3. **wooorm/dictionaries** (lowest priority) — https://github.com/wooorm/dictionaries

If a language is present in more than one source, the file from the higher-priority source is kept. This means the final set uses LibreOffice dictionaries wherever available, then fills the gaps from JetBrains, and finally from wooorm.

The Finnish dictionary (`fi_FI`) is an exception — see its dedicated section below.

## Naming conventions

* Language codes follow the common `xx_YY` form when the upstream provides it (`en_US`, `ru_RU`, `es_AR`).
* Some upstream names use hyphens (`fa-IR`, `sr-Latn`, `tlh-Latn`) or lack a region (`ca`, `fr`, `is`). These are kept as-is.
* Two Belarusian variants exist: `be_BY` and `be-official`. Both are separate dictionaries.

## Licensing

**This repository is an aggregation. It does not relicense any dictionary.**

Each `.aff` and `.dic` file remains under the license assigned by its original author(s) and upstream project. Because dictionaries were merged from multiple sources, **the license varies from file to file**.

The accompanying material from the upstream projects — README files, license texts, copyright notices, changelogs, and per-language documentation — has been intentionally omitted to keep the layout flat and the repository small. This means that if you need the exact license of a specific dictionary, you should consult its original upstream source.

### Source-wide license notes

* **LibreOffice/dictionaries** — the repository is hosted by The Document Foundation, and its top-level license is **MPL‑2.0**, but individual dictionaries carry their own licenses: LGPL‑2.1+, GPL‑2+, GPL‑3+, MPL‑1.1, CC‑BY‑SA‑3.0, CC0‑1.0, and others. A consolidated per-language breakdown is available in the Debian copyright file:
  https://tracker.debian.org/media/packages/libr/libreoffice-dictionaries/copyright-17.1.0rc3-3

* **wooorm/dictionaries** — each dictionary declares its own license in the package metadata (`package.json`) and ships a `LICENSE` file in the corresponding folder. Licenses include MIT, BSD‑2‑Clause, GPL‑2.0, GPL‑2.0 OR GPL‑3.0, GPL‑2.0 OR LGPL‑2.1 OR MPL‑1.1, LGPL‑2.1, and others.

* **JetBrains/hunspell-dictionaries** — dictionaries are generally distributed under **LGPLv3** and/or **MPL**, with some files under MIT. The exact license is stated in the README file shipped with each dictionary.

In most cases the license is one of: LGPL‑2.1+, GPL‑2+, GPL‑3+, MPL‑1.1, MPL‑2.0, MIT, CC‑BY‑SA‑3.0, or CC0 1.0. The list is not exhaustive; always check the upstream source for the dictionary you intend to use.

### What this means for you

* If you use a dictionary in a context where the license matters (redistribution, commercial product, SaaS), **check the license of that specific dictionary** before using it.
* Attribution requirements from the original license still apply. Where a dictionary requires attribution, credit the original authors as stated in the upstream repository.
* This repository does not claim any copyright over the dictionary content. It only collects and renames files.

## Finding the license of a specific dictionary

Because licenses differ from dictionary to dictionary, the authoritative license for a specific file is the one declared in its original upstream source. Use the table below to find the right place to look.

| If the file came from… | Look here |
|---|---|
| LibreOffice | `dictionaries/<lang>/` in https://github.com/LibreOffice/dictionaries, or the Debian copyright file linked above |
| JetBrains | `README` or `LICENSE` file in the corresponding folder at https://github.com/JetBrains/hunspell-dictionaries |
| wooorm | `dictionaries/<lang>/package.json` or `dictionaries/<lang>/LICENSE` at https://github.com/wooorm/dictionaries |
| Finnish (`fi_FI`) | See the dedicated section below |

If you need a machine-readable per-file license list, it can be generated from the upstream metadata, but this repository does not currently include such a list.

If you redistribute a dictionary, keep the attribution required by its upstream license and, where the license requires it, ship the corresponding license text alongside the files.

## Finnish dictionary (fi_FI)

The Finnish dictionary (`fi_FI.aff` + `fi_FI.dic`) was not taken from the three main sources above. It was obtained from a **sailfishos-chum** community repository and **modified locally** (header/`.aff` directives adjusted, file renamed to the flat `fi_FI` scheme; the word list itself was not changed).

The dictionary originates from the **Voikko** project (https://voikko.puimula.org/). Voikko dictionary data is distributed under the **GNU General Public License, version 2 or later (GPL‑2.0‑or‑later)**. Because the file was modified, this notice documents the change as required by GPL‑2 § 2. When redistributing `fi_FI`, keep this notice alongside the file and credit Voikko and the sailfishos-chum repository.

## Disclaimer

* This repository is **not affiliated with** The Document Foundation, LibreOffice, JetBrains, or Titus Wormer.
* Except for `fi_FI` (see its dedicated section above), no dictionary has been modified in content. File names and locations were changed to produce a flat layout.
* The aggregation script and the layout are provided as-is. The dictionary files themselves are subject to their respective upstream licenses.
* If you are the rights holder of a dictionary and believe it is included here incorrectly, open an issue and it will be removed or updated.

## Source repositories

* https://github.com/LibreOffice/dictionaries
* https://github.com/JetBrains/hunspell-dictionaries
* https://github.com/wooorm/dictionaries

## License of this repository

The README text and any aggregation scripts in this repository are provided under the **MIT License**. The dictionary files themselves remain under their original upstream licenses as described above and are not covered by the MIT License.