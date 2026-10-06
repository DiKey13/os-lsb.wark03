Для начала нам нужно узнать кол-во ядер

<img width="204" height="37" alt="image" src="https://github.com/user-attachments/assets/2319f357-7bda-484d-b903-274d5e5b7ec6" />

в нашем случае их было установлено 4.

Создаём 2 процесса на одном ядре

<img width="497" height="114" alt="image" src="https://github.com/user-attachments/assets/c139fb8d-735e-406d-bfa3-b90568887203" />

Теперь мы можем посмотреть расставились ли наши приоритеты как мы задали

<img width="433" height="115" alt="image" src="https://github.com/user-attachments/assets/14d7ea82-deca-4f2f-847c-5154218c460a" />

<img width="765" height="164" alt="image" src="https://github.com/user-attachments/assets/972c2258-85f1-446d-af9c-5288981493c5" />

 Здесь можно увидеть как наши задачи борются за ядро, но nice 0 получает 95%, а nice 19 всего 5%.
 Попробуем поменять приоритеты

 <img width="405" height="72" alt="image" src="https://github.com/user-attachments/assets/1deb7516-1800-4ed9-a2b4-a7515c6d2021" />

 (sudo используется так как повышение "mice" может ухудшить работу других процессов и данная команда вводится только root)

 <img width="732" height="127" alt="image" src="https://github.com/user-attachments/assets/4de1687e-b8a5-4d4f-9862-eb5f9cd864ba" />

После повышения приоритета оба значения MI стали 0 и теперь они делят ресурсы ядра поровну

Завершаем процесс

<img width="518" height="108" alt="image" src="https://github.com/user-attachments/assets/32c8642d-9d7e-4a05-858c-249d28d0ee77" />

Команда taskset требовалась чтобы назначить задачи на одно ядро, запуск без этой команды привело бы к тому что 
задачи распределились бы по разным ядрам.
