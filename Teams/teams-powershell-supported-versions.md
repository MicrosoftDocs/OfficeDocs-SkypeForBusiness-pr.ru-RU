---
title: Teams PowerShell — поддерживаемые версии
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте о версиях, поддерживаемых модулем Teams PowerShell, который используется для администрирования Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fc980420b53d850c48e680d25bdbf6ec437e8f8
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783969"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell — поддерживаемые версии

Microsoft Teams версии модуля PowerShell (TPM) в 4.x.x или более новых версиях будут поддерживаться в будущем. Все более ранние версии находятся на пути выхода на пенсию. Рекомендуется обновить модуль Teams PowerShell до последней версии.



## <a name="new-organizations"></a>Новые организации

С 1 апреля 2022 г. организации, недавно внося в Teams, смогут использовать модуль Teams PowerShell в ряду 4.x.x или более новой.



## <a name="current-organizations-non-tpm-active"></a>Текущие организации (активные не TPM)

Организации, которые не использовали модуль Teams PowerShell в течение последних трех месяцев (22 января — 22 марта), смогут использовать модуль PowerShell Teams только в ряду 4.x.x или более, начиная с 1 апреля 2022 г.



## <a name="current-organizations-tpm-active"></a>Текущие организации (активна TPM)

Организации, использующие модуль Teams PowerShell в течение последних трех месяцев (22 января — 22 марта), смогут использовать модуль PowerShell Teams только в ряду 4.x.x или более, начиная с 15 июня 2022 г. 



## <a name="important-notes"></a>Важные заметки

- Заметки о выпуске всех версий Teams PowerShell можно найти на Teams заметках о [выпуске PowerShell](teams-powershell-release-notes.md).

- Чтобы обновить любой модуль PowerShell, используйте тот же способ, который использовался для установки модуля. Например, если вы изначально использовали install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   При обновлении Teams PowerShell версии 1.1.6 обновите `Connect-MicrosoftTeams` сценарии для использования `New-CsOnlineSession`вместо .

-   Во время обновления предлагается не использовать TPM 4.x.x/3.x.x вместе с более старыми версиями, чем 3.0.0. Например, не рекомендуется использовать версии 4.x.x & 2.6.0 для различных операций администрирования в одной организации. 

- Связанные изменения
  * Обновления для Get-CsOnlineUser & Get-CsOnlineVoiceUser в TPM 3.x.x и выше — дополнительные сведения см. в [get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (публикация Центра сообщений — MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Изменения, внося в Телефон номера : дополнительные сведения в [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (публикация центра сообщений — MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Статьи по теме

[Teams о выпуске PowerShell](teams-powershell-release-notes.md)

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams ссылки на cmdlet](/powershell/module/teams) 

[Skype для бизнеса ссылки на cmdlet](/powershell/module/skype) 
