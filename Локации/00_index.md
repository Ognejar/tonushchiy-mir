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
name ![[Создать_провинцию.jpg|Создать провинцию]]
type command
action Literary Templates: Создать провинцию
```
```button
class create-button
name ![[создать_город.jpg|Создать город]]
type command
action Literary Templates: Создать город
```

</div>

<div class="button-row">

```button
name ⛏️ Создать шахту
color orange
type command
action Literary Templates: Создать шахту
```
```button
name 🏘️ Деревня
color yellow
type command
action Literary Templates: Создать деревню
```
```button
name 🐮 Ферма
type command
action Literary Templates: Создать ферму
```
```button
name 🏭 Завод
color blue
type command
action Literary Templates: Создать завод
```
```button
name 🏰 Замок
color red
type command
action Literary Templates: Создать замок
```

</div>

Обзор всех локаций проекта.

## Государства

```dataview
TABLE WITHOUT ID 
  file.link AS "Государство",
  capital AS "Столица",
  population AS "Население",
  governmentType AS "Правительство"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Государство" 
  AND file.name != this.file.name
SORT file.name ASC
```

## Провинции

```dataview
TABLE WITHOUT ID 
  file.link AS "Провинция",
  state AS "Государство",
  climate AS "Климат",
  population AS "Население"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Провинция" 
  AND file.name != this.file.name
SORT state ASC, file.name ASC
```

## Города

```dataview
TABLE WITHOUT ID 
  file.link AS "Город",
  state AS "Государство",
  province AS "Провинция",
  population AS "Население"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Город" 
  AND tags AND contains(tags, "город")
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Деревни

```dataview
TABLE WITHOUT ID 
  file.link AS "Деревня",
  state AS "Государство",
  province AS "Провинция",
  population AS "Население"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Деревня" 
  AND tags AND contains(tags, "деревня")
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Фортификации

```dataview
TABLE WITHOUT ID 
  file.link AS "Фортификация",
  state AS "Государство",
  province AS "Провинция",
  type AS "Тип"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Фортификация"
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Фермы

```dataview
TABLE WITHOUT ID 
  file.link AS "Ферма",
  state AS "Государство",
  province AS "Провинция",
  farmType AS "Тип фермы"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Ферма"
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Шахты

```dataview
TABLE WITHOUT ID 
  file.link AS "Шахта",
  state AS "Государство",
  province AS "Провинция",
  mineType AS "Тип шахты"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Шахта"
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Заводы

```dataview
TABLE WITHOUT ID 
  file.link AS "Завод",
  state AS "Государство",
  province AS "Провинция",
  factoryType AS "Тип завода"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND type = "Завод"
  AND file.name != this.file.name
SORT state ASC, province ASC, file.name ASC
```

## Прочие локации

```dataview
TABLE WITHOUT ID 
  file.link AS "Локация",
  type AS "Тип",
  state AS "Государство",
  province AS "Провинция"
FROM "Мои Проекты/Тонущий_мир/Локации"
WHERE file.ext = "md" AND tags AND contains(tags, "локация")
  AND type != "Государство" 
  AND type != "Провинция" 
  AND type != "Город" 
  AND type != "Деревня"
  AND file.name != this.file.name
SORT type ASC, state ASC, file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
