---
title: Включить парковку вызовов для пользователей в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включить для пользователей парковку вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830959"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="0a26d-103">Включить парковку вызовов для пользователей в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0a26d-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="0a26d-104">Включить для пользователей парковку вызовов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="0a26d-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0a26d-105">По умолчанию парковка вызовов отключена для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a26d-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="0a26d-106">Пользователи не могут припарковать вызовы или получать припаркованные вызовы, пока они не будут включены для парковки вызовов в политике голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0a26d-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="0a26d-107">Парковку вызовов можно включить на глобальном уровне, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a26d-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="0a26d-108">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="0a26d-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="0a26d-109">Если у вас несколько политик голосовой почты, просмотрите все политики, чтобы включить парковку вызовов, а не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="0a26d-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="0a26d-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span><span class="sxs-lookup"><span data-stu-id="0a26d-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="0a26d-111">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="0a26d-112">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0a26d-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0a26d-113">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="0a26d-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="0a26d-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="0a26d-116">В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="0a26d-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a26d-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="0a26d-118">Использование cmdlets для обеспечения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="0a26d-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="0a26d-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0a26d-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="0a26d-120">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="0a26d-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0a26d-121">Запустите:</span><span class="sxs-lookup"><span data-stu-id="0a26d-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="0a26d-122">Например, чтобы включить парковку вызовов для глобальной политики голосовой почты по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0a26d-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="0a26d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0a26d-123">See also</span></span>



[<span data-ttu-id="0a26d-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0a26d-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

