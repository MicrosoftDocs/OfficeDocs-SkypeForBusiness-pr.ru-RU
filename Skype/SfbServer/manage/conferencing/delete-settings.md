---
title: Удаление параметров конфигурации собрания в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Сводка: сведения о том, как удалить параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: dd07d3239b212f09391e9bc8c66f29bca62b2c3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818590"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="91a30-103">Удаление параметров конфигурации собрания в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="91a30-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="91a30-104">**Сводка:** Сведения о том, как удалить параметры конфигурации собрания в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="91a30-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="91a30-105">Вы можете удалить параметры конфигурации собрания с помощью панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="91a30-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="91a30-p101">Можно удалить конфигурацию сайта или пользователя. Глобальную конфигурацию невозможно удалить. При попытке удалить глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91a30-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="91a30-108">Удаление параметров конфигурации собрания с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="91a30-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="91a30-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="91a30-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="91a30-110">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="91a30-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="91a30-111">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="91a30-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="91a30-112">В списке конфигураций собрания выберите конфигурацию сайта или пула, щелкните **Изменить**, а затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="91a30-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="91a30-113">Удаление параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="91a30-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="91a30-114">Для удаления параметров собраний используйте командлет **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="91a30-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="91a30-115">Следующая команда удаляет параметры конфигурации собраний в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="91a30-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="91a30-116">Следующая команда удаляет все параметры конфигурации собрания, примененные к области сайта:</span><span class="sxs-lookup"><span data-stu-id="91a30-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="91a30-117">Дополнительные сведения, включая полный список параметров, можно найти в разделе [Remove-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="91a30-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

