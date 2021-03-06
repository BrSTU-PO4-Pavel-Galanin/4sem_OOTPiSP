## README

- [English](README.md)
- [Русский](README-ru.md)

## Дерево проекта

```
.
|-- docker-compose.yml  # Конфигурация Docker-compose
|-- LICENSE             # Лицензия репозитория
|-- README*.md          # Файл информации о репозитории
|-- rep                 # Папка с отчётом
|   |-- a               # Папка с готовым "Приложением А"
|   |   |-- a.pdf       # Скомпилированное "Приложение А" в *.pdf
|   |   `-- a.tex       # Исходный код "Приложение A" в *.tex
|   |-- b               # Папка с готовым "Приложением Б"
|   |   |-- b.pdf       # Скомпилированное "Приложение Б" в *.pdf
|   |   `-- b.tex       # Исходный код "Приложения Б" в *.tex
|   |-- _INCLUDES       # Папка с исходными кодами *.tex, которые подключаются
|   |   `-- *           # Любая вложеность папок
|   |       `-- *.tex   # Исходный код *.tex, которые подключаются
|   |-- main            # Папка с готовой "Пояснительной запиской"
|   |   |-- main.pdf    # Скомпилированная "Пояснительная записка" в *.pdf
|   |   `-- main.tex    # Исходный код "Пояснительной записки" в *.tex
|   `-- _STYLES         # Папка со стилями LaTeX *.sty
|       `-- *.sty       # LaTeX styles
`-- src                 # Source code folder
```

## Компиляция PDF

Должен быть установлен Docker.

Запускаем виртуальную машину Docker через `docker-compose.yml`:

```bash
sudo docker-compose run latex /bin/bash
```

Как запустилась виртуальная машина, переходим в директорию с `main.tex` (или `a.tex`, или `b.tex`) файлом:

```bash
cd /content/rep/main
# cd /content/rep/a
# cd /content/rep/b
```

Компилируем файл `main.tex` (или `a.tex`, или `b.tex`):

```bash
pdflatex main.tex
# pdflatex a.tex
# pdflatex b.tex
```

Второй раз компилируем файл `main.tex` (или `a.tex`, или `b.tex`), чтобы корректно работали ссылки в документе.

```bash
pdflatex main.tex
# pdflatex a.tex
# pdflatex b.tex
```

Скомпилированный файл `main.pdf` в папке `rep/main` вместе с `main.tex` файлом.

Скомпилированный файл `a.pdf` в папке `rep/a` вместе с `a.tex` файлом.

Скомпилированный файл `b.pdf` в папке `rep/b` вместе с `b.tex` файлом.
