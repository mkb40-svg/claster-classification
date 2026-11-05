# Классификация и кластеризация текстов / Matnlarni tasniflash va klasterlash

15 тем на двух языках (русский, oʻzbekcha). К каждой теме: интерактивная лаборатория (работает в браузере) и практикум в Google Colab.
Ikki tilda 15 mavzu. Har bir mavzuga: interaktiv laboratoriya (brauzerda ishlaydi) va Google Colab da amaliyot.

## Структура / Tuzilma

```
index.html            выбор языка / til tanlash
ru/  uz/
  index.html          оглавление курса / kurs mundarijasi
  labs/*.html         лаборатории / laboratoriyalar
  notebooks/*.ipynb   практикумы для Colab / Colab amaliyotlari
```

## Публикация на GitHub Pages / GitHub Pages ga joylash

1. Загрузите содержимое папки в корень репозитория (ветка `main`). Файлы прошлой версии (`labs/`, `notebooks/`) удалите.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
3. Через 1–2 минуты сайт откроется по адресу `https://<пользователь>.github.io/<репозиторий>/`. Репозиторий должен быть публичным (Public), иначе Colab не откроет ноутбуки.
4. Ссылки «Практикум в Colab» на странице оглавления подставляются автоматически.

### Если папки не загружаются через сайт GitHub / Agar GitHub saytida papkalar yuklanmasa

Загрузите в корень репозитория сам файл `ml-text-labs.zip`, затем создайте файл `.github/workflows/unzip.yml` (в поле имени файла введите путь целиком) с таким содержимым и запустите его во вкладке Actions → «Unpack site» → Run workflow:

```yaml
name: Unpack site
on:
  workflow_dispatch:
permissions:
  contents: write
jobs:
  unpack:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Unpack
        run: |
          unzip -o ml-text-labs.zip
          rm -rf labs notebooks ru uz index.html
          cp -r ml-text-labs/. .
          rm -rf ml-text-labs ml-text-labs.zip
      - name: Commit
        run: |
          git config user.name "github-actions"
          git config user.email "github-actions@users.noreply.github.com"
          git add -A
          git commit -m "Unpack site"
          git push
```

## Практикумы в Colab / Colab amaliyotlari

Откройте `.ipynb` кнопкой со страницы курса или через Colab: «Файл → Открыть блокнот → GitHub». Каждый ноутбук самодостаточен: первая ячейка создаёт учебный корпус и вспомогательные функции. Запускайте ячейки сверху вниз. Корпуса учебные (шаблонные); для реальной работы замените их своими данными (в ноутбуках указано как).
Har bir daftar oʻz-oʻzidan yetarli: birinchi katak oʻquv korpusi va yordamchi funksiyalarni yaratadi. Kataklarni yuqoridan pastga ishga tushiring.

## Замечание о переводе / Tarjima haqida

Узбекские тексты (латиница, официальная орфография) выполнены автором комплекта; профессиональную терминологию рекомендуется проверить у преподавателя-носителя языка.
