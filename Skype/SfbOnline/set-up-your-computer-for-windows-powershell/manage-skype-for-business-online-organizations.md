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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="a583e-103">Управление организациями Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a583e-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="a583e-104">Последний [общедоступный предварительный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован со Skype для бизнеса Online Connector, что обеспечивает единый модуль для управления Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a583e-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="a583e-105">Сведения о клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a583e-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="a583e-106">Управление клиентами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a583e-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="a583e-107">Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните в [cmdlet Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="a583e-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="a583e-108">Чтобы получить только имя и ИД клиента, воспользуйтесь этой командой.</span><span class="sxs-lookup"><span data-stu-id="a583e-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="a583e-109">Значение параметра _TenantID_ является требоваться при запуске таких параметров, как [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) и [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)</span><span class="sxs-lookup"><span data-stu-id="a583e-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="a583e-110">Чтобы узнать, доступна ли информация о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, используйте cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)</span><span class="sxs-lookup"><span data-stu-id="a583e-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a583e-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a583e-111">Related topics</span></span>
[<span data-ttu-id="a583e-112">Настройка компьютера для управления skype для бизнеса с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a583e-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
