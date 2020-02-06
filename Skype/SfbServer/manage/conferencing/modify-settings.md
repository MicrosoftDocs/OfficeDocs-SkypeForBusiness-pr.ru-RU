---
title: Изменение параметров настройки собраний в Skype для бизнеса Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818500"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3d73b-103">Изменение параметров настройки собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3d73b-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3d73b-104">**Сводка:** Сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3d73b-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="3d73b-105">Параметры конфигурации собрания можно изменить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3d73b-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3d73b-106">Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3d73b-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3d73b-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3d73b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3d73b-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3d73b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3d73b-109">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="3d73b-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="3d73b-110">В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="3d73b-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3d73b-111">В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="3d73b-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="3d73b-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3d73b-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3d73b-113">Изменение параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3d73b-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3d73b-114">Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3d73b-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="3d73b-p101">Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.</span><span class="sxs-lookup"><span data-stu-id="3d73b-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="3d73b-117">Дополнительные сведения, в том числе полный список параметров, можно найти в разделе [Set-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3d73b-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

