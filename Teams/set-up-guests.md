---
title: Включение и отключение гостевого доступа для Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Включение и отключение гостевого доступа в Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498123"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Включение и отключение гостевого доступа для Microsoft Teams
======================================

Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей. 

Параметры гостей задаются в Azure Active Directory. Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов. Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.


> [!IMPORTANT]
> Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365. Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>Настройка доступа к гостевой в группы & Скайп по центру администрирования бизнеса

1.  Войдите в группы & Скайп по центру администрирования бизнеса.

2.  Выберите пункт **Параметры масштабе организации** > **доступ в качестве гостя**.

3. Значение переключатель **Разрешить доступ гостя в группах Microsoft** **на**.

    ![Разрешить переключатель доступа гостя значение на ](media/set-up-guests-image1.png)

4.  Задайте переключение для **вызова**, **собрания**и **системы обмена сообщениями** для **включено** или **отключено**, в зависимости от доступа, которые необходимо разрешить.

5.  Нажмите кнопку **Сохранить**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Чтобы включить доступ в качестве гостя или отключить с помощью PowerShell

1.  Загрузить Скайп для модуля Business Online PowerShell изhttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Подключите сеанс PowerShell Скайп для бизнеса в Интернет конечной точки.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Проверьте конфигурацию и, если `AllowGuestUser` — это `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Установка для `$True`.

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Теперь можно создать гостевых пользователей в группах для вашей организации.

## <a name="more-information"></a>Дополнительная информация

В следующем видео для получения дополнительных сведений о доступ в качестве гостя.

|  |  |
|---------|---------|
| Добавление гостей в Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
