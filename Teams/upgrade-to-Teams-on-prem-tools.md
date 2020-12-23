---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Обновление Skype для бизнеса до Teams — инструменты для обновления
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
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="e303e-103">Инструменты для обновления до Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="e303e-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="e303e-104">В этой статье описаны инструменты для перехода на Teams.</span><span class="sxs-lookup"><span data-stu-id="e303e-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="e303e-105">Эта статья — третья из нескольких статей, описывать понятия обновления и реализацию для ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="e303e-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="e303e-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="e303e-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="e303e-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="e303e-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="e303e-108">**Инструменты для управления обновлением**   (эта статья)</span><span class="sxs-lookup"><span data-stu-id="e303e-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="e303e-109">Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e303e-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="e303e-110">Реализация перехода</span><span class="sxs-lookup"><span data-stu-id="e303e-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="e303e-111">Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)</span><span class="sxs-lookup"><span data-stu-id="e303e-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="e303e-112">Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.</span><span class="sxs-lookup"><span data-stu-id="e303e-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e303e-113">Совместное сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e303e-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="e303e-114">Режимы сосуществования — ссылки</span><span class="sxs-lookup"><span data-stu-id="e303e-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e303e-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="e303e-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="e303e-116">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="e303e-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="e303e-117">Какой бы способ обновления вы ни выбрали, для пользователей, у которых уже есть Skype для бизнеса Online, вы управляете переходом на TeamsOnly с помощью [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)который управляет режимом сосуществования пользователей.</span><span class="sxs-lookup"><span data-stu-id="e303e-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="e303e-118">Для пользователей с локальной учетной записью в Skype для бизнеса Server их также можно использовать для перемещения `Move-CsUser` [в облако.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="e303e-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="e303e-119">Дополнительные сведения о каждом из режимов см. в режиме [сосуществования.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="e303e-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="e303e-120">Независимо от того, выполняете ли вы переход с выбора возможностей в режимах Skype для бизнеса или просто переходите из конфигурации "Острова" в режим TeamsOnly по умолчанию, TeamsUpgradePolicy является основным инструментом для пользователей, у которых уже есть Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e303e-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="e303e-121">Как и любую другую политику в Teams, вы можете назначать TeamsUpgradePolicy напрямую пользователю.</span><span class="sxs-lookup"><span data-stu-id="e303e-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="e303e-122">Вы также можете использовать политику по умолчанию для всего клиента.</span><span class="sxs-lookup"><span data-stu-id="e303e-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="e303e-123">Любое назначение пользователю имеет приоритет над параметром клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e303e-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="e303e-124">Вы можете управлять политикой в консоли администрирования Teams и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e303e-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="e303e-125">Кроме режима TeamsOnly, можно назначить любой режим TeamsUpgradePolicy пользователям, которые работают в локальной сети Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e303e-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="e303e-126">**Режим TeamsOnly можно** на условиях только для пользователя, который уже находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e303e-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="e303e-127">Это нужно, так как функции телефонной системы и службы Федерации, Skype для бизнеса и Microsoft 365 возможны только в том случае, если пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e303e-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="e303e-128">Кроме того, режим **TeamsOnly** невозможно назначить по умолчанию для всего клиента, если у вас развернуто локальное развертывание Skype для бизнеса (обнаружено наличием записи DNS lyncdiscover, которая указывает на расположение, которое не является Office 365).</span><span class="sxs-lookup"><span data-stu-id="e303e-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="e303e-129">Пользователей с учетными записьми Skype для бизнеса, которые были домашней, необходимо перенаправить через Интернет [(в](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) Skype для бизнеса Online или прямо в Teams), используя Move-CsUser в локальном средстве Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e303e-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="e303e-130">Этих пользователей можно 3 или 2 шага 3:</span><span class="sxs-lookup"><span data-stu-id="e303e-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="e303e-131">1 шаг. Указание переключателя -MoveToTeams в Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e303e-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="e303e-132">Для этого требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e303e-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="e303e-133">2 шага: после запуска Move-CsUser предоставить пользователю TeamsUpgradePolicy режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e303e-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="e303e-134">В отличие от других политик, в Microsoft 365 и Office 365 невозможно создавать новые экземпляры TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e303e-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e303e-135">Все существующие экземпляры встроены в службу.</span><span class="sxs-lookup"><span data-stu-id="e303e-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="e303e-136">(Обратите внимание, что режим — это свойство в TeamsUpgradePolicy, а не имя экземпляра политики.) В некоторых случаях (но не для всех) имя экземпляра политики такое же, как в режиме.</span><span class="sxs-lookup"><span data-stu-id="e303e-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="e303e-137">В частности, чтобы назначить пользователю режим TeamsOnly, вы предоставляете этому пользователю экземпляр UpgradeToTeams TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e303e-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="e303e-138">Чтобы увидеть список всех экземпляров, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e303e-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="e303e-139">Чтобы обновить интернет-пользователя до режима TeamsOnly, назначьте экземпляр UpgradeToTeams:</span><span class="sxs-lookup"><span data-stu-id="e303e-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="e303e-140">Чтобы обновить локального пользователя Skype для бизнеса до режима TeamsOnly, Move-CsUser на локальном сервисном сайте:</span><span class="sxs-lookup"><span data-stu-id="e303e-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="e303e-141">Чтобы изменить режим для всех пользователей в клиенте, кроме тех, у которых явное разрешение "на пользователя" (которое имеет приоритет), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e303e-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="e303e-142">Если у вас есть пользователи с локальной учетной записью Skype для бизнеса, назначить режим TeamsOnly на уровне клиента невозможно.</span><span class="sxs-lookup"><span data-stu-id="e303e-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="e303e-143">Их необходимо перемещать в облако по отдельности с помощью Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e303e-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="e303e-144">Использование уведомлений в клиентах Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e303e-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="e303e-145">Администраторы могут предоставлять уведомления конечным пользователям в клиенте Skype для бизнеса, чтобы сообщить пользователям о скором обновлении до Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="e303e-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="e303e-146">Например, за неделю до того, как администратор планирует обновить группу пользователей до режима TeamsOnly, администратор может включить эти уведомления для этой группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="e303e-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="e303e-147">Эти уведомления включены с использованием экземпляра TeamsUpgradePolicy с NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="e303e-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="e303e-148">Для всех режимов, кроме TeamsOnly, в одном режиме фактически два экземпляра, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e303e-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="e303e-149">Для всех режимов, кроме TeamsOnly, в одном режиме фактически два экземпляра, соответствующие двум значениям NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e303e-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Схема с уведомлениями](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="e303e-151">Если ваши пользователи находятся в Skype для бизнеса Online, просто назначьте экземпляр политики, который имеет тот же режим, что и у пользователя, но с notifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="e303e-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="e303e-152">Если ваши пользователи находятся в локальной компании Skype для бизнеса Server, вам потребуется использовать локальное приложение, а вам — Skype для бизнеса Server 2019 или CU8 для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e303e-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="e303e-153">Для пользователей, домашних в локальной сети Skype для бизнеса Server, с учетом свойства mode сетевого экземпляра TeamsUpgradePolicy, но не свойства NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e303e-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="e303e-154">При желании вы должны создать локальное экземпляр TeamsUpgradePolicy, чтобы контролировать поведение клиента.</span><span class="sxs-lookup"><span data-stu-id="e303e-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="e303e-155">В локальном окне PowerShell создайте новый экземпляр TeamsUpgradePolicy с notifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="e303e-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="e303e-156">Затем в том же локальном окне PowerShell назначьте новую политику нужным пользователям.</span><span class="sxs-lookup"><span data-stu-id="e303e-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="e303e-157">Перенос собраний</span><span class="sxs-lookup"><span data-stu-id="e303e-157">Meeting migration</span></span>

<span data-ttu-id="e303e-158">При переходе пользователя в режим TeamsOnly существующие собрания Skype для бизнеса, которые он организовывал, по умолчанию преобразуются в Teams.</span><span class="sxs-lookup"><span data-stu-id="e303e-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="e303e-159">При назначении пользователю режима TeamsOnly можно отключить поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e303e-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="e303e-160">При перемещении пользователей из локальной системы собрания необходимо перенести в облако для работы с учетной записью пользователя в сети, но если не указать -MoveToTeams, собрания будут перенесены как собрания Skype для бизнеса, а не преобразованы в Teams.</span><span class="sxs-lookup"><span data-stu-id="e303e-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="e303e-161">При назначении режима TeamsOnly на уровне клиента перенос собраний не запускается для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e303e-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="e303e-162">Если вы хотите назначить режим TeamsOnly на уровне клиента и перенести собрания, вы можете с помощью PowerShell получить список пользователей в клиенте (например, с помощью Get-CsOnlineUser с нужными фильтрами), а затем переходить между этими пользователями для запуска переноса собраний с помощью start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="e303e-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="e303e-163">Подробные сведения см. [в службе переноса собраний (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="e303e-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="e303e-164">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e303e-164">Related links</span></span>

[<span data-ttu-id="e303e-165">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e303e-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e303e-166">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="e303e-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e303e-167">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="e303e-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e303e-168">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="e303e-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e303e-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e303e-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e303e-170">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="e303e-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

