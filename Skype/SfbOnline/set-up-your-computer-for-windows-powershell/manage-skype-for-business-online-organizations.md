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
description: Используйте Windows PowerShell и командлеты Get-CsTenant и Get-CsTenantLicensingConfiguration для получения сведений о клиенте Skype для бизнеса Online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085695"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="72036-103">Управление организациями Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="72036-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="72036-104">Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72036-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="72036-105">Вы можете найти сведения о клиенте Skype для бизнеса Online с помощью командлетов **Get-CsTenant** и **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="72036-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="72036-106">Управление клиентами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="72036-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="72036-107">Чтобы получить сведения о клиенте Skype для бизнеса Online, вызовите командлет [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="72036-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="72036-108">Чтобы возвратить только имя и идентификатор клиента, используйте эту команду.</span><span class="sxs-lookup"><span data-stu-id="72036-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="72036-109">Значение параметра _TenantID_ является обязательным при выполнении командлетов, таких как [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="72036-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="72036-110">Чтобы найти сведения о том, доступны ли сведения о лицензировании для указанного клиента в центре администрирования Skype для бизнеса Online, используйте командлет [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="72036-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="72036-111">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="72036-111">Related topics</span></span>
[<span data-ttu-id="72036-112">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72036-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
