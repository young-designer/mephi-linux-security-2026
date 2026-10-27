# ДЗ №1 — Изучение средств защиты ОС GNU/Linux

Среда: РЕД ОС 8.0.3 в Oracle VirtualBox.

| Раздел | Результат | Артефакты |
|---|---|---|
| 1. Пользователь | `user1`, UID 1234; включён в `students`; максимальный срок действия пароля — 90 дней | `passwd`, `group`, `shadow` |
| 2. Мониторинг | Найдены setuid-файлы; зафиксирован `passwd` с RUID 1234 и EUID 0 | `setuid_files.out`, `processes.out` |
| 3. setuid | Для `/home/user1/mycat` установлены владелец `root:root` и права `4755`; чтение `/etc/shadow` проверено от имени `user1` | `stat.out`, `history.out` |
| 4. Capabilities | Для `/home/user1/mychown` установлена `cap_chown=ep`; проверена смена владельца файла | `getcap.out`, `stat.out` |
| 5. sudo | В `/etc/sudoers.d/user1-time` разрешены команды для изменения системного времени; конфигурация проверена `visudo` и `sudo -l` | `sudoers`, `sudoers.d-user1-time` |
| 6. Визуальное подтверждение | На скриншоте показан уникальный номер `dsn004` | `mephi-screenshot.png` |

Хеши паролей в файле `shadow` замаскированы перед публикацией в публичном репозитории.
