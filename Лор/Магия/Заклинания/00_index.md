# Заклинания

<div class="button-row">

```button
name ✨ Создать заклинание
data-tooltip Создать новое заклинание
type command
action Literary Templates: Создать заклинание
```

</div>

Обзор всех заклинаний проекта.

## Все заклинания

```dataview
TABLE WITHOUT ID 
  file.link AS "Заклинание",
  school AS "Школа",
  level AS "Уровень",
  castingTime AS "Время наложения",
  range AS "Дальность",
  duration AS "Длительность"
FROM "Мои Проекты/Тонущий_мир/Заклинания"
WHERE file.ext = "md" AND (contains(file.tags, "заклинание") OR contains(file.tags, "spell"))
SORT level ASC, file.name ASC
```

## Заклинания по школе

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Заклинание",
  key AS "Школа",
  r.level AS "Уровень",
  r.castingTime AS "Время наложения",
  r.range AS "Дальность"
FROM "Мои Проекты/Тонущий_мир/Заклинания"
WHERE (contains(file.tags, "заклинание") OR contains(file.tags, "spell"))
GROUP BY school
FLATTEN rows AS r
SORT key ASC, r.level ASC, r.file.name ASC
```

## Заклинания по уровню

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Заклинание",
  key AS "Уровень",
  r.school AS "Школа",
  r.castingTime AS "Время наложения"
FROM "Мои Проекты/Тонущий_мир/Заклинания"
WHERE (contains(file.tags, "заклинание") OR contains(file.tags, "spell"))
GROUP BY level
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
