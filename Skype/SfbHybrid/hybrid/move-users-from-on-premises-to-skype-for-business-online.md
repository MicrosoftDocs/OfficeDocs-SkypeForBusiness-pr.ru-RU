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
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110625"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="3833f-103">Перемещение пользователей из локальной среды в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3833f-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="3833f-104">После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует со Skype для бизнеса Online для его функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="3833f-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="3833f-105">Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3833f-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="3833f-106">Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.</span><span class="sxs-lookup"><span data-stu-id="3833f-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="3833f-107">Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте либо Move-CsUser, либо панель управления Skype для бизнес-серверов, которые являются средствами локального использования.</span><span class="sxs-lookup"><span data-stu-id="3833f-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="3833f-108">Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="3833f-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="3833f-109">Перемещение пользователей с помощью Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="3833f-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="3833f-110">Move-CsUser доступно в локальном окне Skype для управления бизнесом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3833f-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="3833f-111">Вы должны иметь достаточные привилегии как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных.</span><span class="sxs-lookup"><span data-stu-id="3833f-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="3833f-112">Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для управления бизнес-серверами с учетными данными локального сервера и использовать параметр для указания учетных данных для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.</span><span class="sxs-lookup"><span data-stu-id="3833f-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="3833f-113">Перемещение пользователя в интернет с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="3833f-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="3833f-114">Укажите, что пользователь перемещается с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="3833f-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="3833f-115">Укажите параметр -Target со значением sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="3833f-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="3833f-116">Если в помещении и Office 365 нет одной учетной записи с достаточными разрешениями, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3833f-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="3833f-117">Если учетная запись с разрешениями в Office 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="3833f-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="3833f-118">Следующая последовательность смещается для перемещения пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3833f-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="3833f-119">Предполагается, что учетная запись Microsoft 365 или Office 365 является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.</span><span class="sxs-lookup"><span data-stu-id="3833f-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="3833f-120">Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential.</span><span class="sxs-lookup"><span data-stu-id="3833f-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="3833f-121">Администратору будет предложено использовать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3833f-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="3833f-122">Перемещение пользователей с панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="3833f-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="3833f-123">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="3833f-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="3833f-124">В левой навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3833f-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="3833f-125">Используйте **Поиск,** чтобы найти пользователя(ы) вы хотите перейти в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3833f-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="3833f-126">Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных пользователей **в Skype для бизнеса Online**. </span><span class="sxs-lookup"><span data-stu-id="3833f-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="3833f-127">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3833f-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="3833f-128">При запросе вопишитесь в Microsoft 365 или Office 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="3833f-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="3833f-129">Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="3833f-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="3833f-130">Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="3833f-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="3833f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3833f-131">See also</span></span>

[<span data-ttu-id="3833f-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="3833f-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)