---
title: Удаление политик конференц-связи в Skype для бизнеса Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Сводка: сведения об удалении политик конференц-связи в Skype для бизнеса Server.'
ms.openlocfilehash: 3fe5b8c2bb12f48cb6e904df2fe43c6c8a01e3f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818600"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="63593-103">Удаление политик конференц-связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="63593-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="63593-104">**Сводка:** Сведения об удалении политик конференц-связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="63593-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="63593-105">Политики конференц-связи можно удалить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="63593-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="63593-106">Удаление политик конференц-связи с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="63593-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="63593-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="63593-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="63593-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="63593-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="63593-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="63593-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="63593-110">В списке политик конференц-связи выберите политику узла или пользователя для удаления и щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="63593-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="63593-111">Удаление политик конференц-связи с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="63593-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="63593-112">Политики конференц-связи удаляются с помощью командлета **Remove-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="63593-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="63593-113">Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="63593-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="63593-114">При выполнении следующей команды удаляются все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:</span><span class="sxs-lookup"><span data-stu-id="63593-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="63593-115">Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Remove-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63593-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

