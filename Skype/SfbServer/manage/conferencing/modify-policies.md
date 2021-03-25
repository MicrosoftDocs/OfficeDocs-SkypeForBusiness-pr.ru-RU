---
title: Изменение политик conferencing в Skype для бизнеса Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: Сводка. Узнайте, как изменить политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119428"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="8755b-103">Изменение политик conferencing в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8755b-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="8755b-104">**Сводка:** Узнайте, как изменить политики конференций в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8755b-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="8755b-105">Политики конференциинга можно изменить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="8755b-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8755b-106">Изменение политик конференциинга с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="8755b-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8755b-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8755b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8755b-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="8755b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8755b-109">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.</span><span class="sxs-lookup"><span data-stu-id="8755b-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="8755b-110">В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="8755b-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8755b-111">В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="8755b-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="8755b-112">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="8755b-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8755b-113">Изменение политик конференций с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="8755b-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8755b-114">Чтобы изменить политики conferencing, используйте кодлет **Set-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="8755b-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="8755b-115">В следующем примере изменяется значение свойства политики conferencing SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="8755b-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="8755b-116">Команда задает значение свойства AllowConferenceRecording false:</span><span class="sxs-lookup"><span data-stu-id="8755b-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="8755b-117">Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8755b-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
