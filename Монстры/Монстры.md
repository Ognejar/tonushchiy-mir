## Индекс: Монстры

Ниже — таблицы по всем файлам-монстрам в текущей папке (проекта). Убедитесь, что этот файл лежит в папке вашего мира: `.../Монстры/`.

<div class="button-row">

```button
name 🐉Создать монстра
type command
action Literary Templates: Создать монстра
```

</div>

```dataview
TABLE WITHOUT ID
  file.link AS "Монстр",
  type AS "Тип",
  size AS "Размер",
  intelligence AS "Интеллект",
  alignment AS "Мировоззрение",
  choice(default(isPoisonous, false), "☠️", "") AS "Ядовит",
  choice(default(hasMagic, false), "✨", "") AS "Магия"
FROM "Мои Проекты/Тонущий_мир/Монстры"
WHERE file.ext = "md" AND (contains(file.tags, "монстр") OR contains(file.tags, "monster"))
SORT file.name ASC
```

```dataview
TABLE WITHOUT ID
  r.file.link AS "Монстр",
  key AS "Тип",
  r.size AS "Размер",
  r.intelligence AS "Интеллект",
  r.alignment AS "Мировоззрение",
  choice(default(r.isPoisonous, false), "☠️", "") AS "Ядовит",
  choice(default(r.hasMagic, false), "✨", "") AS "Магия"
FROM "Мои Проекты/Тонущий_мир/Монстры"
WHERE (contains(file.tags, "монстр") OR contains(file.tags, "monster"))
GROUP BY type
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```