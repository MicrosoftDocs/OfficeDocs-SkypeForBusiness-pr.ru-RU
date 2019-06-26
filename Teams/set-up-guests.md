---
title: Включение и отключение гостевого доступа к Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Включение и отключение гостевого доступа в Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221453"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Включение и отключение гостевого доступа к Microsoft Teams
===================================================

Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.

Параметры гостей задаются в Azure Active Directory. Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов. Если пользователь видит сообщение "обратитесь к администратору" при попытке добавить гостя в группу, возможно, что функция "гость" не включена или параметры еще не вступают в силу.

> [!IMPORTANT]
> Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365. Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Гостевой доступ и внешний доступ (Федерация)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Настройка гостевого доступа в центре администрирования Microsoft Teams

1.  Войдите в центр администрирования Microsoft Teams.

2.  Выберите **Параметры** > "**гостевой доступ**" в параметрах Организации.

3. Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** и переключитесь на **On (вкл**.).

    ![Установка переключателя "разрешить гостевой доступ" ](media/set-up-guests-image1.png)

4.  Установите переключатель в положение **звонки**, **собрания**и **Обмен сообщениями** в **** зависимости от **** того, какие возможности вы хотите разрешить для гостевых пользователей.

    - **Делайте закрытые звонки** – включите этот **** параметр, чтобы разрешить гостям одноранговые звонки.
    - **Разрешить IP-видео** . Включите этот **** параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.
    - **Режим демонстрации экрана** — этот параметр определяет доступность демонстрации экрана для гостевых пользователей. 
       - Отключите этот параметр, **** чтобы отключить возможность общего доступа гостей к экранам в Teams. 
       - Чтобы разрешить общий доступ к отдельным приложениям, включите этот параметр в **единое приложение** . 
       - Включите этот параметр на **весь экран** , чтобы предоставить полный доступ к экрану.
    - **Разрешить собрание сейчас** – включите этот параметр **** , чтобы разрешить гостям использовать функцию "начать собрание" в Microsoft Teams.
    - **Изменить отправленные сообщения** . Включите этот **** параметр, чтобы разрешить гостям редактировать сообщения, отправленные ранее.
    - **Гости могут удалять отправленные сообщения** – включите этот **** параметр, чтобы разрешить гостям удалять сообщения, которые они ранее отправили.
    - **Чат** : Включите этот параметр **** , чтобы предоставить гостям возможность использовать чат в Teams.
    - **Используйте giphy в беседах** – включите этот **** параметр, чтобы разрешить гостям использовать giphy в беседах. GIF — это Интернет-база данных и поисковая система, с помощью которой пользователи могут искать и совместно использовать анимированные GIF-файлы. Каждому Gifу назначается рейтинг контента.
    - **Оценка содержимого GIF** — выберите оценку из раскрывающегося списка.
       - **Разрешить всем содержимому** – гости смогут вставлять все giphy в чате, независимо от их рейтинга.
       - **Умеренный** — гости смогут вставлять giphy в чате, но это будет умеренно ограничено содержимым для взрослых.
       - **Strict** – гости смогут вставлять giphy в беседы, но они не смогут вставить содержимое для взрослых.
    - **Используйте мемов в беседах** -включите этот **** параметр, чтобы разрешить гостям использовать мемов в беседах.
    - **Используйте наклейки в беседах** – включите этот **** параметр, чтобы разрешить гостям использовать наклейки в беседах. 


5.  Нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Включение и отключение гостевого доступа с помощью PowerShell

1.  Скачайте модуль PowerShell Skype для бизнеса Online изhttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Подключите сеанс PowerShell к конечной точке Skype для бизнеса Online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Проверьте конфигурацию и, если `AllowGuestUser` это `$False`так, используйте командлет [Set-кстеамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) , чтобы установить его `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Теперь вы можете использовать гостевых пользователей в Teams для Организации.

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения о гостевой службе доступа смотрите в следующем видеоролике.

|  |  |
|---------|---------|
| Добавление гостей в Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
