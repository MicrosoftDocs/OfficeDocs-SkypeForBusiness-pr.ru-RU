---
title: Удаление политик conferencing в Skype для бизнеса Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: Сводка. Сведения об удалении политик конференциинга в Skype для бизнеса Server.
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119508"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="44fd6-103">Удаление политик conferencing в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="44fd6-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="44fd6-104">**Сводка:** Узнайте, как удалить политики conferencing в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="44fd6-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="44fd6-105">Политики конференциинга можно удалить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="44fd6-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="44fd6-106">Удаление политик конференций с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="44fd6-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="44fd6-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="44fd6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="44fd6-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="44fd6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="44fd6-109">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.</span><span class="sxs-lookup"><span data-stu-id="44fd6-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="44fd6-110">В списке политик конференциинга щелкните веб-сайт или политику пользователей, которые необходимо удалить, нажмите кнопку **Изменить** и нажмите **кнопку Удалить**.</span><span class="sxs-lookup"><span data-stu-id="44fd6-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="44fd6-111">Удаление политик conferencing с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="44fd6-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="44fd6-112">Чтобы удалить политики conferencing, используйте **cmdlet Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="44fd6-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="44fd6-113">Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="44fd6-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="44fd6-114">Следующая команда удаляет все политики конференц-конференций, которые позволяют внешним пользователям записывать конференцию:</span><span class="sxs-lookup"><span data-stu-id="44fd6-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="44fd6-115">Дополнительные сведения, включая полный синтаксис и список параметров, см. в обзоре [Remove-CsConferencingPolicy.](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="44fd6-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
