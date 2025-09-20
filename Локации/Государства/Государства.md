---
type: государства
project: "Тонущий_мир"
created: "2025-09-20"
image: "Теговые_картинки/Государство.webp"
---

![[Теговые_картинки/Государствo.webp]]

<div class="button-row">

```button
class create-button
name ![[создать_мир.jpg|Создать новый мир]]
type command
action Literary Templates: Создать новый мир/проект
```

```button
class create-button
name ![[Создать_государство.jpg|Создать государство]]
type command
action Literary Templates: Создать государство
```

```button
class create-button
name ![[создать_город.jpg|Создать город]]
type command
action Literary Templates: Создать город
```

</div>

# Государства

## Список государств проекта

```dataview
TABLE WITHOUT ID file.link AS "Государство", governmentType AS "Правление", capital AS "Столица"
FROM "Мои Проекты/Тонущий_мир/Локации/Государства"
WHERE file.ext = "md" AND tags AND contains(tags, "государство")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT file.name ASC
```

## Задачи по государствам

```dataview
TASK
FROM "Мои Проекты/Тонущий_мир/Локации/Государства"
WHERE !completed AND file.ext = "md"
SORT file.ctime desc
```

## Автоматические связи

### Провинции по государствам (в рамках проекта)

```dataview
TABLE state AS "Государство", rows.file.link AS "Провинции"
FROM "Мои Проекты/Тонущий_мир/Локации/Государства"
WHERE file.ext = "md" AND tags AND contains(tags, "провинция")
AND (project = this.project OR contains(file.path, this.project))
GROUP BY state
```
