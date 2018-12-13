---
title: Перемещение локальных пользователей в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Узнайте, как перемещение пользователей на Скайп для бизнеса в Интернет.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243999"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="e3590-103">Перемещение локальных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e3590-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="e3590-104">После перемещения пользователей из локальной Скайп для бизнеса в Интернет, пользователь взаимодействует с Скайп для бизнеса в Интернет для его функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="e3590-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="e3590-105">Все контакты, существовавшие в локальной будут доступны в Скайп для бизнеса в Интернет и для обновляются любых существующих собраний, организованной пользователем в будущем, поэтому эти ссылки указывают на Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="e3590-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="e3590-106">Если пользователь включен для аудиоконференции, собраний также будет включать координаты-связи.</span><span class="sxs-lookup"><span data-stu-id="e3590-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="e3590-107">Для перемещения пользователей из локальной среды Скайп для бизнеса в Интернет, используйте командлет Move-CsUser или Скайп для панели управления Business Server, которые являются локальные средства.</span><span class="sxs-lookup"><span data-stu-id="e3590-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="e3590-108">Перед перемещением пользователей, убедитесь, что соблюдаются [Предварительные требования](move-users-between-on-premises-and-cloud.md#prerequisites) для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="e3590-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="e3590-109">Перемещение пользователей с Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e3590-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="e3590-110">Move-CsUser доступен из локальной Скайп для окна командной консоли управления Business PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3590-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e3590-111">Должно иметь полномочия в обоих в локальной среде также как и клиента Office 365, как описано в [необходимые учетные данные администратора](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="e3590-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e3590-112">Можно либо использовать одной учетной записи, имеющей права в обеих сред, или можно запустить Скайп на месте для окна консоли Business Server с использованием учетных данных на месте и использовать `-Credential` параметр, чтобы указать учетные данные для Office 365 Учетная запись с необходимые административные роли Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3590-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="e3590-113">Перемещение пользователя к сети с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="e3590-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="e3590-114">Укажите пользователей для перемещения с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="e3590-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="e3590-115">Укажите параметр - целевой со значением «sipfed.online.lync. <span>com».</span><span class="sxs-lookup"><span data-stu-id="e3590-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e3590-116">Если у вас одну учетную запись с разрешениями, достаточными в обоих на локальную организацию и Office 365, используйте параметр - учетных данных для предоставления учетной записи с достаточные разрешения в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3590-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="e3590-117">Если учетная запись с разрешениями в Office 365 не заканчивается «on.microsoft. <span>com», а затем необходимо указать параметр - HostedMigrationOverrideUrl с правильное значение, как описано в [необходимые учетные данные администратора](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="e3590-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e3590-118">Следующую последовательность командлет можно использовать для перемещения пользователя Скайп для бизнеса в Интернет и предполагается учетные данные Office 365 — это отдельную учетную запись и указано в качестве входных данных для строки Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="e3590-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e3590-119">Перемещение пользователей с Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="e3590-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="e3590-120">Откройте Скайп для элемента управления сервера Business панель приложения.</span><span class="sxs-lookup"><span data-stu-id="e3590-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e3590-121">В левой панели навигации выберите **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e3590-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e3590-122">Используйте **Поиск** , чтобы найти пользователя, которого вы хотите переместить в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="e3590-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="e3590-123">Выберите одного или нескольких и затем в раскрывающемся списке **Действие** над списком, выберите **переместить выбранных пользователей в Скайп для бизнеса в Интернет**.</span><span class="sxs-lookup"><span data-stu-id="e3590-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="e3590-124">В окне мастера нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3590-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e3590-125">При появлении соответствующего запроса, вход в Office 365 с использованием учетной записи, заканчивающиеся на. onmicrosoft.com и имеет достаточные разрешения.</span><span class="sxs-lookup"><span data-stu-id="e3590-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e3590-126">Нажмите кнопку **Далее**, а затем **Далее** еще раз для перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3590-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e3590-127">Обратите внимание на то, что сообщения о состоянии относительно успешное или неудачное предоставляются в верхней части главного приложения панель управления, не в мастере.</span><span class="sxs-lookup"><span data-stu-id="e3590-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3590-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e3590-128">See also</span></span>

[<span data-ttu-id="e3590-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e3590-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)