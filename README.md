
![image](https://github.com/user-attachments/assets/85cddc52-4468-4d13-98d9-3da233acac5d)
![image](https://github.com/user-attachments/assets/654e4f8e-e9e5-4ad6-b5aa-ea6b4284f1e5)
![image](https://github.com/user-attachments/assets/a7880e66-9335-46b6-98a7-e28d8e73417e)



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

