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
description: Сводка. Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817629"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="ac85b-103">Удаление конфигурации архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ac85b-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="ac85b-104">**Сводка:** Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ac85b-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="ac85b-105">Вы можете удалить конфигурацию сайта или пула, но не глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ac85b-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="ac85b-106">Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac85b-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="ac85b-107">Удаление конфигурации архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="ac85b-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="ac85b-108">Чтобы удалить конфигурацию архивации с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="ac85b-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="ac85b-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ac85b-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ac85b-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ac85b-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ac85b-111">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="ac85b-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="ac85b-112">В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="ac85b-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac85b-113">Вы также можете щелкнуть глобальную конфигурацию, но выбрать этот параметр только в том случае, если необходимо сбросить значения по умолчанию для глобальной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ac85b-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="ac85b-114">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="ac85b-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="ac85b-115">Удаление конфигурации архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac85b-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="ac85b-116">Вы также можете удалить конфигурацию архивации с помощью **cmdlet Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ac85b-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ac85b-117">Например, следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="ac85b-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="ac85b-118">При удалении политики, настроенной на уровне сайта, пользователи, которыми ранее управляла политика сайта, будут автоматически управляться глобальной политикой архива:</span><span class="sxs-lookup"><span data-stu-id="ac85b-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="ac85b-119">Следующая команда удаляет все параметры конфигурации архивации, применяемые к области службы:</span><span class="sxs-lookup"><span data-stu-id="ac85b-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="ac85b-120">Следующая команда удаляет все параметры конфигурации архивации, для которых отключена архивация Exchange:</span><span class="sxs-lookup"><span data-stu-id="ac85b-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="ac85b-121">Для сброса глобальных параметров до значений по умолчанию можно также использовать cmdlet **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ac85b-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="ac85b-122">Например, предположим, что вы включили архивировку сеансов im на глобальном уровне; Следующая команда сбросит значение по умолчанию None, что отключит архив на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="ac85b-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="ac85b-123">Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ac85b-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
