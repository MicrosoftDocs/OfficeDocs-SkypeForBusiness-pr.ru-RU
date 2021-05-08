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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="8353d-103">Управление Skype для бизнеса online</span><span class="sxs-lookup"><span data-stu-id="8353d-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="8353d-104">Последний [общедоступный Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован с Skype для бизнеса Online Connector, предоставляя один модуль для управления Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8353d-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="8353d-105">Сведения о вашем клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="8353d-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="8353d-106">Управление Skype для бизнеса online</span><span class="sxs-lookup"><span data-stu-id="8353d-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="8353d-107">Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните на [веб-сайт Get-CsTenant](/powershell/module/skype/Get-CsTenant) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="8353d-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="8353d-108">Чтобы вернуть только имя клиента и его ИД, воспользуйтесь этой командой.</span><span class="sxs-lookup"><span data-stu-id="8353d-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="8353d-109">Значение параметра _TenantID_ является требоваться при запуске таких cmdlets, как [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) и [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="8353d-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="8353d-110">Сведения о том, доступны ли сведения о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, см. с помощью [cmdlet Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="8353d-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8353d-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8353d-111">Related topics</span></span>
[<span data-ttu-id="8353d-112">Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8353d-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
