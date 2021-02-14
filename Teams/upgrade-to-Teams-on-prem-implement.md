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
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533606"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="2a18c-103">Реализация обновления Skype для бизнеса до Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="2a18c-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="2a18c-104">В этой статье описано, как реализовать обновление.</span><span class="sxs-lookup"><span data-stu-id="2a18c-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="2a18c-105">Эта пятая статья посвящена понятиям обновления и внедрению для ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="2a18c-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="2a18c-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="2a18c-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="2a18c-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="2a18c-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="2a18c-108">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="2a18c-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="2a18c-109">Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2a18c-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="2a18c-110">**Реализация обновления** (эта статья)</span><span class="sxs-lookup"><span data-stu-id="2a18c-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="2a18c-111">Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)</span><span class="sxs-lookup"><span data-stu-id="2a18c-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="2a18c-112">Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.</span><span class="sxs-lookup"><span data-stu-id="2a18c-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="2a18c-113">Совместное сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2a18c-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="2a18c-114">Режимы сосуществования — ссылки</span><span class="sxs-lookup"><span data-stu-id="2a18c-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="2a18c-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="2a18c-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="2a18c-116">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="2a18c-116">Upgrade options</span></span>

<span data-ttu-id="2a18c-117">В этом разделе описано, как реализовать обновление с помощью одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2a18c-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="2a18c-118">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="2a18c-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="2a18c-119">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="2a18c-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="2a18c-120">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="2a18c-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="2a18c-121">Если вам нужны дополнительные сведения о параметрах, убедитесь, что методы обновления уже [прочитали.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="2a18c-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="2a18c-122">Обновление перекрывающихся возможностей (в режиме "О-ва")</span><span class="sxs-lookup"><span data-stu-id="2a18c-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="2a18c-123">Для варианта обновления перекрывающихся возможностей:</span><span class="sxs-lookup"><span data-stu-id="2a18c-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="2a18c-124">Учитывайте этот вариант, если вы можете быстро обновить систему для всей организации.</span><span class="sxs-lookup"><span data-stu-id="2a18c-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="2a18c-125">Поскольку существует риск путаницы с запуском обоих клиентов, лучше всего свести к минимуму период времени, в течение которого пользователи должны запускать оба клиента.</span><span class="sxs-lookup"><span data-stu-id="2a18c-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="2a18c-126">Убедитесь, что пользователи знают, как запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="2a18c-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="2a18c-127">Этот вариант является заданной моделью и не требует действий администратора, чтобы начать работу с Teams, кроме назначения лицензии на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a18c-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="2a18c-128">Если у ваших пользователей уже есть Skype для бизнеса Online, возможно, вы уже стали использовать эту модель.</span><span class="sxs-lookup"><span data-stu-id="2a18c-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="2a18c-129">Выход из режима перекрывания возможностей и переход в TeamsOnly может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="2a18c-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="2a18c-130">Так как обновленные пользователи общаются только через Teams, все другие пользователи в организации, с кем общаются, должны использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="2a18c-131">Если у вас есть пользователи, которые не начали использовать Teams, они будут выявлены из-за отсутствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a18c-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="2a18c-132">Более того, они не будут видеть пользователей TeamsOnly в Интернете в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2a18c-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="2a18c-133">В некоторых организациях обновление на уровне клиента возможно с помощью глобальной политики клиента, но для этого требуется прямое планирование и ожидание обновления всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a18c-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="2a18c-134">Обновление некоторых возможностей для организации, которая еще не начала использовать Teams</span><span class="sxs-lookup"><span data-stu-id="2a18c-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="2a18c-135">Если в вашей организации пока нет активных пользователей в Teams, сначала нужно настроить политику клиента по умолчанию для TeamsUpgradePolicy на один из режимов Skype для бизнеса, например SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2a18c-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="2a18c-136">Пользователи, которые еще не начали использовать Teams, не заметят никакой разницы в работе.</span><span class="sxs-lookup"><span data-stu-id="2a18c-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="2a18c-137">Однако настройка этой политики на уровне клиента позволяет начать обновление пользователей до режима TeamsOnly и гарантирует, что обновленные пользователи по-прежнему смогут общаться с пользователями, которые не были обновлены.</span><span class="sxs-lookup"><span data-stu-id="2a18c-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="2a18c-138">Означив пилотных пользователей, вы можете обновить их до TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2a18c-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="2a18c-139">Если они являются локальной, используйте Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="2a18c-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="2a18c-140">Если они находятся в сети, просто назначьте им режим TeamsOnly с помощью Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="2a18c-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="2a18c-141">По умолчанию все собрания Skype для бизнеса, запланированные этими пользователями, переносются в Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="2a18c-142">Ниже ключевых команд:</span><span class="sxs-lookup"><span data-stu-id="2a18c-142">Following are the key commands:</span></span>

1. <span data-ttu-id="2a18c-143">Задайте для клиента режим SfbWithTeamsCollab следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a18c-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="2a18c-144">Обновим пилотных пользователей до TeamsOnly следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a18c-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="2a18c-145">Для пользователя, который находится в сети:</span><span class="sxs-lookup"><span data-stu-id="2a18c-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="2a18c-146">Для локального пользователя:</span><span class="sxs-lookup"><span data-stu-id="2a18c-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="2a18c-147">Notes</span><span class="sxs-lookup"><span data-stu-id="2a18c-147">Notes</span></span>
 
- <span data-ttu-id="2a18c-148">Вместо того чтобы настраивать политику клиента на SfbWithTeamsCollab, можно настроить ее на SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="2a18c-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="2a18c-149">В результате все пользователи будут планировать все новые собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="2a18c-150">`Move-CsUser` — это cmdlet в локальном средстве.</span><span class="sxs-lookup"><span data-stu-id="2a18c-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="2a18c-151">Для `MoveToTeams` перехода требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="2a18c-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="2a18c-152">Если вы используете более новую версию, вы можете сначала переместить пользователя в Skype для бизнеса Online, а затем предоставить ему режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2a18c-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="2a18c-153">По умолчанию собрания Skype для бизнеса переносются в Teams при обновлении до режима TeamsOnly или при назначении режима SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="2a18c-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="2a18c-154">На схеме ниже показаны концептуальные этапы обновления функций выбора для организации без предварительного использования Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="2a18c-155">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a18c-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="2a18c-156">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="2a18c-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="2a18c-157">Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью Interop и наоборот.</span><span class="sxs-lookup"><span data-stu-id="2a18c-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="2a18c-158">Пользователи в режиме "О-ва" должны обязательно запустить оба клиента.</span><span class="sxs-lookup"><span data-stu-id="2a18c-158">Users in Islands mode must be sure to run both clients.</span></span>

![Схема, показывающая обновление некоторых возможностей без предварительного использования Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="2a18c-160">Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"</span><span class="sxs-lookup"><span data-stu-id="2a18c-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="2a18c-161">Если некоторые пользователи в вашей организации активно используют Teams в режиме "О-ва", вероятно, вы не хотите удалять функции существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a18c-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="2a18c-162">Таким образом, прежде чем изменять политику клиента, необходимо сделать дополнительное.</span><span class="sxs-lookup"><span data-stu-id="2a18c-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="2a18c-163">Решение заключается в том, чтобы захотеть закорестить существующих активных пользователей Teams в режиме "Острова", прежде чем настраивать политику для всего клиента на SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2a18c-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="2a18c-164">После этого вы можете продолжить развертывание, как было выше, однако у вас будет две группы пользователей, которые переходят в TeamsOnly: пользователи, которые были активны в Teams, будут работать в режиме "О-ва", а остальные — в режиме SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2a18c-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="2a18c-165">Вы можете постепенно перемещать этих пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2a18c-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="2a18c-166">Найдите пользователей, активных в Teams, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a18c-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="2a18c-167">В Центре администрирования Microsoft 365 на левой навигации перейдите к области "Отчеты", а затем "Использование".</span><span class="sxs-lookup"><span data-stu-id="2a18c-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="2a18c-168">В dropdown "Select a report" (Выберите отчет) выберите Microsoft Teams, а затем — "Действия пользователя".</span><span class="sxs-lookup"><span data-stu-id="2a18c-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="2a18c-169">Это позволит обеспечить экспортируемую таблицу пользователей, которые были активны в Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="2a18c-170">Нажмите кнопку "Экспорт", откройте Excel и выберите фильтр, чтобы отфильтровать только активных пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="2a18c-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="2a18c-171">Для каждого активного пользователя Teams, найденного на шаге 1, назначьте ему режим "Острова" в удаленной командной командной команде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a18c-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="2a18c-172">Это позволит вам перейти к следующему шагу и не изменять пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2a18c-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="2a18c-173">Задайте для политики клиента SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="2a18c-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="2a18c-174">Обновление выбранных пользователей до режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2a18c-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="2a18c-175">Вы можете обновить либо пользователей в режиме "Острова", либо в режиме SfbWithTeamsCollab, хотя сначала может потребоваться расставить приоритеты при обновлении пользователей в режиме "О-ва", чтобы свести к минимуму вероятность путаницы, которая может возникнуть, когда пользователи находятся в режиме "О-ва".</span><span class="sxs-lookup"><span data-stu-id="2a18c-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="2a18c-176">Для пользователей Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="2a18c-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="2a18c-177">Для пользователей, которые могут использовать локальное серверное приложение Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="2a18c-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="2a18c-178">На приведенной ниже схеме показаны концептуальные этапы перехода между возможностями выбора, при котором в начале есть активные пользователи островов.</span><span class="sxs-lookup"><span data-stu-id="2a18c-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="2a18c-179">Высота столбцов представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a18c-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="2a18c-180">На любом этапе обновления все пользователи могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="2a18c-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="2a18c-181">Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью взаимодействия и наоборот.</span><span class="sxs-lookup"><span data-stu-id="2a18c-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Схема, показывающая обновление некоторых возможностей с активными пользователями в режиме "О-ва"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="2a18c-183">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2a18c-183">Related links</span></span>

[<span data-ttu-id="2a18c-184">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2a18c-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="2a18c-185">Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="2a18c-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="2a18c-186">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="2a18c-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="2a18c-187">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="2a18c-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="2a18c-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="2a18c-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="2a18c-189">Использование службы переноса собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="2a18c-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

