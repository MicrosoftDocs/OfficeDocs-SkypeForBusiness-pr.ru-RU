---
title: Стратегии обновления для ИТ-администраторов
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: В этой статье описаны стратегии внедрения обновления Skype для бизнеса до Teams для ИТ-администраторов.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401362"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="8b34c-103">Стратегии обновления для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="8b34c-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="8b34c-104">![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="8b34c-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8b34c-105">Эта статья для ИТ-администраторов, которые хотят внедрить обновление Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="8b34c-106">Перед внедрением обновления мы рекомендуем следующие статьи, в которых описываются важные концепции и сосуществование:</span><span class="sxs-lookup"><span data-stu-id="8b34c-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="8b34c-107">Понимание сосуществования и совместной работы Microsoft Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8b34c-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="8b34c-108">Режимы сосуществования — ссылки</span><span class="sxs-lookup"><span data-stu-id="8b34c-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="8b34c-109">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="8b34c-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="8b34c-110">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="8b34c-110">Upgrade options</span></span>

<span data-ttu-id="8b34c-111">В этом разделе описано, как реализовать обновление с помощью одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8b34c-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="8b34c-112">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="8b34c-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="8b34c-113">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="8b34c-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="8b34c-114">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="8b34c-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="8b34c-115">Если вам нужны дополнительные сведения о доступных вариантах, убедитесь, что вы уже прочитали статью "Выберите путь обновления от Skype для бизнеса [к Teams".](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8b34c-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="8b34c-116">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="8b34c-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="8b34c-117">Для варианта обновления перекрывающихся возможностей:</span><span class="sxs-lookup"><span data-stu-id="8b34c-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="8b34c-118">Учитывайте этот вариант, если вы можете быстро обновить систему для всей организации.</span><span class="sxs-lookup"><span data-stu-id="8b34c-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="8b34c-119">Поскольку существует риск путаницы с запуском обоих клиентов, лучше всего свести к минимуму период времени, в течение которого пользователи должны запускать оба клиента.</span><span class="sxs-lookup"><span data-stu-id="8b34c-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="8b34c-120">Убедитесь, что пользователи знают, как запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="8b34c-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="8b34c-121">Этот вариант является заданной моделью и не требует действий администратора, чтобы начать работу с Teams, кроме назначения лицензии на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b34c-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="8b34c-122">Если у ваших пользователей уже есть Skype для бизнеса Online, возможно, вы уже стали использовать эту модель.</span><span class="sxs-lookup"><span data-stu-id="8b34c-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="8b34c-123">Выход из режима перекрывания возможностей и переход в TeamsOnly может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="8b34c-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="8b34c-124">Так как обновленные пользователи общаются только через Teams, все другие пользователи в организации, с кем общаются, должны использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="8b34c-125">Если у вас есть пользователи, которые не начали использовать Teams, они будут выявлены из-за отсутствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="8b34c-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="8b34c-126">Более того, они не будут видеть пользователей TeamsOnly в Интернете в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8b34c-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="8b34c-127">В некоторых организациях обновление на уровне клиента возможно с помощью глобальной политики клиента, но для этого требуется прямое планирование и ожидание обновления всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b34c-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="8b34c-128">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="8b34c-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="8b34c-129">Если в вашей организации пока нет активных пользователей в Teams, сначала нужно настроить политику клиента по умолчанию для TeamsUpgradePolicy на один из режимов Skype для бизнеса, например SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8b34c-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="8b34c-130">Пользователи, которые еще не начали использовать Teams, не заметят никакой разницы в работе.</span><span class="sxs-lookup"><span data-stu-id="8b34c-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="8b34c-131">Однако настройка этой политики на уровне клиента позволяет начать обновление пользователей до режима TeamsOnly и гарантирует, что обновленные пользователи по-прежнему смогут общаться с пользователями, которые не были обновлены.</span><span class="sxs-lookup"><span data-stu-id="8b34c-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="8b34c-132">Означив пилотных пользователей, вы можете обновить их до TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8b34c-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="8b34c-133">Если они являются локальной, используйте Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="8b34c-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="8b34c-134">Если они находятся в сети, просто назначьте им режим TeamsOnly с помощью Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="8b34c-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="8b34c-135">По умолчанию все собрания Skype для бизнеса, запланированные этими пользователями, переносются в Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="8b34c-136">Ниже ключевых команд:</span><span class="sxs-lookup"><span data-stu-id="8b34c-136">Following are the key commands:</span></span>

1. <span data-ttu-id="8b34c-137">Задайте для клиента режим SfbWithTeamsCollab следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8b34c-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="8b34c-138">Обновим пилотных пользователей до TeamsOnly следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8b34c-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="8b34c-139">Для пользователя, который находится в сети:</span><span class="sxs-lookup"><span data-stu-id="8b34c-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="8b34c-140">Для локального пользователя:</span><span class="sxs-lookup"><span data-stu-id="8b34c-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="8b34c-141">Notes</span><span class="sxs-lookup"><span data-stu-id="8b34c-141">Notes</span></span>
 
- <span data-ttu-id="8b34c-142">Вместо того чтобы настраивать политику для клиента на SfbWithTeamsCollab, можно настроить ее на SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="8b34c-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="8b34c-143">В результате все пользователи будут планировать все новые собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="8b34c-144">`Move-CsUser` — это cmdlet в локальном средстве.</span><span class="sxs-lookup"><span data-stu-id="8b34c-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="8b34c-145">Для `MoveToTeams` перехода требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8b34c-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="8b34c-146">Если вы используете более новую версию, вы можете сначала переместить пользователя в Skype для бизнеса Online, а затем предоставить ему режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8b34c-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="8b34c-147">По умолчанию собрания Skype для бизнеса переносются в Teams при обновлении до режима TeamsOnly или при назначении режима SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="8b34c-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="8b34c-148">На схеме ниже показаны концептуальные этапы обновления функций выбора для организации без предварительного использования Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-148">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="8b34c-149">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b34c-149">The height of the bars represents number of users.</span></span> <span data-ttu-id="8b34c-150">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="8b34c-150">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="8b34c-151">Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью Interop и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8b34c-151">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="8b34c-152">Пользователи в режиме "О-ва" должны обязательно запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="8b34c-152">Users in Islands mode must be sure to run both clients.</span></span>

![Схема, показывающая обновление некоторых возможностей без предварительного использования Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="8b34c-154">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="8b34c-154">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="8b34c-155">Если некоторые пользователи в вашей организации активно используют Teams в режиме "О-ва", вероятно, вы не хотите удалять функции существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b34c-155">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="8b34c-156">Таким образом, прежде чем изменять политику клиента, необходимо сделать дополнительное.</span><span class="sxs-lookup"><span data-stu-id="8b34c-156">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="8b34c-157">Решение заключается в том, чтобы захотеть закореть существующих активных пользователей Teams в режиме "Острова", прежде чем настраивать политику для всего клиента на SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8b34c-157">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="8b34c-158">После этого вы можете продолжить развертывание, как было выше, однако у вас будет две группы пользователей, которые переходят в TeamsOnly: пользователи, которые были активны в Teams, будут работать в режиме "О-ва", а остальные — в режиме SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8b34c-158">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="8b34c-159">Вы можете постепенно перемещать этих пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8b34c-159">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="8b34c-160">Найдите пользователей, активных в Teams, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8b34c-160">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="8b34c-161">В Центре администрирования Microsoft 365 на левой навигации перейдите в "Отчеты" и "Использование".</span><span class="sxs-lookup"><span data-stu-id="8b34c-161">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="8b34c-162">В dropdown "Select a report" (Выберите отчет) выберите Microsoft Teams, а затем — "Действия пользователя".</span><span class="sxs-lookup"><span data-stu-id="8b34c-162">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="8b34c-163">Это позволит обеспечить экспортируемую таблицу пользователей, которые были активны в Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-163">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="8b34c-164">Нажмите кнопку "Экспорт", откройте Excel и выберите фильтр, чтобы отфильтровать только активных пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="8b34c-164">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="8b34c-165">Для каждого активного пользователя Teams, найденного на шаге 1, назначьте ему режим "Острова" в удаленной командной командной команде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b34c-165">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="8b34c-166">Это позволит вам перейти к следующему шагу и не изменять пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8b34c-166">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="8b34c-167">Задайте для политики клиента SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="8b34c-167">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="8b34c-168">Обновление выбранных пользователей до режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8b34c-168">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="8b34c-169">Вы можете обновить либо пользователей в режиме "Острова", либо в режиме SfbWithTeamsCollab, хотя сначала может потребоваться повысить приоритет обновления пользователей в режиме "О-ва", чтобы свести к минимуму вероятность путаницы, которая может возникнуть, когда пользователи находятся в режиме "Острова".</span><span class="sxs-lookup"><span data-stu-id="8b34c-169">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="8b34c-170">Для пользователей Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="8b34c-170">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="8b34c-171">Для пользователей, которые могут использовать локальное серверное приложение Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="8b34c-171">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="8b34c-172">На приведенной ниже схеме показаны концептуальные этапы перехода между возможностями выбора, при котором в начале есть активные пользователи островов.</span><span class="sxs-lookup"><span data-stu-id="8b34c-172">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="8b34c-173">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b34c-173">The height of the bars represents the number of users.</span></span> <span data-ttu-id="8b34c-174">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="8b34c-174">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="8b34c-175">Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью взаимодействия и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8b34c-175">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Схема, показывающая обновление некоторых возможностей с активными пользователями в режиме "О-ва"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="8b34c-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8b34c-177">Related links</span></span>

[<span data-ttu-id="8b34c-178">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8b34c-178">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="8b34c-179">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="8b34c-179">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="8b34c-180">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="8b34c-180">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="8b34c-181">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="8b34c-181">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="8b34c-182">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="8b34c-182">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="8b34c-183">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="8b34c-183">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

