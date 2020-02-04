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
description: Используйте Windows PowerShell и командлеты Get-Кстенант и Get-Кстенантлиценсингконфигуратион для получения сведений о клиенте Skype для бизнеса Online.
ms.openlocfilehash: 3c4a8f72caca634b208de5cf4aa555b88518f4da
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706254"
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление организациями Skype для бизнеса Online

Вы можете найти сведения о клиенте Skype для бизнеса Online с помощью командлетов **Get-кстенант** и **Get-кстенантлиценсингконфигуратион** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление клиентами Skype для бизнеса Online

Чтобы получить сведения о клиенте Skype для бизнеса Online, вызовите командлет [Get-кстенант](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.
  
```PowerShell
Get-CsTenant
```

Чтобы возвратить только имя и идентификатор клиента, используйте эту команду.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является обязательным при выполнении командлетов, таких как [Set-кстенантпубликпровидер](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-кстенантфедератионконфигуратион](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Чтобы найти сведения о том, доступны ли сведения о лицензировании для указанного клиента в центре администрирования Skype для бизнеса Online, используйте командлет [Get-кстенантлиценсингконфигуратион](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>См. также
[Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
