# Text2Anki — открытые данные

Открытая часть проекта Text2Anki (Android-читалка с карточками Anki).
Здесь размещаются лицензионные соглашения и базы данных, скачиваемые
приложением: локальные базы транскрипции (IPA).

## Базы транскрипции (phonetics/)

| Файл | Источник | Язык | Описание |
|---|---|---|---|
| `cmudict-ipa-en.sqlite` | CMUdict | en | 126 тыс. английских слов, ARPAbet→IPA |
| `wiktionary-ipa-en.sqlite` | Wiktionary (kaikki.org) | en | Частотные слова с IPA |

Формат SQLite:

```sql
CREATE TABLE meta(key TEXT PRIMARY KEY, value TEXT);
CREATE TABLE words(word TEXT PRIMARY KEY, ipa TEXT);
```

Приложение скачивает базу по кнопке «Скачать» в Настройки → Транскрипция (IPA),
проверяет SHA-256 и использует для локальной транскрипции без сети.
Составная транскрипция фраз собирается пословно.

## Лицензии данных

- **CMUdict** — BSD-подобная лицензия CMU (см. `LICENSE-cmudict.txt`).
- **Wiktionary** — CC BY-SA 4.0 (см. `LICENSE-wiktionary.txt`); данные
  распаршены проектом kaikki.org (также CC BY-SA).
- **Частотные списки** — FrequencyWords (hermitdave, CC BY-SA 4.0).
