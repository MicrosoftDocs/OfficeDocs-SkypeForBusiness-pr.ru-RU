---
title: Изменение параметров конфигурации собраний в Skype для бизнеса Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: Сводка. Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827999"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="cb885-103">Изменение параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb885-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="cb885-104">**Сводка:** Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cb885-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="cb885-105">Изменить параметры конфигурации собраний можно с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cb885-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cb885-106">Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb885-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cb885-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cb885-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="cb885-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cb885-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cb885-109">В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**</span><span class="sxs-lookup"><span data-stu-id="cb885-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="cb885-110">В списке конфигураций собраний выберите конфигурацию, которую нужно изменить, нажмите кнопку "Изменить", а затем щелкните **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="cb885-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cb885-111">В **области "Изменение конфигурации** собрания" измените любые параметры конфигурации, за исключением имени конфигурации, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="cb885-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="cb885-112">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="cb885-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cb885-113">Изменение параметров конфигурации собраний с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb885-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="cb885-114">Чтобы изменить параметры конфигурации собрания, используйте **cmdlet Set-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="cb885-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="cb885-115">Команда, показанная в следующем примере, изменяет параметры конфигурации собраний, присвоенные сайту Redmond (-Identity site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="cb885-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="cb885-116">В этом случае свойству DesignateAsPresenter задается значение Everyone:</span><span class="sxs-lookup"><span data-stu-id="cb885-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="cb885-117">Дополнительные сведения, включая полный список параметров, см. в подстроке [Set-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cb885-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

