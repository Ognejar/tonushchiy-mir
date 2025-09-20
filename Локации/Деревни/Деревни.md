---
project: "Тонущий_мир"
type: "Индекс"
created: "2025-09-19"
---

<div class="button-row">

```button
name 🏘️Создать деревню
data-tooltip Создать новую деревню в текущем мире
type command
action Literary Templates: Создать деревню
```

```button
name 🏰Создать город
color yellow
type command
action Literary Templates: Создать город
```

</div>

# Деревни проекта

```dataview
TABLE WITHOUT ID file.link AS "Деревня", state AS "Государство", province AS "Провинция"
FROM ""
WHERE tags AND contains(tags, "деревня")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```
