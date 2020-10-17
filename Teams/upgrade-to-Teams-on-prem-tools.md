---
title: Переход на Teams из локального развертывания Skype для бизнеса (Microsoft Teams)
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Переход с Skype для бизнеса на Teams – инструменты для обновления
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533576"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="01adc-103">Средства для перехода на Teams &mdash; для ИТ – администраторов</span><span class="sxs-lookup"><span data-stu-id="01adc-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="01adc-104">В этой статье описаны инструменты для перехода на Teams.</span><span class="sxs-lookup"><span data-stu-id="01adc-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="01adc-105">В этой статье объясняется, как это третья часть, в которой описаны основные понятия и реализация обновления для ИТ – администраторов.</span><span class="sxs-lookup"><span data-stu-id="01adc-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="01adc-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="01adc-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="01adc-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="01adc-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="01adc-108">**Средства для управления обновлением**   (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="01adc-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="01adc-109">Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="01adc-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="01adc-110">Реализация перехода</span><span class="sxs-lookup"><span data-stu-id="01adc-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="01adc-111">Общие сведения о коммутируемых телефонных сетях (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="01adc-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="01adc-112">Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.</span><span class="sxs-lookup"><span data-stu-id="01adc-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="01adc-113">Сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="01adc-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="01adc-114">Режимы сосуществования — справочные материалы</span><span class="sxs-lookup"><span data-stu-id="01adc-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="01adc-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="01adc-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="01adc-116">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="01adc-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="01adc-117">Какой бы метод обновления вы выбрали для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), который управляет режимом сосуществования пользователя.</span><span class="sxs-lookup"><span data-stu-id="01adc-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="01adc-118">Пользователи, у которых есть локальная учетная запись в Skype для бизнеса Server, также используются `Move-CsUser` для [перемещения их в облако](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span><span class="sxs-lookup"><span data-stu-id="01adc-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="01adc-119">Дополнительные сведения о каждом из режимов можно найти в разделе [режимы сосуществования](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="01adc-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="01adc-120">Если вы выполняете переход на выбор возможностей в режимах Skype для бизнеса или просто переходите к режиму TeamsOnly по умолчанию, то TeamsUpgradePolicy является основным инструментом для пользователей, у которых уже есть Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="01adc-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="01adc-121">Как и любые другие политики в Teams, вы можете назначить TeamsUpgradePolicy прямо пользователю.</span><span class="sxs-lookup"><span data-stu-id="01adc-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="01adc-122">Вы также можете задать политику в качестве значения по умолчанию на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="01adc-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="01adc-123">Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="01adc-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="01adc-124">Политику можно управлять на консоли администрирования Teams и в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01adc-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="01adc-125">Вы также можете назначить любой режим TeamsUpgradePolicy, за исключением режима TeamsOnly, для пользователей, которые находятся в локальной версии Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="01adc-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="01adc-126">**Режим TeamsOnly можно назначить только пользователю, уже подключенному к Skype для бизнеса Online**.</span><span class="sxs-lookup"><span data-stu-id="01adc-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="01adc-127">Это связано с тем, что взаимодействие с пользователями и федерациями Skype для бизнеса, а также с функциями телефонной системы Microsoft 365 возможно только в том случае, если пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="01adc-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="01adc-128">Кроме того, **вы не можете назначить режим TeamsOnly в качестве значения по умолчанию на уровне клиента, если у вас есть развертывание в локальной среде Skype для бизнеса** (которое определяется наличием записи DNS lyncdiscover, которая указывает на расположение, отличное от Office 365.</span><span class="sxs-lookup"><span data-stu-id="01adc-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="01adc-129">Пользователи с учетными записями Skype для бизнеса, расположенные в локальной среде, [должны быть перемещены в Интернет](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (как в Skype для бизнеса Online, так и прямо в Teams) с помощью Move-CsUser в локальном наборе инструментов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="01adc-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="01adc-130">Эти пользователи могут быть перемещены в TeamsOnly в одном или двух шагах:</span><span class="sxs-lookup"><span data-stu-id="01adc-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="01adc-131">1 шаг: укажите параметр-MoveToTeams в разделе Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="01adc-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="01adc-132">Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с обновления HF1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="01adc-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="01adc-133">2 шага: после запуска Move-CsUser, предоставьте пользователю режим TeamsOnly, используя TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="01adc-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="01adc-134">В отличие от других политик, нельзя создавать новые экземпляры TeamsUpgradePolicy в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="01adc-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="01adc-135">Все существующие экземпляры встроены в службу.</span><span class="sxs-lookup"><span data-stu-id="01adc-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="01adc-136">(Обратите внимание, что Mode является свойством в TeamsUpgradePolicy, а не именем экземпляра политики.) В некоторых случаях имя экземпляра политики является таким же, как и в случае с режимом.</span><span class="sxs-lookup"><span data-stu-id="01adc-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="01adc-137">В частности, чтобы назначить пользователю режим TeamsOnly, необходимо предоставить этому пользователю экземпляр "UpgradeToTeams" TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="01adc-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="01adc-138">Чтобы просмотреть список всех экземпляров, вы можете выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="01adc-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="01adc-139">Чтобы обновить пользователя Online до режима TeamsOnly, назначьте экземпляр "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="01adc-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="01adc-140">Чтобы обновить локальный пользователь Skype для бизнеса до режима TeamsOnly, используйте Move-CsUser в локальном наборе инструментов.</span><span class="sxs-lookup"><span data-stu-id="01adc-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="01adc-141">Чтобы изменить режим для всех пользователей в клиенте, за исключением тех, у которых есть явное разрешение пользователя (приоритет), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="01adc-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="01adc-142">Если у вас есть пользователи с локальными учетными записями Skype для бизнеса, вы не сможете назначить режим TeamsOnly на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="01adc-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="01adc-143">Вы должны перемещать пользователей по отдельности в облако с помощью функции Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="01adc-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="01adc-144">Использование уведомлений в клиентах Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="01adc-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="01adc-145">Администраторы могут предоставить уведомления конечных пользователей в клиенте Skype для бизнеса, чтобы уведомить пользователей о том, что они вскоре будут обновлены до Teams, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="01adc-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="01adc-146">Например, за неделю до того, как администратор планирует обновить группу пользователей до TeamsOnly режима, администратор может попытаться включить эти уведомления для этой группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="01adc-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="01adc-147">Эти уведомления включены с помощью экземпляра TeamsUpgradePolicy с NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="01adc-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="01adc-148">Для всех режимов, кроме TeamsOnly, существует два экземпляра на каждый режим, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="01adc-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="01adc-149">Для всех режимов, кроме TeamsOnly, существует два экземпляра на каждый режим, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="01adc-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Диаграмма, на которой показаны уведомления](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="01adc-151">Если пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, имеющий тот же режим, что и у пользователя, но с помощью NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="01adc-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="01adc-152">Если пользователи находятся в локальной среде Skype для бизнеса Server, вам потребуется использовать локальный набор инструментов, и вам понадобится Skype для бизнеса Server 2019 или обновления HF1 для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="01adc-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="01adc-153">Для пользователей, размещенных в локальной версии Skype для бизнеса, свойство Mode из экземпляра Online TeamsUpgradePolicy принимается, но свойство NotifySfbUsers — нет.</span><span class="sxs-lookup"><span data-stu-id="01adc-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="01adc-154">Если вы хотите получать уведомления, необходимо создать локальный экземпляр TeamsUpgradePolicy для управления поведением клиента.</span><span class="sxs-lookup"><span data-stu-id="01adc-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="01adc-155">В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с NotifySfbUsers = true:</span><span class="sxs-lookup"><span data-stu-id="01adc-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="01adc-156">Затем в том же локальном окне PowerShell Назначьте новую политику для нужных пользователей:</span><span class="sxs-lookup"><span data-stu-id="01adc-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="01adc-157">Миграция собрания</span><span class="sxs-lookup"><span data-stu-id="01adc-157">Meeting migration</span></span>

<span data-ttu-id="01adc-158">Когда пользователь переносится в режим TeamsOnly, существующие собрания Skype для бизнеса по умолчанию будут преобразованы в Teams.</span><span class="sxs-lookup"><span data-stu-id="01adc-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="01adc-159">Вы можете дополнительно отключить поведение по умолчанию при назначении пользователю режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="01adc-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="01adc-160">При перемещении пользователей из локальной сети собрания должны быть перенесены в облако для работы с учетной записью пользователя в Интернете, но если не указать параметр-MoveToTeams, собрания будут переноситься в качестве собраний Skype для бизнеса, а не преобразуются в Teams.</span><span class="sxs-lookup"><span data-stu-id="01adc-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="01adc-161">При назначении режима TeamsOnly на уровне клиента миграция собрания не запускается ни для каких пользователей.</span><span class="sxs-lookup"><span data-stu-id="01adc-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="01adc-162">Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете использовать PowerShell для получения списка пользователей в клиенте (например, с помощью Get-CsOnlineUser с необходимыми фильтрами), а затем пройти каждый из этих пользователей для активации миграции собраний с помощью Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="01adc-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="01adc-163">Подробности можно найти в разделе [Использование службы миграции собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="01adc-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="01adc-164">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="01adc-164">Related links</span></span>

[<span data-ttu-id="01adc-165">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="01adc-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="01adc-166">Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="01adc-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="01adc-167">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="01adc-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="01adc-168">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="01adc-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="01adc-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="01adc-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="01adc-170">Использование службы миграции собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="01adc-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

