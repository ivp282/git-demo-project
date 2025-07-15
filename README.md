# Git Demo Project

## Цель работы

Создание базового репозитория, работа с ветками, коммитами и удалённым сервером.

## Ход работы

### 1. Установка и настройка Git

Устанавливаем Git и проверяем версию:
```bash
git --version
```

Настраиваем имя пользователя и почту:
```bash
git config --global user.name "Igor Popkov"
git config --global user.email "ivp282@gmail.com"
```

### 2. Создание локального репозитория

Создаем папку проекта и инициализируем репозиторий:
```bash
mkdir git-demo-project && cd git-demo-project
git init
```

Создаем базовую структуру проекта:
```bash
mkdir src test docs
echo "# Git Demo Project" > README.md
echo "*.pyc
__pycache__/" > .gitignore
```

### 3. Работа с коммитами

Добавляем файлы в индекс и создаем первый коммит:
```bash
git add .
git commit -m "Initial commit: структура проекта, README, .gitignore"
```

Проверяем историю коммитов:
```bash
git log --oneline
```

### 4. Работа с ветками

Создаем новую ветку и переходим в нее:
```bash
git branch feature/login
git checkout feature/login
```

Добавляем файл и коммитим изменения:
```bash
echo "# login logic" > src/login.py
git add src/login.py
git commit -m "Добавлен модуль login"
```

### 5. Слияние веток

Возвращаемся в ветку `master` и объединяем изменения:
```bash
git checkout master
git merge feature/login
```

При возникновении конфликта — разрешаем его вручную, затем:
```bash
git add <файл>
git commit -m "Решён конфликт при слиянии feature/login"
```

### 6. Работа с удаленным репозиторием

Добавляем удалённый репозиторий:
```bash
git remote add origin https://github.com/ivp282/git-demo-project.git
git push -u origin master
```

### 7. Дополнительные задания

Создаем тег:
```bash
git tag v1.0
git push origin v1.0
```

Добавляем временный файл и коммитим:
```bash
echo "temp" > temp.txt
git add temp.txt
git commit -m "Временный файл"
```

Откатываем коммит полностью:
```bash
git reset --hard HEAD~1
```

Создаем ошибочный файл и делаем откат с сохранением истории:
```bash
echo "ошибочный файл" > bad.txt
git add bad.txt
git commit -m "Добавлен ошибочный файл"
git revert HEAD
```

Проверяем историю:
```bash
git log --oneline
```

## Вывод

Создан локальный и удалённый Git-репозиторий. Освоены основные операции: создание, слияние веток, откат изменений и работа с удалённым сервером.

## Ссылка на репозиторий

[ivp282/git-demo-project: A training repository for learning Git and GitHub](https://github.com/ivp282/git-demo-project)
