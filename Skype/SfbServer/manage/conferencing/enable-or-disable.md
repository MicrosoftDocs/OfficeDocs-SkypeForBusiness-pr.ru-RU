---
title: Включить или отключить диалоговое общение в Skype для бизнеса Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: Сводка. Узнайте, как использовать панель управления или панель управления, чтобы включить или отключить диалоговое общение в Skype для бизнеса Server.
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119468"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="7c5c8-103">Включить или отключить диалоговое общение в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7c5c8-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="7c5c8-104">**Сводка:** Узнайте, как использовать панель управления или панель управления, чтобы включить или отключить диалоговое общение в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="7c5c8-105">Вы можете включить диалоговое видеоконференцию с помощью панели управления Skype для бизнес-серверов или с помощью панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7c5c8-106">Включить или отключить диалоговое общение с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="7c5c8-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7c5c8-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7c5c8-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7c5c8-109">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="7c5c8-110">В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="7c5c8-p101">Чтобы разрешить пользователям присоединяться к собранием по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="7c5c8-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="7c5c8-113">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c5c8-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7c5c8-114">Включить или отключить диалоговое общение с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="7c5c8-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7c5c8-115">Чтобы включить или отключить диалоговое видеоконференцию, используйте комлет **Set-CsConferencingPolicy** с параметром EnableDialInConferencing следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c5c8-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="7c5c8-116">Дополнительные сведения см. в дополнительных сведениях [в set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7c5c8-116">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
