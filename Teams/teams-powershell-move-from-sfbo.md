---
title: Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти Skype для бизнеса Online Connector к Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866361"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell

Teams Модуль PowerShell содержит полный набор командлетов для управления Teams непосредственно из командной строки PowerShell. Администраторам не требуется Skype Для бизнеса Online Connector для Teams администрирования.

> [!NOTE]
> Teams сообщение центра сообщений (MC244740 от 16 марта 2021 г.); MC250940 от 16 апреля 2021 г.) об этом изменении.
>
> Teams Модуль PowerShell использует современную проверку подлинности, но Windows клиента удаленного управления (WinRM), чтобы разрешить базовую проверку подлинности. Инструкции [о том, как](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) включить проверку подлинности WinRM для Основных, см. в Windows PowerShell и установить Windows PowerShell.

## <a name="how-to-migrate"></a>Перенос

Перейти с Skype для бизнеса Online Connector на Teams powerShell очень просто. Ниже объясняется, как это сделать.

1. Установите последнюю версию Teams PowerShell. По шагам см. [Microsoft Teams PowerShell.](teams-powershell-install.md)

2. Удалить соединитель Skype для бизнеса Online. Для этого на панели управления перейдите в программу и функции **,** выберите Skype для бизнеса **Online,** Windows PowerShell модуль , а затем выберите Удалить **.**

3. В сценариях PowerShell измените имя модуля, на который ссылается ```Import-Module```

    `SkypeOnlineConnector` или `LyncOnlineConnector` в `MicrosoftTeams` .

    Например, измените `Import-Module -Name SkypeOnlineConnector` на `Import-Module -Name MicrosoftTeams` .

4. При использовании Teams PowerShell Module 2.0 или более поздней версии обновите сценарии, которые ссылаются на `New-CsOnlineSession` `Connect-MicrosoftTeams` . `Import-PsSession`больше не требуется создавать сеанс удаленной Skype для бизнеса PowerShell в Интернете, так как он делается неявным при использовании `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Статьи по теме

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)
