---
title: Удаление политик конференц-связи в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="3c2cc-103">Удаление политик конференц-связи в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c2cc-103">Delete conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c2cc-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3c2cc-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3c2cc-106">Delete conferencing policies by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="3c2cc-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3c2cc-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3c2cc-108">Open Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3c2cc-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="3c2cc-110">В списке политик конференц-связи выберите политику узла или пользователя для удаления и щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3c2cc-111">Delete conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3c2cc-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3c2cc-112">Политики конференц-связи удаляются с помощью командлета **Remove-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="3c2cc-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3c2cc-113">Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="3c2cc-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="3c2cc-114">При выполнении следующей команды удаляются все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:</span><span class="sxs-lookup"><span data-stu-id="3c2cc-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="3c2cc-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3c2cc-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

