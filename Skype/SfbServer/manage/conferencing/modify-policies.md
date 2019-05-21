---
title: Изменение политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Сводка: сведения о том, как изменять политики конференц-связи в Skype для бизнеса Server.'
ms.openlocfilehash: b2c192948f0119a70f031c1c2bbe5de8e776c2f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280413"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="9c4d7-103">Изменение политик конференц-связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c4d7-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="9c4d7-104">**Сводка:** Сведения о том, как изменять политики конференц-связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="9c4d7-105">Вы можете изменять политики конференц-связи с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9c4d7-106">Изменение политик конференц-связи с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c4d7-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9c4d7-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9c4d7-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9c4d7-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="9c4d7-110">В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9c4d7-111">В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="9c4d7-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9c4d7-113">Изменение политик конференц-связи с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c4d7-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9c4d7-114">Чтобы изменить политики Конференции, используйте командлет **Set-ксконференЦингполици** .</span><span class="sxs-lookup"><span data-stu-id="9c4d7-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="9c4d7-115">В следующем примере показано изменение значения свойства политики конференц-связи SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="9c4d7-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="9c4d7-116">Команда присваивает свойству AllowConferenceRecording значение False:</span><span class="sxs-lookup"><span data-stu-id="9c4d7-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="9c4d7-117">Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Set-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9c4d7-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

