## Использованные команды 
    ```bash
    uname -r # узнать текущее ядро
    apt update && apt install linux-image-6.17.0-10-generic -y # установка ядра     
	sudo apt-get update # обновление индекса пакетов
    apt remove --purge linux-image-6.14.0-33-generic -y # удаление ядра системы (1 способ) 
    dpkg --remove linux-image-6.14.0-33-generic # принудительное удаление ядра (2 способ)
    apt remove --purge linux-image-generic-hwe-24.04 -y # удаление зависимостей ядра
    sudo -i # войти под root-пользователем
    lsblk # отображает список всех жёстких дисков  
    chroot /mnt # заходим в систему  
    apt-get update # обновление пакетов
    apt-get install linux-image-6.17.0-10-generic # установка ядра
    umount /mnt/dev # размонтирование /dev
    umount /mnt/proc # размонтирование /proc
    umount /mnt/sys # размонтирование /sys
    umount /mnt # размонтирование /mnt
