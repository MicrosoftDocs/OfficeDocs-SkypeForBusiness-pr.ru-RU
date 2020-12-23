---
title: Метки конфиденциальности для Microsoft Teams
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
description: Узнайте, как определить и использовать метки конфиденциальности в Microsoft Teams.
ms.openlocfilehash: 21d70bf48448ccef5555078e4aba65bb10d5d6a2
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476724"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="0be28-103">Метки конфиденциальности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0be28-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="0be28-104">[Метки конфиденциальности позволяют](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) администраторам Teams регулировать доступ к конфиденциальному контенту организации, созданному во время совместной работы в командах.</span><span class="sxs-lookup"><span data-stu-id="0be28-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="0be28-105">Вы можете определить метки конфиденциальности и связанные с ними политики в Центре [& безопасности.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="0be28-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="0be28-106">Эти метки и политики автоматически применяются к командам в организации.</span><span class="sxs-lookup"><span data-stu-id="0be28-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="0be28-107">В чем разница между метами конфиденциальности и метами классификации Teams?</span><span class="sxs-lookup"><span data-stu-id="0be28-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="0be28-108">Метки конфиденциальности отличаются от меток классификации, которые необходимо создавать с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0be28-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="0be28-109">Метки классификации — это текстовые строки, которые можно связывать с группой, но не связанные с ними фактические политики.</span><span class="sxs-lookup"><span data-stu-id="0be28-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="0be28-110">Метки классификации используются в качестве метаданных для ручного применения политик с помощью внутренних средств и сценариев.</span><span class="sxs-lookup"><span data-stu-id="0be28-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="0be28-111">С другой стороны, метки конфиденциальности и их политики автоматически применяются на основе сочетания платформы Groups, Центра безопасности & соответствия требованиям и служб Teams.</span><span class="sxs-lookup"><span data-stu-id="0be28-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="0be28-112">Метки конфиденциальности обеспечивают мощную поддержку инфраструктуры для защиты конфиденциальных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="0be28-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="0be28-113">Чтобы перенести существующие группы с меток классификации на использование меток конфиденциальности, воспользуйтесь инструкциями в категории и метах конфиденциальности Azure Active Directory для групп [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="0be28-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="0be28-114">Создание, управление и публикация меток конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="0be28-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="0be28-115">Чтобы узнать, как включить, создать и опубликовать метки конфиденциальности для Teams, см. метки классификации и конфиденциальности Azure Active Directory для групп [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="0be28-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="0be28-116">Создание, обновление и удаление меток конфиденциальности требует тщательной последовательности публикации меток для пользователей.</span><span class="sxs-lookup"><span data-stu-id="0be28-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="0be28-117">Любое отклонение в последовательности может привести к сохраняемой ошибке при создании группы для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="0be28-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="0be28-118">Поэтому при создании и публикации меток, изменении и <a href="#modifydeletelabels"></a>удалении опубликованных меток и управлении ошибками создания группы крайне важно сделать <a href="#manageerrors">следующее.</a> <a href="#createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="0be28-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="0be28-119">**Создание и публикация наклеев** <a name="createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="0be28-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="0be28-120">Когда метка создается и публикуется в Центре безопасности и соответствия требованиям &, она становится видимой в интерфейсе создания команд в течение 10 минут.</span><span class="sxs-lookup"><span data-stu-id="0be28-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="0be28-121">Чтобы опубликовать метку для всех пользователей клиента, с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0be28-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="0be28-122">Создайте метку и опубликуйте ее для нескольких учетных записей выбранных пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0be28-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="0be28-123">После публикации метки подождите 10 минут.</span><span class="sxs-lookup"><span data-stu-id="0be28-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="0be28-124">Через 10 минут попробуйте создать команду с меткой, используя одну из учетных записей пользователей, у них есть к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="0be28-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="0be28-125">Если группа успешно создана на шаге 3, опубликуем метку для остальных пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="0be28-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="0be28-126">**Изменение и удаление опубликованных меток** <a name="modifydeletelabels"></a></span><span class="sxs-lookup"><span data-stu-id="0be28-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="0be28-127">Удаление или изменение метки, связанной с политиками конфиденциальности, может привести к сбоям при создании группы в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0be28-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="0be28-128">Таким образом, перед удалением или изменением метки необходимо сначала отвязать ее от связанных с ней политик.</span><span class="sxs-lookup"><span data-stu-id="0be28-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="0be28-129">С помощью следующих действий</span><span class="sxs-lookup"><span data-stu-id="0be28-129">Use the following steps</span></span>  
<span data-ttu-id="0be28-130">чтобы удалить или изменить метку:</span><span class="sxs-lookup"><span data-stu-id="0be28-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="0be28-131">Удалите метку из всех политик, которые используют метку.</span><span class="sxs-lookup"><span data-stu-id="0be28-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="0be28-132">Кроме того, вы можете удалить политики сами.</span><span class="sxs-lookup"><span data-stu-id="0be28-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="0be28-133">После удаления метки из политик или самих политик подождите 10 минут, прежде чем переустраняться.</span><span class="sxs-lookup"><span data-stu-id="0be28-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="0be28-134">Через 10 минут запустите интерфейс создания группы и убедитесь, что метка больше не видна ни для одного пользователя в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0be28-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="0be28-135">Теперь вы можете безопасно удалить или изменить метку.</span><span class="sxs-lookup"><span data-stu-id="0be28-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="0be28-136">**Управление ошибками при создании команд** <a name="manageerrors"></a></span><span class="sxs-lookup"><span data-stu-id="0be28-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="0be28-137">Если во время общедоступных предварительных версий начнется сбой создания группы, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="0be28-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="0be28-138">Убедитесь, что метки конфиденциальности не являются обязательными для всех пользователей при создании группы.</span><span class="sxs-lookup"><span data-stu-id="0be28-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="0be28-139">Отключите метки конфиденциальности с помощью сценариев в [режиме "Включить эту предварительную версию".](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)</span><span class="sxs-lookup"><span data-stu-id="0be28-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="0be28-140">Обратите внимание, что для параметра EnableMIPLabels должно быть установлено ложное следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0be28-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="0be28-141">Использование меток конфиденциальности в Teams</span><span class="sxs-lookup"><span data-stu-id="0be28-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="0be28-142">Вот несколько примеров сценариев использования меток конфиденциальности в Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="0be28-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="0be28-143">Параметр конфиденциальности команд</span><span class="sxs-lookup"><span data-stu-id="0be28-143">Privacy setting of teams</span></span>

<span data-ttu-id="0be28-144">Вы можете создать метку конфиденциальности, которая при ее применении позволяет пользователям создавать команды с определенным параметром конфиденциальности (общедоступный или закрытый).</span><span class="sxs-lookup"><span data-stu-id="0be28-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="0be28-145">Например, вы создаете в Центре безопасности и соответствия требованиям метку "Конфиденциальная информация &" и настраивает Teams так, чтобы все команды, созданные с этой меткой, были закрытыми.</span><span class="sxs-lookup"><span data-stu-id="0be28-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="0be28-146">Когда пользователь создает новую команду и  выбирает метку "Конфиденциально", для него доступен только параметр **конфиденциальности "Частное".**</span><span class="sxs-lookup"><span data-stu-id="0be28-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="0be28-147">Другие параметры конфиденциальности, такие как общедоступный и общедоступный для всей организации, отключены для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0be28-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Снимок экрана: метка конфиденциальности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="0be28-149">Аналогичным образом, если пользователь  выбирает "Общие" при создании команды, он может создавать только общедоступные команды или команды для всей организации.</span><span class="sxs-lookup"><span data-stu-id="0be28-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Снимок экрана: метка общей конфиденциальности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="0be28-151">Когда группа будет создана, метка конфиденциальности будет видна в ее верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="0be28-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Снимок экрана: метка конфиденциальности в канале группы](media/sensitivity-labels-channel.png)

<span data-ttu-id="0be28-153">Владелец команды может в любое время изменить метку конфиденциальности и параметр конфиденциальности для команды, вылившись в команду и нажав кнопку "Изменить **команду".**</span><span class="sxs-lookup"><span data-stu-id="0be28-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Снимок экрана: метка конфиденциальности в канале группы](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="0be28-155">Гостевой доступ к командам</span><span class="sxs-lookup"><span data-stu-id="0be28-155">Guest access to teams</span></span>

<span data-ttu-id="0be28-156">Вы можете указать, разрешает ли команда с определенной меткой гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="0be28-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="0be28-157">Команды, созданные с меткой, которая не разрешает гостевой доступ, доступны только пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0be28-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="0be28-158">Людей за пределами организации добавить в команду нельзя.</span><span class="sxs-lookup"><span data-stu-id="0be28-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0be28-159">Метки конфиденциальности в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0be28-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="0be28-160">Метки конфиденциальности можно настроить при создании или редактировании группы в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0be28-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0be28-161">Метки конфиденциальности также видны в свойствах  группы и в столбце "Классификация" на странице "Управление командами" Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0be28-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0be28-162">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="0be28-162">Known issues</span></span>

<span data-ttu-id="0be28-163">**Поддержка меток конфиденциальности в API Teams Graph, командлетах и шаблонах Powershell**</span><span class="sxs-lookup"><span data-stu-id="0be28-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="0be28-164">В настоящее время пользователи не могут применять метки конфиденциальности к командам, созданным непосредственно с помощью API Graph, командлетов Powershell и шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0be28-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="0be28-165">**Поддержка меток конфиденциальности в skUs Teams EDU**</span><span class="sxs-lookup"><span data-stu-id="0be28-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="0be28-166">Метки конфиденциальности в настоящее время неподтверчены для клиентов, использующих skUs Teams для образования.</span><span class="sxs-lookup"><span data-stu-id="0be28-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="0be28-167">**Редактирование меток конфиденциальности непосредственно в коллекции веб-сайтов SharePoint для частных каналов**</span><span class="sxs-lookup"><span data-stu-id="0be28-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="0be28-168">Закрытые каналы, созданные в команде, наследуют метку конфиденциальности, примененную к группе.</span><span class="sxs-lookup"><span data-stu-id="0be28-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="0be28-169">Более того, в коллекции веб-сайтов SharePoint для частного канала автоматически применяется та же метка.</span><span class="sxs-lookup"><span data-stu-id="0be28-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="0be28-170">Если пользователь напрямую обновляет метку конфиденциальности в коллекции веб-сайтов SharePoint для частного канала, эта метка не обновляется в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="0be28-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="0be28-171">В этом случае пользователи будут по-прежнему видеть метку конфиденциальности, примененную к группе в заглавной области частного канала.</span><span class="sxs-lookup"><span data-stu-id="0be28-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="0be28-172">**Время распространения изменений, примененных к меткам конфиденциальности за пределами приложения Teams**</span><span class="sxs-lookup"><span data-stu-id="0be28-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="0be28-173">Изменения, внесенные в метки конфиденциальности за пределами приложения Teams, могут отражаться в приложении Teams в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="0be28-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="0be28-174">Это относится ко любым изменениям, внесенным для того, чтобы включить или отключить метки для клиента, изменения имен меток, параметров и политик.</span><span class="sxs-lookup"><span data-stu-id="0be28-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="0be28-175">Кроме того, распространение изменений метки, внесенной непосредственно в группу или коллекцию веб-сайтов SharePoint, которая является backs team, может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="0be28-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
