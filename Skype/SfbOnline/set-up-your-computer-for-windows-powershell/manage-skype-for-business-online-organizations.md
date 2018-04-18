---
title: Управление Скайп для бизнеса в Интернет организаций
ms.author: tonysmit
author: tonysmit
manager: serdars
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
ms.openlocfilehash: 1b58686b2330b43cc5978752ac4f6b4a91f9588e
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="87cfa-103">Управление Скайп для бизнеса в Интернет организаций</span><span class="sxs-lookup"><span data-stu-id="87cfa-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="87cfa-104">Можно найти сведения о вашей Скайп для бизнеса интерактивного клиента с помощью командлетов **Get-CsTenant** и **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="87cfa-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="87cfa-105">Управление Скайп для бизнеса в Интернет клиентов</span><span class="sxs-lookup"><span data-stu-id="87cfa-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="87cfa-106">Для возвращения сведений о вашей Скайп для бизнеса интерактивного клиента, вызовите командлет [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="87cfa-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="87cfa-107">Для возврата только что клиента, имя и идентификатор, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="87cfa-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="87cfa-108">Значение параметра _TenantID_ является обязательным при запуске командлета [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="87cfa-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="87cfa-109">Чтобы найти сведения о доступна ли сведения о лицензировании для указанного клиента в Скайп для бизнеса в Интернет центра администрирования, командлет [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="87cfa-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="87cfa-110">See also</span><span class="sxs-lookup"><span data-stu-id="87cfa-110">Related topics</span></span>
[<span data-ttu-id="87cfa-111">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87cfa-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 