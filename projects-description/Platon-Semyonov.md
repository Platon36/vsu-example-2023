# Платон Семенов
---

## Описание предметной области

Админка онлайн бюро находок.

Мобильная версия админки бюро находок предоставляет возможность управления каталогом находок, включая их добавление, удаление, редактирование, а также просмотр, сортировку и фильтрацию. Будет содержать в себе функциональность, связанную с валидацией добавляемых и редактируемых находок.

### Стек

`TypeScript`, `React`, `Next.js`

---

## Описание страниц

* Главная страница — список находок
* Страница конкретной находки — содержит фото, описание, место, дату и время находки, категорию (одежда/аксессуар/техника/документ и т.д.).
* Страница редактирования описания находки:
  * Форма для редактирования с валидацией
  * Основные поля для редактирования, такие как название, описание, место, дату и время находки и тд
* Аналогично страница добавления новой находки
* Страница подтверждения удаления находки
* Кастомные страницы ошибок:
  * 404
  * 500

Для навигации будут использоваться таббар и кнопка назад

### Фильтрация

* Страница со списком находок
  * Дата и время находки
  * Место находки
  * Категория находки

### Сортировка

Для каждого параметра должна быть реализована сортировка по убыванию и возрастанию

* Страница со списком находок
  * По дате находки
  * По расстоянию от определенного места
  * По дате добавления

---

## Список API

Список очень приблизительный, детально проработаю его в процессе, сейчас планируется:

---

Эндпоинт: `/get-finds`

Используется для получения списка находок, с возможностью фильтрации и сортировки

Http метод: `GET`

Параметры:

* `page: number`
* `category: Category | undefined`
* `countPerPage: number | undefined`
* `orderBy: SortingKey | undefined`
* `filters: Filters | undefined`

---

Эндпоинт: `/update-find`

Позволяет обновить информацию о существующей находке

Http метод: `PATCH`

Параметры:

* Название
* Место
* Время
* Категория
* Описание

---

Эндпоинт: `/remove-find`

Предназначен для удаления находки из каталога

Http метод: `DELETE`

Параметры:

* id

---

Эндпоинт: `/add-find`

Позволяет добавить новую находку в каталог бюро

Http метод: `POST`

Параметры:

* Название
* Описание
* Место
* Время
* Категория

---

Эндпоинт: `/get-validation-schema`

Этот эндпоинт используется для получения схемы валидации форм для добавления и обновления игр

Http метод: `GET`

Параметры:

* `category: Category`

---
