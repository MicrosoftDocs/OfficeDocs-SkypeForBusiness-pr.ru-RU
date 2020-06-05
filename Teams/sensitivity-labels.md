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
ms.openlocfilehash: 7f8eb7e0fa0d34ae21829a12011f094d8e9c9126
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562074"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="b70ac-103">Метки чувствительности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b70ac-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b70ac-104">[Метки чувствительности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) позволяют администраторам Teams регулировать доступ к конфиденциальному содержимому Организации, созданному во время совместной работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="b70ac-105">Метки пометок и связанные с ними политики можно задать в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="b70ac-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="b70ac-106">Эти метки и политики автоматически применяются к командам в Организации.</span><span class="sxs-lookup"><span data-stu-id="b70ac-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="b70ac-107">В чем разница между метками чувствительности и метками классификации групп?</span><span class="sxs-lookup"><span data-stu-id="b70ac-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="b70ac-108">Метки чувствительности отличаются от меток классификации, для которых требуется создать их с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b70ac-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="b70ac-109">Метки классификации — это текстовые строки, которые могут быть связаны с группой, но не связаны с реальными политиками.</span><span class="sxs-lookup"><span data-stu-id="b70ac-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="b70ac-110">Метки классификаций используются в качестве метаданных для принудительного применения политик с помощью внутренних средств и сценариев.</span><span class="sxs-lookup"><span data-stu-id="b70ac-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="b70ac-111">С другой стороны, метки чувствительности и их политики автоматически принудительно обрабатываются с помощью комбинации платформы групп, центра безопасности & соответствия требованиям и служб Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="b70ac-112">Метки чувствительности обеспечивают широкие возможности поддержки инфраструктуры для обеспечения безопасности конфиденциальных данных Организации.</span><span class="sxs-lookup"><span data-stu-id="b70ac-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="b70ac-113">Создание меток о конфиденциальности для групп, управление ими и их публикация</span><span class="sxs-lookup"><span data-stu-id="b70ac-113">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="b70ac-114">Сведения о том, как включать, создавать и публиковать метки чувствительности для групп, приведены в разделе [Использование меток о конфиденциальности в Microsoft Teams, microsoft 365 Groups и сайты SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="b70ac-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b70ac-115">Для создания, обновления и удаления меток конфиденциальности требуется тщательное упорядочение меток при публикации для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b70ac-115">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="b70ac-116">Любые отклонения в последовательности могут привести к постоянным ошибкам создания команды для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="b70ac-116">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="b70ac-117">Таким образом, при <a href="#createpublishlabels">создании и публикации наклеек</a>, <a href="#modifydeletelabels">изменении и удалении</a>подписей, а также для <a href="#manageerrors">управления ошибками создания групп</a>важно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b70ac-117">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="b70ac-118">**Создание и публикация меток** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="b70ac-118">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="b70ac-119">Когда метка создается и публикуется в центре безопасности &, может потребоваться до 24 часов, чтобы метка стала видна в интерфейсе создания команд.</span><span class="sxs-lookup"><span data-stu-id="b70ac-119">When a label is created and published in the Security & Compliance Center, it can take up to 24 hours for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="b70ac-120">Чтобы опубликовать метку для всех пользователей в клиенте, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b70ac-120">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="b70ac-121">Создайте метку и опубликуйте ее для нескольких выбранных учетных записей пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b70ac-121">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="b70ac-122">Когда метка будет опубликована, подождите 24 часа.</span><span class="sxs-lookup"><span data-stu-id="b70ac-122">When the label is published, wait 24 hours.</span></span>
3. <span data-ttu-id="b70ac-123">Через 24 часа попробуйте создать команду с меткой с помощью одной из учетных записей пользователя, у которых есть доступ к метке.</span><span class="sxs-lookup"><span data-stu-id="b70ac-123">After 24 hours, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="b70ac-124">Если команда была успешно создана на шаге 3, вы можете опубликовать метку для остальных пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b70ac-124">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="b70ac-125">**Изменение и удаление опубликованных наклеек** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="b70ac-125">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="b70ac-126">Удаление или изменение метки, связанной с политиками чувствительности, может привести к сбоям при создании группы в рамках клиента.</span><span class="sxs-lookup"><span data-stu-id="b70ac-126">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="b70ac-127">Поэтому перед удалением или изменением метки необходимо сначала отключить эту метку от связанных с ней политик.</span><span class="sxs-lookup"><span data-stu-id="b70ac-127">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="b70ac-128">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b70ac-128">Use the following steps</span></span>  
<span data-ttu-id="b70ac-129">чтобы удалить или изменить метку, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b70ac-129">to delete or modify a label:</span></span>
1. <span data-ttu-id="b70ac-130">Удалите метку из всех политик, использующих эту метку.</span><span class="sxs-lookup"><span data-stu-id="b70ac-130">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="b70ac-131">Кроме того, вы также можете удалить сами политики.</span><span class="sxs-lookup"><span data-stu-id="b70ac-131">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="b70ac-132">Когда метка удаляется из политик или сами политики удаляются, подождите 48 часа, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="b70ac-132">When the label is removed from the policies or the policies themselves are deleted, wait 48 hours before proceeding further.</span></span>
3. <span data-ttu-id="b70ac-133">После 48 часов запустите интерфейс создания команд и убедитесь, что метка больше не отображается для любого пользователя в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b70ac-133">After 48 hours, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="b70ac-134">Теперь вы можете безопасно удалить или изменить метку.</span><span class="sxs-lookup"><span data-stu-id="b70ac-134">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="b70ac-135">**Управление ошибками** <a name="manageerrors"> </a> при создании группы</span><span class="sxs-lookup"><span data-stu-id="b70ac-135">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="b70ac-136">Если при попытке создания группы в любой момент в общедоступном предварительном просмотре происходит сбой, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="b70ac-136">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="b70ac-137">Убедитесь, что метки чувствительности не являются обязательными для всех пользователей во время создания группы.</span><span class="sxs-lookup"><span data-stu-id="b70ac-137">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="b70ac-138">Чтобы [включить эту](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)функцию, отключите метки чувствительности, используя сценарии.</span><span class="sxs-lookup"><span data-stu-id="b70ac-138">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="b70ac-139">Обратите внимание, что для параметра EnableMIPLabels должно быть задано значение false, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b70ac-139">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="b70ac-140">Использование меток чувствительности к командам</span><span class="sxs-lookup"><span data-stu-id="b70ac-140">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="b70ac-141">Ниже приведено несколько примеров ситуаций, в которых можно использовать метки чувствительности для групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="b70ac-141">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="b70ac-142">Параметры конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="b70ac-142">Privacy setting of teams</span></span>

<span data-ttu-id="b70ac-143">Вы можете создать метку чувствительности, которая при применении при создании группы позволяет пользователям создавать группы с определенными параметрами конфиденциальности (общедоступные или личные).</span><span class="sxs-lookup"><span data-stu-id="b70ac-143">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="b70ac-144">Например, вы можете создать метку под названием "конфиденциально" в центре безопасности & соответствия требованиям и настроить группы, чтобы все команды, созданные с помощью этой наклейки, должны быть закрытыми.</span><span class="sxs-lookup"><span data-stu-id="b70ac-144">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="b70ac-145">Когда пользователь создает новую группу и выберет метку " **конфиденциально** ", единственным доступным для пользователя режимом конфиденциальности является **частный**.</span><span class="sxs-lookup"><span data-stu-id="b70ac-145">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="b70ac-146">Другие параметры конфиденциальности, такие как общедоступная и общая Организации, отключены для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b70ac-146">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Снимок экрана с меткой конфиденциальной чувствительности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="b70ac-148">Точно так же, если пользователь выбирает **Общие** при создании новой команды, он может создавать только общедоступные группы или команды на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="b70ac-148">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Снимок экрана: метка общего чувствительности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="b70ac-150">После создания группы метка чувствительности отображается в правом верхнем углу каналов в группе.</span><span class="sxs-lookup"><span data-stu-id="b70ac-150">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-channel.png)

<span data-ttu-id="b70ac-152">Владелец группы может в любой момент изменить метку конфиденциальности и параметры конфиденциальности группы, выбрав команду **изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="b70ac-152">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="b70ac-154">Гостевой доступ к Teams</span><span class="sxs-lookup"><span data-stu-id="b70ac-154">Guest access to teams</span></span>

<span data-ttu-id="b70ac-155">Вы можете указать, будет ли команда, созданная с определенной меткой, допускает гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="b70ac-155">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="b70ac-156">Команды, созданные с помощью метки, не разрешающей гостевой доступ, доступны только для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b70ac-156">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="b70ac-157">Пользователи за пределами вашей организации не могут быть добавлены в группу.</span><span class="sxs-lookup"><span data-stu-id="b70ac-157">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b70ac-158">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="b70ac-158">Known issues</span></span>

<span data-ttu-id="b70ac-159">**Поддержка меток о конфиденциальности в центре администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b70ac-159">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="b70ac-160">В настоящее время метки чувствительности не поддерживаются в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-160">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b70ac-161">Если вы используете метки чувствительности, вы не сможете указывать метки чувствительности при создании или изменении команды.</span><span class="sxs-lookup"><span data-stu-id="b70ac-161">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="b70ac-162">Метки чувствительности также не отображаются в свойствах команды и не отображаются в столбце **классификация** в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-162">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="b70ac-163">**Поддержка меток чувствительности в API Team Graph, командлеты PowerShell и шаблоны**</span><span class="sxs-lookup"><span data-stu-id="b70ac-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="b70ac-164">В настоящее время пользователи не могут применять метки чувствительности к командам, созданным непосредственно с помощью API Graph, командлетов PowerShell и шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b70ac-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="b70ac-165">**Поддержка меток о конфиденциальности в Teams для образовательных учреждений**</span><span class="sxs-lookup"><span data-stu-id="b70ac-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="b70ac-166">Метки чувствительности в настоящее время не поддерживаются для клиентов, использующих группы для образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="b70ac-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="b70ac-167">**Изменение меток чувствительности непосредственно в семействе веб-сайтов SharePoint для частных каналов**</span><span class="sxs-lookup"><span data-stu-id="b70ac-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="b70ac-168">Закрытые каналы, созданные в команде, наследуют метку чувствительности, примененную к группе.</span><span class="sxs-lookup"><span data-stu-id="b70ac-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="b70ac-169">Кроме того, в семействе веб-сайтов SharePoint для закрытого канала автоматически применяются одинаковые метки.</span><span class="sxs-lookup"><span data-stu-id="b70ac-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="b70ac-170">Если пользователь непосредственно обновляет метку чувствительности в семействе веб-сайтов SharePoint для закрытого канала, эта метка не обновляется в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="b70ac-171">В этом случае пользователи будут по-прежнему видеть метку чувствительности, примененную к группе в заголовке личного канала.</span><span class="sxs-lookup"><span data-stu-id="b70ac-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="b70ac-172">**Временем распространения изменений, примененных к меткам чувствительности за пределами приложения Teams**</span><span class="sxs-lookup"><span data-stu-id="b70ac-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="b70ac-173">Изменения, внесенные в метки секретности за пределами приложения Teams, могут занимать до 24 часов, чтобы отразить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="b70ac-174">Это относится к изменениям включения или отключения меток для клиента, изменения имен, параметров и политик подписей.</span><span class="sxs-lookup"><span data-stu-id="b70ac-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="b70ac-175">Кроме того, любые изменения метки, внесенные непосредственно в группу или на семейство веб-сайтов SharePoint, для которых может потребоваться выполнение команды, могут пройти до 24 часов, чтобы распространить его в приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="b70ac-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
