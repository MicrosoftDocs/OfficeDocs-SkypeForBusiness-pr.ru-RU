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
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113185"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="ef592-103">Управление организациями Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef592-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="ef592-104">Последний [общедоступный предварительный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован со Skype для бизнеса Online Connector, что обеспечивает единый модуль для управления Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef592-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="ef592-105">Сведения о клиенте Skype для бизнеса Online можно найти с помощью **cmdlets Get-CsTenant** и **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ef592-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="ef592-106">Управление клиентами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ef592-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="ef592-107">Чтобы получить сведения о клиенте Skype для бизнеса Online, позвоните в [cmdlet Get-CsTenant](/powershell/module/skype/Get-CsTenant) без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="ef592-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="ef592-108">Чтобы получить только имя и ИД клиента, воспользуйтесь этой командой.</span><span class="sxs-lookup"><span data-stu-id="ef592-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="ef592-109">Значение параметра _TenantID_ является требоваться при запуске таких параметров, как [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) и [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="ef592-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="ef592-110">Чтобы узнать, доступна ли информация о лицензировании для указанного клиента в Центре администрирования Skype для бизнеса Online, используйте cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="ef592-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ef592-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ef592-111">Related topics</span></span>
[<span data-ttu-id="ef592-112">Настройка компьютера для управления интернет-приложением Skype для бизнеса с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef592-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
