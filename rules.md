Клонирование репозитория (второй разработчик)
После принятия приглашения:
​

bash
# 1. Перейдите в папку для проектов
cd C:\Users\ВашеИмя\Documents\projects

# 2. Клонируйте репозиторий (замените YOUR_USERNAME)
git clone https://github.com/YOUR_USERNAME/ai-crm-monorepo.git

# 3. Перейдите в папку проекта
cd ai-crm-monorepo

# 4. Откройте в VS Code
code .

# 5. Установите зависимости
pnpm install
Часть 7: Рабочий процесс для двух разработчиков
Базовый workflow (используйте каждый день)
Перед началом работы (ВСЕГДА!):

bash
# 1. Убедитесь что вы на main ветке
git checkout main

# 2. Получите последние изменения от коллеги
git pull

# 3. Создайте новую ветку для вашей задачи
git checkout -b feature/online-booking
# или
git checkout -b fix/calendar-bug
Именование веток:

feature/название — новая функциональность

fix/название — исправление бага

refactor/название — рефакторинг кода

Во время работы:

bash
# Периодически сохраняйте прогресс
git add .
git commit -m "Add booking calendar component"

# Можно делать несколько коммитов
git add packages/db/prisma/schema.prisma
git commit -m "Add Appointment model to database schema"
После завершения задачи:

bash
# 1. Убедитесь что все изменения закоммичены
git status

# 2. Отправьте ветку на GitHub
git push origin feature/online-booking
Создание Pull Request
​
​
Откройте репозиторий на GitHub

Вверху появится жёлтый баннер "Compare & pull request" — нажмите

Заполните:

Title: "Добавлена система онлайн-записи"

Description: что сделано, какие файлы изменены

В правом меню Reviewers выберите коллегу

Нажмите "Create pull request"

Ревью кода (второй разработчик)
Откройте Pull Request на GitHub

Просмотрите изменения во вкладке Files changed

Можно оставить комментарии к строкам кода

Если всё ОК → нажмите Merge pull request → Confirm merge

Удалите ветку после мерджа (GitHub предложит сам)

Получение изменений после мерджа
bash
# 1. Вернитесь на main
git checkout main

# 2. Получите обновления
git pull

# 3. Удалите старую локальную ветку (опционально)
git branch -d feature/online-booking
Часть 8: Полезные команды для совместной работы
bash
# Посмотреть статус (какие файлы изменены)
git status

# Посмотреть историю коммитов
git log --oneline --graph

# Посмотреть изменения в файлах
git diff

# Отменить изменения в файле (ДО commit)
git checkout -- имя_файла

# Посмотреть все ветки
git branch -a

# Переключиться на ветку коллеги (для проверки его кода)
git checkout feature/ai-assistant

# Вернуться на свою ветку
git checkout main

# Если забыли git pull и уже начали работать
git stash                    # Спрячьте изменения
git pull                     # Получите обновления
git stash pop                # Верните свои изменения
Часть 9: Решение конфликтов
Если вы и коллега редактировали одни и те же файлы:
​

bash
git pull
# Git сообщит о конфликте
Откройте файл с конфликтом в VS Code

Увидите метки:

text
<<<<<<< HEAD
ваш код
=======
код коллеги
>>>>>>> branch-name
VS Code покажет кнопки: Accept Current Change / Accept Incoming Change / Accept Both

Выберите нужное, удалите метки

Сохраните файл

Закоммитьте:

bash
git add .
git commit -m "Resolve merge conflict in schema.prisma"
git push
Часть 10: Правила хорошего тона
Коммитьте часто — маленькие коммиты лучше одного большого
​

Pull каждое утро — чтобы работать с актуальным кодом

Пишите понятные commit messages:

✅ "Add Telegram notification service"

❌ "fix", "update", "changes"

Не коммитьте .env файлы — они уже в .gitignore

Делайте code review — это помогает учиться друг у друга

Общайтесь — если меняете что-то важное, предупредите коллегу

Быстрый чеклист на каждый день
Начало работы:

bash
git checkout main
git pull
git checkout -b feature/my-task
Конец работы:

bash
git add .
git commit -m "Описание что сделано"
git push origin feature/my-task
# → Создать Pull Request на GitHub