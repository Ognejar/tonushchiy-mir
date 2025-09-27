# Персонажи

<div class="button-row">

```button
name 🧙Создать персонажа
data-tooltip Создать нового персонажа
type command
action Literary Templates: Создать персонажа
```

</div>

Обзор всех персонажей проекта.

## Главные герои

```dataview
TABLE WITHOUT ID 
  file.link AS "Персонаж",
  role AS "Роль",
  age AS "Возраст",
  occupation AS "Занятие"
FROM "Мои Проекты/Тонущий_мир/Персонажи"
WHERE file.ext = "md" AND type = "Персонаж" 
  AND contains(tags, "главный_герой")
  AND file.name != this.file.name
SORT file.name ASC
```

## Второстепенные персонажи

```dataview
TABLE WITHOUT ID 
  file.link AS "Персонаж",
  role AS "Роль",
  age AS "Возраст",
  occupation AS "Занятие"
FROM "Мои Проекты/Тонущий_мир/Персонажи"
WHERE file.ext = "md" AND type = "Персонаж" 
  AND contains(tags, "второстепенный")
  AND file.name != this.file.name
SORT file.name ASC
```

## Антагонисты

```dataview
TABLE WITHOUT ID 
  file.link AS "Персонаж",
  role AS "Роль",
  age AS "Возраст",
  occupation AS "Занятие"
FROM "Мои Проекты/Тонущий_мир/Персонажи"
WHERE file.ext = "md" AND type = "Персонаж" 
  AND contains(tags, "антагонист")
  AND file.name != this.file.name
SORT file.name ASC
```

## Все персонажи

```dataview
TABLE WITHOUT ID 
  file.link AS "Персонаж",
  role AS "Роль",
  age AS "Возраст",
  occupation AS "Занятие",
  tags AS "Теги"
FROM "Мои Проекты/Тонущий_мир/Персонажи"
WHERE file.ext = "md" AND type = "Персонаж" 
  AND file.name != this.file.name
SORT file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
