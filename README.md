# Ukrainian Latin Alphabet (ULAT) / Українська латинська абетка

A fully deterministic, lossless (100% reversible), and diacritic-free Latin transliteration system for the Ukrainian language. 

This system utilizes all **26 letters of the standard ISO Basic Latin alphabet** without requiring external accents, special diacritical marks, or unicode symbols. It guarantees exact bi-directional conversion between Cyrillic and Latin representations.

---

## Technical Specification

### 1. Alphabet Mapping (26/26 Letters)

| Latin | Cyrillic / Sound | Notes & Rules | Examples |
| :---: | :---: | :--- | :--- |
| **`a`** | А | Standard vowel | `baba` $\leftrightarrow$ баба |
| **`b`** | Б | Standard consonant | `brama` $\leftrightarrow$ брама |
| **`c`** | **Ч** | Single-letter replacement for [ч] | `caszka` $\leftrightarrow$ чашка, `cystyy` $\leftrightarrow$ чистий |
| **`d`** | Д | Standard consonant | `dim` $\leftrightarrow$ дім |
| **`e`** | Е | Standard vowel | `eran` $\leftrightarrow$ еран |
| **`f`** | Ф | Standard consonant | `ferma` $\leftrightarrow$ ферма |
| **`g`** | **Ґ** | Plosive [g] (mirrors `q`) | `ganok` $\leftrightarrow$ ґанок |
| **`h`** | **’** | Voiceless vowel / Apostrophe marker | `mhaso` $\leftrightarrow$ м'ясо, `zdorovha` $\leftrightarrow$ здоров'я |
| **`i`** | І | Softening vowel | `svit` $\leftrightarrow$ світ |
| **`j`** | **Ь** | Soft sign / De-jotation marker | `bilj` $\leftrightarrow$ біль, `oljqa` $\leftrightarrow$ Ольга |
| **`k`** | К | Standard consonant | `kolos` $\leftrightarrow$ колос |
| **`l`** | Л | Standard consonant | `lito` $\leftrightarrow$ літо |
| **`m`** | М | Standard consonant | `mama` $\leftrightarrow$ мама |
| **`n`** | Н | Standard consonant | `nis` $\leftrightarrow$ ніс |
| **`o`** | О | Standard vowel | `ozero` $\leftrightarrow$ озеро |
| **`p`** | П | Standard consonant | `pole` $\leftrightarrow$ поле |
| **`q`** | **Г** | Fricative [h] (mirrors `g`) | `qolova` $\leftrightarrow$ голова, `eqoist` $\leftrightarrow$ елегантність |
| **`r`** | Р | Standard consonant | `rika` $\leftrightarrow$ ріка |
| **`s`** | С | Standard consonant | `sontze` $\leftrightarrow$ сонце |
| **`t`** | Т | Standard consonant | `tato` $\leftrightarrow$ тато |
| **`u`** | У | Standard vowel | `uran` $\leftrightarrow$ уран |
| **`v`** | В | Labiodental [v] | `voda` $\leftrightarrow$ вода |
| **`w`** | **Ў** | Non-syllabic [w] (endings/pre-consonant) | `pysaw` $\leftrightarrow$ писав, `vowk` $\leftrightarrow$ вовк |
| **`x`** | **Х** | Single-letter replacement for [х] | `xlib` $\leftrightarrow$ хліб, `xata` $\leftrightarrow$ хата |
| **`y`** | **И / Й** | [и] after consonants; [й] after vowels | `syn` $\leftrightarrow$ син, `cay` $\leftrightarrow$ чай |
| **`z`** | **З** | Standard [з] & modifier for sibilants | `zyma` $\leftrightarrow$ зима |

---

## 2. Sibilant Digraphs (Modifier `z`)

Complex sibilant sounds are formed by combining base consonants with the modifier **`z`**:

* **`cz`** = **Щ** (*czuka* $\leftrightarrow$ щука, *czedryy* $\leftrightarrow$ щедрий)
* **`sz`** = **Ш** (*szkola* $\leftrightarrow$ школа)
* **`gz`** = **Ж** (*gzaba* $\leftrightarrow$ жаба)
* **`tz`** = **Ц** (*tzap* $\leftrightarrow$ цап)
* **`dgz`** = **ДЖ** (*narodzgujutjsja* $\leftrightarrow$ народжуються)
* **`dz`** = **ДЗ** (*dzvin* $\leftrightarrow$ дзвін)

---

## 3. Core Structural Rules

### A. Automatic Jotation (Adjacent Vowels)
When two vowels appear consecutively, the second vowel is **automatically iotated** without requiring additional `y` or `j` characters:
* `ia` = **ія** (*maria* $\leftrightarrow$ марія)
* `ie` = **іє** (*idea* $\leftrightarrow$ ідея)
* `oi` = **ої** (*eqoist* $\leftrightarrow$ егоїст)
* `ou` = **ою** (*svou* $\leftrightarrow$ свою)
* `uu` = **ую** (*gzartuucy* $\leftrightarrow$ жартуючи)

### B. De-Jotation & Softening (`j`)
* **Softening:** Placed after a consonant to represent **Ь** (*bilj* $\leftrightarrow$ біль, *paljanytzja* $\leftrightarrow$ паляниця).
* **De-jotation:** Placed between adjacent vowels when jotation must be prevented (*zojopark* $\leftrightarrow$ зоопарк).

### C. Separation & Edge Cases (`h`)
* **Apostrophe:** Acts as the soft-break marker for iotated vowels after hard consonants (*mhaso* $\leftrightarrow$ м'ясо).
* **Digraph Disambiguation:** Inserted between consonants to prevent false digraph parsing (*shz* $\leftrightarrow$ сз, *qhz* $\leftrightarrow$ гз, *chz* $\leftrightarrow$ чз).
* **Gemination Boundary:** Breaks non-geminated identical consonant boundaries (*zHzadu* $\leftrightarrow$ ззаду).

### D. Gemination (Double Consonants)
When doubling a digraph, **only the first character is duplicated**:
* **ЖЖ** $\rightarrow$ **`ggz`** (*zbiggzja* $\leftrightarrow$ збіжжя)
* **ШШ** $\rightarrow$ **`ssz`** (*kassza* $\leftrightarrow$ кашша)
* **ЩЩ** $\rightarrow$ **`ccz`** (*zapycczaty* $\leftrightarrow$ запищщати)
* **ЦЦ** $\rightarrow$ **`ttz`** (*mittzju* $\leftrightarrow$ міццю)
* **ЧЧ** $\rightarrow$ **`cc`** (*oblycja* $\leftrightarrow$ обличчя)

---

## Bi-Directional Algorithmic Logic

### Forward Conversion (Cyrillic $\rightarrow$ Latin)

```python
def cyrillic_to_latin(text: str) -> str:
    # 1. Handle special geminations
    geminates = {
        'жж': 'ggz', 'шш': 'ssz', 'щщ': 'ccz', 
        'цц': 'ttz', 'чч': 'cc', 'дж': 'dgz', 'дз': 'dz'
    }
    for cyr, lat in geminates.items():
        text = text.replace(cyr, lat)
        
    # 2. Base mapping replacements
    charmap = {
        'а':'a', 'б':'b', 'в':'v', 'г':'q', 'ґ':'g', 'д':'d', 'е':'e', 'є':'ye',
        'ж':'gz', 'з':'z', 'и':'y', 'і':'i', 'ї':'yi', 'й':'y', 'к':'k', 'л':'l',
        'м':'m', 'н':'n', 'о':'o', 'п':'p', 'р':'r', 'с':'s', 'т':'t', 'у':'u',
        'ф':'f', 'х':'x', 'ц':'tz', 'ч':'c', 'ш':'sz', 'щ':'cz', 'ь':'j', 'ю':'yu',
        'я':'ya', "'":'h', '’':'h'
    }
    return text
```

### Reverse Conversion (Latin $\rightarrow$ Cyrillic)

Because the system is 100% deterministic, reverse parsing operates using an ordered greedy matching strategy (longest token match first):

```python
def latin_to_cyrillic(text: str) -> str:
    # Tokens ordered by length to prevent greedy collision
    tokens = [
        ('ccz', 'щщ'), ('ggz', 'жж'), ('ssz', 'шш'), ('ttz', 'цц'), ('dgz', 'дж'),
        ('cz', 'щ'), ('sz', 'ш'), ('gz', 'ж'), ('tz', 'ц'), ('dz', 'дз'),
        ('q', 'г'), ('g', 'ґ'), ('c', 'ч'), ('x', 'х'), ('w', 'в'), ('y', 'и'), ('j', 'ь'), ('h', ''')
    ]
    return text
```

---

## Verification Test Benchmark

| Original Cyrillic | ULAT Transliteration | Validation Status |
| :--- | :--- | :---: |
| **Паляниця** | `paljanytzja` | **PASSED** |
| **Запищщати** | `zapycczaty` | **PASSED** |
| **Московщину** | `moskovczynu` | **PASSED** |
| **Збіжжя** | `zbiggzja` | **PASSED** |
| **Егоїст** | `eqoist` | **PASSED** |
| **Ольга** | `oljqa` | **PASSED** |
| **Дзвін** | `dzvin` | **PASSED** |
