# Артефакты

<div class="button-row">

```button
name ⚔️ Создать артефакт
data-tooltip Создать новый артефакт
type command
action Literary Templates: Создать артефакт
```

</div>

Обзор всех артефактов проекта.

## Все артефакты

```dataview
TABLE WITHOUT ID 
  file.link AS "Артефакт",
  type AS "Тип",
  rarity AS "Редкость",
  power AS "Сила",
  origin AS "Происхождение"
FROM "Мои Проекты/Тонущий_мир/Лор/Магия/Артефакты"
WHERE file.ext = "md" AND (contains(file.tags, "артефакт") OR contains(file.tags, "artifact"))
SORT file.name ASC
```

## Артефакты по типу

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Артефакт",
  key AS "Тип",
  r.rarity AS "Редкость",
  r.power AS "Сила",
  r.origin AS "Происхождение"
FROM "Мои Проекты/Тонущий_мир/Артефакты"
WHERE (contains(file.tags, "артефакт") OR contains(file.tags, "artifact"))
GROUP BY type
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

## Артефакты по редкости

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Артефакт",
  key AS "Редкость",
  r.type AS "Тип",
  r.power AS "Сила"
FROM "Мои Проекты/Тонущий_мир/Артефакты"
WHERE (contains(file.tags, "артефакт") OR contains(file.tags, "artifact"))
GROUP BY rarity
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
