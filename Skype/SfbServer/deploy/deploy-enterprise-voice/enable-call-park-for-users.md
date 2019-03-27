---
title: Включение парковки вызовов для пользователей в Скайп для бизнеса
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включите пользователей для парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 98b02294beb633e5d9a0147fcce7257a4497753d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894545"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="54f13-103">Включение парковки вызовов для пользователей в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="54f13-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="54f13-104">Включите пользователей для парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54f13-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="54f13-105">По умолчанию парковка вызовов отключена для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="54f13-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="54f13-106">Пользователи не могут приостанавливать вызовы и возобновлять их включены для парковки вызовов в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54f13-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="54f13-107">Можно включить парковки вызовов на глобальном уровне или на уровне сайта или уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="54f13-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="54f13-108">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь – перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="54f13-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="54f13-109">Если у вас несколько политик голосовой связи, просмотрите все политики для включения парковки вызовов, не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="54f13-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="54f13-110">Чтобы использовать Скайп для панели управления сервера Business Включение парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="54f13-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="54f13-111">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="54f13-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="54f13-112">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="54f13-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="54f13-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="54f13-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="54f13-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="54f13-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="54f13-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="54f13-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="54f13-116">В разделе **Функции звонков** установите флажок **Разрешить парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="54f13-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="54f13-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="54f13-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="54f13-118">Использование командлетов для включение парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="54f13-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="54f13-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54f13-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="54f13-120">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="54f13-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="54f13-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="54f13-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="54f13-122">Например, чтобы включить парковки вызовов для голосовой связи глобальной политики по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="54f13-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="54f13-123">См. также</span><span class="sxs-lookup"><span data-stu-id="54f13-123">See also</span></span>



[<span data-ttu-id="54f13-124">Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="54f13-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

