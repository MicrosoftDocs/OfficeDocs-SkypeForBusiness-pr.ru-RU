---
title: Удаление параметров конфигурации собрания в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Сводка: Узнайте, как для удаления параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222760"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="da0ba-103">Удаление параметров конфигурации собрания в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="da0ba-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="da0ba-104">**Сводка:** Удаление параметров конфигурации собрания в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="da0ba-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="da0ba-105">Можно удалить параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="da0ba-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="da0ba-p101">Можно удалить конфигурацию сайта или пользователя. Глобальную конфигурацию невозможно удалить. При попытке удалить глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da0ba-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="da0ba-108">Удаление параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="da0ba-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="da0ba-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="da0ba-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="da0ba-110">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="da0ba-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="da0ba-111">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="da0ba-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="da0ba-112">В списке конфигураций собрания выберите конфигурацию сайта или пула, щелкните **Изменить**, а затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="da0ba-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="da0ba-113">Удаление параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="da0ba-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="da0ba-114">Для удаления параметров собраний используйте командлет **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="da0ba-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="da0ba-115">Следующая команда удаляет параметры конфигурации собраний в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="da0ba-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="da0ba-116">Следующая команда удаляет все параметры конфигурации собрания, примененные к области сайта:</span><span class="sxs-lookup"><span data-stu-id="da0ba-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="da0ba-117">Дополнительные сведения, включая полный список параметров [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="da0ba-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

