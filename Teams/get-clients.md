---
title: Работа с клиентами для Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Узнайте, как установить различные клиенты, доступные для Microsoft Teams на ПК, macOS и мобильных устройствах.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec6958c481cf8d16477aeb7728b82b76de8f78b
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706716"
---
# <a name="get-clients-for-microsoft-teams"></a>Работа с клиентами для Microsoft Teams

> [!TIP]
> **Хотите установить Teams на компьютере с Windows, Mac или на мобильном устройстве?** Ознакомьтесь со статьей [Установка клиента Teams](https://go.microsoft.com/fwlink/?linkid=855754).

Microsoft Teams можно установить на ПК, компьютеры Mac и мобильные устройства, а также использовать через веб-браузер. Большинство конечных пользователей могут начать использовать Teams только после самостоятельной [установки клиента](https://go.microsoft.com/fwlink/?linkid=855754). После установки клиента Teams им нужно только войти в систему с помощью имени пользователя и пароля.

Если вы ИТ-профессионал и хотите узнать больше об установке и требованиях Teams, выберите клиентскую операционную систему в этой статье для получения дополнительных сведений.

Подробные сведения о возможностях каждого клиента на разных платформах см. в статье [Возможности Teams на разных платформах](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-clients"></a>Классические клиенты

Настольный клиент Teams доступен в качестве автономного приложения и в составе [Приложений Microsoft 365 для предприятий](/deployoffice/teams-install) для следующих операционных систем:

- 32- и 64-разрядная версия Windows (8.1 и более поздние версии, кроме Windows 10 LTSC) 
- ARM64 для Windows 10 на ARM 
- Windows Server 2012 R2 или более поздние версии
- macOS
- Linux (в форматах `.deb` и `.rpm`)
- Chrome OS (дополнительные сведения см. в статье [Как использовать Microsoft Office на Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

При наличии соответствующих локальных разрешений (для установки клиента Teams на компьютере Mac требуются права администратора, а на компьютере с Windows — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).

ИТ-профессионалы могут выбрать предпочтительный способ распространения установочных файлов на компьютеры в своей организации. Некоторые примеры включают Microsoft Endpoint Configuration Manager (Windows) или Jamf Pro (macOS). Дополнительные сведения о распространении Teams см. в следующих статьях:

- **Windows** [Установка Microsoft Teams с помощью Endpoint Configuration Manager](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> Распространение посредством этих механизмов подходит только для начальной установки клиентов Teams, но не для дальнейших обновлений. Дополнительные сведения о процессе обновления Teams см. в статье [Процесс обновления Teams](teams-client-update.md).

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)

Teams для Windows предоставляет скачиваемые установщики MSI в [32-разрядной](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true), [64-разрядной](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true) архитектуре и в архитектуре [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true). Архитектура x86 Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office. Рекомендуется использовать 64-разрядную версию Teams в 64-разрядных системах.

Для Teams требуется .NET Framework 4.5 или более поздней версии. Если .NET Framework или более поздняя версия не установлены, установщик Teams предложит установить платформу.

Клиент Windows развертывается в папке AppData внутри профиля пользователя. Развертывание в локальный профиль пользователя позволяет установить клиент без повышенного уровня разрешений. Клиент Windows использует следующие расположения:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Когда пользователи впервые выполняют звонок через клиент Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие. Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена". Создаются два правила входящего трафика для teams.exe с действием разрешения для протоколов TCP и UDP.

Если вы хотите запретить Teams предлагать пользователям создавать правила брандмауэра при первом вызове из Teams, используйте [сценарий PowerShell для брандмауэра Microsoft Teams в примере сценария PowerShell](client-firewall-script.md).

### <a name="mac"></a>[Mac](#tab/Mac)

Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS. Для установки клиента Mac требуется административный доступ. Клиент macOS устанавливается в папку /Applications.

1. На [странице скачивания Teams](https://teams.microsoft.com/downloads) в разделе **Mac** нажмите кнопку **Скачать**.
2. Дважды щелкните PKG-файл.
3. Для завершения установки следуйте инструкциям мастера.
4. Teams установится в папку /Applications. Это установка на уровне компьютера.

> [!NOTE]
> Во время установки PKG запросит учетные данные администратора. Пользователю потребуется ввести учетные данные администратора независимо от того, является ли он администратором.

Если пользователь в настоящее время использует установку DMG приложения Teams и хочет заменить ее установкой PKG, следует сделать следующее:

1. Выйти из приложения Teams.
2. Удалить приложение Teams.
3. Установить PKG-файл.

ИТ-профессионалы могут использовать средство управляемого развертывания, например, Jamf Pro, для распространения установочных файлов на все компьютеры Mac в организации.

### <a name="linux"></a>[Linux](#tab/Linux)

В Linux, диспетчеры пакетов, такие как `apt` и `yum`, пытаются установить любые требования. Однако, если этого не произойдет, вам нужно будет установить все заявленные требования перед установкой Teams в Linux.

Пользователи смогут установить собственные пакеты Linux в форматах `.deb` и `.rpm`. Установка пакета DEB или RPM автоматически установит репозиторий пакетов.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

Ключ подписи для автоматического обновления с помощью системного менеджера пакетов устанавливается автоматически. Однако его также можно найти по адресу: <https://packages.microsoft.com/keys/microsoft.asc>. Teams поставляется ежемесячно, и если репозиторий был установлен правильно, ваш системный менеджер пакетов должен обрабатывать автоматическое обновление так же, как и другие пакеты в системе.

#### <a name="install-teams-using-deb-package"></a>Установить команды, используя пакет DEB

1. Скачайте пакет из <https://aka.ms/getteams>.
2. Установите с помощью одного из следующих:
    - Откройте соответствующий инструмент управления пакетами и пройдите процедуру самостоятельной установки приложений Linux.
    - Или, если вы любите Терминал, введите: `sudo dpkg -i **teams download file**`

Вы можете запустить Teams через Действия или через Терминал, набрав `teams`.

#### <a name="install-teams-using-rpm-package"></a>Установите Команды, используя пакет RPM

1. Скачайте пакет из <https://aka.ms/getteams>.
2. Установите с помощью одного из следующих:
    - Откройте соответствующий инструмент управления пакетами и пройдите процедуру самостоятельной установки приложений Linux.
    - Или, если вы любите Терминал, введите: `sudo yum install **teams download file**`

Вы можете запустить Teams через Действия или через Терминал, набрав `teams`.

#### <a name="install-manually-from-the-command-line"></a>Установить вручную из командной строки

Установите вручную в дистрибутивах Debian и Ubuntu:

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg

sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

Установите вручную в дистрибутивах на основе RHEL, Fedora и CentOS:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

Также можно использовать yum вместо dnf:

```bash
yum check-update
sudo yum install teams
```

Установите вручную в дистрибутивах на основе openSUSE:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>Мобильные клиенты

Мобильные приложения Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок. Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store.

Для мобильных приложений Teams поддерживаются следующие мобильные платформы:

- **Android**: поддержка ограничена последними четырьмя основными версиями Android. Когда выпущена новая основная версия Android, официально поддерживается новая версия и предыдущие три версии.

- **iOS**: поддержка ограничена двумя последними основными версиями iOS. Когда выпущена новая основная версия iOS, официально поддерживается новая версия iOS и предыдущая версия.

> [!NOTE]
> Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.

Мобильные приложения распространяются и обновляются только через магазин приложений для соответствующей мобильной платформы. Распространение мобильных приложений через MDM и загрузка неопубликованных приложений не поддерживаются корпорацией Майкрософт. Как только мобильное приложение Teams будет установлено на поддерживаемой мобильной платформе, оно само будет поддерживаться, при условии что с момента выпуска текущей версии прошло не более трех месяцев.   

Если вы находитесь в Китае, вы можете установить Teams из следующих магазинов приложений:

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Выполните поиск по запросу "Teams" в магазине Oppo
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

## <a name="browser-client"></a>Клиент-браузер

Клиент-браузер ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах. Клиент-браузер поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в браузере. В браузере должно быть разрешено использование сторонних файлов cookie.

[!INCLUDE [browser-support](includes/browser-support.md)]

Клиент-браузер определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). В случае обнаружения неподдерживаемой версии он блокирует доступ к интерфейсу браузера и рекомендует пользователю скачать классический клиент или мобильное приложение.
