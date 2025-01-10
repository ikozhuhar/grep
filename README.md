
![image](https://github.com/user-attachments/assets/85cddc52-4468-4d13-98d9-3da233acac5d)

Эта команда ищет "pattern" в указанном файле и выводит все совпадающие строки.

```
grep "pattern" ./file.txt
```

Отображение номеров строк в которых есть pattern (-n):

```
grep -n "pattern" logfile.txt
```
Пример:

![image](https://github.com/user-attachments/assets/aa1ec7c9-ec0a-492f-8c04-9649e1caddf3)

Выводит строки, не содержащие "debug". 

```
grep -v "debug" logfile.txt
```

Выводит количество совпадающих строк вместо самих строк.

```
grep -c "error" logfile.txt
```

