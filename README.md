# Виртуальные лаборатории по компьютерной лингвистике / Kompyuter lingvistikasi boʻyicha virtual laboratoriyalar

Два курса на двух языках (русский, oʻzbekcha). В каждой теме есть интерактивная лаборатория (работает в браузере) и практикум в Google Colab.
Ikki kurs, ikki tilda. Har bir mavzuda interaktiv laboratoriya (brauzerda ishlaydi) va Google Colab da amaliyot bor.

| Курс / Kurs | Тем / Mavzu | ru | uz |
|---|---|---|---|
| Классификация и кластеризация текстов / Matnlarni tasniflash va klasterlash | 15 | `ru/ml-text/` | `uz/ml-text/` |
| Алгоритмы NLP / NLP algoritmlari | 18 | `ru/nlp/` | `uz/nlp/` |

## Структура / Tuzilma

```
index.html                  выбор языка / til tanlash
ru/  uz/
  index.html                выбор курса / kurs tanlash
  ml-text/  nlp/
    index.html              оглавление курса / kurs mundarijasi
    labs/*.html             лаборатории / laboratoriyalar
    notebooks/*.ipynb       практикумы для Colab / Colab amaliyotlari
```

## Публикация на GitHub Pages / GitHub Pages ga joylash

1. Загрузите содержимое папки в корень репозитория (ветка `main`). Если в репозитории остались файлы прошлой версии (`labs/`, `notebooks/`), удалите их.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
3. Через 1–2 минуты сайт откроется по адресу `https://<пользователь>.github.io/<репозиторий>/`. Репозиторий должен быть публичным (Public), иначе Colab не откроет ноутбуки.
4. Ссылки «Практикум в Colab» на страницах оглавления подставляются автоматически (ветка `main`).

## Практикумы в Colab / Colab amaliyotlari

Откройте нужный `.ipynb` кнопкой со страницы курса или через Colab: «Файл → Открыть блокнот → GitHub». Каждый ноутбук самодостаточен: первая ячейка создаёт файл с учебным корпусом и функциями, ячейка с `!pip install` ставит недостающие библиотеки. Запускайте ячейки сверху вниз.

- Корпуса учебные и шаблонные (русский с падежами, узбекский с цепочками суффиксов). Для реальной работы замените их своими данными.
- Необязательные блоки (`transformers`, `sentence-transformers`) требуют интернета и загрузки моделей; без них ноутбук выполняется и пропускает эти блоки.
- Все ноутбуки выполнены автоматически в тестовой среде (scikit-learn 1.8, Python 3.12); необязательные блоки с моделями в ней не запускались.

## Замечание о переводе / Tarjima haqida

Узбекские тексты (латиница, официальная орфография) выполнены автором комплекта; профессиональную терминологию рекомендуется проверить у преподавателя-носителя языка. Правки вносятся прямо в HTML и ноутбуки.
