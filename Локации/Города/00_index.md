---
project: Тонущий_мир
type: Индекс
cssclasses:
  - lit-style
---

<div class="button-row">

```button
name 🏰
data-tooltip Создать новый город в текущем мире
type command
action Literary Templates: Создать город
```

```button
name ⛏️ 
color orange
type command
action Literary Templates: Создать шахту
```
```button
name 🏘️ Создать деревню
color yellow
type command
action Literary Templates: Создать деревню
```

</div>



# Города проекта
```dataview
LIST FROM ""
WHERE tags AND contains(tags, "город")
AND (project = this.project OR contains(file.path, this.project))
AND file.name != this.file.name
SORT file.name ASC
```

Города с провинциями:
```dataview
TABLE WITHOUT ID file.link AS "Город", state AS "Государство", province AS "Провинция"
FROM ""
WHERE tags AND contains(tags, "город")
AND (project = this.project OR contains(file.path, this.project))
AND province != null AND province != ""
SORT state ASC, province ASC, file.name ASC
```

Города без провинций:
```dataview
TABLE WITHOUT ID file.link AS "Город", state AS "Государство"
FROM ""
WHERE tags AND contains(tags, "город")
AND (project = this.project OR contains(file.path, this.project))
AND (province = null OR province = "")
SORT state ASC, file.name ASC
```




