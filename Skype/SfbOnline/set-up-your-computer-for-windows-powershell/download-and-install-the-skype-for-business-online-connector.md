---
title: Скачайте и установите модуль Skype для бизнеса Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: fd0a114bcd434e624937b323fbfa787d252db96ffafb701c3f13ff3a677b7118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339287"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Скачивание и установка модуля Teams PowerShell

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> Последний [общедоступный Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован с Skype для бизнеса Online Connector, предоставляя один модуль для управления Teams и Skype для бизнеса PowerShell.


1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
