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
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119418"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="bed7f-103">Изменение параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bed7f-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bed7f-104">**Сводка:** Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bed7f-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="bed7f-105">Параметры конфигурации собраний можно изменить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bed7f-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bed7f-106">Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="bed7f-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bed7f-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bed7f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="bed7f-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bed7f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bed7f-109">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.</span><span class="sxs-lookup"><span data-stu-id="bed7f-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="bed7f-110">В списке конфигураций собраний щелкните конфигурацию, которую необходимо изменить, нажмите **кнопку Изменить** и нажмите **кнопку Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="bed7f-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bed7f-111">В **изменении конфигурации** собраний измените любые параметры конфигурации, за исключением имени конфигурации, которое невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="bed7f-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="bed7f-112">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="bed7f-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bed7f-113">Изменение параметров конфигурации собраний с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="bed7f-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bed7f-114">Чтобы изменить параметры конфигурации собраний, используйте комлет **Set-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="bed7f-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="bed7f-115">Команда, показанная в следующем примере, изменяет параметры конфигурации собраний, присвоенные сайту Redmond (-Identity site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="bed7f-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="bed7f-116">В этом случае значение свойства DesignateAsPresenter устанавливается для всех:</span><span class="sxs-lookup"><span data-stu-id="bed7f-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="bed7f-117">Дополнительные сведения, включая полный список параметров, см. в [списке Set-CsMeetingConfiguration.](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bed7f-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
