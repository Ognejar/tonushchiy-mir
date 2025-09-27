---
type: провинции
project: "Новый_мир"
created: "2025-09-19"
image: "Теговые_картинки/Провинция.webp"
---

![[Теговые_картинки/Провинция.webp]]

<div class="button-row">

```button
name 🏞️Создать провинцию
data-tooltip Создать новую провинцию в текущем мире
type command
action Literary Templates: Создать провинцию
```

```button
name 🏰Создать город
color yellow
type command
action Literary Templates: Создать город
```

```button
name 🏘️Создать деревню
color orange
type command
action Literary Templates: Создать деревню
```

</div>

# Провинции

## Список провинций проекта

```dataview
TABLE WITHOUT ID file.link AS "Провинция", state AS "Государство"
FROM ""
WHERE tags AND contains(tags, "провинция")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT state ASC, file.name ASC
```

# Провинции проекта
```dataview
LIST FROM ""
WHERE tags AND contains(tags, "провинция")
AND project = this.project
AND file.name != this.file.name
SORT file.name ASC
```
## Задачи по провинциям

```dataview
TASK
WHERE !completed AND contains(file.path, this.file.folder) AND contains(file.path, "Провинции/")
SORT file.ctime desc
```

## Автоматические связи

### Города по провинциям (в рамках проекта)
```dataview
TABLE province AS "Провинция", rows.file.link AS "Города"
FROM ""
WHERE tags AND contains(tags, "город")
AND (project = this.project OR contains(file.path, this.project))
GROUP BY province
```

### Деревни по провинциям (в рамках проекта)
```dataview
TABLE province AS "Провинция", rows.file.link AS "Деревни"
FROM ""
WHERE tags AND contains(tags, "деревня")
AND (project = this.project OR contains(file.path, this.project))
GROUP BY province
```
