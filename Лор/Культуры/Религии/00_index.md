# Религии

```dataview
TABLE WITHOUT ID "[[" + file.path + "|" + name + "]]" AS "Религия", join(регион, ", ") AS "Регионы"
FROM "Мои Проекты/Тонущий_мир/Лор/Культуры/Религии"
WHERE type = "Религия"
SORT name ASC
```