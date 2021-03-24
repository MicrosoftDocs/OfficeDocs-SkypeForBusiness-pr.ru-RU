---
title: Переход из Соединителю Skype для бизнеса Online в модуль Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти с Соединителю Skype для бизнеса Online на модуль Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094130"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Переход из Соединителю Skype для бизнеса Online в модуль Teams PowerShell

Чтобы перейти от использования Соединителю Skype для бизнеса Online к модуле Teams PowerShell для управления Teams, необходимо обновить существующие сценарии PowerShell. В этой статье объясняется, как это сделать.

1. Установите последнюю версию модуля Teams PowerShell. По шагам [см. установку Microsoft Teams Powershell.](teams-powershell-install.md)
2. Удалить соединитель Skype для бизнеса Online. Для этого на панели управления перейдите в приложение "Программы и компонентов", выберите Skype для бизнеса **Online, Windows PowerShell** модуль, а затем выберите **"Удалить".** 
3. В сценариях PowerShell измените имя модуля, на которое ссылается ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` ссылка.

    Например, измените ```Import-Module -Name SkypeOnlineConnector``` на ```Import-Module -Name MicrosoftTeams``` .
4. При использовании модуля Teams PowerShell 2.0 или более поздней, измените new-csOnlineSession на Connect-MicrosoftTeams. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>Статьи по теме

[Установка Microsoft Teams Powershell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](/powershell/skype/intro?view=skype-ps)