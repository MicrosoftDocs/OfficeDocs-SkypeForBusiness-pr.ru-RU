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
f1keywords: None
ms.custom:
- PowerShell
description: Используйте Windows PowerShell и командлеты Get-Кстенант и Get-Кстенантлиценсингконфигуратион для получения сведений о клиенте Skype для бизнеса Online.
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284693"
---
# <a name="manage-skype-for-business-online-organizations"></a>Управление организациями Skype для бизнеса Online

Вы можете найти сведения о клиенте Skype для бизнеса Online с помощью командлетов **Get-кстенант** и **Get-кстенантлиценсингконфигуратион** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Управление клиентами Skype для бизнеса Online

Чтобы получить сведения о клиенте Skype для бизнеса Online, вызовите командлет [Get-кстенант](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.
  
```
Get-CsTenant
```

Чтобы возвратить только имя и идентификатор клиента, используйте эту команду.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

Значение параметра _TenantID_ является обязательным при выполнении командлетов, таких как [Set-кстенантпубликпровидер](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-кстенантфедератионконфигуратион](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Чтобы найти сведения о том, доступны ли сведения о лицензировании для указанного клиента в центре администрирования Skype для бизнеса Online, используйте командлет [Get-кстенантлиценсингконфигуратион](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
