---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов, доступных для Microsoft Teams, включая веб-клиент, классический клиент (Windows и Mac), а также мобильный клиент (Android и iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4abae267bf1a8c0c770eebf1c1b12018a6c7deb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833769"
---
# <a name="get-clients-for-microsoft-teams"></a>Работа с клиентами для Microsoft Teams 


В Microsoft Teams доступны клиенты для настольных компьютеров (Windows, Mac и Linux), веб-сайтов и мобильных устройств (Android и iOS). Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.

> [!NOTE]
> С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store. Вместо этого теперь вы можете скачать и установить классический клиент Teams на устройствах с Windows 10 в S-режиме. Чтобы скачать классический клиент, перейдите по ссылке [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). Сборки MSI для классического клиента Teams пока недоступны на устройствах с Windows 10 в S-режиме.
>
> Дополнительные сведения о Windows 10 в S-режиме см. в статье [Знакомство с Windows 10 в S-режиме](https://www.microsoft.com/windows/s-mode). 

## <a name="desktop-client"></a>Классический клиент

> [!TIP]
> Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)

Классический клиент Microsoft Teams представляет собой автономное приложение, а также [входит в состав Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install). Teams поддерживается для Windows (7 +), Windows Server (2012 R2 +), 32-bit и 64-bit Versions, macOS (10.10 +) и Linux (in `.deb` и `.rpm` formats). В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует. В Linux диспетчеры пакетов, такие как Апт и Юм, будут пытаться установить любые требования. Однако в противном случае вам потребуется установить любые требования, предъявляемые перед установкой Teams в Linux.

Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.

При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).

ИТ — администраторы могут выбрать предпочтительный способ распространения установочных файлов на компьютеры в своей организации. Некоторые примеры включают диспетчер конфигурации конечных точек Майкрософт (Windows) или Жамф Pro (macOS). Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).  

> [!NOTE]
> Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.

### <a name="windows"></a>Windows

Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.

> [!NOTE]
> Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.

Клиент Windows развертывается в папке AppData внутри профиля пользователя. Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав. Клиент Windows использует следующие расположения:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие. Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена". Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.

### <a name="mac"></a>Mac

Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS. Для установки клиента Mac требуется административный доступ. Клиент macOS устанавливается в папку /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Установка Teams с помощью PKG-файла

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

ИТ-администраторы могут использовать средство управляемого развертывания Teams для распространения установочных файлов на все компьютеры Mac в организации, например Jamf Pro.

> [!NOTE]
> Сообщите нам, если у вас возникают проблемы при установке PKG. В разделе **Обратная связь** в конце этой статьи нажмите кнопку **Отзыв о продукте**.

### <a name="linux"></a>Linux

Пользователи смогут устанавливать собственные пакеты Linux в `.deb` и `.rpm` форматах.
При установке пакета DEB или RPM будет автоматически установлена база данных пакетов.
- DEB`https://packages.microsoft.com/repos/ms-teams stable main`
- ОБОРОТ`https://packages.microsoft.com/yumrepos/ms-teams` 

Ключ подписи, позволяющий включить автоматическое обновление с помощью диспетчера пакетов системы, устанавливается автоматически. Однако ее также можно найти по адресу (https://packages.microsoft.com/keys/microsoft.asc). Microsoft Teams ежемесячно обновляется, и если репозиторий установлен правильно, диспетчер пакетов системы должен обрабатывать автоматическое обновление таким же образом, как и другие пакеты в системе.

> [!NOTE] 
> Если обнаружена ошибка, отправьте ее с помощью `Report a Problem` клиента. Известные проблемы можно найти в разделе [Известные проблемы](Known-issues.md).
> Для поддержки Teams для Linux вы можете использовать [канал поддержки форумов Linux в Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html). Не забудьте использовать `teams-linux` тег при отправке вопросов. 

#### <a name="install-teams-using-deb-package"></a>Установка Teams с помощью пакета DEB

1. Скачайте пакет https://aka.ms/getteams.
2. Установите одно из указанных ниже действий.  
    - Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.
    - Или, если вы любите контакт, введите:`sudo apt install **teams download file**`

Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст. 

#### <a name="install-teams-using-rpm-package"></a>Установка Teams с помощью пакета RPM

1. Скачайте пакет https://aka.ms/getteams.
2. Установите одно из указанных ниже действий.
    - Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.
    - Или, если вы любите контакт, введите:`sudo yum install **teams download file**`

Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст.

#### <a name="install-manually-from-the-command-line"></a>Установка вручную из командной строки

Установка вручную в Debian и Ubuntu:
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

Установка вручную на основе РХЕЛ, Fedora и Центос для дистрибутивов:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

Кроме того, чтобы использовать Юм вместо ДНФ, выполните указанные ниже действия.
```
yum check-update
sudo yum install teams
```

Установка вручную в дистрибутивах на базе openSUSE:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Веб-клиент 

Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах. Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере. В браузере должно быть разрешено использование сторонних файлов cookie. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.

## <a name="mobile-clients"></a>Мобильные клиенты

Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок. Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store. Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать. 

Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:

-   **Android**: поддержка ограничена последними основными версиями Android. Если выпущена новая старшая версия Android, официально поддерживаются новая версия и три предыдущие версии.

-   **iOS**: поддержка ограничена двумя последними основными версиями iOS. При выпуске новой основной версии iOS официально поддерживаются новая версия iOS и Предыдущая версия.

> [!NOTE]
> Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.

Мобильные приложения распространяются и обновляются только через магазин приложений для соответствующей мобильной платформы. Распространение мобильных приложений через MDM и загрузка неопубликованных приложений не поддерживаются корпорацией Майкрософт. Как только мобильное приложение Teams будет установлено на поддерживаемой мобильной платформе, оно само будет поддерживаться, при условии что с момента выпуска текущей версии прошло не более трех месяцев.   


| | | |
|---------|---------|---------|
|![Значок, изображающий точку принятия решения](media/Get_clients_for_Microsoft_Teams_image4.png)      |Точка принятия решений         |Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?         |
|![Значок, изображающий дальнейшие действия](media/Get_clients_for_Microsoft_Teams_image5.png)     |Дальнейшие действия         |Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams. Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.         |

## <a name="client-update-management"></a>Управление обновлениями клиентов

Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора. При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения начинает процесс обновления.

## <a name="client-side-configurations"></a>Конфигурации на стороне клиента

Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.

## <a name="notification-settings"></a>Параметры уведомлений

Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами. Все эти параметры задает пользователь. Приведенный ниже рисунок показывает параметры клиента по умолчанию.

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a>Пример скрипта PowerShell

Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users. Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams. 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
