---
title: Переход с Skype для бизнеса Online Connector на модуль PowerShell Для Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти от Skype для бизнеса Online Connector к модулю Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242293"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Переход с Skype для бизнеса Online Connector на модуль PowerShell Для Teams

Модуль PowerShell Teams предоставляет полный набор командлетов для управления Teams непосредственно из командной строки PowerShell. Администраторам не требуется соединитель Skype для бизнеса Online для администрирования Teams.

> [!NOTE]
> Администратор Teams был уведомлен через сообщение центра сообщений (MC244740 от 16 марта 2021 г.; MC250940 от 16 апреля 2021 г.) об этом изменении.
>
> Модуль PowerShell Teams использует современную проверку подлинности, но базовый клиент удаленного управления Windows (WinRM) должен быть настроен на разрешение обычной проверки подлинности. Инструкции по включению WinRM для обычной проверки подлинности см. в статье [Скачивание и установка Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1).

## <a name="how-to-migrate"></a>Как выполнить миграцию

Миграция с Skype для бизнеса Online Connector на модуль PowerShell Для Teams очень просто. Ниже описано, как это сделать.

1. Установите последнюю версию модуля Teams PowerShell. Инструкции см[. в разделе Установка PowerShell Майкрософт Teams](teams-powershell-install.md).

2. Удалите соединитель Skype для бизнеса Online. Для этого в панель управления перейдите в раздел **Программы и компоненты**, выберите **Skype для бизнеса в сети, Windows PowerShell модуль**, а затем выберите **Удалить**.

3. В сценариях PowerShell измените имя модуля, на который ссылается в ```Import-Module``` , с

    `SkypeOnlineConnector` или `LyncOnlineConnector` в `MicrosoftTeams`.

    Например, измените на `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams`.

4. При использовании Модуля PowerShell Teams 2.0 или более поздней версии обновите скрипты, которые ссылаются `New-CsOnlineSession` на `Connect-MicrosoftTeams`. `Import-PsSession`Больше не требуется для установки Skype для бизнеса удаленного сеанса PowerShell в сети, так как это делается неявно при использовании `Connect-MicrosoftTeams`.

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

## <a name="related-topics"></a>См. также

[Установка PowerShell Майкрософт Teams](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Майкрософт Teams](/powershell/teams/)

[Справочник по командлетам Skype для бизнеса](/powershell/skype/intro)
