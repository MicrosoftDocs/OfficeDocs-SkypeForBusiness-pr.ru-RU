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
description: Сводка. Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828186"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="61e30-103">Удаление параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61e30-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="61e30-104">**Сводка:** Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61e30-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="61e30-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="61e30-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="61e30-106">Вы можете удалить конфигурацию сайта или пользователя, но не глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="61e30-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="61e30-107">При попытке удалить глобальную конфигурацию она автоматически сбрасывается до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61e30-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="61e30-108">Удаление параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61e30-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="61e30-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61e30-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="61e30-110">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61e30-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="61e30-111">В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**</span><span class="sxs-lookup"><span data-stu-id="61e30-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="61e30-112">В списке конфигураций собраний выберите конфигурацию сайта или пула, которую нужно удалить, нажмите кнопку "Изменить", а затем выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="61e30-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="61e30-113">Удаление параметров конфигурации собраний с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61e30-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="61e30-114">Чтобы удалить параметры собрания, используйте **cmdlet Remove-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="61e30-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="61e30-115">Следующая команда удаляет параметры конфигурации собраний, применяемые к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="61e30-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="61e30-116">Следующая команда удаляет все параметры конфигурации собраний, примененные к области сайта:</span><span class="sxs-lookup"><span data-stu-id="61e30-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="61e30-117">Дополнительные сведения, включая полный список параметров, см. в подстроке [Remove-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="61e30-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

