## Использованные команды 
```bash 
sudo apt update # обновление пакетов
sudo apt install stress-ng -y # установка stress-ng
sudo swapoff -a # отключение swap
sudo apt update && sudo apt install htop # установка htop
htop # запуск htop
sudo dmesg -w # Просмотр логов ядра
stress-ng --vm 3 --vm-bytes 1G --vm-keep # Запуск пожираьтеля памяти. Пример для машины с 2 ГБ RAM
dmesg | grep -i "oom-killer" # Проверка, сработал ли OOM Killer
free -h # Анализ состояния оперативной памяти до и после
