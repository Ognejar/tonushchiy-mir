# Народы

```dataview
TABLE WITHOUT ID "[[" + file.path + "|" + name + "]]" AS "Народ", join(language, ", ") AS "Языки", join(religion, ", ") AS "Религии"
FROM "Мои Проекты/Тонущий_мир/Лор/Культуры/Народы"
WHERE contains(tags, "народ")
SORT name ASC
```