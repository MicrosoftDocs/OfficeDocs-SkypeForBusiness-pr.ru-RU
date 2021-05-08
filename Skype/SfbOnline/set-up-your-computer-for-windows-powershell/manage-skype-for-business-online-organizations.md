---
title: Управление Skype для бизнеса online
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
description: Используйте Windows PowerShell и Get-CsTenant и Get-CsTenantLicensingConfiguration, чтобы получить сведения о клиенте Skype для бизнеса Online.
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238789"
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление Skype для бизнеса online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> Последний [общедоступный Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован с Skype для бизнеса Online Connector, предоставляя один модуль для управления Teams PowerShell.

Сведения о вашем клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление Skype для бизнеса online

Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните на [веб-сайт Get-CsTenant](/powershell/module/skype/Get-CsTenant) без дополнительных параметров.
  
```PowerShell
Get-CsTenant
```

Чтобы вернуть только имя клиента и его ИД, воспользуйтесь этой командой.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является требоваться при запуске таких cmdlets, как [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) и [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Сведения о том, доступны ли сведения о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, см. с помощью [cmdlet Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
