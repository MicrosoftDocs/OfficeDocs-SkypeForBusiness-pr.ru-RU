---
title: Перемещение пользователей из облака в локальную среду
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
description: Сведения о том, как переместить пользователей из Skype для бизнеса Online в локальную среду.
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779675"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="032d1-103">Перемещение пользователей из облака в локальную среду</span><span class="sxs-lookup"><span data-stu-id="032d1-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="032d1-104">При необходимости вы можете переместить пользователя, который ранее был перенесен из локальной сети в облако (только в Skype для бизнеса Online или Teams), обратно в локальную среду.</span><span class="sxs-lookup"><span data-stu-id="032d1-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="032d1-105">Чтобы переместить пользователей из Skype для бизнеса Online или Теамсонли в режим локального развертывания Skype для бизнеса Server, используйте командлет Move-CsUser или панель управления Skype для бизнеса Server, оба из которых являются локальными средствами.</span><span class="sxs-lookup"><span data-stu-id="032d1-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="032d1-106">При перемещении пользователя обратно в локальное развертывание необходимо выбрать пул, в который необходимо переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="032d1-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="032d1-107">Если пользователь ранее находился в режиме Теамсонли и вы используете более раннюю версию, чем Skype для бизнеса Server 2015 с 8, то необходимо также удалить назначение режима Теамсонли Теамсупградеполици для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="032d1-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="032d1-108">Локальные пользователи не должны иметь режим = Теамсонли.</span><span class="sxs-lookup"><span data-stu-id="032d1-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="032d1-109">Последующие версии Skype для бизнеса Server автоматически удаляют это назначение.</span><span class="sxs-lookup"><span data-stu-id="032d1-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="032d1-110">Дополнительные сведения см. в разделе [Grant – кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span><span class="sxs-lookup"><span data-stu-id="032d1-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="032d1-111">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="032d1-111">Prerequisites</span></span>

- <span data-ttu-id="032d1-112">Для Организации необходимо правильно настроить подключение Azure AD и синхронизировать все нужные атрибуты для пользователя, как описано в разделе [Configure Azure AD Connect](configure-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="032d1-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="032d1-113">Пользователь, который перемещается из сети обратно в локальную среду, должен существовать в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="032d1-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="032d1-114">Необходимо настроить гибридную среду Skype для бизнеса, как описано в разделе [Настройка гибридной среды Skype для бизнеса](configure-federation-with-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="032d1-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="032d1-115">Перемещение пользователей обратно в локальную среду</span><span class="sxs-lookup"><span data-stu-id="032d1-115">Moving users back to on-premises</span></span>

<span data-ttu-id="032d1-116">После того как вы перемещаете пользователя из облака обратно в локальную среду:</span><span class="sxs-lookup"><span data-stu-id="032d1-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="032d1-117">Пользователь взаимодействует с развертыванием Skype для бизнеса Server для своих функций.</span><span class="sxs-lookup"><span data-stu-id="032d1-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="032d1-118">Все контакты, существовавшие в Skype для бизнеса Online или в Teams, переносятся в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="032d1-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="032d1-119">Два набора контактов сливаются, а затем переносятся обратно в локальную среду.</span><span class="sxs-lookup"><span data-stu-id="032d1-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="032d1-120">Кроме того, в Teams остались контакты, которые уже существуют в Teams.</span><span class="sxs-lookup"><span data-stu-id="032d1-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="032d1-121">Если пользователь также использует Teams, он не сможет взаимодействовать с пользователями Skype для бизнеса, а также не сможет общаться с пользователями в федеративных организациях.</span><span class="sxs-lookup"><span data-stu-id="032d1-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="032d1-122">Собрания в Skype для бизнеса Online *не* переносятся обратно в локальную среду.</span><span class="sxs-lookup"><span data-stu-id="032d1-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="032d1-123">Пользователи должны либо перепланировать собрания, либо, при необходимости, воспользоваться [средством миграции собраний](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span><span class="sxs-lookup"><span data-stu-id="032d1-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="032d1-124">Перемещение пользователей с помощью Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="032d1-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="032d1-125">Move-CsUser доступен из локального окна PowerShell для командной консоли Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="032d1-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="032d1-126">У вас должны быть достаточные права как в локальной среде, так и в организации Office 365, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="032d1-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="032d1-127">Можно использовать одну учетную запись с правами в обеих средах или можно запустить локальное окно командной консоли Skype для бизнеса Server с локальными учетными данными и использовать `-Credential` параметр для указания учетных данных для учетной записи Office 365 с необходимой административной ролью Office 365.</span><span class="sxs-lookup"><span data-stu-id="032d1-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="032d1-128">Чтобы переместить пользователя в локальную среду с помощью Move — CsUser:</span><span class="sxs-lookup"><span data-stu-id="032d1-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="032d1-129">Укажите пользователя для перемещения с помощью параметра Identity.</span><span class="sxs-lookup"><span data-stu-id="032d1-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="032d1-130">Укажите параметр – target с полным доменным именем нужного локального пула, в котором будет размещаться пользователь.</span><span class="sxs-lookup"><span data-stu-id="032d1-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="032d1-131">Если у вас нет одной учетной записи с достаточными разрешениями как в локальной среде, так и в Office 365, используйте параметр – Credential, чтобы предоставить учетную запись с достаточными разрешениями в Office 365.</span><span class="sxs-lookup"><span data-stu-id="032d1-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="032d1-132">Если учетная запись с разрешениями в Office 365 не заканчивается на "on.microsoft.com", необходимо указать параметр – Хостедмигратионоверридеурл, указав правильное значение, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="032d1-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="032d1-133">Следующая последовательность командлетов может использоваться для перемещения пользователя в Skype для бизнеса Server и предполагается, что учетные данные Office 365 являются отдельной учетной записью и предоставляются в качестве входных данных для приглашения Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="032d1-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="032d1-134">Перемещение пользователей с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="032d1-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="032d1-135">Откройте приложение панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="032d1-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="032d1-136">В области навигации слева выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="032d1-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="032d1-137">Используйте **Find** , чтобы найти пользователей, которых вы хотите переместить в локальную систему.</span><span class="sxs-lookup"><span data-stu-id="032d1-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="032d1-138">Выберите пользователей, а затем в раскрывающемся списке **действий** над списком выберите **переместить выбранных пользователей в локальную**среду.</span><span class="sxs-lookup"><span data-stu-id="032d1-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="032d1-139">В мастере выберите пул пользователей, на котором будет размещен пользователь, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="032d1-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="032d1-140">При появлении соответствующего запроса войдите в Office 365, используя учетную запись, которая оканчивается на. onmicrosoft.com и обладает достаточными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="032d1-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="032d1-141">Нажмите кнопку **Далее**, а **затем еще раз,** чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="032d1-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="032d1-142">Обратите внимание на то, что сообщения о состоянии Success или Failure представлены в верхней части главного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="032d1-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="032d1-143">Удаление режима Теамсонли</span><span class="sxs-lookup"><span data-stu-id="032d1-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="032d1-144">Если вы используете версию, предшествующую Skype для бизнеса 2015 с 8, и пользователь перемещается обратно в локальную среду в режиме Теамсонли, необходимо удалить экземпляр Упградетотеамс `TeamsUpgradePolicy` перед перемещением локального пользователя.</span><span class="sxs-lookup"><span data-stu-id="032d1-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="032d1-145">Вы можете либо явно предоставить политику в другом режиме, либо просто удалить существующее назначение политики для этого пользователя, чтобы использовать глобальную политику (если глобальная политика клиента не Упградетотеамс).</span><span class="sxs-lookup"><span data-stu-id="032d1-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="032d1-146">Чтобы удалить назначение пользователя Теамсупградеполици, выполните следующий командлет в окне PowerShell для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="032d1-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="032d1-147">Кроме того, чтобы назначить другой экземпляр Теамсупградеполици, для которого не задан режим = Теамсонли, можно указать имя нужного экземпляра в качестве значения параметра PolicyName в командлете.</span><span class="sxs-lookup"><span data-stu-id="032d1-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="032d1-148">Чтобы просмотреть список доступных экземпляров Теамсупградеполици, выполните командлет Get – Кстеамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="032d1-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="032d1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="032d1-149">See also</span></span>

[<span data-ttu-id="032d1-150">Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="032d1-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
