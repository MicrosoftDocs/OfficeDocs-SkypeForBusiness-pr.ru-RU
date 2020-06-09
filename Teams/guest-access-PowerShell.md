---
title: Использование PowerShell для управления гостевым доступом в команде
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как с помощью PowerShell разрешить или заблокировать гостевой доступ ко всем командам и определенным командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d438b9d5cf3af8d200da07fcebe39f4222c2b25a
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637308"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Использование PowerShell для управления гостевым доступом в команде
================================================

Кроме того, чтобы использовать центр администрирования Microsoft 365 и портал Azure Active Directory (Azure AD), вы можете управлять гостевым доступом с помощью Windows PowerShell. PowerShell предоставляет следующие возможности:
  
- Разрешение и блокирование гостевого доступа ко всем группам и Microsoft 365

- Разрешение на добавление гостей во все группы и Microsoft 365

- Разрешение и блокирование гостевых пользователей для определенной группы или группы Microsoft 365

Дополнительные сведения можно найти в разделе "Использование PowerShell для управления гостевым доступом" в [группах Microsoft 365 "Гостевой](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)доступ".

  
Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену. Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam). Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы. Дополнительные сведения можно найти [в разделе разрешение и блокирование гостевого доступа для групп Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Если вы хотите заблокировать гостей в Teams и по-прежнему хотите разрешить им доступ к сайтам SharePoint, можно использовать командлеты Azure AD PowerShell для отключения параметра AllowGuestsToAccessGroups в объекте Company, предполагая, что внешний общий доступ включен для сайтов SharePoint.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Включение и отключение гостевого доступа с помощью PowerShell

1.    Скачайте модуль PowerShell Skype для бизнеса Online со страницы https://www.microsoft.com/download/details.aspx?id=39366
 
2.    Подключите сеанс PowerShell к конечной точке Skype для бизнеса Online.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.    Проверьте настройку, и если параметру `AllowGuestUser` присвоено значение `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps), чтобы присвоить ему значение `$True`.

    ```PowerShell
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


## <a name="guest-access-vs-external-access"></a>Гостевой доступ и внешний доступ

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
