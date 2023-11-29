## Part 1. Установка ОС
- ![clockber](screens/1_ubuntu_ver.png)
_Отображает версию ОС_

## Part 2. Создание пользователя
- ![clockber](screens/2_new_user_adm.png)
_Создание нового пользователя и добавление его в группу 'adm'_

## Part 3. Настройка сети ОС
- ![clockber](screens/3_host_zone.png)
_Задача имя машины вида user-1 и установка временной зоны в соответсвии с текущим местоположением_

- ![clockber](screens/4_iplink.png)
_Вывод названий сетевых интерфейсов_
- lo (loopback device) – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него есть dns-имя – localhost. Посмотреть привязку можно в файле /etc/hosts..

- ![clockber](screens/5_ip_a.png)
_ip адрес устройства от DHCP сервера_
- Dynamic Host Configuration Protocol (DHCP) — сетевой протокол, предназначенный для автоматической конфигурации параметров сети на сетевых узлах.

- ![clockber](screens/5_ip_a.png)
_Внутренний ip адрес шлюза_

- ![clockber](screens/6_extr_ip.png)
_Внешний ip адрес_

- ![clockber](screens/7_netplan_apply.png)
_вручную задаем статичные адреса_

- Перезагрузить виртуальную машину. Убедиться, что статичные сетевые настройки (ip, gw, dns) соответствуют заданным в предыдущем пункте.

- ![clockber](screens/8_ping_ya_and_1.png)
- пропинговать удаленные хосты 1.1.1.1 и ya.ru

## Part 4. Обновление ОС
- ![clockber](screens/9_apt_upgrade.png)
_Обновление системных пакетов до последней версии через apt upgrade_

## Part 5. Использование команды sudo
- sudo — это утилита, предоставляющая привилегии root для выполнения административных операций в соответствии со своими настройками. Она позволяет легко контролировать доступ к важным приложениям в системе. 
- ![clockber](screens/10_sudo_rights.png)
_предоставляем права root пользователю_
- ![clockber](screens/11_check_rights.png)
_Переключаемся и проверяем права_

- ![clockber](screens/12_change_hostname.png)
_меняем имя хоста и проверяем_

## Part 6. Установка и настройка службы времени
- ![clockber](screens/13_timedate.png)
_Вывод timedatectl show, показывает время часового пояса._

## Part 7. Установка и использование текстовых редакторов
- Использованы редакторы Vim, Nano, Joe
_установка: usdo apt install vim_
_sudo apt install nano_
_sudo apt install joe_

_создаем файл *test_X.txt*_
- ![clockber](screens/14_vim_testX.png)
_1) Создание файла в vim : vim test_VIM.txt 2) Выйти c сохранениeм(esc) :wq!_
- ![clockber](screens/15_nano_testX.png)
_1) Создание файла в nano : nano test_NANO.txt 2) Выйти c сохранениeм ^+O, ^+X_
- ![clockber](screens/16_joe_testx.png)
_1) Создание файла в joe : joe test_JOE.txt 2) Выйти c сохранениeм ^K+W, ^K+Z_

- Меняем никнейм на строку "21 School 21", без сохранения

- ![clockber](screens/17_vim_edit.png)
_Выйти без сохранения(esc) :q!_
- ![clockber](screens/18_nano_edit.png)
_Выйти без сохранения ^+O_
- ![clockber](screens/19_joe_edit.png)
_Выйти без сохранения ^K+Z_

- Функции поиска по содержимому файла (слово)

- ![clockber](screens/20_search_vim.png)
_найти что-то в файле :/clockber и заменить :%s/clockber/world/g - clockber заменяем на world_
- ![clockber](screens/21_search_joe.png)
_найти что-то в файле ^K+F и заменить ^K+F: (R)eplace_
- ![clockber](screens/22_search_nano.png)
_найти что-то в файле Cntr+W и заменить Cntr+W & Cntr+R_

## Part 8. Установка и базовая настройка сервиса SSHD

_Установить службу SSHd: sudo apt install openssh-server_
_Проверяем стату службы: systemctl status sshd_

- ![clockber](screens/23_autostart_ssh.png)
_автостарт службы SSHd_

- ![clockber](screens/24_SSHd_port2022.png)
_Перенастроить службу SSHd на порт 2022_
_Рестарт сервиса: sudo systemctl restart ssh_

- ![clockber](screens/25_ps_ssh.png)

- ps - выводит список текущих процессов на сервере. Флаги: -A, -e, (a) - выбрать все процессы; -a - выбрать все процессы, кроме фоновых; -d, (g) - выбрать все процессы, даже фоновые, кроме процессов сессий; -N - выбрать все процессы кроме указанных; -С - выбирать процессы по имени команды; -G - выбрать процессы по ID группы; -p, (p) - выбрать процессы PID; --ppid - выбрать процессы по PID родительского процесса; -s - выбрать процессы по ID сессии; -t, (t) - выбрать процессы по tty; -u, (U) - выбрать процессы пользователя.

- Перезагрузить систему: sudo reboot

_Установим netstat: sudo apt install net-tools_
- ![clockber](screens/26_netstat_tan.png)
_Вывод команды netstat -tan_

- -a - Отображение всех подключений и ожидающих портов. -n - Отображение адресов и номеров портов в числовом формате. -t - Отображение текущего подключения в состоянии переноса нагрузки с процессора на сетевой адаптер при передаче данных ( "offload" ). 0.0.0.0 означает, что подключение может быть выполнено с/на любой адрес LISTEN - готовность к установке соединения

## Установка и использование утилит top, htop

- ![clockber](screens/27_top_screen.png)
_Вывод комынды top_
  * uptime = 24 min
  * количество авторизованных пользователей 1
  * общая загрузка системы - load avarage
  * общее количество процессов - tasks
  * загрузка cpu - %Cpu(s)
  * загрузка памяти - MiB mem

- ![clockber](screens/28_top_mem.png)
_pid процесса занимающего больше всего памяти Shift+m_

- ![clockber](screens/29_top_cpu.png)
_pid процесса, занимающего больше всего процессорного времени Shift+p_

- ![clockber](screens/30_htop_sort.png)
_Вывод htop с ссортировкой по PID, PERCENT_CPU, PERCENT_MEM, TIME_

- ![clockber](screens/31_htop_sshd.png)
_отфильтрованному для процесса sshd_

- ![clockber](screens/32_htop_syslog.png)
_с процессом syslog, найденным, используя поиск_

- ![clockber](screens/33_htop_setup.png)
_с добавленным выводом hostname, clock и uptime_

## Part 10. Использование утилиты fdisk

- ![clockber](screens/34_fdisk_l.png)

## Part 11. Использование утилиты df

- ![clockber](screens/35_df_root.png)
_Вывод команды df /root_
  * размер раздела - 31270768
  * размер занятого пространства - 7119720
  * размер свободного пространства - 22537020
  * процент использования - 25%
  * единицa измерения в выводе - Kb

- ![clockber](screens/36_df_th.png)
_Вывод команды df -Th /root_
  * размер раздела - 30Gb
  * размер занятого пространства - 6.8Gb
  * размер свободного пространства - 22Gb
  * процент использования - 25%
  * единицa измерения в выводе - Gb

## Part 12. Использование утилиты du

- ![clockber](screens/37_du_h.png)
_Вывод команды du -h_

- ![clockber](screens/38_du_varlog.png)
_размер папок /home, /var, /var/log (в байтах, в человекочитаемом виде)_

## Part 13. Установка и использование утилиты ncdu
_Установка: sudo apt install ncdu_

- ![clockber](screens/39_ncdu_home.png)
_размер /home_

- ![clockber](screens/40_ncdu_var.png)
_размер /var_

- ![clockber](screens/41_ncdu_varlog.png)
_размер /var/log_

## Part 14. Работа с системными журналами
- ![clockber](screens/42_dmesg.png)
_просмотр less /var/log/dmesg_

- ![clockber](screens/43_syslog.png)
_просмотр less /var/log/syslog_

- ![clockber](screens/44_authlog.png)
_просмотр less /var/log/auth.log_

- ![clockber](screens/45_session_root.png)
_время последней успешной авторизации, имя пользователя и метод входа в систему._

- ![clockber](screens/46_ssh_restart.png)
_перезапуск sshd service ssh restart_

## Part 15. Использование планировщика заданий CRON

- ![clockber](screens/47_crontab.png)
_с помощью команды crontab -e задаем задачу что бы каждые 2 минуты выполнялся скрипт_

- ![clockber](screens/48_cron_2min.png)
_смотрим в логах записи /var/log/syslog_

- ![clockber](screens/49_crontab_r.png)
_список текущих заданий, а затем их удаление_