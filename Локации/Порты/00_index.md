---
project: "Тонущий_мир"
type: "Индекс"
created: "2025-09-19"
---

<div class="button-row">

```button
name ⚓Создать порт
data-tooltip Создать новый порт в текущем мире
type command
action Literary Templates: Создать порт
```

```button
name 🏰Создать город
color yellow
type command
action Literary Templates: Создать город
```

</div>

# Порты проекта

```dataview
TABLE WITHOUT ID file.link AS "Порт", state AS "Государство", province AS "Провинция"
FROM ""
WHERE tags AND contains(tags, "порт")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```
