## Посмотреть статус (какие файлы изменены)
```git status ```

## Посмотреть историю коммитов
```git log --oneline --graph```

## Посмотреть изменения в файлах
```git diff```

## Отменить изменения в файле (ДО commit)
```git checkout -- имя_файла```

## Посмотреть все ветки
```git branch -a```

## Переключиться на ветку коллеги (для проверки его кода)
``` git checkout feature/ai-assistant```

## Вернуться на свою ветку
```git checkout main```

## Если забыли git pull и уже начали работать
```
git stash                    # Спрячьте изменения
git pull                     # Получите обновления
git stash pop                # Верните свои изменения
```

## Коммиты:
```
git add .
git commit -m "Resolve merge conflict in schema.prisma"
git push
```
## Начало работы:

git checkout main
git pull
git checkout -b feature/my-task
```

## Конец работы:
```
git add .
git commit -m "Описание что сделано"
git push origin feature/my-task
```