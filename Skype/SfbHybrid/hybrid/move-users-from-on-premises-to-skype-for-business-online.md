---
title: Перемещение пользователей из локальной среды в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Узнайте, как переместить пользователей в Skype для бизнеса Online.
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305983"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="e533b-103">Перемещение пользователей из локальной среды в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e533b-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="e533b-104">После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует с Skype для бизнеса Online за его функции.</span><span class="sxs-lookup"><span data-stu-id="e533b-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="e533b-105">Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e533b-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="e533b-106">Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.</span><span class="sxs-lookup"><span data-stu-id="e533b-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="e533b-107">Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте Move-CsUser или панель управления Skype для бизнеса Server, которые являются локальной программой.</span><span class="sxs-lookup"><span data-stu-id="e533b-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e533b-108">Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="e533b-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="e533b-109">В рамках подготовки к предстоящему выходу на пенсию Skype для бизнеса Online Корпорация Майкрософт упростит переход организаций на Teams в ближайшем будущем, и больше не будет возможности перейти в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e533b-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="e533b-110">После того как эти изменения станут доступными, при перемещении пользователя из локального в облако пользователям автоматически будет назначен режим TeamsOnly, а собрания из локального помещения автоматически преобразуются в собрания Teams, как если бы переключатель был задан, независимо от того, действительно ли задан `-MoveToTeams` переключатель.</span><span class="sxs-lookup"><span data-stu-id="e533b-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="e533b-111">Мы планируем выпустить эту функцию до фактического выхода на пенсию 31 июля 2021 г.</span><span class="sxs-lookup"><span data-stu-id="e533b-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="e533b-112">В настоящее время, если этот переключатель не указан, пользователи переходят из локального Skype для бизнеса Server в Skype для бизнеса Online, и их режим остается неизменным, что является функциональными возможностями, задокументированными в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e533b-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="e533b-113">Перемещение пользователей с помощью Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e533b-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="e533b-114">Move-CsUser доступно в локальном окне Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e533b-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e533b-115">Вы должны иметь достаточные привилегии как в локальной среде, так и в Microsoft 365 организации, как описано в необходимых административных [учетных данных.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="e533b-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e533b-116">Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для бизнеса Server Management Shell с учетными данными локального доступа и использовать параметр для указания учетных данных для учетной записи Microsoft 365 с необходимой административной `-Credential` ролью.</span><span class="sxs-lookup"><span data-stu-id="e533b-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="e533b-117">Перемещение пользователя в интернет с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="e533b-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="e533b-118">Укажите, что пользователь перемещается с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="e533b-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="e533b-119">Укажите параметр -Target со значением sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="e533b-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e533b-120">Если у вас нет одной учетной записи с достаточными разрешениями как на локальном, так и на Microsoft 365, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e533b-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="e533b-121">Если учетная запись с разрешениями в Microsoft 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="e533b-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e533b-122">Для перемещения пользователя в Skype для бизнеса Online можно использовать следующую последовательность Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e533b-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="e533b-123">Предполагается, что Microsoft 365 учетная запись является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.</span><span class="sxs-lookup"><span data-stu-id="e533b-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="e533b-124">Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential.</span><span class="sxs-lookup"><span data-stu-id="e533b-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="e533b-125">Администратору будет предложено использовать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e533b-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e533b-126">Перемещение пользователей с Skype для бизнеса Server панели управления</span><span class="sxs-lookup"><span data-stu-id="e533b-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="e533b-127">Откройте приложение Skype для бизнеса Server панели управления.</span><span class="sxs-lookup"><span data-stu-id="e533b-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e533b-128">В левой навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e533b-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e533b-129">Используйте **Поиск,** чтобы найти пользователя(ы) вы хотели бы перейти в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e533b-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="e533b-130">Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных пользователей в **Skype для бизнеса Online**. </span><span class="sxs-lookup"><span data-stu-id="e533b-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="e533b-131">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e533b-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e533b-132">В случае запроса вопишитесь Microsoft 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="e533b-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e533b-133">Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="e533b-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e533b-134">Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="e533b-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="e533b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e533b-135">See also</span></span>

[<span data-ttu-id="e533b-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e533b-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
