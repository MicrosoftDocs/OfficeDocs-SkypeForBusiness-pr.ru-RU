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
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863200"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="d9afb-103">Перемещение пользователей из локальной среды в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d9afb-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="d9afb-104">После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует с Skype для бизнеса Online за его функции.</span><span class="sxs-lookup"><span data-stu-id="d9afb-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="d9afb-105">Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d9afb-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="d9afb-106">Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.</span><span class="sxs-lookup"><span data-stu-id="d9afb-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="d9afb-107">Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте Move-CsUser или панель управления Skype для бизнеса Server, которые являются локальной программой.</span><span class="sxs-lookup"><span data-stu-id="d9afb-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="d9afb-108">Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="d9afb-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="d9afb-109">В рамках подготовки к предстоящему выходу на пенсию Skype для бизнеса Online корпорация Майкрософт упростила переход организаций на Teams.</span><span class="sxs-lookup"><span data-stu-id="d9afb-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="d9afb-110">При перемещении пользователей из локального в облако пользователям автоматически назначен режим TeamsOnly, а их собрания из локального помещения автоматически преобразуются в Teams собрания, как если бы коммутатор был задан, независимо от того, был ли на самом деле указан `-MoveToTeams` переключатель.</span><span class="sxs-lookup"><span data-stu-id="d9afb-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="d9afb-111">До выхода на пенсию Skype для бизнеса Online организации, которые требуют перемещения пользователей из локального в Skype для бизнеса Online, могут достичь этого за два шага, обновив режим пользователя после перехода пользователя в *TeamsOnly.*</span><span class="sxs-lookup"><span data-stu-id="d9afb-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="d9afb-112">Однако в ближайшее время невозможно будет назначить режим, кроме TeamsOnly, пользователям, уехав в облако.</span><span class="sxs-lookup"><span data-stu-id="d9afb-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="d9afb-113">Перемещение пользователей с помощью Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d9afb-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="d9afb-114">Move-CsUser доступно в локальном окне Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9afb-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="d9afb-115">Вы должны иметь достаточные привилегии как в локальной среде, так и в Microsoft 365 организации, как описано в необходимых административных [учетных данных.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="d9afb-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="d9afb-116">Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для бизнеса Server Management Shell с учетными данными локального доступа и использовать параметр для указания учетных данных для учетной записи Microsoft 365 с необходимой административной `-Credential` ролью.</span><span class="sxs-lookup"><span data-stu-id="d9afb-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="d9afb-117">Перемещение пользователя в интернет с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="d9afb-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="d9afb-118">Укажите, что пользователь перемещается с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="d9afb-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="d9afb-119">Укажите параметр -Target со значением sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="d9afb-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="d9afb-120">Если у вас нет одной учетной записи с достаточными разрешениями как на локальном, так и на Microsoft 365, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9afb-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="d9afb-121">Если учетная запись с разрешениями в Microsoft 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="d9afb-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="d9afb-122">Следующая последовательность cmdlet может быть использована для перемещения пользователя Skype для бизнеса Online и назначает режим по умолчанию клиента пользователю.</span><span class="sxs-lookup"><span data-stu-id="d9afb-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="d9afb-123">Предполагается, что Microsoft 365 учетная запись является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.</span><span class="sxs-lookup"><span data-stu-id="d9afb-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="d9afb-124">Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential.</span><span class="sxs-lookup"><span data-stu-id="d9afb-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="d9afb-125">Администратору будет предложено использовать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d9afb-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="d9afb-126">Перемещение пользователей с Skype для бизнеса Server панели управления и Teams Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="d9afb-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="d9afb-127">Откройте приложение Skype для бизнеса Server панели управления.</span><span class="sxs-lookup"><span data-stu-id="d9afb-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="d9afb-128">В левой навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d9afb-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="d9afb-129">Используйте **Поиск,** чтобы найти пользователя(ы) вы хотели бы перейти в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d9afb-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="d9afb-130">Выберите пользователя(ы), а затем  из выпадаемой ниже списка действия выберите Перемещение выбранных пользователей в Skype для бизнеса **Online** или Перемещение выбранных **пользователей в Teams**.</span><span class="sxs-lookup"><span data-stu-id="d9afb-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="d9afb-131">Любой из вариантов сначала перемещает пользователя в режим TeamsOnly, но после перемещения можно назначить другой режим.</span><span class="sxs-lookup"><span data-stu-id="d9afb-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="d9afb-132">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9afb-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="d9afb-133">В случае запроса вопишитесь Microsoft 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="d9afb-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="d9afb-134">Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9afb-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="d9afb-135">Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="d9afb-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="d9afb-136">Откройте центр администрирования Teams и выберите "Пользователи" в левой навигации.</span><span class="sxs-lookup"><span data-stu-id="d9afb-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="d9afb-137">Щелкните нужный пользователь в listview.</span><span class="sxs-lookup"><span data-stu-id="d9afb-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="d9afb-138">Нажмите **кнопку Изменить** в разделе, в Teams **обновления.**</span><span class="sxs-lookup"><span data-stu-id="d9afb-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="d9afb-139">В правом флауате выберите нужный режим сосуществования и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d9afb-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="d9afb-140">См. также</span><span class="sxs-lookup"><span data-stu-id="d9afb-140">See also</span></span>

[<span data-ttu-id="d9afb-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="d9afb-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
