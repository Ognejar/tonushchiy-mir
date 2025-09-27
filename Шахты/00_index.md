---
type: шахты
project: "Тонущий_мир"
created: "2025-09-19"
image: "Теговые_картинки/Шахта.webp"
cssclasses:
  - lit-style
---

![[Теговые_картинки/Шахта.webp]]

<div class="button-row">

```button
name ⛏️Создать шахту
data-tooltip Создать новую шахту в текущем мире
type command
action Literary Templates: Создать шахту (мастер)
```
```button
name 🏘️Создать деревню
color yellow
type command
action Literary Templates: Создать деревню
```

</div>

# Шахты и горнодобывающие объекты

## Шахты с провинциями

```dataview
TABLE WITHOUT ID file.link AS "Шахта", state AS "Государство", province AS "Провинция", mineType AS "Тип шахты", status AS "Статус"
FROM ""
WHERE tags AND contains(tags, "шахта")
AND (project = this.project OR contains(file.path, this.project))
AND province != null AND province != ""
SORT state ASC, province ASC, file.name ASC
```

## По типам шахт

```dataview
TABLE WITHOUT ID file.link AS "Шахта", state AS "Государство", province AS "Провинция", mineType AS "Тип шахты"
FROM ""
WHERE tags AND contains(tags, "шахта")
AND (project = this.project OR contains(file.path, this.project))
SORT mineType ASC, state ASC, province ASC, file.name ASC
```
