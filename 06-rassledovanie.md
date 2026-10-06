Начнём с имитации заражения

<img width="543" height="100" alt="image" src="https://github.com/user-attachments/assets/f251ac0c-8f81-42d5-87f1-86b37523a859" />

Сделаем проверку 

<img width="460" height="19" alt="image" src="https://github.com/user-attachments/assets/77afba67-e8c4-4d06-83ed-9724a247359d" />

<img width="405" height="93" alt="image" src="https://github.com/user-attachments/assets/282f4fc2-0a75-4a26-8d53-c54a794945f8" />

Проверка прошла успешно, имитация заражения выполнена, так же команда на скриншоте 2 является началом "расследования", где мы видим подозрительные строчки, так как потоки ядра всегда находятся в квадратных скобках, строчки без них - являются самозванцем.

Продолжаем искать признаки, временный каталог

<img width="682" height="36" alt="image" src="https://github.com/user-attachments/assets/db86a1a8-5661-48a6-a26e-f3511596977e" />
/cwd указывает на /tmp - системные процесса так не запускаются.

Удалённый файл

<img width="739" height="36" alt="image" src="https://github.com/user-attachments/assets/9b7868b1-f661-4305-bc69-9ffcbe724d8e" />
файл удалён, но процесс работает. Так могут делать чтобы скрыть своё присутсвие.

Открытый порт

<img width="751" height="50" alt="image" src="https://github.com/user-attachments/assets/6248d5d0-be22-4976-948a-5625b071f29b" />

<img width="617" height="52" alt="image" src="https://github.com/user-attachments/assets/31f3fea9-2f40-4a0f-9600-b351cd40d564" />
порт 8080 слушается процессом python3

Теперь нам следует выявить кто запустил подозрительный процесс

<img width="432" height="105" alt="image" src="https://github.com/user-attachments/assets/05ef3df9-3836-4188-b441-eab157b432e9" />
Здесь мы увидели что сами запустили данный процесс.

Мы выяснили что хотели, теперь переходим к устранению

<img width="553" height="71" alt="image" src="https://github.com/user-attachments/assets/6ecbcca3-7011-4751-af17-f497511af2bd" />

Проверка, получилось ли очистить систему от заражения

<img width="501" height="157" alt="image" src="https://github.com/user-attachments/assets/c2b0c5c8-35a9-4151-866e-61a4fd7d9270" />

Вывод: Имени процесса нельзя доверять потому что его легко подделать, а сделать такое с /proc/PID/exe - нельзя.
И поэтому системный аналитик смотрит на сетевые соединения и на exe, cwd, cmdline.

<img width="379" height="230" alt="image" src="https://github.com/user-attachments/assets/d2cd5ece-5650-4b19-a959-ddc379796aa6" />

В системе остался только настоящий потом ядра, значит система очищена от заражения.
