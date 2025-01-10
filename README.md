![image](https://github.com/user-attachments/assets/0d49e8a9-9b61-44cb-92ba-489b2c2807d6)

> **grep [OPTION...] PATTERNS [FILE...]**
>
> 



_Команда ищет "pattern" в указанном файле и выводит все совпадающие строки._

```
grep "pattern" ./file.txt
```

_Отображение номеров строк в которых есть pattern (-n)_

```
grep -n "pattern" logfile.txt
```
![image](https://github.com/user-attachments/assets/aa1ec7c9-ec0a-492f-8c04-9649e1caddf3)

_Выводит строки, не содержащие "debug"_

```
grep -v "debug" logfile.txt
```

_Выводит количество совпадающих строк вместо самих строк_

```
grep -c "error" logfile.txt
```

_Поиск без учета регистра (-i)_

```
grep -i "error" logfile.txt
```

_Поиск строки с "error" или "warning"_

```
grep -E "error|warning" logfile.txt
```

- `^pattern`: ищет строки, начинающиеся с "pattern"
- `pattern$`: ищет строки, заканчивающиеся на "pattern"
- `[abc]`: ищет любой из символов a, b или c
- `.*`: ищет любое количество любых символов

_Рекурсивный поиск во всех файлах директории и поддиректорий_

```
grep -r "error" /var/log
```

_Исключение файлов или директорий из поиска_

```
# исключаем файл
grep -r --exclude="*.log" "error" /var/log

# исключаем директорию
grep -r --exclude-dir="backup" "error" /var/log
```

```gitattributes
# Apply override to all files in the directory
project-docs/* linguist-documentation
# Apply override to a specific file
docs/formatter.rb -linguist-documentation
# Apply override to all files and directories in the directory
ano-dir/** linguist-documentation
```


