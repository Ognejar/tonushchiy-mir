---
created: "2025-01-27"
name: "Индекс алхимии"
type: "индекс"
tags: [магия, алхимия, индекс]
---

# Индекс алхимии

## Поиск по категориям

### Трансмутация
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "transmutation")
SORT file.name ASC
```

### Эликсиры
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "elixirs")
SORT file.name ASC
```

### Философский камень
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "philosophers_stone")
SORT file.name ASC
```

### Магические материалы
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "magical_materials")
SORT file.name ASC
```

### Лечебные составы
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "healing")
SORT file.name ASC
```

### Боевые смеси
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "combat")
SORT file.name ASC
```

### Ритуальные вещества
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "ritual")
SORT file.name ASC
```

## Поиск по сложности

### Рецепты для новичков (1-3 уровень)
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "новичок")
SORT file.name ASC
```

### Рецепты для учеников (4-6 уровень)
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "ученик")
SORT file.name ASC
```

### Рецепты для мастеров (7-9 уровень)
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "мастер")
SORT file.name ASC
```

### Рецепты для архимагов (10+ уровень)
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "архимаг")
SORT file.name ASC
```

## Поиск по доступности

### Общедоступные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "общедоступное")
SORT file.name ASC
```

### Гильдейские рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "гильдейское")
SORT file.name ASC
```

### Дворцовые рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "дворцовое")
SORT file.name ASC
```

### Запрещенные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "запрещенное")
SORT file.name ASC
```

### Утерянные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.tags, "утерянное")
SORT file.name ASC
```

## Поиск по создателям

### Рецепты с известными создателями
```dataview
LIST FROM #алхимия
WHERE file.frontmatter.creator AND file.frontmatter.creator != ""
SORT file.frontmatter.creator ASC
```

## Поиск по местам изучения

### Рецепты по местам изучения
```dataview
LIST FROM #алхимия
WHERE file.frontmatter.studyLocation AND file.frontmatter.studyLocation != ""
SORT file.frontmatter.studyLocation ASC
```

## Статистика

### Общее количество рецептов
```dataview
TABLE length(rows) as "Количество"
FROM #алхимия
```

### Рецепты по категориям
```dataview
TABLE length(rows) as "Количество"
FROM #алхимия
GROUP BY file.frontmatter.category
SORT length(rows) DESC
```

### Рецепты по сложности
```dataview
TABLE length(rows) as "Количество"
FROM #алхимия
GROUP BY file.frontmatter.difficulty
SORT length(rows) DESC
```

### Рецепты по доступности
```dataview
TABLE length(rows) as "Количество"
FROM #алхимия
GROUP BY file.frontmatter.availability
SORT length(rows) DESC
```

## Быстрый поиск

### Все рецепты (алфавитный порядок)
```dataview
LIST FROM #алхимия
SORT file.name ASC
```

### Недавно созданные рецепты
```dataview
LIST FROM #алхимия
SORT file.created DESC
LIMIT 10
```

### Рецепты без описания
```dataview
LIST FROM #алхимия
WHERE !file.frontmatter.description OR file.frontmatter.description == ""
```

### Рецепты без создателя
```dataview
LIST FROM #алхимия
WHERE !file.frontmatter.creator OR file.frontmatter.creator == ""
```

## Поиск по применению

### Экономически выгодные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.frontmatter.description, "золот") OR contains(file.frontmatter.description, "драгоцен") OR contains(file.frontmatter.description, "ценн")
SORT file.name ASC
```

### Опасные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.frontmatter.description, "опасн") OR contains(file.frontmatter.description, "риск") OR contains(file.frontmatter.description, "токсич")
SORT file.name ASC
```

### Лечебные рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.frontmatter.description, "лечен") OR contains(file.frontmatter.description, "исцел") OR contains(file.frontmatter.description, "лекар")
SORT file.name ASC
```

### Боевые рецепты
```dataview
LIST FROM #алхимия
WHERE contains(file.frontmatter.description, "боев") OR contains(file.frontmatter.description, "атака") OR contains(file.frontmatter.description, "оружие")
SORT file.name ASC
```

## Связи с другими системами

### Рецепты, использующие зелья
```dataview
LIST FROM #алхимия
WHERE contains(file.text, "зелье") OR contains(file.text, "зелья")
SORT file.name ASC
```

### Рецепты, создающие артефакты
```dataview
LIST FROM #алхимия
WHERE contains(file.text, "артефакт") OR contains(file.text, "устройство") OR contains(file.text, "прибор")
SORT file.name ASC
```

### Рецепты, требующие редкие материалы
```dataview
LIST FROM #алхимия
WHERE contains(file.text, "редк") OR contains(file.text, "драгоцен") OR contains(file.text, "древн")
SORT file.name ASC
``` 
