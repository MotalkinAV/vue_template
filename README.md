# Шаблон структуры проекта на VUE3 + VITE

## Установка
```
npm install
```

### Режим разработки
```
npm run dev
```

### Сборка проекта (+ CSS)
```
npm run build
```

### Сборка CSS
```
npm run sass
```

## Структура проекта
---
- [`src/`](#src/)  
  - [`assets/`](#assets/)  
  - [`components/`](#components/)  
  - [`directives/`](#directives/)   
  - [`layouts/`](#layouts/)  
  - [`composables/`](#composables/) 
  - [`config/`](#config/)   
  - [`router/`](#router/)  
  - [`services/`](#services/)
  - [`store/`](#store/)  
  - [`utils/`](#utils/)  
  - [`views/`](#views/)  
- [`.env`](#.env)
---
### `src/`
Папка `src` является центральной частью структуры проекта, содержащей исходный код приложения. Эта директория включает в себя компоненты, страницы, стили, изображения и другие активы и модули, необходимые для работы приложения.

---
### `assets/`
Папка `assets` используется для хранения статических ресурсов приложения, таких как изображения, стили (CSS или препроцессоры, такие как SASS/SCSS, LESS), шрифты и другие файлы, которые требуются для визуального оформления и функциональности приложения.
### Пример структуры папки:
```
src/
|-- assets/
    |-- images/         // Изображения, используемые в приложении
        |-- logo.png
        |-- icons/
            |-- close.svg
            |-- menu.svg
    |-- styles/         // Стилевые файлы (CSS, SASS/SCSS, LESS)
        |-- main.scss
        |-- _variables.scss
        |-- _mixins.scss
    |-- fonts/          // Шрифты
        |-- OpenSans-Regular.ttf
        |-- OpenSans-Bold.ttf
```
---
### `components/`
Папка `components` предназначенная для хранения и организации компонентов. В простейшем случае компоненты могут быть организованы напрямую в папке components, но по мере роста приложения рекомендуется внедрять дополнительную структурированность, например, разделяя компоненты по функциональности или области применения.
### Пример структуры папки:
```
src/
|-- components/
    |-- ui/               // Общие компоненты, используемые во всем приложении
        |-- Button.vue
        |-- TextInput.vue
    |-- layout/               // Компоненты макета, такие как шапки, подвалы и навигационные панели
        |-- Header.vue
        |-- Footer.vue
        |-- Sidebar.vue
    |-- icons/                // Специфические иконки или маленькие компоненты, используемые как части других компонентов
        |-- CloseIcon.vue
        |-- MenuIcon.vue
```
---
### `directives/`
Папка `directives` используется для организации пользовательских директив.  Директивы могут быть зарегистрированы глобально в главном файле приложения (например, в main.js или app.js) или локально в компонентах, где они используются. Организация директив в отдельных файлах и их явная регистрация делает код более модульным и удобным для понимания и поддержки.
### Пример структуры папки:
```
src/
|-- directives/
    |-- focus.js          // Директива для автоматического фокусирования на элементе
    |-- highlight.js      // Директива для выделения текста элемента
    |-- lazyload.js       // Директива для ленивой загрузки изображений
    |-- click-outside.js  // Директива для обработки кликов вне элемента
    |-- scroll-lock.js    // Директива для блокировки прокрутки страницы
```
---
### `layouts/`
Папка `layouts` предназначена для хранения компонентов макетов (шаблонов), которые определяют общую структуру страницы или группы страниц в приложении. Макеты обычно содержат разметку и компоненты, которые являются общими для нескольких страниц, такие как шапка, навигационное меню, подвал и т.д. Использование макетов позволяет избежать дублирования кода, облегчает поддержку и обновление приложения.
### Пример структуры папки:
```
src/
|-- layouts/
    |-- default.vue      // Основной макет, используемый для большинства страниц
    |-- admin.vue        // Макет для административного раздела
    |-- auth.vue         // Макет для страниц аутентификации
```
---
### `composables/`
Папка `composables` используется для хранения и организации внешних плагинов и пользовательских добавлений, которые расширяют базовый функционал фреймворка. Плагины могут включать в себя библиотеки сторонних разработчиков а также пользовательские плагины. Плагины регистрируются в главном файле приложения (main.js или main.ts), где Vue инстанс инициализируется и монтируется. Для использования плагина его необходимо импортировать и затем использовать с помощью метода .use() Vue инстанса.
### Пример структуры папки:
```
src/
|-- composables/
    |-- I18n.js         // Плагин интернационализации
    |-- my-plugin.js    // Пример пользовательского плагина
```
---
### `config/`
Папка `config` используется для хранения конфигураций приложения.
### Пример структуры папки:
```
src/
|-- config/
    |-- myCfg.js        // Файл конфигурации
```
---
### `router/`
Папка `router` содержит всю конфигурацию маршрутов и настройки маршрутизатора, определяя, как приложение отвечает на различные пути URL. Обычно содержит один файл конфигурации, например index.js или routes.js, где находится вся логика маршрутизации. В более крупных проектах, конфигурация может быть разделена на несколько файлов или директорий для улучшения управляемости и организации.
### Пример структуры папки:
```
src/
|-- router/
    |-- index.js // Файл конфигурации

    // В крупных проектах можно добавить:
    |-- routes.js // Файл конфигурации
    |-- adminRoutes.js // Настройка роутов администратора
    |-- userRoutes.js // Настройка роутов пользователя
```

---
### `services/`
Папка `services` обычно содержит файлы и подпапки, которые организуют логику взаимодействия приложения с различными внешними интерфейсами. Вот несколько примеров того, что может быть включено в эту директорию:

- API вызовы: Функции для выполнения HTTP запросов к внешним API, такие как получение, создание, обновление или удаление данных.
- Утилиты для работы с API: Функции-хелперы для обработки запросов и ответов, включая обработку ошибок, форматирование данных и пр.
- Аутентификация и авторизация: Сервисы, отвечающие за управление сессиями пользователей, включая логин, логаут, обновление токенов и проверку прав доступа.
- Веб-сокеты: Управление веб-сокет соединениями для реализации функционала реалтаймовых обновлений.
- Интеграция с внешними SDK: Код, необходимый для интеграции с SDK сторонних сервисов, например, платежных систем или аналитики.
### Пример структуры папки:
```
src/
|-- services/
    |-- apiClient.js // Настройка и экспорт настроенного HTTP клиента (напр., axios)
    |-- authService.js // Функции для аутентификации и управления сессиями пользователя
    |-- userService.js // API вызовы, связанные с пользователями
    |-- taskService.js // API вызовы для управления задачами
```
---
### `store/`
Папка `store` содержит в себе файлы управления глобальным состоянием. Это централизованное хранилище для всех компонентов в приложении, которое позволяет делиться состоянием (данными) между компонентами без необходимости пропускать их через родительские или дочерние компоненты.
### Пример структуры папки:
```
src/
|-- store/
    |-- index.js            // Основной файл, где создается экземпляр Pinia и экспортируется
    |-- userStore.js        // Хранилище для пользовательских данных
    |-- cartStore.js        // Хранилище для данных корзины покупок
```
---
### `utils/`
Папка `utils` предназначена для хранения вспомогательных функций и утилит, которые предоставляют общие или повторно используемые решения для различных задач в приложении. Эти утилиты могут включать функции для работы с датами, строками, числами, трансформаций данных, валидации и многого другого.

- Функции форматирования: Например, функции для форматирования чисел, дат, текста и т.д.
- Функции валидации: Код для проверки корректности данных, например, электронных адресов, номеров телефонов, идентификаторов и других пользовательских данных.
- Утилиты для работы с массивами и объектами: Функции для упрощения и унификации операций над структурами данных, такими как фильтрация, сортировка, поиск и преобразование.
- Полифиллы и кросс-браузерные решения: Код, обеспечивающий совместимость функциональности между разными браузерами.
- Утилиты для работы с URL и параметрами запроса: Функции для анализа и конструирования URL-адресов, а также для работы с параметрами запроса.
- Утилиты асинхронной логики: Например, функции для управления асинхронными операциями, включая обработку промисов и асинхронно/ожидаемые функции.
### Пример структуры папки:
```
src/
|-- utils/
    |-- format.js // Функции форматирования
    |-- validate.js // Функции валидации
    |-- arrayHelpers.js // Утилиты для работы с массивами
    |-- objectHelpers.js // Утилиты для работы с объектами
    |-- polyfills.js // Полифиллы
    |-- urlUtils.js // Утилиты для работы с URL
```

---
### `views/`
Папка `views` используется для хранения компонентов, которые представляют собой страницы приложения. Эти компоненты обычно являются "контейнерами" или "корневыми компонентами", которые связаны с маршрутами в приложении через Vue Router. Структура с использованием папки views помогает разделять логику приложения на логические разделы и облегчает понимание того, какие компоненты являются страницами, доступными для пользователя.
### Пример структуры папки:
```
src/
|-- views/
    |-- HomePage.vue       // Компонент для главной страницы
    |-- AboutPage.vue      // Компонент для страницы "О нас"
    |-- ContactPage.vue    // Компонент для страницы контактов
```

---
### `.env`
### Пример кода
Пример .env переменной:
```
VITE_URL=https://example.com
```

Переменные импортируются при помощи:
```
import.meta.env.VITE_URL
```
---