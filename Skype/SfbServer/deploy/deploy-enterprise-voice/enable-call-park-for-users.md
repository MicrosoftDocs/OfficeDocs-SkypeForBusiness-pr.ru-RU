---
title: Включение для пользователей приостановки звонков в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включите пользователей для парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 88385ae1332905ae242cf0b4a5002f96b336a1af
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500453"
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="a9612-103">Включение для пользователей приостановки звонков в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="a9612-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="a9612-104">Включите пользователей для парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a9612-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a9612-105">По умолчанию парковка вызовов отключена для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a9612-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="a9612-106">Пользователи не могут приостанавливать вызовы и возобновлять их включены для парковки вызовов в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a9612-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="a9612-107">Можно включить парковки вызовов на глобальном уровне или на уровне сайта или уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="a9612-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="a9612-108">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь – перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="a9612-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="a9612-109">Если у вас несколько политик голосовой связи, просмотрите все политики для включения парковки вызовов, не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="a9612-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="a9612-110">Чтобы использовать Скайп для панели управления сервера Business Включение парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="a9612-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="a9612-111">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="a9612-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="a9612-112">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="a9612-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a9612-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a9612-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="a9612-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a9612-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="a9612-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a9612-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="a9612-116">В разделе **Функции звонков** установите флажок **Разрешить парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a9612-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="a9612-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a9612-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="a9612-118">Использование командлетов для включение парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="a9612-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="a9612-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a9612-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="a9612-120">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a9612-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a9612-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a9612-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="a9612-122">Например, чтобы включить парковки вызовов для голосовой связи глобальной политики по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a9612-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="a9612-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a9612-123">See also</span></span>

[<span data-ttu-id="a9612-124">Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="a9612-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)