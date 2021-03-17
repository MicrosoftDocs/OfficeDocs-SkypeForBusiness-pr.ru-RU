---
title: Перемещение пользователей из Skype для бизнеса Server 2019 в Teams
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
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836986"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="b8a83-103">Перемещение пользователей из локальной среды в Teams</span><span class="sxs-lookup"><span data-stu-id="b8a83-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="b8a83-104">Когда пользователь перемещается из локального помещения в Teams Only, домашний skype для бизнеса пользователя перемещается из локального в online, а пользователю назначена TeamsUpgradePolicy с mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b8a83-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="b8a83-105">После того как пользователь перемещается из локального в режим TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="b8a83-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="b8a83-106">Все входящие вызовы и чаты от других пользователей (будь то отправлены из Skype для бизнеса или teams) будут отправлены в клиент teams пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8a83-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="b8a83-107">Пользователь сможет работать с другими пользователями, которые используют Skype для бизнеса (будь то в Интернете или на локальной основе).</span><span class="sxs-lookup"><span data-stu-id="b8a83-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="b8a83-108">Пользователь сможет общаться с пользователями в федерадных организациях.</span><span class="sxs-lookup"><span data-stu-id="b8a83-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="b8a83-109">Новые собрания, запланированные этим пользователем, это собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="b8a83-110">Пользователь по-прежнему может присоединяться к любым собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b8a83-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="b8a83-111">Запланированные ранее собрания пользователя будут перенесены из локального в Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="b8a83-112">Контакты, которые существовали на месте, доступны в Teams вскоре после того, как пользователь впервые вошел в систему.</span><span class="sxs-lookup"><span data-stu-id="b8a83-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="b8a83-113">Пользователи не могут инициировать звонки или чаты из Skype для бизнеса и не могут планировать новые собрания в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b8a83-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="b8a83-114">Если они попытаются открыть клиент Skype для бизнеса, они будут перенаправлены для использования Teams, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a83-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="b8a83-115">Если клиент Teams не установлен, он будет направлен в веб-версию Teams с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="b8a83-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="b8a83-116">![Сообщение, перенаправление пользователя в Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="b8a83-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="b8a83-117">Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="b8a83-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="b8a83-118">Кроме того, не забудьте просмотреть руководство по миграции и совместной работе для организаций, использующих [Teams вместе со Skype для бизнеса.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="b8a83-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="b8a83-119">Унифицированный магазин контактов должен быть отключен на учетной записи SfB на предварительной основе для перемещений контакта в Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="b8a83-120">Существует два метода перемещения пользователя из локального помещения в Teams:</span><span class="sxs-lookup"><span data-stu-id="b8a83-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="b8a83-121">Если вы используете версию раньше, чем Skype для бизнеса Server 2015 CU8, для перемещения требуется два шага (которые можно сценарий, которые можно сделать вместе как один шаг, если требуется):</span><span class="sxs-lookup"><span data-stu-id="b8a83-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="b8a83-122">[Перемещение пользователя из Skype для бизнеса Server (на месте) в Skype для бизнеса Online](move-users-from-on-premises-to-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="b8a83-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="b8a83-123">После того как пользователь находится в Skype для бизнеса Online, назначьте пользователю TeamsUpgradePolicy режим= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b8a83-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="b8a83-124">Чтобы предоставить режим TeamsOnly, запустите следующий командлет из окна Skype для бизнеса Online PowerShell: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="b8a83-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="b8a83-125">Если у вас есть средства администрирования из Skype для бизнеса Server 2015 CU8 или более поздней, вы можете использовать метод выше, или вы можете сделать этот шаг в один шаг, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a83-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="b8a83-126">Кроме того, вы можете дополнительно предоставить уведомление в клиенте Skype для бизнеса перед их перемещением в Teams Only, а также необязательно, чтобы клиент Teams был безмолвно загружен клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b8a83-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="b8a83-127">Перемещение пользователя напрямую из Skype для бизнеса на локальном сайте в Teams Only</span><span class="sxs-lookup"><span data-stu-id="b8a83-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="b8a83-128">Средства локального администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют перемещать пользователей из локального режима в режим Teams Only в одном шаге с помощью командлета Move-CsUser в PowerShell или панели управления Skype для бизнес-серверов, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a83-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="b8a83-129">Перемещение в Teams с Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="b8a83-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="b8a83-130">Move-CsUser доступно в локальном окне Skype для управления бизнесом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8a83-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="b8a83-131">Действия ниже и необходимые разрешения такие же, как перемещение пользователя в Skype для бизнеса Online, за исключением того, что вы также должны указать переключатель MoveToTeams, и вы должны убедиться, что пользователю также была предоставлена лицензия для Teams (в дополнение к Skype для бизнеса Online).</span><span class="sxs-lookup"><span data-stu-id="b8a83-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="b8a83-132">Вы должны иметь достаточные привилегии как в локальной среде, так и в облачной службе (Microsoft 365 или Office 365), как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных.</span><span class="sxs-lookup"><span data-stu-id="b8a83-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="b8a83-133">Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для управления бизнес-серверами с учетными данными локального сервера и использовать параметр для указания учетных данных для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.</span><span class="sxs-lookup"><span data-stu-id="b8a83-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="b8a83-134">Перемещение пользователя в режим Teams Only с помощью Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="b8a83-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="b8a83-135">Укажите пользователя для перемещения с помощью `Identity` параметра.</span><span class="sxs-lookup"><span data-stu-id="b8a83-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="b8a83-136">Укажите параметр -Target со значением sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="b8a83-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="b8a83-137">Укажите `MoveToTeams` переключатель.</span><span class="sxs-lookup"><span data-stu-id="b8a83-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="b8a83-138">Если у вас нет одной учетной записи с достаточными разрешениями как в локальной, так и в облачной службе (Microsoft 365 или Office 365), используйте этот параметр для поставки учетной записи с достаточными разрешениями в `-credential` Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8a83-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="b8a83-139">Если учетная запись с разрешениями в Microsoft 365 или Office 365 не заканчивается в "onmicrosoft. <span> com", необходимо указать параметр с правильным значением, как описано в `-HostedMigrationOverrideUrl` [необходимых административных учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="b8a83-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="b8a83-140">Следующая последовательность командлетов может использоваться для перемещения пользователя в TeamsOnly и предполагает, что учетная запись Microsoft 365 или Office 365 является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.</span><span class="sxs-lookup"><span data-stu-id="b8a83-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="b8a83-141">Поскольку существуют различные условия, требующие различных параметров, по умолчанию в большинстве случаев существует команда:</span><span class="sxs-lookup"><span data-stu-id="b8a83-141">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8a83-142">Перемещение в Teams с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="b8a83-142">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b8a83-143">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="b8a83-143">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="b8a83-144">В левой навигации выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b8a83-144">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="b8a83-145">Используйте **Поиск,** чтобы найти пользователя(ы), который вы хотите перейти в Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-145">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="b8a83-146">Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных **пользователей в Teams.** </span><span class="sxs-lookup"><span data-stu-id="b8a83-146">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="b8a83-147">В мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b8a83-147">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="b8a83-148">При запросе вопишитесь в Microsoft 365 или Office 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.</span><span class="sxs-lookup"><span data-stu-id="b8a83-148">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="b8a83-149">Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8a83-149">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="b8a83-150">Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.</span><span class="sxs-lookup"><span data-stu-id="b8a83-150">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="b8a83-151">Уведомление пользователей Skype для бизнеса о предстоящем переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="b8a83-151">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="b8a83-152">Собственные средства администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют уведомлять пользователей Skype для бизнеса о предстоящем переходе в Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-152">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="b8a83-153">Когда вы включаете эти уведомления, пользователи увидят уведомление в клиенте Skype для бизнеса (Win32, Mac, web и mobile), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8a83-153">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="b8a83-154">Если пользователи нажимают кнопку **Try it,** клиент Teams будет запущен, если он установлен; в противном случае пользователи будут перенавигуться в веб-версию Teams в браузере.</span><span class="sxs-lookup"><span data-stu-id="b8a83-154">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="b8a83-155">По умолчанию при включении уведомлений клиенты Win32 Skype для бизнеса безмолвно загружают клиент Teams, чтобы богатый клиент был доступен до перехода пользователя в режим Teams Only; однако вы также можете отключить это поведение.</span><span class="sxs-lookup"><span data-stu-id="b8a83-155">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="b8a83-156">Уведомления настраиваются с помощью локальной версии, а бесшумная загрузка для клиентов Win32 контролируется с помощью локального `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` комлета.</span><span class="sxs-lookup"><span data-stu-id="b8a83-156">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="b8a83-157">Некоторым серверам может потребоваться перезагрузка для работы в Skype для бизнеса 2015 с cu8.</span><span class="sxs-lookup"><span data-stu-id="b8a83-157">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Уведомление о предстоящем переходе в Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="b8a83-159">Чтобы уведомить пользователей о скором обновлении до Teams, создайте новый экземпляр TeamsUpgradePolicy с Помощью NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="b8a83-159">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="b8a83-160">Затем назначьте эту политику пользователям, которых вы хотите уведомить, назначив политику непосредственно пользователю или установив политику на сайте, пуле или глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="b8a83-160">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="b8a83-161">Следующие cmdlets создать и предоставить политику на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="b8a83-161">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="b8a83-162">Автоматическая загрузка Teams через клиент Skype для бизнеса Win32 контролируется с помощью командлета TeamsUpgradeConfiguration с параметром DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="b8a83-162">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="b8a83-163">Вы создаете эту конфигурацию на глобальном, сайте и уровне пула.</span><span class="sxs-lookup"><span data-stu-id="b8a83-163">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="b8a83-164">Например, следующая команда создает конфигурацию для сайта Redmond1:</span><span class="sxs-lookup"><span data-stu-id="b8a83-164">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="b8a83-165">По умолчанию значение DownloadTeams является true; Однако это честь только *в* том случае, если NotifySfbUser = True для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8a83-165">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8a83-166">См. также</span><span class="sxs-lookup"><span data-stu-id="b8a83-166">See also</span></span>

[<span data-ttu-id="b8a83-167">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="b8a83-167">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="b8a83-168">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="b8a83-168">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="b8a83-169">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b8a83-169">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="b8a83-170">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b8a83-170">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
