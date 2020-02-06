---
title: Включение и отключение конференц-связи с телефонным подключением в Skype для бизнеса Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Сводка: сведения о том, как с помощью панели управления или консоли управления включить или отключить Конференц-связь с телефонным подключением в Skype для бизнеса Server.'
ms.openlocfilehash: 8ce0fcfb4f785397075aa9d7b89b94eacb096167
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818560"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="58672-103">Включение и отключение конференц-связи с телефонным подключением в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="58672-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="58672-104">**Сводка:** В этой статье объясняется, как с помощью панели управления или консоли управления включить или отключить Конференц-связь с телефонным подключением в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58672-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="58672-105">Вы можете включить Конференц-связь с телефонным подключением с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58672-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="58672-106">Включение и отключение конференц-связи с телефонным подключением с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="58672-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="58672-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="58672-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="58672-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58672-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="58672-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="58672-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="58672-110">В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="58672-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="58672-p101">Чтобы разрешить пользователям присоединяться к собраниям по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="58672-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="58672-113">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="58672-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="58672-114">Включение и отключение конференц-связи с телефонным подключением с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="58672-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="58672-115">Для включения или отключения конференц-связи с телефонным подключением используется командлет **Set-CsConferencingPolicy** с параметром EnableDialInConferencing (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="58672-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="58672-116">Дополнительные сведения можно найти в разделе [Set-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="58672-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

