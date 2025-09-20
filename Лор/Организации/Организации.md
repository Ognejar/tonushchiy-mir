# Организации

<div class="button-row">

```button
name 🏛️ Создать организацию
data-tooltip Создать новую организацию
type command
action Literary Templates: Создать организацию
```

</div>

Обзор всех организаций проекта.

## Все организации

```dataview
TABLE WITHOUT ID 
  file.link AS "Организация",
  type AS "Тип",
  purpose AS "Цель",
  size AS "Размер",
  influence AS "Влияние",
  headquarters AS "Штаб-квартира"
FROM "Мои Проекты/Тонущий_мир/Организации"
WHERE file.ext = "md" AND (contains(file.tags, "организация") OR contains(file.tags, "organization"))
SORT file.name ASC
```

## Организации по типу

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Организация",
  key AS "Тип",
  r.purpose AS "Цель",
  r.size AS "Размер",
  r.influence AS "Влияние"
FROM "Мои Проекты/Тонущий_мир/Организации"
WHERE (contains(file.tags, "организация") OR contains(file.tags, "organization"))
GROUP BY type
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

## Организации по влиянию

```dataview
TABLE WITHOUT ID 
  r.file.link AS "Организация",
  key AS "Влияние",
  r.type AS "Тип",
  r.purpose AS "Цель",
  r.size AS "Размер"
FROM "Мои Проекты/Тонущий_мир/Организации"
WHERE (contains(file.tags, "организация") OR contains(file.tags, "organization"))
GROUP BY influence
FLATTEN rows AS r
SORT key ASC, r.file.name ASC
```

---
*Этот файл создан автоматически при создании мира*
