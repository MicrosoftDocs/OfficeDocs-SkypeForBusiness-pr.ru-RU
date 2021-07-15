---
title: Стратегии обновления для ИТ-администраторов
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: В этой статье для ИТ-администраторов описаны стратегии по внедрению обновления с Skype для бизнеса до Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f11d14bc7bf302a864afe3062ef8f2bb8eccd7da
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437646"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="1d3b1-103">Стратегии обновления для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="1d3b1-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="1d3b1-104">![Этапы пути обновления с акцентом на этапе развертывания и внедрения](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")</span><span class="sxs-lookup"><span data-stu-id="1d3b1-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1d3b1-105">Эта статья для ИТ-администраторов, которые хотят выполнить обновление до Teams из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="1d3b1-106">Перед внедрением обновления рекомендуем следующие статьи, в которых описываются основные понятия обновления и принципы совместной использования.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1d3b1-107">Понимание Microsoft Teams и Skype для бизнеса сосуществования и совместной работы</span><span class="sxs-lookup"><span data-stu-id="1d3b1-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1d3b1-108">Режимы сосуществования — справка</span><span class="sxs-lookup"><span data-stu-id="1d3b1-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1d3b1-109">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="1d3b1-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="1d3b1-110">Параметры обновления</span><span class="sxs-lookup"><span data-stu-id="1d3b1-110">Upgrade options</span></span>

<span data-ttu-id="1d3b1-111">В этом разделе описано, как реализовать обновление с помощью одного из следующих вариантов обновления:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="1d3b1-112">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="1d3b1-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="1d3b1-113">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="1d3b1-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="1d3b1-114">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="1d3b1-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="1d3b1-115">Если вам нужны дополнительные сведения о параметрах, убедитесь, что вы уже прочитали статью Выберите путь обновления от Skype для бизнеса [до Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1d3b1-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="1d3b1-116">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="1d3b1-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="1d3b1-117">Для перекрытие возможностей обновления:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="1d3b1-118">Рассмотрите этот вариант, если вы можете быстро обновить систему для всей организации.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="1d3b1-119">Так как существует риск путаницы с запуском обоих клиентов, лучше всего свести к минимуму период времени, в течение которого пользователи должны запускать оба клиента.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="1d3b1-120">Убедитесь, что пользователи знают, как запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="1d3b1-121">Этот вариант является заданной моделью и не требует действий администратора для начала работы с Teams кроме назначения Microsoft 365 или Office 365 лицензии.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="1d3b1-122">Если у ваших пользователей уже Skype для бизнеса Online, возможно, вы уже стали использовать эту модель.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="1d3b1-123">Выйти из режима перекрывания возможностей и двигаться в TeamsOnly может быть непросто.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="1d3b1-124">Так как обновленные пользователи общаются только через Teams, все другие пользователи в организации, которые общаются с этим пользователем, должны использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="1d3b1-125">Если у вас есть пользователи, которые не начали использовать Teams, они будут выявлены из-за отсутствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="1d3b1-126">Кроме того, они не увидят пользователей TeamsOnly в Интернете в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="1d3b1-127">В некоторых организациях обновление для всего клиента возможно с помощью глобальной политики клиента, но для этого требуется не только планирование, но и ожидание обновления для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="1d3b1-128">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="1d3b1-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="1d3b1-129">Если в вашей организации еще нет активных пользователей в Teams, сначала необходимо настроить политику клиента по умолчанию для TeamsUpgradePolicy на один из режимов Skype для бизнеса, например SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="1d3b1-130">Пользователи, которые еще не начали Teams, не заметите разницу в работе.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="1d3b1-131">Однако настройка этой политики на уровне клиента позволяет начать обновление пользователей до режима TeamsOnly и гарантирует, что обновленные пользователи по-прежнему смогут общаться с пользователями, которые не были обновлены.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="1d3b1-132">Означив пилотных пользователей, вы можете обновить их до TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="1d3b1-133">Если они являются локальной, используйте Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="1d3b1-134">Если они находятся в сети, просто назначьте им режим TeamsOnly с помощью Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="1d3b1-135">По умолчанию все Skype для бизнеса, запланированные этими пользователями, переносются в Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="1d3b1-136">Ниже ключевых команд:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-136">Following are the key commands:</span></span>

1. <span data-ttu-id="1d3b1-137">Задайте для клиента по умолчанию режим SfbWithTeamsCollab следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="1d3b1-138">Обновление пилотных пользователей до TeamsOnly следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="1d3b1-139">Для пользователя, который находится в сети:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="1d3b1-140">Для пользователя, который является локальной:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="1d3b1-141">Notes</span><span class="sxs-lookup"><span data-stu-id="1d3b1-141">Notes</span></span>
 
- <span data-ttu-id="1d3b1-142">Вместо того чтобы настраивать политику для всего клиента на SfbWithTeamsCollab, можно установить для нее SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="1d3b1-143">В результате все пользователи будут планировать все новые собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="1d3b1-144">По умолчанию Skype для бизнеса собрания переносются в Teams при обновлении до режима TeamsOnly или при назначении режима SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-144">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="1d3b1-145">В ходе подготовки к предстоящей Skype для бизнеса Online корпорация Майкрософт упростила переход организаций на Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-145">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="1d3b1-146">Для перемещения пользователей непосредственно из локальной сети в TeamsOnly больше не требуется указывать `-MoveToTeams` `Move-CsUser` переключатель.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-146">It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly.</span></span> <span data-ttu-id="1d3b1-147">Раньше, если этот переключатель не был указан, пользователи перешли с локального Skype для бизнеса Server на Skype для бизнеса Online, а их режим не изменился.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-147">Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="1d3b1-148">Теперь при перемещении пользователя из локальной службы в облако с помощью , пользователям автоматически назначен режим TeamsOnly, а их собрания из локальной службы автоматически преобразуются в собрания Teams, как если бы переключатель не был `Move-CsUser` `-MoveToTeams switch had been specified` указан.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-148">Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="1d3b1-149">Такое поведение доступно во всех версиях Skype Для бизнеса Server и Lync Server 2013 (поддержка которых никогда не была `-MoveToTeams` доступна).</span><span class="sxs-lookup"><span data-stu-id="1d3b1-149">This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).</span></span>

<span data-ttu-id="1d3b1-150">На схеме ниже показаны концептуальные этапы обновления функций выбора для организации без предварительного использования Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-150">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="1d3b1-151">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-151">The height of the bars represents number of users.</span></span> <span data-ttu-id="1d3b1-152">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-152">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="1d3b1-153">Skype для бизнеса общаться с пользователями TeamsOnly с помощью interop и наоборот.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-153">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="1d3b1-154">Пользователи в режиме "О-ва" должны обязательно запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-154">Users in Islands mode must be sure to run both clients.</span></span>

![Схема, показывающая обновление некоторых возможностей без предварительного использования Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="1d3b1-156">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="1d3b1-156">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="1d3b1-157">Если некоторые пользователи в вашей организации активно Teams в режиме "Острова", вероятно, вы не хотите удалять функции существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-157">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="1d3b1-158">Таким образом, прежде чем изменять политику клиента, необходимо сделать еще один шаг.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-158">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="1d3b1-159">Решение состоит в том, чтобы "закорестить" этих активных Teams пользователей в режиме "Острова", прежде чем настраивать политику для всего клиента на SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-159">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="1d3b1-160">После этого вы можете продолжить развертывание, как было выше, однако у вас будет две группы пользователей, которые переходят в TeamsOnly: пользователи, которые были активны в Teams, будут работать в режиме "Острова", а остальные — в режиме SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-160">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="1d3b1-161">Вы можете постепенно перемещать этих пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-161">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="1d3b1-162">Найдите пользователей, которые активны в Teams следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-162">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="1d3b1-163">На Центр администрирования Microsoft 365 в области навигации слева перейдите в меню Отчеты, а затем — Использование.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-163">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="1d3b1-164">В области "Выберите отчет" выберите Microsoft Teams, а затем — Действия пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-164">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="1d3b1-165">В этом случае будет предоставляться экспортируемая таблица для пользователей, которые были активны в Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-165">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="1d3b1-166">Нажмите кнопку Экспорт, откройте Excel и отфильтруем, чтобы отфильтровать только активных Teams.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-166">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="1d3b1-167">Для каждого активного Teams, найденных на шаге 1, назначьте им режим "Острова" в удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-167">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="1d3b1-168">Это позволит вам перейти к следующему шагу и не изменять пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-168">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="1d3b1-169">Задайте для политики клиента SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-169">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="1d3b1-170">Обновление выбранных пользователей до режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-170">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="1d3b1-171">Вы можете обновить пользователей в режиме Islands или SfbWithTeamsCollab, хотя сначала вам может потребоваться уставить приоритеты при обновлении пользователей в режиме "Острова", чтобы свести к минимуму вероятность путаницы, которая может возникнуть, когда пользователи находятся в режиме "Острова".</span><span class="sxs-lookup"><span data-stu-id="1d3b1-171">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="1d3b1-172">Для пользователей, которые могут Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-172">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="1d3b1-173">Для пользователей, которые Skype для бизнеса Server локально:</span><span class="sxs-lookup"><span data-stu-id="1d3b1-173">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="1d3b1-174">На схеме ниже показаны концептуальные этапы перехода между возможностями выбора, в котором в начале находятся активные пользователи островов.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-174">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="1d3b1-175">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-175">The height of the bars represents the number of users.</span></span> <span data-ttu-id="1d3b1-176">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-176">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="1d3b1-177">Skype для бизнеса пользователями TeamsOnly можно общаться с помощью взаимодействия и наоборот.</span><span class="sxs-lookup"><span data-stu-id="1d3b1-177">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Схема, показывающая обновление выбранных возможностей с активными пользователями в режиме "О-ва"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="1d3b1-179">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d3b1-179">Related links</span></span>

[<span data-ttu-id="1d3b1-180">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1d3b1-180">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1d3b1-181">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="1d3b1-181">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1d3b1-182">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="1d3b1-182">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1d3b1-183">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="1d3b1-183">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1d3b1-184">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1d3b1-184">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1d3b1-185">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="1d3b1-185">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
