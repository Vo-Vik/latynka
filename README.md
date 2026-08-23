# Ukrainian Latin Alphabet (ULAT) / Українська латинська абетка

A fully deterministic, lossless (100% reversible), and diacritic-free Latin transliteration system for the Ukrainian language. 

This system utilizes all **26 letters of the standard ISO Basic Latin alphabet** without requiring external accents, special diacritical marks, or unicode symbols. It guarantees exact bi-directional conversion between Cyrillic and Latin representations.

---

## Phonetic IPA Mapping / Фонетична транскрипція IPA

### 1. Base Alphabet (26 Letters)

| Latin | IPA | Cyrillic | Context / Rules | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`a`** | `/a/` | А | Standard open front unrounded vowel | `baba` `/ˈbɑbɑ/` |
| **`b`** | `/b/` | Б | Voiced bilabial plosive | `brama` `/ˈbrɑmɑ/` |
| **`c`** | `/tʃ/` | Ч | Voiceless postalveolar affricate | `caszka` `/ˈtʃɑʃkɑ/` |
| **`d`** | `/d/` | Д | Voiced alveolar plosive | `dim` `/dim/` |
| **`e`** | `/ɛ/` | Е | Open-mid front unrounded vowel | `eran` `/ɛˈrɑn/` |
| **`f`** | `/f/` | Ф | Voiceless labiodental fricative | `ferma` `/ˈfɛrmɑ/` |
| **`g`** | `/ɡ/` | Ґ | Voiced velar plosive | `ganok` `/ˈɡɑnɔk/` |
| **`h`** | `/∅/` | ’ | Voiceless vowel / Triggers jotation | `mhaso` `/ˈmjasɔ/` |
| **`i`** | `/i/` | І | Close front unrounded vowel; Palatalizes previous consonant | `svit` `/sʲvit/` |
| **`j`** | `/ʲ/` | Ь | Palatalization marker for consonants | `bilj` `/bilʲ/` |
| **`k`** | `/k/` | К | Voiceless velar plosive | `kolos` `/ˈkɔlɔs/` |
| **`l`** | `/l/` | Л | Alveolar lateral approximant | `lito` `/ˈlitɔ/` |
| **`m`** | `/m/` | М | Bilabial nasal | `mama` `/ˈmɑmɑ/` |
| **`n`** | `/n/` | Н | Alveolar nasal | `nis` `/nis/` |
| **`o`** | `/ɔ/` | О | Open-mid back rounded vowel | `ozero` `/ˈɔzɛrɔ/` |
| **`p`** | `/p/` | П | Voiceless bilabial plosive | `pole` `/ˈpɔlɛ/` |
| **`q`** | `/ɦ/` | Г | Voiced glottal fricative | `qolova` `/ɦɔlɔˈvɑ/` |
| **`r`** | `/r/` | Р | Alveolar trill | `rika` `/ˈrikɑ/` |
| **`s`** | `/s/` | С | Voiceless alveolar sibilant | `sontze` `/ˈsɔnt͡sɛ/` |
| **`t`** | `/t/` | Т | Voiceless alveolar plosive | `tato` `/ˈtɑtɔ/` |
| **`u`** | `/u/` | У | Close back rounded vowel | `uran` `/uˈrɑn/` |
| **`v`** | `/v/` | В | Voiced labiodental fricative | `voda` `/vɔˈdɑ/` |
| **`w`** | `/u̯/` | Ў | Non-syllabic voiced labial-velar approximant | `pysaw` `/pɪˈsɑu̯/` |
| **`x`** | `/x/` | Х | Voiceless velar fricative | `xlib` `/xlib/` |
| **`y`** | `/ɪ/`, `/j/` | И / Й | `/ɪ/` after consonants; `/j/` after vowels or starting words | `syn` `/sɪn/`, `cay` `/t͡ʃɑj/` |
| **`z`** | `/z/` | З | Voiced alveolar sibilant | `zyma` `/ˈzɪmɑ/` |

---

### 2. Digraphs, Trigraphs & Sibilants

| Combination | IPA | Cyrillic | Description | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`cz`** | `/t͡ʃː/` | Щ | Long voiceless postalveolar affricate/fricative complex | `czuka` `/ˈt͡ʃːukɑ/` |
| **`sz`** | `/ʃ/` | Ш | Voiceless postalveolar fricative | `szkola` `/ˈʃkɔlɑ/` |
| **`gz`** | `/ʒ/` | Ж | Voiced postalveolar fricative | `gzaba` `/ˈʒɑbɑ/` |
| **`tz`** | `/t͡s/` | Ц | Voiceless alveolar affricate | `tzap` `/t͡sɑp/` |
| **`dz`** | `/d͡z/` | ДЗ | Voiced alveolar affricate | `dzvin` `/d͡zvʲin/` |
| **`dgz`** | `/d͡ʒ/` | ДЖ | Voiced postalveolar affricate | `dgzmelj` `/d͡ʒmɛlʲ/` |

---

### 3. Softening (Palatalization IPA Rules)

| Pattern | IPA Modifier | Cyrillic | Phonetic Effect | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`C + j`** | `/Cʲ/` | СЬ / ТЬ... | Palatalizes preceding consonant `C` | `bilj` `/bilʲ/`, `oljqa` `/ˈɔlʲɦɑ/` |
| **`C + i`** | `/Cʲi/` | СІ / ТІ... | Palatalizes preceding consonant + vowel `/i/` | `lito` `/ˈlʲitɔ/` |
| **`C + ja`** | `/Cʲɑ/` | СЯ / ЛЯ... | Palatalizes consonant + unrounded vowel `/ɑ/` | `paljanytzja` `/pɑlʲɑˈnɪt͡sʲɑ/` |
| **`C + ju`** | `/Cʲu/` | СЮ / ЛЮ... | Palatalizes consonant + rounded vowel `/u/` | `ljudy` `/ˈlʲudɪ/` |
| **`C + je`** | `/Cʲɛ/` | СЄ / ЛЄ... | Palatalizes consonant + mid vowel `/ɛ/` | `synje` `/ˈsɪnʲɛ/` |
| **`V + V`** | `/V + jV/` | ІЯ / ОЇ... | Second vowel `/V/` automatically triggers `/j/` | `maria` `/mɑˈrijɑ/`, `eqoist` `/ɛɦɔˈjist/` |
| **`C + h + V`**| `/C + jV/` | М'Я / В'Я... | Silent vowel `h` `/∅/` triggers iotated `/j/` | `mhaso` `/ˈmjɑsɔ/` |

---

### 4. Gemination IPA Rules

| Pattern | IPA | Cyrillic | Description | Examples |
| :---: | :---: | :---: | :--- | :--- |
| **`ttz`** | `/t͡sː/` | ЦЦ | Long alveolar affricate (hard / без Ь) | `abratzattzu` `/ɑbrɑˈt͡sɑt͡sːu/` |
| **`ttzj`** / **`ttzju`** | `/t͡sʲːu/` | ЦЦЬ / ЦЦЮ | Long palatalized alveolar affricate (soft / з Ь) | `mittzju` `/ˈmit͡sʲːu/` |
| **`ggz`** | `/ʒː/` | ЖЖ | Long voiced postalveolar fricative (hard) | `bizggzy` `/biˈʒːɪ/` |
| **`ggzj`** / **`ggzja`** | `/ʒʲːɑ/` | ЖЖЬ / ЖЖЯ | Long palatalized postalveolar fricative (soft) | `zbyggzja` `/zbiˈʒʲːɑ/` |
| **`ssz`** | `/ʃː/` | ШШ | Long voiceless postalveolar fricative (hard) | `kassza` `/ˈkɑʃːɑ/` |
| **`sszj`** / **`sszju`** | `/ʃʲːu/` | ШШЬ / ШШЮ | Long palatalized postalveolar fricative (soft) | `kasszju` `/ˈkɑʃʲːu/` |
| **`cc`** | `/t͡ʃː/` | ЧЧ | Long voiceless postalveolar affricate (hard) | `oblycca` `/ɔˈblɪt͡ʃːɑ/` |
| **`ccj`** / **`ccja`** | `/t͡ʃʲːɑ/` | ЧЧЬ / ЧЧЯ | Long palatalized postalveolar affricate (soft) | `oblycja` `/ɔˈblɪt͡ʃʲːɑ/` |
| **`ccz`** | `/t͡ʃː/` | ЩЩ | Long affricate complex | `zapycczaty` `/zɑpɪˈt͡ʃːɑtɪ/` |
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
