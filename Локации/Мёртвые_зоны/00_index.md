---
project: "Тонущий_мир"
type: "Индекс"
created: "2025-09-20"
---

<div class="button-row">

```button
name 💀Создать мёртвую зону
data-tooltip Создать новую мёртвую зону в текущем мире
type command
action Literary Templates: Создать мёртвую зону
```

```button
name 🏰Создать город
color yellow
type command
action Literary Templates: Создать город
```

</div>

# Мёртвые зоны проекта

```dataview
TABLE WITHOUT ID file.link AS "Мёртвая зона", state AS "Государство", province AS "Провинция"
FROM ""
WHERE tags AND contains(tags, "мёртвая_зона")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```
