Для получения детальной информации о процессах оболочки введём команды "cat /proc/$$/status | head -12" и 
"cat /proc/$$/cmdline | tr '\0' ' ' ; echo" (взяты из методички)

<img width="503" height="256" alt="image" src="https://github.com/user-attachments/assets/72b2715c-5f57-41dd-808c-dda7780d5049" />

Для удобство показа следующие команды изображены на одном скриншоте, а именно:
1) исполняемый файл
2) текущий каталог
3) открытые файлы

<img width="662" height="170" alt="image" src="https://github.com/user-attachments/assets/10cd5927-4876-4035-93a6-c0ec53558e20" />

Также проведём эксперимент для ответа на вопросы ниже

<img width="576" height="70" alt="image" src="https://github.com/user-attachments/assets/0f513f0a-84b5-4e57-a354-d81b402fdd29" />

Отвечая на вопрос, /proc/$$/cwd стал указывать на /home/ и имя пользователя(В моём случае linuxuset), так как cwd 
является ссылкой ядра на текущий каталог процесса, где cd его меняет.

/proc является интерфейсом ядра, а ps и top просто читают информацию и выводят в виде таблицы
