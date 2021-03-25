---
title: Удаление параметров конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: Сводка. Сведения об удалении параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119498"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a1d00-103">Удаление параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a1d00-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a1d00-104">**Сводка:** Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a1d00-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a1d00-105">Параметры конфигурации собраний можно удалить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a1d00-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="a1d00-106">Вы можете удалить конфигурацию сайта или пользователя, но не можете удалить глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a1d00-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="a1d00-107">Если вы попытайтесь удалить глобальную конфигурацию, она автоматически сброшена до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a1d00-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a1d00-108">Удаление параметров конфигурации собраний с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="a1d00-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a1d00-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a1d00-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a1d00-110">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a1d00-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a1d00-111">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.</span><span class="sxs-lookup"><span data-stu-id="a1d00-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="a1d00-112">В списке конфигураций собраний щелкните конфигурацию сайта или пула, которую необходимо удалить, нажмите кнопку **Изменить** и нажмите **кнопку Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a1d00-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a1d00-113">Удаление параметров конфигурации собраний с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="a1d00-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a1d00-114">Чтобы удалить параметры собраний, используйте комлет **Remove-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a1d00-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="a1d00-115">Следующая команда удаляет параметры конфигурации собраний, применяемые к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="a1d00-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="a1d00-116">Следующая команда удаляет все параметры конфигурации собраний, применяемые к области сайта:</span><span class="sxs-lookup"><span data-stu-id="a1d00-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="a1d00-117">Дополнительные сведения, включая полный список параметров, см. в [рублях Remove-CsMeetingConfiguration.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a1d00-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
