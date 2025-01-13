![image](https://github.com/user-attachments/assets/0d49e8a9-9b61-44cb-92ba-489b2c2807d6)

<br/>
 
#### _Использование: grep [ПАРАМЕТР]… ШАБЛОНЫ [ФАЙЛ]…_

<br/>

_Команда ищет "pattern" в указанном файле и выводит все совпадающие строки._

```ruby
grep "pattern" ./file.txt
```

_Отображение номеров строк в которых есть pattern (-n)_

```ruby
grep -n "pattern" logfile.txt
```
![image](https://github.com/user-attachments/assets/aa1ec7c9-ec0a-492f-8c04-9649e1caddf3)

_Выводит строки, не содержащие "debug"_

```ruby
grep -v "debug" logfile.txt
```

_Выводит количество совпадающих строк вместо самих строк_

```ruby
grep -c "pattern" logfile.txt
```

_Поиск без учета регистра (-i)_

```ruby
grep -i "pattern" logfile.txt
```

_Поиск строки с "pattern" или "warning"_

```ruby
grep -E "error|warning" logfile.txt
```

- `^pattern`: ищет строки, начинающиеся с "pattern"
- `pattern$`: ищет строки, заканчивающиеся на "pattern"
- `[abc]`: ищет любой из символов a, b или c
- `.*`: ищет любое количество любых символов

_Рекурсивный поиск во всех файлах директории и поддиректорий_

```ruby
grep -r "error" /var/log
```

_Исключение файлов или директорий из поиска_

```ruby
# исключаем файл
grep -r --exclude="*.log" "error" /var/log

# исключаем директорию
grep -r --exclude-dir="backup" "error" /var/log
```

Игнорируем бинарники

```ruby
grep --binary-files=without-match "pattern" directory
```

Даже если файл с бинарными заголовками, grep будет работать как часы

```ruby
grep -a "pattern" binaryfile
```

Получишь только первые 5 совпадений

```ruby
grep -m 5 "error" logfile.txt
```

Найденные совпадения будут подсвечены. Красиво и функционально

```ruby
grep --color=auto "pattern" file
```

Эта команда игнорирует бинарники, подсвечивает результаты и выдаёт только первые 10 совпадений

```ruby
grep --binary-files=without-match --color=auto -m 10 "error" /var/log/*
```

Ищем ошибки прямо в сжатых логах. Экономия места и времени

```ruby
zgrep "error" logfile.gz
```

Обработка потоков на лету

```ruby
cat file | grep "pattern"
```

Ищем текст даже там, где его не должно быть

```ruby
grep --text "pattern" binaryfile
```

Найдёт все определения функций в Python-файлах с номерами строк

```ruby
grep -n "function" *.py
```

Найдёт все .txt файлы и прочешет их на наличие "pattern"

```ruby
find /path -type f -name "*.txt" -exec grep "pattern" {} \;
```

Выбирает второе поле из строк, содержащих "pattern"

```ruby
grep "pattern" file | awk '{print $2}'
```

Находит строки с "pattern" и заменяет "old" на "new"

```ruby
grep "pattern" file | sed 's/old/new/g'
```

Находит файлы с "pattern" и удаляет их

```ruby
grep -l "pattern" * | xargs rm
```

Эта команда найдёт все уникальные файлы с "TODO" в текущей директории и ниже

```ruby
find . -type f | xargs grep "TODO" | awk '{print $1}' | sort | uniq


