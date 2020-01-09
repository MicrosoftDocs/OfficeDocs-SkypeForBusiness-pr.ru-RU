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
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991814"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="892b4-103">Изменение политик конференц-связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="892b4-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="892b4-104">**Сводка:** Сведения о том, как изменять политики конференц-связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="892b4-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="892b4-105">Вы можете изменять политики конференц-связи с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="892b4-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="892b4-106">Изменение политик конференц-связи с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="892b4-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="892b4-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="892b4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="892b4-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="892b4-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="892b4-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="892b4-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="892b4-110">В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="892b4-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="892b4-111">В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="892b4-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="892b4-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="892b4-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="892b4-113">Изменение политик конференц-связи с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="892b4-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="892b4-114">Чтобы изменить политики Конференции, используйте командлет **Set-ксконференЦингполици** .</span><span class="sxs-lookup"><span data-stu-id="892b4-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="892b4-115">В следующем примере показано изменение значения свойства политики конференц-связи SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="892b4-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="892b4-116">Команда присваивает свойству AllowConferenceRecording значение False:</span><span class="sxs-lookup"><span data-stu-id="892b4-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="892b4-117">Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Set-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="892b4-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

