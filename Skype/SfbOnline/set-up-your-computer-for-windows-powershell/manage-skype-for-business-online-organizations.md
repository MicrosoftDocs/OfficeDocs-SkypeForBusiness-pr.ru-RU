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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="57205-103">Управление организациями Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="57205-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="57205-104">Вы можете найти сведения о клиенте Skype для бизнеса Online с помощью командлетов **Get-кстенант** и **Get-кстенантлиценсингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="57205-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="57205-105">Управление клиентами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="57205-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="57205-106">Чтобы получить сведения о клиенте Skype для бизнеса Online, вызовите командлет [Get-кстенант](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="57205-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="57205-107">Чтобы возвратить только имя и идентификатор клиента, используйте эту команду.</span><span class="sxs-lookup"><span data-stu-id="57205-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="57205-108">Значение параметра _TenantID_ является обязательным при выполнении командлетов, таких как [Set-кстенантпубликпровидер](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-кстенантфедератионконфигуратион](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="57205-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="57205-109">Чтобы найти сведения о том, доступны ли сведения о лицензировании для указанного клиента в центре администрирования Skype для бизнеса Online, используйте командлет [Get-кстенантлиценсингконфигуратион](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="57205-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="57205-110">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="57205-110">Related topics</span></span>
[<span data-ttu-id="57205-111">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57205-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
