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
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085695"
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление организациями Skype для бизнеса Online
> [!NOTE]
> Последний [общедоступный предварительный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован со Skype для бизнеса Online Connector, что обеспечивает единый модуль для управления Teams PowerShell.

Сведения о клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление клиентами Skype для бизнеса Online

Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните в [cmdlet Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.
  
```PowerShell
Get-CsTenant
```

Чтобы получить только имя и ИД клиента, воспользуйтесь этой командой.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является требоваться при запуске таких параметров, как [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)
  
Чтобы узнать, доступна ли информация о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, используйте cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления skype для бизнеса с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
