## Использованные команды 
```bash
sudo nano /etc/fstab # открыть файл fstab 
```text
    /dev/sdX99  /mnt/test  ext4  defaults  0 0 # Вставить в файл fstab
```bash
    sudo reboot # перезагрузка
    sudo -i # вход под пользователем root
    sudo mount /dev/sda2 /mnt # примонтировать корневой раздел
    sudo nano /mnt/etc/fstab # редактирование файла fstab
    sudo umount /mnt # размонтирование /mnt