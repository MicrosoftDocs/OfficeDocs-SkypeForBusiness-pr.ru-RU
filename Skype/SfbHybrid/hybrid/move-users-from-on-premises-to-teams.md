---
title: Перемещение пользователей Skype для бизнеса Server 2019 г. в Teams
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
description: Сводка. Сведения о переносе параметров пользователей и переносе пользователей в Teams.
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856308"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="e8013-103">Перемещение пользователей из локальной среды в Teams</span><span class="sxs-lookup"><span data-stu-id="e8013-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="e8013-104">Когда пользователь перемещается из локального помещения в Teams Только, Skype для бизнеса дома пользователя перемещается из локального в online и пользователю назначено TeamsUpgradePolicy с mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e8013-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="e8013-105">После того как пользователь перемещается из локального в режим TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="e8013-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="e8013-106">Все входящие вызовы и чаты от других пользователей (Skype для бизнеса или Teams) будут Teams клиента пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8013-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="e8013-107">Пользователь сможет скооперироваться с другими пользователями, которые используют Skype для бизнеса (будь то в Интернете или в помещении).</span><span class="sxs-lookup"><span data-stu-id="e8013-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="e8013-108">Пользователь сможет общаться с пользователями в федерадных организациях.</span><span class="sxs-lookup"><span data-stu-id="e8013-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="e8013-109">Новые собрания, запланированные этим пользователем, Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="e8013-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="e8013-110">Пользователь по-прежнему может присоединяться к Skype для бизнеса собраниям.</span><span class="sxs-lookup"><span data-stu-id="e8013-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="e8013-111">Запланированные на будущее собрания пользователя будут перенесены из локального в Teams.</span><span class="sxs-lookup"><span data-stu-id="e8013-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="e8013-112">Контакты, которые существовали на месте, доступны в Teams вскоре после того, как пользователь впервые вошел в систему.</span><span class="sxs-lookup"><span data-stu-id="e8013-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="e8013-113">Пользователи не могут инициировать звонки или чаты из Skype для бизнеса и не могут планировать новые собрания в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e8013-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="e8013-114">Если они попытаются открыть Skype для бизнеса клиента, они будут перенаправлены для использования Teams, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e8013-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="e8013-115">Если клиент Teams не установлен, он будет направлен в веб-версию Teams браузера.</span><span class="sxs-lookup"><span data-stu-id="e8013-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="e8013-116">![Сообщение перенаправление пользователя на Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="e8013-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="e8013-117">Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="e8013-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="e8013-118">Также обязательно просмотрите руководство по миграции и [совместной](/microsoftteams/migration-interop-guidance-for-teams-with-skype)работы для организаций, использующих Teams вместе с Skype для бизнеса .</span><span class="sxs-lookup"><span data-stu-id="e8013-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="e8013-119">Единый магазин контактов должен быть отключен на учетной записи SfB на преме, чтобы контакт был перемещен в Teams.</span><span class="sxs-lookup"><span data-stu-id="e8013-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>

> [!IMPORTANT]
><span data-ttu-id="e8013-120">При перемещении пользователя из локального облака в облако с помощью Move-CsUser пользователям автоматически назначен режим TeamsOnly, а собрания из локального помещения автоматически преобразуются в Teams собрания независимо от того, задан ли `-MoveToTeams` переключатель.</span><span class="sxs-lookup"><span data-stu-id="e8013-120">When moving a user from on-premises to the cloud with Move-CsUser, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automatically converted to Teams meetings, regardless of whether the `-MoveToTeams` switch is actually specified.</span></span> <span data-ttu-id="e8013-121">(Это включает миграции с Lync Server 2013, у которого никогда не было `-MoveToTeams` переключателя.)  Ранее, если этот переключатель не был указан, пользователи переходили из локального Skype для бизнеса Server в Skype для бизнеса Online, и их режим остался неизменным.</span><span class="sxs-lookup"><span data-stu-id="e8013-121">(This includes migrations from Lync Server 2013, which never had the `-MoveToTeams` switch.)  Previously if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="e8013-122">Это недавно было изменено при подготовке к выходу на пенсию Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e8013-122">This has recently been changed in preparation for retirement of Skype for Business Online.</span></span>


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="e8013-123">Перемещение пользователя непосредственно из Skype для бизнеса в Teams только</span><span class="sxs-lookup"><span data-stu-id="e8013-123">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="e8013-124">Средства администрирования в Skype для бизнеса Server и Lync Server 2013 позволяют перемещать пользователей из локального режима в режим TeamsOnly одним шагом с помощью командлета Move-CsUser PowerShell или панели управления Skype для бизнеса Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e8013-124">The on-premises admin tools in Skype for Business Server and Lync Server 2013 enable you to move users from on premises to TeamsOnly mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span> <span data-ttu-id="e8013-125">Теперь не требуется указывать переключатель и поведение, чтобы перейти непосредственно из помещения в Teams Только теперь автоматически, независимо от того, какая версия Skype для бизнеса Server или `-MoveToTeams` Lync Server используется.</span><span class="sxs-lookup"><span data-stu-id="e8013-125">It is no longer required to specify the `-MoveToTeams` switch and the behavior to move directly from on premises to Teams Only is now automatic, regardless of which version of Skype for Business Server or Lync Server is used.</span></span> 

<span data-ttu-id="e8013-126">Вы должны иметь достаточные привилегии как в локальной среде, так и в облачной службе (Microsoft 365 или Office 365), как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных.</span><span class="sxs-lookup"><span data-stu-id="e8013-126">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e8013-127">Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для бизнеса Server Management Shell с учетными данными локального доступа и использовать параметр для указания учетных данных для Microsoft 365 с необходимой административной `-Credential` ролью.</span><span class="sxs-lookup"><span data-stu-id="e8013-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 with the necessary administrative role.</span></span>

<span data-ttu-id="e8013-128">Кроме того, необходимо убедиться, что пользователю была предоставлена лицензия на Teams (в дополнение к Skype для бизнеса Online).</span><span class="sxs-lookup"><span data-stu-id="e8013-128">In addition, you must ensure the user has been granted a license for Teams (in addition to Skype for Business Online).</span></span> <span data-ttu-id="e8013-129">Не отключать лицензию Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e8013-129">Do not disable the Skype for Business Online license.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="e8013-130">Переместите Teams с Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e8013-130">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="e8013-131">Move-CsUser можно получить в локальном окне Skype для бизнеса Server PowerShell с оболочкой управления или в окне PowerShell для управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8013-131">Move-CsUser is available from an on-premises Skype for Business Server Management Shell PowerShell window or from a Lync Server Management Shell PowerShell window.</span></span> <span data-ttu-id="e8013-132">Перемещение пользователя в режим TeamsOnly с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="e8013-132">To move a user to TeamsOnly mode using Move-CsUser:</span></span>
- <span data-ttu-id="e8013-133">Укажите пользователя для перемещения с помощью `Identity` параметра.</span><span class="sxs-lookup"><span data-stu-id="e8013-133">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="e8013-134">Укажите `-Target` параметр со значением sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="e8013-134">Specify the `-Target` parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e8013-135">Если у вас нет одной учетной записи с достаточными разрешениями как на локальной, так и на облачной службе (Microsoft 365), используйте этот параметр, чтобы предоставить учетную запись с достаточными `-credential` разрешениями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8013-135">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365), use the `-credential` parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="e8013-136">Если учетная запись с разрешениями в Microsoft 365 не заканчивается в onmicrosoft. <span> com", необходимо указать параметр с правильным значением, как описано в `-HostedMigrationOverrideUrl` [необходимых административных учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="e8013-136">If the account with permissions in Microsoft 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e8013-137">Следующая последовательность командлетов может использоваться для перемещения пользователя в TeamsOnly и предполагает, что учетная запись Microsoft 365 является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.</span><span class="sxs-lookup"><span data-stu-id="e8013-137">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span> <span data-ttu-id="e8013-138">Поведение одно и то же, указывается переключатель `-MoveToTeams` или нет.</span><span class="sxs-lookup"><span data-stu-id="e8013-138">The behavior is the same whether `-MoveToTeams` switch is specified or not.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="e8013-139">Поскольку существуют различные условия, требующие различных параметров, по умолчанию в большинстве случаев существует команда:</span><span class="sxs-lookup"><span data-stu-id="e8013-139">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e8013-140">Перемещение в Teams с Skype для бизнеса Server панели управления</span><span class="sxs-lookup"><span data-stu-id="e8013-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e8013-141">Откройте приложение Skype для бизнеса Server панели управления.</span><span class="sxs-lookup"><span data-stu-id="e8013-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e8013-142">В левой навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e8013-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e8013-143">Используйте **Поиск,** чтобы найти пользователя(ы) вы хотели бы перейти к Teams.</span><span class="sxs-lookup"><span data-stu-id="e8013-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="e8013-144">Выберите пользователя(ы), а затем, из выпадаемой ниже списка действия, выберите Перемещение выбранных пользователей в Teams или Переместить выбранных пользователей в **Skype для бизнеса Online**.  </span><span class="sxs-lookup"><span data-stu-id="e8013-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams** or **Move selected users to Skype for Business Online**.</span></span>   <span data-ttu-id="e8013-145">Теперь любой параметр перемещает пользователей непосредственно в TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e8013-145">Either option now moves users directly to TeamsOnly.</span></span>
5. <span data-ttu-id="e8013-146">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8013-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e8013-147">В случае запроса вопишитесь Microsoft 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="e8013-147">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e8013-148">Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8013-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e8013-149">Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="e8013-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="e8013-150">Сообщите Skype для бизнеса локальному пользователю о предстоящем переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="e8013-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="e8013-151">Средства локального администрирования в Skype для бизнеса Server 2015 г. с cu8, а также в Skype для бизнеса Server 2019 г. позволяют уведомлять Skype для бизнеса пользователей о предстоящем переходе в Teams.</span><span class="sxs-lookup"><span data-stu-id="e8013-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="e8013-152">Когда вы включаете эти уведомления, пользователи увидят уведомление в Skype для бизнеса клиенте (Win32, Mac, web и mobile), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e8013-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="e8013-153">Если пользователи нажмет кнопку **Try it,** Teams клиент будет запущен, если он установлен; в противном случае пользователи будут перенавигуться в веб-версию Teams в браузере.</span><span class="sxs-lookup"><span data-stu-id="e8013-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="e8013-154">По умолчанию при включении уведомлений клиенты Win32 Skype для бизнеса безмолвно загружают клиент Teams, чтобы богатый клиент был доступен до перехода пользователя в режим TeamsOnly; однако вы также можете отключить это поведение.</span><span class="sxs-lookup"><span data-stu-id="e8013-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to TeamsOnly mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="e8013-155">Уведомления настраиваются с помощью локальной версии, а бесшумная загрузка для клиентов Win32 контролируется с помощью локального `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` комлета.</span><span class="sxs-lookup"><span data-stu-id="e8013-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="e8013-156">Некоторым серверам может потребоваться перезагрузка для работы в Skype для бизнеса 2015 г. с cu8.</span><span class="sxs-lookup"><span data-stu-id="e8013-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Уведомление о предстоящем переходе Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="e8013-158">Чтобы уведомить пользователей о скором обновлении до Teams, создайте новый экземпляр TeamsUpgradePolicy с помощью NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="e8013-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="e8013-159">Затем назначьте эту политику пользователям, которых вы хотите уведомить, назначив политику непосредственно пользователю или установив политику на сайте, пуле или глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="e8013-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="e8013-160">Следующие cmdlets создать и предоставить политику на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="e8013-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="e8013-161">Автоматическая загрузка Teams через клиент Skype для бизнеса Win32 контролируется с помощью локального командлета TeamsUpgradeConfiguration с параметром DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="e8013-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="e8013-162">Вы создаете эту конфигурацию на глобальном, сайте и уровне пула.</span><span class="sxs-lookup"><span data-stu-id="e8013-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="e8013-163">Например, следующая команда создает конфигурацию для сайта Redmond1:</span><span class="sxs-lookup"><span data-stu-id="e8013-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="e8013-164">По умолчанию значение DownloadTeams является true; Однако это честь только *в* том случае, если NotifySfbUser = True для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8013-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8013-165">См. также</span><span class="sxs-lookup"><span data-stu-id="e8013-165">See also</span></span>

[<span data-ttu-id="e8013-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e8013-166">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="e8013-167">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e8013-167">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="e8013-168">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e8013-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="e8013-169">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e8013-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
