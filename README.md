# Поиск доменных имен

Открыть страницу в Chrome, нажать F12 - Перейти во вкладку console, прописать команду allow pasting , а не скопировать (так не работает)

Затем следующую команду скопировать и вставить в console

> _window.domains = [...new Set(performance.getEntriesByType('resource').map(r => (new URL(r.name)).hostname))];_
> _console.log(domains);_

Полученные домены скопировать и вставить в https://rockblack.pro/ip-address

# Searching for domain names

Open page in Chrome, press F12, go to the console tab, enter the command allow pasting instead of copying (this doesn't work)

Then copy and paste the following command into the console

> _window.domains = [...new Set(performance.getEntriesByType('resource').map(r => (new URL(r.name)).hostname))];_
> _console.log(domains);_

Copy the obtained domains and paste them into https://rockblack.pro/ip-address

# Актуальные маршруты для Keenetic 

<img width="1177" height="879" alt="image" src="https://github.com/user-attachments/assets/cef8a652-63ea-4b9b-876e-638253ba7746" />

1.	Добавить конфиг  Wireguard в боковом меню:
Интернет → Другие подключения → Wireguard → Загрузить из файла
2.	Выбираем созданный конфиг Wireguard
3.	Нажимаем на добавленный конфиг в веб интерфейсе и устанавливаем галочку “Использовать для выхода в интернет” и в самом низу установить значение 30 сек “Проверка активности”
4.	Перейти в боковом меню:
Сетевые правила  → Интернет-фильтры → Настройка DNS → Имя профиля “Системный”
И убираем галочку с “Транзит запросов”
5.	Скачать архив системы пакетов Entware https://help.keenetic.com/hc/ru/articles/360021214160-Установка-системы-пакетов-репозитория-Entware-на-USB-накопитель
6.	В корне раздела диска создайте директорию install, куда положите файл mipsel-installer.tar.gz либо другой в зависимости от ядра модели
7.	Перейти в первой вкладке по адресу 192.168.1.1/a и http://192.168.1.1/diagnostics/general/log
8.	Выполнить команду opkg > disk storage:/ отправить запрос, мониторить состояние установки пакетов в Логах до “Установка пакетов системы завершена 5/5”
9.	Снова зайдите в админ панель роутера по адресу: 192.168.1.1/a и введите следующую команду > _opkg dns-override
10.	В том же поле введите команду > system configuration save
11.	И затем, необходимо перегрузить роутер, для этого, в том же поле введите > _system reboot
12.	Переходим в приложение Putty, прописываем ip адрес роутера и ssh port 222
13.	Пользователь > root пароль > keenetic
14.	Меняем пароль командой > _Passwd root ВАШПАРОЛЬ
15.	Обновляем информацию о репозитории командой > opkg update
16.	Устанавливаем Curl командой (opkg install curl) ниже сразу
17.	Устанавливаем пакет KVAS командой > opkg install curl && curl -sOfL http://kvas.zeleza.ru/upgrade && sh upgrade
18.	Пакеты, которые не смогли установиться автоматом, устанавливаем предложенной командой 
Попробуйте установить пакет вручную командой
> opkg update && opkg install /opt/packages/kvas_1.1.9-beta_3_all.ipk
19.	Выбираем VPN интерфейс для работы пакета с названием готовой конфигурации WireGuard
20.	Пишем команду > kvas setup
21.	Пишем команду > ipset list unblock
22.	Пишем команду и ждем около 10 минут > cd /tmp && curl -O https://raw.githubusercontent.com/dacukel/vpn/main/dns/1full && kvas import 1full
23.	Убеждаемся в добавлении списка командой kvas show
