---
type: замки
project: "Тонущий_мир"
created: "2025-09-19"
image: "Теговые_картинки/Замок.webp"
cssclasses:
  - lit-style
---

![[Теговые_картинки/Замок.webp]]

<div class="button-row">

```button
name 🏰Создать замок
data-tooltip Создать новую фортификацию в текущем мире
type command
action Literary Templates: Создать замок (мастер)
```
```button
name 🏘️Создать деревню
color yellow
type command
action Literary Templates: Создать деревню
```

</div>

# Замки и фортификации

## Фортификации с провинциями

```dataview
TABLE WITHOUT ID file.link AS "Фортификация", state AS "Государство", province AS "Провинция", type AS "Тип"
FROM ""
WHERE tags AND contains(tags, "фортификация")
AND (project = this.project OR contains(file.path, this.project))
AND province != null AND province != ""
SORT state ASC, province ASC, file.name ASC
```

## По типам фортификаций

```dataview
TABLE WITHOUT ID file.link AS "Фортификация", state AS "Государство", province AS "Провинция", type AS "Тип"
FROM ""
WHERE tags AND contains(tags, "фортификация")
AND (project = this.project OR contains(file.path, this.project))
SORT type ASC, state ASC, province ASC, file.name ASC
```
