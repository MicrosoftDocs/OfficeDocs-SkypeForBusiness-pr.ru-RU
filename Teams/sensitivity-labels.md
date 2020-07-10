---
title: Метки чувствительности для Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как определять и использовать метки чувствительности в Microsoft Teams.
ms.openlocfilehash: 4f1bdc4715fd1375cff637604c93962e2f30c258
ms.sourcegitcommit: d7f49f8c28cba32d3715ea1965c736e6ba574bda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091272"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="a32b1-103">Метки чувствительности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a32b1-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="a32b1-104">[Метки чувствительности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) позволяют администраторам Teams регулировать доступ к конфиденциальному содержимому Организации, созданному во время совместной работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="a32b1-105">Метки пометок и связанные с ними политики можно задать в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="a32b1-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="a32b1-106">Эти метки и политики автоматически применяются к командам в Организации.</span><span class="sxs-lookup"><span data-stu-id="a32b1-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="a32b1-107">В чем разница между метками чувствительности и метками классификации групп?</span><span class="sxs-lookup"><span data-stu-id="a32b1-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="a32b1-108">Метки чувствительности отличаются от меток классификации, для которых требуется создать их с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a32b1-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="a32b1-109">Метки классификации — это текстовые строки, которые могут быть связаны с группой, но не связаны с реальными политиками.</span><span class="sxs-lookup"><span data-stu-id="a32b1-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="a32b1-110">Метки классификаций используются в качестве метаданных для принудительного применения политик с помощью внутренних средств и сценариев.</span><span class="sxs-lookup"><span data-stu-id="a32b1-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="a32b1-111">С другой стороны, метки чувствительности и их политики автоматически принудительно обрабатываются с помощью комбинации платформы групп, центра безопасности & соответствия требованиям и служб Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="a32b1-112">Метки чувствительности обеспечивают широкие возможности поддержки инфраструктуры для обеспечения безопасности конфиденциальных данных Организации.</span><span class="sxs-lookup"><span data-stu-id="a32b1-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="a32b1-113">Чтобы перенести существующие группы с использованием меток классификации для использования меток о конфиденциальности, воспользуйтесь инструкциями в разделе "Классификация и секретность" в [Azure Active Directory для групп Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="a32b1-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="a32b1-114">Создание меток о конфиденциальности для групп, управление ими и их публикация</span><span class="sxs-lookup"><span data-stu-id="a32b1-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="a32b1-115">Сведения о том, как включать, создавать и публиковать метки чувствительности для Teams, можно найти в разделе [классификация и метка о конфиденциальности Azure Active Directory для групп Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="a32b1-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="a32b1-116">Для создания, обновления и удаления меток конфиденциальности требуется тщательное упорядочение меток при публикации для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a32b1-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="a32b1-117">Любые отклонения в последовательности могут привести к постоянным ошибкам создания команды для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a32b1-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="a32b1-118">Таким образом, при <a href="#createpublishlabels">создании и публикации наклеек</a>, <a href="#modifydeletelabels">изменении и удалении</a>подписей, а также для <a href="#manageerrors">управления ошибками создания групп</a>важно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a32b1-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="a32b1-119">**Создание и публикация меток** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="a32b1-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="a32b1-120">Когда метка создается и публикуется в центре безопасности &, может потребоваться до 10 минут, чтобы метка стала видна в интерфейсе создания команд.</span><span class="sxs-lookup"><span data-stu-id="a32b1-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="a32b1-121">Чтобы опубликовать метку для всех пользователей в клиенте, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a32b1-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="a32b1-122">Создайте метку и опубликуйте ее для нескольких выбранных учетных записей пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a32b1-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="a32b1-123">Когда метка будет опубликована, подождите 10 минут.</span><span class="sxs-lookup"><span data-stu-id="a32b1-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="a32b1-124">Через 10 минут попробуйте создать команду с меткой, используя одну из учетных записей пользователя, у которых есть доступ к метке.</span><span class="sxs-lookup"><span data-stu-id="a32b1-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="a32b1-125">Если команда была успешно создана на шаге 3, вы можете опубликовать метку для остальных пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a32b1-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="a32b1-126">**Изменение и удаление опубликованных наклеек** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="a32b1-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="a32b1-127">Удаление или изменение метки, связанной с политиками чувствительности, может привести к сбоям при создании группы в рамках клиента.</span><span class="sxs-lookup"><span data-stu-id="a32b1-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="a32b1-128">Поэтому перед удалением или изменением метки необходимо сначала отключить эту метку от связанных с ней политик.</span><span class="sxs-lookup"><span data-stu-id="a32b1-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="a32b1-129">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a32b1-129">Use the following steps</span></span>  
<span data-ttu-id="a32b1-130">чтобы удалить или изменить метку, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a32b1-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="a32b1-131">Удалите метку из всех политик, использующих эту метку.</span><span class="sxs-lookup"><span data-stu-id="a32b1-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="a32b1-132">Кроме того, вы также можете удалить сами политики.</span><span class="sxs-lookup"><span data-stu-id="a32b1-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="a32b1-133">Когда метка удаляется из политик или сами политики удаляются, подождите 10 минут, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="a32b1-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="a32b1-134">Через 10 минут запустите интерфейс создания групп и убедитесь, что метка больше не отображается для любого пользователя в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a32b1-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="a32b1-135">Теперь вы можете безопасно удалить или изменить метку.</span><span class="sxs-lookup"><span data-stu-id="a32b1-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="a32b1-136">**Управление ошибками** <a name="manageerrors"> </a> при создании группы</span><span class="sxs-lookup"><span data-stu-id="a32b1-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="a32b1-137">Если при попытке создания группы в любой момент в общедоступном предварительном просмотре происходит сбой, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="a32b1-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="a32b1-138">Убедитесь, что метки чувствительности не являются обязательными для всех пользователей во время создания группы.</span><span class="sxs-lookup"><span data-stu-id="a32b1-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="a32b1-139">Чтобы [включить эту](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)функцию, отключите метки чувствительности, используя сценарии.</span><span class="sxs-lookup"><span data-stu-id="a32b1-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="a32b1-140">Обратите внимание, что для параметра EnableMIPLabels должно быть задано значение false, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="a32b1-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="a32b1-141">Использование меток чувствительности к командам</span><span class="sxs-lookup"><span data-stu-id="a32b1-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="a32b1-142">Ниже приведено несколько примеров ситуаций, в которых можно использовать метки чувствительности для групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="a32b1-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="a32b1-143">Параметры конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="a32b1-143">Privacy setting of teams</span></span>

<span data-ttu-id="a32b1-144">Вы можете создать метку чувствительности, которая при применении при создании группы позволяет пользователям создавать группы с определенными параметрами конфиденциальности (общедоступные или личные).</span><span class="sxs-lookup"><span data-stu-id="a32b1-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="a32b1-145">Например, вы можете создать метку под названием "конфиденциально" в центре безопасности & соответствия требованиям и настроить группы, чтобы все команды, созданные с помощью этой наклейки, должны быть закрытыми.</span><span class="sxs-lookup"><span data-stu-id="a32b1-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="a32b1-146">Когда пользователь создает новую группу и выберет метку " **конфиденциально** ", единственным доступным для пользователя режимом конфиденциальности является **частный**.</span><span class="sxs-lookup"><span data-stu-id="a32b1-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="a32b1-147">Другие параметры конфиденциальности, такие как общедоступная и общая Организации, отключены для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a32b1-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Снимок экрана с меткой конфиденциальной чувствительности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="a32b1-149">Точно так же, если пользователь выбирает **Общие** при создании новой команды, он может создавать только общедоступные группы или команды на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="a32b1-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Снимок экрана: метка общего чувствительности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="a32b1-151">После создания группы метка чувствительности отображается в правом верхнем углу каналов в группе.</span><span class="sxs-lookup"><span data-stu-id="a32b1-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-channel.png)

<span data-ttu-id="a32b1-153">Владелец группы может в любой момент изменить метку конфиденциальности и параметры конфиденциальности группы, выбрав команду **изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="a32b1-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="a32b1-155">Гостевой доступ к Teams</span><span class="sxs-lookup"><span data-stu-id="a32b1-155">Guest access to teams</span></span>

<span data-ttu-id="a32b1-156">Вы можете указать, будет ли команда, созданная с определенной меткой, допускает гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="a32b1-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="a32b1-157">Команды, созданные с помощью метки, не разрешающей гостевой доступ, доступны только для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a32b1-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="a32b1-158">Пользователи за пределами вашей организации не могут быть добавлены в группу.</span><span class="sxs-lookup"><span data-stu-id="a32b1-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a32b1-159">Метки чувствительности в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a32b1-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="a32b1-160">Метки чувствительности можно задать при создании или изменении команды в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a32b1-161">Метки чувствительности также отображаются в свойствах группы и в столбце **классификация** на странице Управление группами в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a32b1-162">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a32b1-162">Known issues</span></span>

<span data-ttu-id="a32b1-163">**Дочерние метки по умолчанию не отображаются во время создания группы**</span><span class="sxs-lookup"><span data-stu-id="a32b1-163">**Child default labels not showing during team creation**</span></span>

<span data-ttu-id="a32b1-164">В настоящее время дочерняя метка, установленная в качестве метки по умолчанию для Teams, не отображается в верхней части списка в раскрывающемся списке Метки чувствительности в модели создания групп.</span><span class="sxs-lookup"><span data-stu-id="a32b1-164">Currently, a child label set as the default label for Teams will not show at the top of the list in the sensitivity labels dropdown in the team creation model.</span></span> <span data-ttu-id="a32b1-165">Создатели групп по-прежнему могут использовать раскрывающийся список для применения метки дочернего элемента в качестве временного решения.</span><span class="sxs-lookup"><span data-stu-id="a32b1-165">Team creators can still use the dropdown to apply the child label as a workaround.</span></span>

<span data-ttu-id="a32b1-166">**Поддержка меток чувствительности в API Team Graph, командлеты PowerShell и шаблоны**</span><span class="sxs-lookup"><span data-stu-id="a32b1-166">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="a32b1-167">В настоящее время пользователи не могут применять метки чувствительности к командам, созданным непосредственно с помощью API Graph, командлетов PowerShell и шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a32b1-167">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="a32b1-168">**Поддержка меток о конфиденциальности в Teams для образовательных учреждений**</span><span class="sxs-lookup"><span data-stu-id="a32b1-168">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="a32b1-169">Метки чувствительности в настоящее время не поддерживаются для клиентов, использующих группы для образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="a32b1-169">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="a32b1-170">**Изменение меток чувствительности непосредственно в семействе веб-сайтов SharePoint для частных каналов**</span><span class="sxs-lookup"><span data-stu-id="a32b1-170">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="a32b1-171">Закрытые каналы, созданные в команде, наследуют метку чувствительности, примененную к группе.</span><span class="sxs-lookup"><span data-stu-id="a32b1-171">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="a32b1-172">Кроме того, в семействе веб-сайтов SharePoint для закрытого канала автоматически применяются одинаковые метки.</span><span class="sxs-lookup"><span data-stu-id="a32b1-172">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="a32b1-173">Если пользователь непосредственно обновляет метку чувствительности в семействе веб-сайтов SharePoint для закрытого канала, эта метка не обновляется в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-173">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="a32b1-174">В этом случае пользователи будут по-прежнему видеть метку чувствительности, примененную к группе в заголовке личного канала.</span><span class="sxs-lookup"><span data-stu-id="a32b1-174">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="a32b1-175">**Временем распространения изменений, примененных к меткам чувствительности за пределами приложения Teams**</span><span class="sxs-lookup"><span data-stu-id="a32b1-175">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="a32b1-176">Изменения, внесенные в метки секретности за пределами приложения Teams, могут занимать до 24 часов, чтобы отразить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-176">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="a32b1-177">Это относится к изменениям включения или отключения меток для клиента, изменения имен, параметров и политик подписей.</span><span class="sxs-lookup"><span data-stu-id="a32b1-177">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="a32b1-178">Кроме того, любые изменения метки, внесенные непосредственно в группу или на семейство веб-сайтов SharePoint, для которых может потребоваться выполнение команды, могут пройти до 24 часов, чтобы распространить его в приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="a32b1-178">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
