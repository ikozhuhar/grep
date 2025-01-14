<p align="center">
<img src="https://github.com/ikozhuhar/grep/blob/main/img/grep.jpeg
 </p>
![image](https://github.com/user-attachments/assets/5a9085de-ab73-44db-bd6a-75a34b54fe5b)

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

- `^pattern`: _ищет строки, начинающиеся с "pattern"_
- `pattern$`: _ищет строки, заканчивающиеся на "pattern"_
- `[abc]`: _ищет любой из символов a, b или c_
- `.*`: _ищет любое количество любых символов_

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

_Игнорируем бинарники_

```ruby
grep --binary-files=without-match "pattern" directory
```

_Даже если файл с бинарными заголовками, grep будет работать как часы_

```ruby
grep -a "pattern" binaryfile
```

_Получишь только первые 5 совпадений_

```ruby
grep -m 5 "error" logfile.txt
```

_Найденные совпадения будут подсвечены. Красиво и функционально_

```ruby
grep --color=auto "pattern" file
```

_Эта команда игнорирует бинарники, подсвечивает результаты и выдаёт только первые 10 совпадений_

```ruby
grep --binary-files=without-match --color=auto -m 10 "error" /var/log/*
```

_Ищем ошибки прямо в сжатых логах. Экономия места и времени_

```ruby
zgrep "error" logfile.gz
```

_Обработка потоков на лету_

```ruby
cat file | grep "pattern"
```

_Ищем текст даже там, где его не должно быть_

```ruby
grep --text "pattern" binaryfile
```

_Найдёт все определения функций в Python-файлах с номерами строк_

```ruby
grep -n "function" *.py
```

_Найдёт все .txt файлы и прочешет их на наличие "pattern"_

```ruby
find /path -type f -name "*.txt" -exec grep "pattern" {} \;
```

_Выбирает второе поле из строк, содержащих "pattern"_

```ruby
grep "pattern" file | awk '{print $2}'
```

_Находит строки с "pattern" и заменяет "old" на "new"_

```ruby
grep "pattern" file | sed 's/old/new/g'
```

_Находит файлы с "pattern" и удаляет их_

```ruby
grep -l "pattern" * | xargs rm
```

_Эта команда найдёт все уникальные файлы с "TODO" в текущей директории и ниже_

```ruby
find . -type f | xargs grep "TODO" | awk '{print $1}' | sort | uniq
```

_Мгновенно выявляем проблемы в системе_

```ruby
grep "ERROR" /var/log/syslog
```

_Быстро находим определения функций в Python-файлах_

```ruby
grep "def " *.py
```

_Вытаскиваем строки с ключевым словом из CSV-файла_

```ruby
grep "keyword" dataset.csv
```

_Эта команда найдет все уникальные ошибки в логах, отсортирует их по частоте_

```ruby
grep "ERROR" /var/log/* | sort | uniq -c | sort -nr
```


