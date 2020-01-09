---
title: Изменение параметров настройки собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992856"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="41d21-103">Изменение параметров настройки собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41d21-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="41d21-104">**Сводка:** Сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41d21-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="41d21-105">Параметры конфигурации собрания можно изменить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41d21-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="41d21-106">Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41d21-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="41d21-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41d21-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="41d21-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41d21-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="41d21-109">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="41d21-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="41d21-110">В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="41d21-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="41d21-111">В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="41d21-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="41d21-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="41d21-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="41d21-113">Изменение параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41d21-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="41d21-114">Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41d21-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="41d21-p101">Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.</span><span class="sxs-lookup"><span data-stu-id="41d21-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="41d21-117">Дополнительные сведения, в том числе полный список параметров, можно найти в разделе [Set-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41d21-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

