---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов, доступных для Microsoft Teams, включая веб-клиент, классический клиент (Windows и Mac), а также мобильный клиент (Android и iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 378abc8f49e15a0ef8cb4084ef7968fd8b3ed327
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402107"
---
<a name="get-clients-for-microsoft-teams"></a>Работа с клиентами для Microsoft Teams 
===========================

В Microsoft Teams доступен классический клиент (Windows и Mac), веб-клиент и мобильный клиент (Android и iOS). Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.

> [!NOTE]
> С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store. Вместо этого можно теперь Загрузите и установите клиентское групп на устройствах под управлением Windows 10 S режим. Чтобы загрузить настольных компьютеров клиента, перейдите к [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). Построения MSI клиента рабочего стола команды не доступен для устройств под управлением Windows 10 S режим.
>
> Дополнительные сведения о режиме Windows 10 S приведены [Краткие сведения о 10 Windows в режиме S](https://www.microsoft.com/windows/s-mode). 

<a name="desktop-client"></a>Классический клиент
--------------

> [!Tip]
> Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)

Классический клиент Microsoft Teams представляет собой автономное приложение и сейчас не входит в состав Office 365 профессиональный плюс. Teams доступен как для 32- и 64-разрядных версий Windows (7+), так и для macOS (10.10+). В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует. 

Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.

При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).

ИТ-администраторы могут использовать предпочитаемый способ распространения установочных файлов на компьютеры в своей организации, например System Center Configuration Manager (Windows) или Jamf Pro (macOS). Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).  

> [!NOTE]
> Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.

### <a name="windows"></a>Windows

Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.

> [!NOTE]
> Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.

Клиент Windows развертывается в папке AppData внутри профиля пользователя. Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав. Клиент Windows использует следующие расположения:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingsAddin

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

<a name="web-client"></a>Веб-клиент 
----------

Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах. Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере. В браузере должно быть разрешено использование сторонних файлов cookie. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.

<a name="mobile-clients"></a>Мобильные клиенты
--------------

Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок. Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store. Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать. 

Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:

-   **Android**: 4.4 или более поздней версии

-   **iOS**: 10.0 или более поздней версии

> [!NOTE]
> Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.

Мобильные приложения распространяются и обновляются только через магазин приложений соответствующей платформы и недоступны для распространения через решения по управлению мобильными устройствами (MDM), а также для загрузки в неопубликованном виде.


| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Точка принятия решений         |Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?         |
|![Значок дальнейших действий.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Дальнейшие действия         |Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams. Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.         |

<a name="client-update-management"></a>Управление обновлениями клиентов
------------------------

Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора. Если обновление доступно, клиент автоматически загружать обновления и когда приложение idled на определенный период времени, начинается процесс обновления.

<a name="client-side-configurations"></a>Конфигурации на стороне клиента
---------------------------

Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.

<a name="notification-settings"></a>Параметры уведомлений
----------------------------

Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами. Все эти параметры задает пользователь. Приведенный ниже рисунок показывает параметры клиента по умолчанию.

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>Пример скрипта PowerShell
----------------------------

Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users. Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
