---
title: Включение и отключение гостевого доступа для Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
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
ms.openlocfilehash: f00b585b1473a366769650c2a59f6dee2a9d3bea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242622"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Включение и отключение гостевого доступа для Microsoft Teams
===================================================

Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.

Параметры гостей задаются в Azure Active Directory. Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов. Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.

> [!IMPORTANT]
> Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365. Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Сравнение гостевого и внешнего доступа (федерация)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Настройка гостевого доступа в Центре администрирования Microsoft Teams

1.  Войдите в Центр администрирования Microsoft Teams.

2.  Выберите **Параметры на уровне организации** > **Гостевой доступ**.

3. Установите переключатель **Разрешить гостевой доступ в Teams** в положение **Вкл**.

    ![Переключатель "Разрешить гостевой доступ в Teams", установленный в положение "Вкл" ](media/set-up-guests-image1.png)

4.  Установите переключатели в разделах **Звонки**, **Собрание** и **Сообщения** в положение **Вкл** или **Выкл** с учетом возможностей, которые нужно предоставить гостевым пользователям.

    - **Приватные звонки**. **Включите** этот параметр, чтобы разрешить гостям одноранговые звонки.
    - **Разрешить видео по IP**. **Включите** этот параметр, чтобы разрешить гостям использовать видео в своих звонках и собраниях.
    - **Режим демонстрации экрана**. Этот параметр управляет возможностью демонстрации экрана для гостевых пользователей. 
       - Присвойте ему значение **Отключено**, чтобы запретить гостям демонстрировать свои экраны в Teams. 
       - Присвойте ему значение **Одно приложение**, чтобы разрешить демонстрацию отдельных приложений. 
       - Присвойте ему значение **Весь экран**, чтобы разрешить полную демонстрацию экрана.
    - **Разрешить функцию "Начать собрание"**. **Включите** этот параметр, чтобы разрешить гостям использовать функцию "Начать собрание" в Microsoft Teams.
    - **Редактирование отправленных сообщений**. **Включите** этот параметр, чтобы разрешить гостям редактировать ранее отправленные сообщения.
    - **Удаление отправленных сообщений гостями**. **Включите** этот параметр, чтобы разрешить гостям удалять ранее отправленные сообщения.
    - **Чат**. **Включите** этот параметр, чтобы предоставить гостям возможность использовать чат в Teams.
    - **Использование Giphy в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать Giphy в беседах. Giphy — это сетевая база данных и поисковая система, позволяющая пользователям искать и обмениваться анимированными GIF-файлами. Каждому Giphy присваивается рейтинг контента.
    - **Рейтинг контента Giphy**. Выберите рейтинг из раскрывающегося списка:
       - **Разрешить весь контент**. Гости смогут вставлять все Giphy в беседы, независимо от рейтинга контента.
       - **Умеренно**. Гости смогут вставлять Giphy в беседы, при этом будет применяться умеренное ограничение в отношении контента для взрослых. 
       - **Строго**. Гости смогут вставлять Giphy в беседы, но будет запрещено вставлять контент для взрослых. 
    - **Использование мемов в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать мемы в беседах.
    - **Использование стикеров в беседах**. **Включите** этот параметр, чтобы разрешить гостям использовать стикеры в беседах. 


5.  Нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Включение и отключение гостевого доступа с помощью PowerShell

1.  Скачайте модуль PowerShell Skype для бизнеса Online со страницы https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Подключите сеанс PowerShell к конечной точке Skype для бизнеса Online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Проверьте настройку, и если параметру `AllowGuestUser` присвоено значение `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps), чтобы присвоить ему значение `$True`.

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
Теперь у вас есть гостевые пользователи в Teams для вашей организации.

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения о гостевом доступе см. в следующем видео.

|  |  |
|---------|---------|
| Добавление гостей в Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
