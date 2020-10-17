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
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ca844-103">Внедрение вашего обновления из Skype для бизнеса в Teams &mdash; для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="ca844-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="ca844-104">В этой статье описано, как реализовать обновление.</span><span class="sxs-lookup"><span data-stu-id="ca844-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="ca844-105">В этой статье рассказывается о том, что представляют собой пятый из описанных выше принципов и реализации обновлений для ИТ – администраторов.</span><span class="sxs-lookup"><span data-stu-id="ca844-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ca844-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="ca844-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ca844-107">Способы обновления</span><span class="sxs-lookup"><span data-stu-id="ca844-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ca844-108">Инструменты для управления обновлением</span><span class="sxs-lookup"><span data-stu-id="ca844-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="ca844-109">Дополнительные рекомендации для организаций с локальными приложениями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ca844-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="ca844-110">**Реализация обновления (в** этой статье)</span><span class="sxs-lookup"><span data-stu-id="ca844-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="ca844-111">Общие сведения о коммутируемых телефонных сетях (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="ca844-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ca844-112">Кроме того, в следующих статьях описаны важные концепции обновления и поведение сосуществования.</span><span class="sxs-lookup"><span data-stu-id="ca844-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ca844-113">Сосуществование Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ca844-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ca844-114">Режимы сосуществования — справочные материалы</span><span class="sxs-lookup"><span data-stu-id="ca844-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ca844-115">Взаимодействие с клиентом Teams и соответствие режимам сосуществования</span><span class="sxs-lookup"><span data-stu-id="ca844-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="ca844-116">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="ca844-116">Upgrade options</span></span>

<span data-ttu-id="ca844-117">В этом разделе описана процедура реализации обновления с помощью одного из следующих вариантов обновления:</span><span class="sxs-lookup"><span data-stu-id="ca844-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="ca844-118">Перекрывающиеся возможности обновления (с использованием режима острова)</span><span class="sxs-lookup"><span data-stu-id="ca844-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="ca844-119">Обновление возможностей выбора для Организации, еще не запущенной в Teams</span><span class="sxs-lookup"><span data-stu-id="ca844-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="ca844-120">Обновление возможностей выбора для Организации, уже использующей команды в режиме "острова"</span><span class="sxs-lookup"><span data-stu-id="ca844-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="ca844-121">Если вам нужны дополнительные сведения о параметрах, убедитесь, что вы уже прочли [методы обновления](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ca844-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="ca844-122">Перекрывающиеся возможности обновления (с использованием режима острова)</span><span class="sxs-lookup"><span data-stu-id="ca844-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="ca844-123">Для варианта обновления возможностей перекрытия:</span><span class="sxs-lookup"><span data-stu-id="ca844-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="ca844-124">Используйте этот вариант, если вы можете быстро выполнить обновление всей Организации.</span><span class="sxs-lookup"><span data-stu-id="ca844-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="ca844-125">Поскольку для конечных пользователей, выполняющих оба клиента, может возникнуть угроза, лучше всего свести к минимуму период времени, в течение которого пользователи должны работать на обоих клиентах.</span><span class="sxs-lookup"><span data-stu-id="ca844-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="ca844-126">Вы должны убедиться, что ваши пользователи знают, что они работают и на обоих клиентах.</span><span class="sxs-lookup"><span data-stu-id="ca844-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="ca844-127">Этот параметр является встроенной моделью и не требует вмешательства администратора, чтобы приступить к работе с группами за исключением назначения лицензии Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca844-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="ca844-128">Если у пользователей уже есть Skype для бизнеса Online, возможно, эта модель уже есть.</span><span class="sxs-lookup"><span data-stu-id="ca844-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="ca844-129">Это может стать затруднительным выходить из режима перекрывающихся возможностей и переходить в TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ca844-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="ca844-130">Так как обновленные пользователи обмениваются данными только с помощью Teams, любые другие пользователи в Организации, взаимодействующие с этим пользователем, должны использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="ca844-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="ca844-131">Если у вас есть пользователи, которые не начали работать с группами, они будут открыты для отсутствующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="ca844-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="ca844-132">Кроме того, пользователи TeamsOnly в Skype для бизнеса не увидят пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ca844-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="ca844-133">В некоторых организациях для того, чтобы избежать этого, необходимо выполнить обновление клиента, используя глобальную политику клиента, но для этого требуется предварительное планирование и ожидание до тех пор, пока все пользователи не будут готовы к обновлению.</span><span class="sxs-lookup"><span data-stu-id="ca844-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="ca844-134">Обновление возможностей выбора для Организации, еще не запущенной в Teams</span><span class="sxs-lookup"><span data-stu-id="ca844-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="ca844-135">Если в вашей организации еще нет активных пользователей в Teams, сначала необходимо настроить политику клиента по умолчанию для TeamsUpgradePolicy на один из режимов Skype для бизнеса, например SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ca844-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ca844-136">Пользователи, которые еще не начали работать с командами, не заметят никакого отличия от поведения.</span><span class="sxs-lookup"><span data-stu-id="ca844-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="ca844-137">Тем не менее, установка этой политики на уровне клиента позволяет начать обновление пользователей до режима TeamsOnly и гарантирует, что обновленные пользователи смогут взаимодействовать с необновленными пользователями.</span><span class="sxs-lookup"><span data-stu-id="ca844-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="ca844-138">После того как вы определили, что ваши пилотные пользователи смогут обновить их до TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ca844-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="ca844-139">Если они являются локальными, используйте Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ca844-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="ca844-140">Если они подключены к сети, просто назначьте им режим TeamsOnly с помощью GRANT-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ca844-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="ca844-141">По умолчанию в Teams будут перенесены собрания Skype для бизнеса, запланированные этими пользователями.</span><span class="sxs-lookup"><span data-stu-id="ca844-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="ca844-142">Ниже приведены основные команды.</span><span class="sxs-lookup"><span data-stu-id="ca844-142">Following are the key commands:</span></span>

1. <span data-ttu-id="ca844-143">Установите для уровня клиента по умолчанию режим SfbWithTeamsCollab, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="ca844-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="ca844-144">Обновите пробные пользователи до TeamsOnly следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ca844-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="ca844-145">Для пользователя, который находится в сети:</span><span class="sxs-lookup"><span data-stu-id="ca844-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="ca844-146">Для локального пользователя:</span><span class="sxs-lookup"><span data-stu-id="ca844-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="ca844-147">Notes</span><span class="sxs-lookup"><span data-stu-id="ca844-147">Notes</span></span>
 
- <span data-ttu-id="ca844-148">Вместо того чтобы задать для клиента политику SfbWithTeamsCollab, вы можете установить для нее значение SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="ca844-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="ca844-149">Это приведет к тому, что все пользователи смогут планировать все новые собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="ca844-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="ca844-150">`Move-CsUser` является командлетом в локальных средствах.</span><span class="sxs-lookup"><span data-stu-id="ca844-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="ca844-151">`MoveToTeams`Для этого коммутатора требуется Skype для бизнеса server 2019 или Skype для бизнеса server 2015 с обновления HF1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ca844-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="ca844-152">Если вы используете более раннюю версию, вы можете сначала переместить пользователя в Skype для бизнеса Online, а затем предоставить ему режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ca844-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="ca844-153">По умолчанию собрания Skype для бизнеса переносятся в Teams при переходе в режим TeamsOnly или при назначении SfbWithTeamsCollabAndMeetings режима.</span><span class="sxs-lookup"><span data-stu-id="ca844-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="ca844-154">На приведенной ниже схеме показаны концептуальные этапы обновления выбор возможностей для Организации без предварительного использования Teams.</span><span class="sxs-lookup"><span data-stu-id="ca844-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="ca844-155">Высота отрезков представляет количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca844-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="ca844-156">На любом этапе обновления все пользователи могут взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="ca844-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ca844-157">Пользователи Skype для бизнеса взаимодействуют с пользователями TeamsOnly с помощью взаимодействия и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ca844-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="ca844-158">Пользователи в режиме "острова" должны обязательно запускать оба клиента.</span><span class="sxs-lookup"><span data-stu-id="ca844-158">Users in Islands mode must be sure to run both clients.</span></span>

![Схема, на которой показаны возможности обновления выборки без предварительного использования Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="ca844-160">Обновление возможностей выбора для Организации, уже использующей команды в режиме "острова"</span><span class="sxs-lookup"><span data-stu-id="ca844-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="ca844-161">Если некоторые пользователи в вашей организации активно используют Teams в режиме острова, вам, скорее всего, не нужно удалять функциональность существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca844-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="ca844-162">Таким образом, перед изменением политики на уровне клиента требуется дополнительный шаг.</span><span class="sxs-lookup"><span data-stu-id="ca844-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="ca844-163">Решение — это "grandfather", которые были активны активными пользователями Teams в режиме "острова", прежде чем приступить к настройке политики на уровне клиента в SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ca844-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ca844-164">После того как вы закончите это, вы можете перейти к развертыванию, как описано выше, но у вас есть две группы пользователей, которые переходят в TeamsOnly: пользователи, которые были активны в Teams, будут находиться в режиме "острова", а остальные пользователи будут в режиме SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ca844-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="ca844-165">Вы можете последовательно переместить этих пользователей в TeamsOnlyный режим.</span><span class="sxs-lookup"><span data-stu-id="ca844-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="ca844-166">Найдите пользователей, активных в Teams, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="ca844-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="ca844-167">В центре администрирования Microsoft 365 на левой панели навигации перейдите в раздел отчеты и использование.</span><span class="sxs-lookup"><span data-stu-id="ca844-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="ca844-168">В раскрывающемся списке "выберите отчет" выберите Microsoft Teams, а затем действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="ca844-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="ca844-169">Будет предоставлена экспортируемая таблица пользователей, которые были активны в Teams.</span><span class="sxs-lookup"><span data-stu-id="ca844-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="ca844-170">Нажмите кнопку Экспорт, откройте Excel и выберите пункт фильтр, чтобы отобразить только тех пользователей, которые активны в Teams.</span><span class="sxs-lookup"><span data-stu-id="ca844-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="ca844-171">Для каждого активного пользователя Teams, найденного на этапе 1, назначьте режим "острова" в удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca844-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="ca844-172">Это позволяет перейти к следующему этапу и гарантировать, что вы не измените пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ca844-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="ca844-173">Установите для параметра политики на уровне клиента значение SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="ca844-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="ca844-174">Переход с выбранных пользователей в режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ca844-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="ca844-175">Вы можете обновить пользователей в режиме "острова" или в SfbWithTeamsCollab режиме, но может возникнуть необходимость в определении приоритета обновления пользователей в режиме острова, чтобы свести к минимуму вероятность путаницы, которая может возникнуть, если пользователи находятся в режиме "острова".</span><span class="sxs-lookup"><span data-stu-id="ca844-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="ca844-176">Для пользователей, размещенных в Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="ca844-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="ca844-177">Для пользователей, размещенных в локальной среде Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ca844-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="ca844-178">На приведенной ниже схеме показаны концептуальные этапы перехода "выбор возможностей", в начале которого находятся пользователи с активными островами.</span><span class="sxs-lookup"><span data-stu-id="ca844-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="ca844-179">Высота отрезков соответствует количеству пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca844-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="ca844-180">На любом этапе обновления все пользователи могут взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="ca844-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ca844-181">Пользователи Skype для бизнеса взаимодействуют с пользователями TeamsOnly с помощью взаимодействия и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ca844-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Диаграмма, на которой показаны возможности обновления SELECT с активными пользователями в режиме "острова"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="ca844-183">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="ca844-183">Related links</span></span>

[<span data-ttu-id="ca844-184">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ca844-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ca844-185">Настройка гибридной связи между Skype для бизнеса Server и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="ca844-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ca844-186">Перемещение пользователей между локальной средой и облаком</span><span class="sxs-lookup"><span data-stu-id="ca844-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ca844-187">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="ca844-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ca844-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ca844-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ca844-189">Использование службы миграции собраний (MMS)</span><span class="sxs-lookup"><span data-stu-id="ca844-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

