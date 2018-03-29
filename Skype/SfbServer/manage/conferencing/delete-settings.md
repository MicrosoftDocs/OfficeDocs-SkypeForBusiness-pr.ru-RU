---
title: Удаление параметров конфигурации собраний в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Сводка: Узнайте, как для удаления параметров конфигурации собрания в Скайп для Business Server 2015.'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="37509-103">Удаление параметров конфигурации собраний в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="37509-103">Delete meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="37509-104">**Сводка:** Удаление параметров конфигурации собрания в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="37509-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="37509-105">Можно удалить параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="37509-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="37509-p101">Можно удалить конфигурацию сайта или пользователя. Глобальную конфигурацию невозможно удалить. При попытке удалить глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37509-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="37509-108">Удаление параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="37509-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="37509-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="37509-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="37509-110">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="37509-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="37509-111">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="37509-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="37509-112">В списке конфигураций собрания выберите конфигурацию сайта или пула, щелкните **Изменить**, а затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="37509-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="37509-113">Удаление параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="37509-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="37509-114">Для удаления параметров собраний используйте командлет **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="37509-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="37509-115">Следующая команда удаляет параметры конфигурации собраний в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="37509-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="37509-116">Следующая команда удаляет все параметры конфигурации собрания, примененные к области сайта:</span><span class="sxs-lookup"><span data-stu-id="37509-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="37509-117">Дополнительные сведения, включая полный список параметров [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="37509-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

