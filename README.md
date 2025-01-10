![image](https://github.com/user-attachments/assets/0d49e8a9-9b61-44cb-92ba-489b2c2807d6)

grep [OPTION...] PATTERNS [FILE...]

Команда ищет "pattern" в указанном файле и выводит все совпадающие строки.

```
grep "pattern" ./file.txt
```

Отображение номеров строк в которых есть pattern (-n):

```
grep -n "pattern" logfile.txt
```
![image](https://github.com/user-attachments/assets/aa1ec7c9-ec0a-492f-8c04-9649e1caddf3)

Выводит строки, не содержащие "debug". 

```
grep -v "debug" logfile.txt
```

Выводит количество совпадающих строк вместо самих строк.

```
grep -c "error" logfile.txt
```

Поиск без учета регистра (-i):

```
grep -i "error" logfile.txt
```

Поиск строки с "error" или "warning".

```
grep -E "error|warning" logfile.txt
```

- `^pattern`: Ищет строки, начинающиеся с "pattern"
- `pattern$`: Ищет строки, заканчивающиеся на "pattern"
- `[abc]`: Ищет любой из символов a, b или c
- `.*`: Ищет любое количество любых символов

Рекурсивный поиск во всех файлах директории и поддиректорий:

```
grep -r "error" /var/log
```

Исключение файлов или директорий из поиска:

```
grep -r --exclude="*.log" "error" /var/log
grep -r --exclude-dir="backup" "error" /var/log
```
