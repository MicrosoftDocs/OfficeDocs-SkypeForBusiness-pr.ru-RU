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
ms.openlocfilehash: ea8a755c75c5f91c5dbf3a4cd4dd749ac576557c
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2022
ms.locfileid: "63762013"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell — поддерживаемые версии

Microsoft Teams модуль PowerShell (TPM) версии 4.0.0 или выше будут поддерживаться только в будущем. Все более ранние версии находятся на пути выхода на пенсию.



## <a name="new-organizations"></a>Новые организации

С 1 апреля 2022 Teams организации смогут использовать только Teams PowerShell Module 4.0.0 или более новых.



## <a name="current-organizations-non-tpm-active"></a>Текущие организации (активные не TPM)

Организации, которые не использовали TPM в течение последних трех месяцев (с 22 января по 22 марта), смогут использовать TPM только 4.0.0 или более, начиная с 1 апреля 2022 г.



## <a name="current-organizations-tpm-active"></a>Текущие организации (активна TPM)

Организации, использующие TPM в течение последних трех месяцев (22 января — 22 марта), смогут использовать TPM 4.0.0 или более, начиная с 15 июня 2022 г. Рекомендуется обновить модуль Teams PowerShell до последней версии.


## <a name="important-notes"></a>Важные заметки

- Заметки о выпуске всех версий Teams PowerShell можно найти на Teams заметках о [выпуске PowerShell](teams-powershell-release-notes.md).

- Чтобы обновить любой модуль PowerShell, используйте тот же способ, который использовался для установки модуля. Например, если вы изначально использовали install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   При обновлении Teams PowerShell версии 1.1.6 обновите `Connect-MicrosoftTeams` сценарии для использования `New-CsOnlineSession`вместо .

-   Во время обновления предлагается не использовать TPM 4.x.x/3.x.x вместе с более старыми версиями, чем 3.0.0. Например, не рекомендуется использовать версии 4.0.0 & 2.6.0 для различных операций администрирования в одной организации. 

- Связанные изменения
  * Обновления для Get-CsOnlineUser & Get-CsOnlineVoiceUser в TPM 3.0.0 и выше — дополнительные сведения см. в окне [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (публикация центра сообщений — MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Изменения, внося в Телефон номера : дополнительные сведения в [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (публикация центра сообщений — MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Статьи по теме

[Teams о выпуске PowerShell](teams-powershell-release-notes.md)

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams ссылки на cmdlet](/powershell/module/teams) 

[Skype для бизнеса ссылки на cmdlet](/powershell/module/skype) 
