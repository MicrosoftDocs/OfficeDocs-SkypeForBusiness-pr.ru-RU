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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="cf848-103">Управление Скайп для бизнеса в Интернет организаций</span><span class="sxs-lookup"><span data-stu-id="cf848-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="cf848-104">Можно найти сведения о вашей Скайп для бизнеса интерактивного клиента с помощью командлетов **Get-CsTenant** и **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="cf848-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="cf848-105">Управление Скайп для бизнеса в Интернет клиентов</span><span class="sxs-lookup"><span data-stu-id="cf848-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="cf848-106">Для возвращения сведений о вашей Скайп для бизнеса интерактивного клиента, вызовите командлет [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="cf848-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="cf848-107">Для возврата только что клиента, имя и идентификатор, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="cf848-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="cf848-108">Значение параметра _TenantID_ является обязательным при запуске командлета [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf848-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="cf848-109">Чтобы найти сведения о доступна ли сведения о лицензировании для указанного клиента в Скайп для бизнеса в Интернет центра администрирования, командлет [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="cf848-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cf848-110">See also</span><span class="sxs-lookup"><span data-stu-id="cf848-110">Related topics</span></span>
[<span data-ttu-id="cf848-111">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf848-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 