# Зелья

<div class="button-row">

```button
name 🧪 Создать зелье
data-tooltip Создать новое зелье
type command
action Literary Templates: Создать зелье
```

</div>

Обзор всех зелий проекта.

## Все зелья

```dataview
TABLE WITHOUT ID 
  file.link AS "Зелье",
  type AS "Тип",
  rarity AS "Редкость",
  effect AS "Эффект",
  duration AS "Длительность",
  ingredients AS "Ингредиенты"
FROM "Мои Проекты/Тонущий_мир/Зелья"
WHERE file.ext = "md" AND (contains(file.tags, "зелье") OR contains(file.tags, "potion"))
SORT file.name ASC
```

## Зелья по типу

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Зелье",
  key AS "Тип",
  r.rarity AS "Редкость",
  r.effect AS "Эффект",
  r.duration AS "Длительность"
FROM "Мои Проекты/Тонущий_мир/Зелья"
WHERE (contains(file.tags, "зелье") OR contains(file.tags, "potion"))
GROUP BY type
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

## Зелья по редкости

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Зелье",
  key AS "Редкость",
  r.type AS "Тип",
  r.effect AS "Эффект"
FROM "Мои Проекты/Тонущий_мир/Зелья"
WHERE (contains(file.tags, "зелье") OR contains(file.tags, "potion"))
GROUP BY rarity
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
