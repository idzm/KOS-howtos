# Quick start with **KOS** in **WSL** (**Ubuntu 24.04**) on **Windows** (**VS Code**)

1. Запуск **WSL**:

```cmd
wsl
```

2. Скачивание **SDK KasperskyOS Community Edition QEMU 1.4**:

```sh
curl -O "https://products.s.kaspersky-labs.com/special/KasperskyOSCommunityEdition/1.4.0.102/multilanguage-INT-1.4.0.102/df76b13a0f0c4eb7953d596b7ae0d29a/KasperskyOS-Community-Edition-Qemu-1.4.0.102_ru.deb"
```

3. Установка предварительных условий (**libncurses5**, **libffi7**):

```sh
# Download only the required compatibility packages instead of adding
# the full Ubuntu 20.04 repository to Ubuntu 24.04.
wget http://archive.ubuntu.com/ubuntu/pool/universe/n/ncurses/libncurses5_6.2-0ubuntu2_amd64.deb
wget https://archive.ubuntu.com/ubuntu/pool/main/libf/libffi/libffi7_3.3-4_amd64.deb

# Install the downloaded packages directly.
sudo apt install ./libncurses5_6.2-0ubuntu2_amd64.deb ./libffi7_3.3-4_amd64.deb
```

4. Установка **SDK KasperskyOS Community Edition QEMU 1.4**:

```sh
sudo apt install ./KasperskyOS-Community-Edition-Qemu-1.4.0.102_ru.deb
```
4. Установка значений переменных окружения:

```sh
cd /opt/KasperskyOS-Community-Edition-Qemu-1.4.0.102/common/
source set_env.sh
```

После этого будут установлены следующие переменные окружения:
 - **KOSCEVER**=**1.4.0.102**
 - **KOSCEPATH**=**/opt/KasperskyOS-Community-Edition-Qemu-1.4.0.102**

5. Настройка связки **VS Code** и **WSL**:

Запустите **VS Code** в Windows. Перейдите в раздел **Extensions** (расширения)
через **Ctrl+Shift+X**. Найдите и установите официальное расширение **WSL** (от
Microsoft). Нажмите **F1**, введите и выберите команду **WSL: Connect to WSL**.
Редактор перезапустится и подключится напрямую к вашей **Ubuntu**.

6. Установка расширения **KasperskyOS SDK Extension** для **VS Code**:

Нажмите на клавишу **F1**. Выполните команду **Extensions: Install from
VSIX...** в появившейся в верхней части окна командной строке. Выберите файл
расширения **kos-extension-<version>.vsix**, расположенный в директории
**/opt/KasperskyOS-Community-Edition-Qemu-1.4.0.102/dev_tools/ide_integration/vscode/**.

7. Создание проекта **hello_kos**:

Откройте палитру команд **VS Code** (**Ctrl+Shift+P**) и выполните команду
**KOS: New project**. В отобразившемся списке путей к установленным
**KasperskyOS SDK** выберите путь к **SDK**. В отобразившемся списке доступных в
**SDK** шаблонов и примеров проектов, выберите шаблон **hello**. Укажите
директорию для создаваемого проекта.

Процесс создания проекта запустится. По окончании процесса отобразится окно
уведомления.



