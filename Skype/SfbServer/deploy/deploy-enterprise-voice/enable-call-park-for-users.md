---
title: Включение приостановки звонков для пользователей в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включение пользователей на приостановку звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240377"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="280ee-103">Включение приостановки звонков для пользователей в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="280ee-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="280ee-104">Включение пользователей на приостановку звонков в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="280ee-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="280ee-105">По умолчанию приостановление звонков для всех пользователей отключено.</span><span class="sxs-lookup"><span data-stu-id="280ee-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="280ee-106">Пользователи не могут приостановить звонки или получить припаркованные звонки, пока они не будут включены в политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="280ee-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="280ee-107">Вы можете включить приостановку звонков в глобальной области или в области действия сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="280ee-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="280ee-108">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь – перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="280ee-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="280ee-109">Если у вас несколько политик голосовой связи, проверьте все политики, чтобы включить приостановку звонков, а не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="280ee-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="280ee-110">Использование панели управления Skype для бизнеса Server для поддержки приостановки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="280ee-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="280ee-111">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="280ee-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="280ee-112">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="280ee-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="280ee-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="280ee-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="280ee-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="280ee-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="280ee-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="280ee-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="280ee-116">В разделе **Функции звонков** установите флажок **Разрешить парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="280ee-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="280ee-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="280ee-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="280ee-118">Использование командлетов для поддержки приостановки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="280ee-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="280ee-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="280ee-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="280ee-120">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="280ee-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="280ee-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="280ee-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="280ee-122">Например, чтобы включить приостановку звонков для глобальной политики голосовой связи по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="280ee-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="280ee-123">См. также</span><span class="sxs-lookup"><span data-stu-id="280ee-123">See also</span></span>



[<span data-ttu-id="280ee-124">Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="280ee-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

