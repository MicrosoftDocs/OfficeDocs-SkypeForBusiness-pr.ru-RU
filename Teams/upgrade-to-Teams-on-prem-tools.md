---
title: Средства для обновления до Teams из Skype для бизнеса локального развертывания
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Инструменты для обновления с Skype для бизнеса до Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437636"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="5e802-103">Средства для обновления до Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="5e802-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="5e802-104">В этой статье описаны средства для перехода с Teams Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5e802-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="5e802-105">Перед началом обновления корпорация Майкрософт рекомендует следующие статьи, в которые описываются основные понятия обновления и принципы совместной работы.</span><span class="sxs-lookup"><span data-stu-id="5e802-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="5e802-106">Совместное Teams Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5e802-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="5e802-107">Режимы сосуществования — справка</span><span class="sxs-lookup"><span data-stu-id="5e802-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="5e802-108">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="5e802-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="5e802-109">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="5e802-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="5e802-110">Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом совместной работы пользователя.</span><span class="sxs-lookup"><span data-stu-id="5e802-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="5e802-111">Для пользователей с локальной учетной записью в Skype для бизнеса Server вы также можете переместить их `Move-CsUser` [в облако.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="5e802-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="5e802-112">Дополнительные сведения о каждом из режимов см. в теме [Режимы сосуществования.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="5e802-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5e802-113">Если вы используете Skype для бизнеса Online Connector для управления службами, необходимо перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e802-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="5e802-114">Дополнительные сведения см. в Skype для бизнеса [Online Connector в модуле Teams PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="5e802-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="5e802-115">Независимо от того, выполняете ли вы переход на выборку с помощью Skype для бизнеса или просто переходите в режим TeamsOnly с конфигурации "Острова", Основным средством является TeamsUpgradePolicy. Как и любую другую политику в Teams, вы можете назначать TeamsUpgradePolicy напрямую пользователю.</span><span class="sxs-lookup"><span data-stu-id="5e802-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="5e802-116">Вы также можете использовать политику по умолчанию для всего клиента.</span><span class="sxs-lookup"><span data-stu-id="5e802-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="5e802-117">Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e802-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="5e802-118">Вы можете управлять политикой в консоли Teams администратора и в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e802-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="5e802-119">Пользователям, которые работают в локальной Skype для бизнеса TeamsUpgradePolicy, можно назначить любой режим TeamsUpgradePolicy, кроме Режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="5e802-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="5e802-120">И наоборот, пользователям, которые работают в облаке, может быть назначен только режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="5e802-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="5e802-121">**Режим TeamsOnly** можно на назначень только пользователю, который уже находится в облаке, так как функциональность Skype для бизнеса и федерация с Skype для бизнеса, а также Microsoft 365 телефонная система функции будут возможен только в том случае, если пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5e802-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="5e802-122">Кроме того, вы не можете назначить **режим TeamsOnly** стандартным для всего клиента, если у вас есть локальное развертывание Skype для бизнеса (которое обнаруживается наличием записи DNS lyncdiscover, которая указывает на другое расположение, кроме Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e802-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="5e802-123">Подробные сведения см. в том, как отключить [гибридную конфигурацию для завершения](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)миграции только на Teams.</span><span class="sxs-lookup"><span data-stu-id="5e802-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="5e802-124">Пользователей с Skype для бизнеса локальной учетной записью необходимо перетасковить в режим Teams только Move-CsUser в локальном Skype для бизнеса. [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)</span><span class="sxs-lookup"><span data-stu-id="5e802-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="5e802-125">В отличие от других политик, создать новые экземпляры TeamsUpgradePolicy в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e802-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5e802-126">Все существующие экземпляры встроены в службу.</span><span class="sxs-lookup"><span data-stu-id="5e802-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="5e802-127">(Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не все) имя экземпляра политики такое же, как в режиме.</span><span class="sxs-lookup"><span data-stu-id="5e802-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="5e802-128">В частности, чтобы назначить пользователю режим TeamsOnly, необходимо предоставить ему экземпляр TeamsUpgradePolicy "UpgradeToTeams".</span><span class="sxs-lookup"><span data-stu-id="5e802-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="5e802-129">Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5e802-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="5e802-130">Чтобы перейти в режим TeamsOnly, назначьте экземпляр UpgradeToTeams:</span><span class="sxs-lookup"><span data-stu-id="5e802-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="5e802-131">Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, используйте Move-CsUser в локальном средстве:</span><span class="sxs-lookup"><span data-stu-id="5e802-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="5e802-132">Чтобы изменить режим для всех пользователей в клиенте, за исключением тех, у которых есть явное разрешение на предоставление пользователю (имеет приоритет), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5e802-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="5e802-133">Если у вас есть пользователи с Skype для бизнеса локальной учетной записью, назначить режим TeamsOnly на уровне клиента невозможно.</span><span class="sxs-lookup"><span data-stu-id="5e802-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="5e802-134">С помощью Move-CsUser эти пользователи должны перемещаться в Teams только в режиме перемещения.</span><span class="sxs-lookup"><span data-stu-id="5e802-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="5e802-135">Использование уведомлений в Skype для бизнеса клиентах</span><span class="sxs-lookup"><span data-stu-id="5e802-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="5e802-136">Администраторы могут предоставлять уведомления конечным пользователям в клиенте Skype для бизнеса о том, что их скоро обновят до Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="5e802-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="5e802-137">Например, за неделю до того, как администратор планирует перейти в режим TeamsOnly, администратор может включить эти уведомления для этой группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e802-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="5e802-138">Эти уведомления включены с помощью экземпляра TeamsUpgradePolicy с NotificationSfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="5e802-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="5e802-139">Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="5e802-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="5e802-140">Для всех режимов, кроме TeamsOnly, в одном режиме фактически есть два экземпляра, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="5e802-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Схема с уведомлениями](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="5e802-142">Если ваши пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, который имеет тот же режим, что и пользователь, но с помощью NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="5e802-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="5e802-143">Если ваши пользователи находятся в локальной Skype для бизнеса Server, вам потребуется использовать локальное решение для Skype для бизнеса Server 2019 или CU8 для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5e802-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="5e802-144">Для пользователей, Skype для бизнеса Server локального экземпляра TeamsUpgradePolicy, будет соблюдаться свойство mode из интернет-экземпляра TeamsUpgradePolicy, но свойство NotifySfbUsers не будет.</span><span class="sxs-lookup"><span data-stu-id="5e802-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="5e802-145">При желании необходимо создать локальное экземпляр TeamsUpgradePolicy, чтобы контролировать поведение клиента.</span><span class="sxs-lookup"><span data-stu-id="5e802-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="5e802-146">В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с функцией NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="5e802-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="5e802-147">Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям:</span><span class="sxs-lookup"><span data-stu-id="5e802-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="5e802-148">Перенос собраний</span><span class="sxs-lookup"><span data-stu-id="5e802-148">Meeting migration</span></span>

<span data-ttu-id="5e802-149">При переносе пользователя в режим TeamsOnly существующие собрания, Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams.</span><span class="sxs-lookup"><span data-stu-id="5e802-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="5e802-150">При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e802-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="5e802-151">При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams.</span><span class="sxs-lookup"><span data-stu-id="5e802-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="5e802-152">При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e802-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="5e802-153">Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете использовать PowerShell для получения списка пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем цикличной миграции для каждого из них, чтобы запустить перенос собраний с помощью Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="5e802-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="5e802-154">Подробные сведения см. в том, как использовать службу [переноса собраний (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="5e802-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="5e802-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5e802-155">Related links</span></span>

[<span data-ttu-id="5e802-156">Режимы сосуществования — справка</span><span class="sxs-lookup"><span data-stu-id="5e802-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="5e802-157">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5e802-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="5e802-158">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="5e802-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="5e802-159">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="5e802-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="5e802-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="5e802-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="5e802-161">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="5e802-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
