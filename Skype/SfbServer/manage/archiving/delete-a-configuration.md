---
title: Удаление конфигурации архивации в Skype для бизнеса Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: Сводка. Сведения об удалении конфигурации архивации в Skype для бизнеса Server.
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095413"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="de7d6-103">Удаление конфигурации архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="de7d6-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="de7d6-104">**Сводка:** Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="de7d6-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="de7d6-105">Вы можете удалить конфигурацию сайта или конфигурацию пула, но не можете удалить глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="de7d6-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="de7d6-106">Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de7d6-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="de7d6-107">Удаление конфигурации архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="de7d6-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="de7d6-108">Удаление конфигурации архивации с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="de7d6-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="de7d6-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="de7d6-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="de7d6-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="de7d6-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="de7d6-111">В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**</span><span class="sxs-lookup"><span data-stu-id="de7d6-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="de7d6-112">В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="de7d6-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="de7d6-113">Вы также можете щелкнуть глобальную конфигурацию, но выберите этот параметр только в том случае, если вы хотите сбросить глобальную конфигурацию до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de7d6-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="de7d6-114">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="de7d6-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="de7d6-115">Удаление конфигурации архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de7d6-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="de7d6-116">Вы также можете удалить конфигурацию архивации с помощью **cmdlet Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="de7d6-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="de7d6-117">Например, следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="de7d6-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="de7d6-118">При удалении политики, настроенной в области сайта, пользователи, ранее управляемые политикой сайта, будут автоматически управляться глобальной политикой архива:</span><span class="sxs-lookup"><span data-stu-id="de7d6-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="de7d6-119">Следующая команда удаляет все параметры конфигурации архивации, применяемые к области службы:</span><span class="sxs-lookup"><span data-stu-id="de7d6-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="de7d6-120">Следующая команда удаляет все параметры конфигурации архивации, в которых архивация Exchange отключена:</span><span class="sxs-lookup"><span data-stu-id="de7d6-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="de7d6-121">Для сброса глобальных параметров к значениям по умолчанию можно также использовать комлет **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="de7d6-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="de7d6-122">Например, предположим, что вы включили архивировку сеансов im на глобальном уровне; Следующая команда сбросит значение по умолчанию none, что отключит архивировать на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="de7d6-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="de7d6-123">Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsArchivingConfiguration.](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="de7d6-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>