---
title: Включение и отключение конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Сводка: Узнайте, как использовать панель управления или командной консоли для включения или отключения конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 47393140e41277aef3ec137ee3f1c6a96fa9efca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983863"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="fab65-103">Включение и отключение конференц-связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fab65-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="fab65-104">**Сводка:** Узнайте, как использовать панель управления или командной консоли для включения или отключения конференц-связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fab65-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="fab65-105">Конференц-связь можно включить с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="fab65-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fab65-106">Включение или отключение конференц-связи с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="fab65-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fab65-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fab65-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="fab65-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fab65-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fab65-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fab65-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="fab65-110">В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fab65-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="fab65-p101">Чтобы разрешить пользователям присоединяться к собраниям по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="fab65-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="fab65-113">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="fab65-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fab65-114">Включение или отключение конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="fab65-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="fab65-115">Для включения или отключения конференц-связи с телефонным подключением используется командлет **Set-CsConferencingPolicy** с параметром EnableDialInConferencing (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="fab65-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="fab65-116">Для получения дополнительных сведений см [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fab65-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

