---
title: "Управление Скайп для бизнеса в Интернет организаций"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Использование Windows PowerShell и командлетов Get-CsTenant и Get-CsTenantLicensingConfiguration для получения сведений о вашей Скайп для бизнеса интерактивного клиента."
ms.openlocfilehash: cab693fa153eae99ac605981112a30ec09f49920
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="c86cf-103">Управление Скайп для бизнеса в Интернет организаций</span><span class="sxs-lookup"><span data-stu-id="c86cf-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="c86cf-104">Можно найти сведения о вашей Скайп для бизнеса интерактивного клиента с помощью командлетов **Get-CsTenant** и **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c86cf-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="c86cf-105">Управление Скайп для бизнеса в Интернет клиентов</span><span class="sxs-lookup"><span data-stu-id="c86cf-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="c86cf-106">Для возвращения сведений о вашей Скайп для бизнеса интерактивного клиента, вызовите командлет [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="c86cf-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="c86cf-107">Для возврата только что клиента, имя и идентификатор, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c86cf-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="c86cf-108">Значение параметра _TenantID_ является обязательным при запуске командлета [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="c86cf-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="c86cf-109">Чтобы найти сведения о доступна ли сведения о лицензировании для указанного клиента в Скайп для бизнеса в Интернет центра администрирования, командлет [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="c86cf-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c86cf-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="c86cf-110">Related topics</span></span>
[<span data-ttu-id="c86cf-111">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c86cf-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
