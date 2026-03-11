## Восстановление

```markdown
# Решение: Восстановление системы после удаления ядер

## Инструменты
- LiveCD Ubuntu (та же версия)
- chroot
- apt
- mount
- fdisk

## Шаги восстановления

1. Загрузиться с LiveCD (Try Ubuntu).
    Выключаем виртуальную машину, кликаем правой кнопкой мыши по нашей проблемной ВМ и переходим в настройки. Далее кликаем на "Носители". Видим контроллер IDE кликаем на пустой и смотрим на правую колонку, которая называется Атрибуты, кликаем на значок диска и выбираем образ с Linux (можно скачать любую версию главное, чтобы было 64 Bit)
    Запускаем машину и видим окно, выбираем Try or Install Ubuntu 
    ВАЖНО:Не нажимай сразу «Install Ubuntu»! Нам нужен живой рабочий стол, чтобы открыть терминал и начать восстановление.
    Запускается ознакомительный сеанс он нам и нужен, устанавливать по новой не обязательно, для начала нам необходимо закрыть окно с установкой и открыть терминал.
2. Определить разделы:
   ```bash 
   sudo fdisk -l
   # или lsblk
3. Примонтировать корневой раздел:
    sudo mount /dev/sda2 /mnt
4. Примонтировать виртуальные ФС:
    ```bash
    sudo mount --bind /dev /mnt/dev
    sudo mount --bind /proc /mnt/proc
    sudo mount --bind /sys /mnt/sys
5. Войти в среду chroot:
    ```bash
    sudo chroot /mnt
6. Установить ядро:
    ```bash
    apt update
    apt install linux-image-generic-hwe-20.04 -y
7. Переустановить GRUB:
    ```bash
    grub-install /dev/sda
    update-grub
8. Выйти, размонтировать /dev /proc /sys и перезагрузиться:
    exit
    sudo umount /mnt/dev
    sudo umount /mnt/proc
    sudo umount /mnt/sys
    sudo umount /mnt
    sudo reboot