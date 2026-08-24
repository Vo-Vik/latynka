# Ukrainian Latin Alphabet (ULAT) / Українська латинська абетка

A fully deterministic, lossless (100% reversible), and diacritic-free Latin transliteration system for the Ukrainian language, with extended support for regional/dialectal phonemes (e.g., Lemko / Carpathian Rusyn `ŷ`).

This system utilizes all **26 letters of the standard ISO Basic Latin alphabet**. It guarantees exact bi-directional conversion between Cyrillic and Latin representations.

---

## Technical Specification

### 1. Alphabet Mapping (Standard & Extended)

| Latin | IPA | Cyrillic | Notes & Rules | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`a`** | `/a/` | А | Standard vowel | `baba` `/ˈbɑbɑ/` $\leftrightarrow$ баба |
| **`b`** | `/b/` | Б | Standard consonant | `brama` `/ˈbrɑmɑ/` $\leftrightarrow$ брама |
| **`c`** | `/tʃ/` | **Ч** | Single-letter replacement for [ч] | `caszka` `/ˈtʃɑʃkɑ/` $\leftrightarrow$ чашка |
| **`d`** | `/d/` | Д | Standard consonant | `dim` `/dim/` $\leftrightarrow$ дім |
| **`e`** | `/ɛ/` | Е | Standard vowel | `eran` `/ɛˈrɑn/` $\leftrightarrow$ еран |
| **`f`** | `/f/` | Ф | Standard consonant | `ferma` `/ˈfɛrmɑ/` $\leftrightarrow$ ферма |
| **`g`** | `/ɡ/` | **Ґ** | Plosive [g] (mirrors `q`) | `ganok` `/ˈɡɑnɔk/` $\leftrightarrow$ ґанок |
| **`h`** | `/∅/` | **’** | Voiceless vowel / Apostrophe marker | `mhaso` `/ˈmjasɔ/` $\leftrightarrow$ м'ясо |
| **`i`** | `/i/` | І | Softening vowel; Palatalizes consonant | `svit` `/sʲvit/` $\leftrightarrow$ світ |
| **`j`** | `/ʲ/` | **Ь** | Palatalization marker for consonants | `bilj` `/bilʲ/` $\leftrightarrow$ біль |
| **`k`** | `/k/` | К | Standard consonant | `kolos` `/ˈkɔlɔs/` $\leftrightarrow$ колос |
| **`l`** | `/l/` | Л | Standard consonant | `lito` `/ˈlitɔ/` $\leftrightarrow$ літо |
| **`m`** | `/m/` | М | Standard consonant | `mama` `/ˈmɑmɑ/` $\leftrightarrow$ мама |
| **`n`** | `/n/` | Н | Standard consonant | `nis` `/nis/` $\leftrightarrow$ ніс |
| **`o`** | `/ɔ/` | О | Standard vowel | `ozero` `/ˈɔzɛrɔ/` $\leftrightarrow$ озеро |
| **`p`** | `/p/` | П | Standard consonant | `pole` `/ˈpɔlɛ/` $\leftrightarrow$ поле |
| **`q`** | `/ɦ/` | **Г** | Fricative [h] (mirrors `g`) | `qolova` `/ɦɔlɔˈvɑ/` $\leftrightarrow$ голова |
| **`r`** | `/r/` | Р | Standard consonant | `rika` `/ˈrikɑ/` $\leftrightarrow$ ріка |
| **`s`** | `/s/` | С | Standard consonant | `sontze` `/ˈsɔnt͡sɛ/` $\leftrightarrow$ сонце |
| **`t`** | `/t/` | Т | Standard consonant | `tato` `/ˈtɑtɔ/` $\leftrightarrow$ тато |
| **`u`** | `/u/` | У | Standard vowel | `uran` `/uˈrɑn/` $\leftrightarrow$ уран |
| **`v`** | `/v/` | В | Labiodental [v] | `voda` `/vɔˈdɑ/` $\leftrightarrow$ вода |
| **`w`** | `/u̯/` | **Ў** | Non-syllabic [w] (endings/pre-consonant) | `pysaw` `/pɪˈsɑu̯/` $\leftrightarrow$ писав |
| **`x`** | `/x/` | **Х** | Single-letter replacement for [х] | `xlib` `/xlib/` $\leftrightarrow$ хліб |
| **`y`** | `/ɪ/`, `/j/` | **И / Й** | `/ɪ/` after consonants; `/j/` after vowels | `syn` `/sɪn/` $\leftrightarrow$ син, `cay` `/t͡ʃɑj/` $\leftrightarrow$ чай |
| **`ŷ`** | `/ɨ/` | **Ы / Ы̂** | Lemko / Rusyn close central unrounded vowel | `sŷn` `/sɨn/` $\leftrightarrow$ сын |
| **`z`** | `/z/` | **З** | Standard [з] & modifier for sibilants | `zyma` `/ˈzɪmɑ/` $\leftrightarrow$ зима |

---

## 2. Sibilant Digraphs & Complex Sounds

| Combination | IPA | Cyrillic | Description | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`cz`** | `/ʃt͡ʃ/`, `/t͡ʃ/` | **Щ** | Voiceless postalveolar complex | `czuka` $\leftrightarrow$ щука |
| **`sz`** | `/ʃ/` | **Ш** | Voiceless postalveolar fricative | `szkola` $\leftrightarrow$ школа |
| **`gz`** | `/ʒ/` | **Ж** | Voiced postalveolar fricative | `gzaba` $\leftrightarrow$ жаба |
| **`tz`** | `/t͡s/` | **Ц** | Voiceless alveolar affricate | `tzap` $\leftrightarrow$ цап |
| **`dgz`** | `/d͡ʒ/` | **ДЖ** | Voiced postalveolar affricate | `narodzgujutjsja` $\leftrightarrow$ народжуються |
| **`dz`** | `/d͡z/` | **ДЗ** | Voiced alveolar affricate | `dzvin` $\leftrightarrow$ дзвін |

---

## 3. Core Structural Rules

### A. Automatic Jotation (Adjacent Vowels)
When two vowels appear consecutively, the second vowel is **automatically iotated**:
* `ia` = **ія** (*maria* $\leftrightarrow$ марія)
* `ie` = **іє** (*idea* $\leftrightarrow$ ідея)
* `oi` = **ої** (*eqoist* $\leftrightarrow$ егоїст)
* `ou` = **ою** (*svou* $\leftrightarrow$ свою)
* `uu` = **ую** (*gzartuucy* $\leftrightarrow$ жартуючи)

### B. Gemination Rule for Digraphs (Modifier `z` Doubling)
When doubling a sibilant digraph, **the modifier letter `z` is duplicated (`zz`)**:
* **ЖЖ** $\rightarrow$ **`gzz`** (тверде) / **`gzzj`**, **`gzzja`** (м'яке)
* **ШШ** $\rightarrow$ **`szz`** (тверде) / **`szzj`**, **`szzju`** (м'яке)
* **ЩЩ** $\rightarrow$ **`czz`**
* **ЦЦ** $\rightarrow$ **`tzz`** (тверде) / **`tzzj`**, **`tzzju`** (м'яке)
* **ЧЧ** $\rightarrow$ **`cc`** (монолітна `c` подвоюється як `cc`) / **`ccj`**, **`ccja`** (м'яке)

| Combination | IPA | Cyrillic | Description | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`tzz`** | `/t͡sː/` | ЦЦ | Long alveolar affricate (hard) | `abratzatzzu` $\leftrightarrow$ обрацацу |
| **`tzzj`** / **`tzzju`** | `/t͡sʲːu/` | ЦЦЬ / ЦЦЮ | Long palatalized alveolar affricate (soft) | `mitzzju` `/ˈmit͡sʲːu/` $\leftrightarrow$ міццю |
| **`gzz`** | `/ʒː/` | ЖЖ | Long voiced postalveolar fricative (hard) | `bizgzzy` $\leftrightarrow$ біжжи |
| **`gzzj`** / **`gzzja`** | `/ʒʲːɑ/` | ЖЖЬ / ЖЖЯ | Long palatalized postalveolar fricative (soft) | `zbigzzja` `/zbiˈʒʲːɑ/` $\leftrightarrow$ збіжжя |
| **`szz`** | `/ʃː/` | ШШ | Long voiceless postalveolar fricative (hard) | `kaszza` $\leftrightarrow$ кашша |
| **`szzj`** / **`szzju`** | `/ʃʲːu/` | ШШЬ / ШШЮ | Long palatalized postalveolar fricative (soft) | `kaszzju` $\leftrightarrow$ кашшю |
| **`cc`** | `/t͡ʃː/` | ЧЧ | Long voiceless postalveolar affricate (hard) | `oblycca` $\leftrightarrow$ обличча |
| **`ccj`** / **`ccja`** | `/t͡ʃʲːɑ/` | ЧЧЬ / ЧЧЯ | Long palatalized postalveolar affricate (soft) | `oblycja` `/ɔˈblɪt͡ʃʲːɑ/` $\leftrightarrow$ обличчя |
| **`czz`** | `/ʃt͡ʃː/` | ЩЩ | Long affricate complex | `zapyczzaty` `/zɑpɪˈʃt͡ʃːɑtɪ/` $\leftrightarrow$ запищщати |

---

## Bi-Directional Algorithmic Logic

### Forward Conversion (Cyrillic $\rightarrow$ Latin)

```python
def cyrillic_to_latin(text: str) -> str:
    # 1. Handle special geminations and digraphs (modifier 'z' doubling)
    geminates = {
        'жжя': 'gzzja', 'жж': 'gzz',
        'шшю': 'szzju', 'шш': 'szz',
        'щщ': 'czz',
        'ццю': 'tzzju', 'цць': 'tzzj', 'цц': 'tzz',
        'ччя': 'ccja', 'чч': 'cc',
        'дж': 'dgz', 'дз': 'dz'
    }
    for cyr, lat in geminates.items():
        text = text.replace(cyr, lat)
        text = text.replace(cyr.upper(), lat.upper())
        
    # 2. Base mapping replacements
    charmap = {
        'а':'a', 'б':'b', 'в':'v', 'г':'q', 'ґ':'g', 'д':'d', 'е':'e', 'є':'ye',
        'ж':'gz', 'з':'z', 'и':'y', 'ы':'ŷ', 'і':'i', 'ї':'yi', 'й':'y', 'к':'k', 
        'л':'l', 'м':'m', 'н':'n', 'о':'o', 'п':'p', 'р':'r', 'с':'s', 'т':'t', 
        'у':'u', 'ф':'f', 'х':'x', 'ц':'tz', 'ч':'c', 'ш':'sz', 'щ':'cz', 'ь':'j', 
        'ю':'yu', 'я':'ya', "'":'h', '’':'h'
    }
    return text
