---
title: Управление Скайп для бизнеса в Интернет организаций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Использование Windows PowerShell и командлетов Get-CsTenant и Get-CsTenantLicensingConfiguration для получения сведений о вашей Скайп для бизнеса интерактивного клиента.
ms.openlocfilehash: 53043fbf623ce2cc7342bf5ac7b32c363927def5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление Скайп для бизнеса в Интернет организаций

Можно найти сведения о вашей Скайп для бизнеса интерактивного клиента с помощью командлетов **Get-CsTenant** и **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление Скайп для бизнеса в Интернет клиентов

Для возвращения сведений о вашей Скайп для бизнеса интерактивного клиента, вызовите командлет [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.
  
```
Get-CsTenant
```

Для возврата только что клиента, имя и идентификатор, используйте следующую команду.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является обязательным при запуске командлета [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Чтобы найти сведения о доступна ли сведения о лицензировании для указанного клиента в Скайп для бизнеса в Интернет центра администрирования, командлет [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>See also
[Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 