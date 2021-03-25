---
title: Управление организациями Skype для бизнеса Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
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
description: Используйте Windows PowerShell и Get-CsTenant и Get-CsTenantLicensingConfiguration для получения сведений о клиенте Skype для бизнеса Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113185"
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление организациями Skype для бизнеса Online
> [!NOTE]
> Последний [общедоступный предварительный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован со Skype для бизнеса Online Connector, что обеспечивает единый модуль для управления Teams PowerShell.

Сведения о клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление клиентами Skype для бизнеса Online

Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните в [cmdlet Get-CsTenant](/powershell/module/skype/Get-CsTenant) без дополнительных параметров.
  
```PowerShell
Get-CsTenant
```

Чтобы получить только имя и ИД клиента, воспользуйтесь этой командой.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является требоваться при запуске таких параметров, как [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) и [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Чтобы узнать, доступна ли информация о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, используйте cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления интернет-приложением Skype для бизнеса с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
