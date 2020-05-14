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
description: Сведения о том, как перемещать пользователей в Skype для бизнеса Online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221119"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="77321-103">Перемещение пользователей из локальной среды в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="77321-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="77321-104">После того как вы перемещаете пользователя из локальной среды в Skype для бизнеса Online, пользователь взаимодействует с Skype для бизнеса Online для своих функций.</span><span class="sxs-lookup"><span data-stu-id="77321-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="77321-105">Все контакты, которые существовали в локальной среде, будут доступны в Skype для бизнеса Online, а все существующие собрания, упорядоченные для будущего пользователя, будут обновлены, поэтому ссылки указывают на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="77321-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="77321-106">Если пользователю разрешено проведение голосовой конференц-связи, собрания также будут включать координаты для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="77321-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="77321-107">Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте командлет Move-CsUser или панель управления Skype для бизнеса Server, оба из которых являются локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="77321-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="77321-108">Прежде чем перемещать пользователей, обязательно изучите [необходимые условия](move-users-between-on-premises-and-cloud.md#prerequisites) для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="77321-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="77321-109">Перемещение пользователей с помощью Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="77321-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="77321-110">Move-CsUser доступен из локального окна PowerShell для командной консоли Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="77321-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="77321-111">У вас должны быть достаточные права как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="77321-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="77321-112">Можно использовать одну учетную запись с правами в обеих средах или можно запустить локальное окно командной консоли Skype для бизнеса Server с локальными учетными данными и использовать `-Credential` параметр для указания учетных данных для учетной записи Microsoft 365 или Office 365 с необходимой административной ролью.</span><span class="sxs-lookup"><span data-stu-id="77321-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="77321-113">Чтобы переместить пользователя в Интернет с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="77321-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="77321-114">Укажите пользователя для перемещения с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="77321-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="77321-115">Укажите параметр-target со значением "sipfed. Online. Lync. <span> com ".</span><span class="sxs-lookup"><span data-stu-id="77321-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="77321-116">Если у вас нет одной учетной записи с достаточными разрешениями в локальной среде и Office 365, используйте параметр – Credential для предоставления учетной записи с достаточными разрешениями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="77321-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="77321-117">Если учетная запись с разрешениями в Office 365 не заканчивается на ". onmicrosoft <span> ". com ", то необходимо указать параметр-Хостедмигратионоверридеурл с правильным значением, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="77321-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="77321-118">Для перемещения пользователя в Skype для бизнеса Online можно использовать следующую последовательность командлетов.</span><span class="sxs-lookup"><span data-stu-id="77321-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="77321-119">Предполагается, что учетные данные Microsoft 365 или Office 365 являются отдельной учетной записью и предоставляются в качестве входных данных для приглашения Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="77321-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="77321-120">Если учетная запись администратора включает в себя MFA (многофакторная проверка подлинности), не указывайте параметр-Credential.</span><span class="sxs-lookup"><span data-stu-id="77321-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="77321-121">Администратору потребуется ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="77321-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="77321-122">Перемещение пользователей с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77321-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="77321-123">Откройте приложение панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77321-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="77321-124">В области навигации слева выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="77321-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="77321-125">Используйте **Find** , чтобы найти пользователей, которых вы хотите переместить в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="77321-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="77321-126">Выберите пользователей, а затем в раскрывающемся списке **действий** над списком выберите **переместить выбранных пользователей в Skype для бизнеса Online**.</span><span class="sxs-lookup"><span data-stu-id="77321-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="77321-127">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77321-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="77321-128">При появлении соответствующего запроса войдите в Microsoft 365 или Office 365 с помощью учетной записи, которая оканчивается на. onmicrosoft.com и обладает достаточными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="77321-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="77321-129">Нажмите кнопку **Далее**, а **затем еще раз,** чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="77321-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="77321-130">Обратите внимание на то, что сообщения о состоянии Success или Failure представлены в верхней части главного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="77321-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="77321-131">См. также</span><span class="sxs-lookup"><span data-stu-id="77321-131">See also</span></span>

[<span data-ttu-id="77321-132">Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="77321-132">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
