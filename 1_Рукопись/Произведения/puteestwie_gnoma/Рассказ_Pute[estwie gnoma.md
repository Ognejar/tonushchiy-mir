---
    title: "Pute[estwie gnoma"
    type: произведение
    subtype: "Рассказ"
    epoch: "эпоха ранней Республики"
    year: 120
    context: "ddddddddddddddddd"
    created: 2025-09-01
    status: в_работе
    ---
    
    # Pute[estwie gnoma
    
    ## Тип
    Рассказ
    
    ## Описание
    aaaaaaaaaaa
    
    ## Эпоха
    - **Название:** эпоха ранней Республики
    - **Год:** 120
    - **Период:** 38 - 500
    
    ## Контекст
    ddddddddddddddddd
    
    ## Структура
    
    ### Главы
    ```dataview
    TABLE title, chapter, status
    FROM "1_Рукопись/Произведения/puteestwie_gnoma/Главы"
    SORT chapter ASC
    ```
    
    ### Сцены
    ```dataview
    TABLE title, chapter, location
    FROM "1_Рукопись/Произведения/puteestwie_gnoma/Сцены"
    SORT chapter ASC, file.ctime ASC
    ```
    
    ### Персонажи
    ```dataview
    TABLE name, role, location
    FROM "1_Рукопись/Произведения/puteestwie_gnoma/Персонажи"
    SORT name ASC
    ```
    
    ## Заметки
    ```dataview
    TABLE title, created
    FROM "1_Рукопись/Произведения/puteestwie_gnoma/Заметки"
    SORT file.ctime DESC
    ```
