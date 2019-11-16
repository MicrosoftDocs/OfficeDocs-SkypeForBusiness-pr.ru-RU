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
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как определять и использовать метки чувствительности в Microsoft Teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653605"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="4a563-103">Метки чувствительности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a563-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="4a563-104">[Метки чувствительности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) позволяют администраторам Teams регулировать доступ к конфиденциальному содержимому Организации, созданному во время совместной работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="4a563-105">Метки пометок и связанные с ними политики можно задать в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="4a563-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="4a563-106">Эти метки и политики автоматически применяются к командам в Организации.</span><span class="sxs-lookup"><span data-stu-id="4a563-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="4a563-107">В чем разница между метками чувствительности и метками классификации групп?</span><span class="sxs-lookup"><span data-stu-id="4a563-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="4a563-108">Метки чувствительности отличаются от меток классификации, для которых требуется создать их с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a563-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="4a563-109">Метки классификации — это текстовые строки, которые могут быть связаны с группой, но не связаны с реальными политиками.</span><span class="sxs-lookup"><span data-stu-id="4a563-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="4a563-110">Метки классификаций используются в качестве метаданных для принудительного применения политик с помощью внутренних средств и сценариев.</span><span class="sxs-lookup"><span data-stu-id="4a563-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="4a563-111">С другой стороны, метки чувствительности и их политики автоматически принудительно обрабатываются с помощью комбинации платформы групп, центра безопасности & соответствия требованиям и служб Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="4a563-112">Метки чувствительности обеспечивают широкие возможности поддержки инфраструктуры для обеспечения безопасности конфиденциальных данных Организации.</span><span class="sxs-lookup"><span data-stu-id="4a563-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="4a563-113">Создание и публикация меток о конфиденциальности для групп</span><span class="sxs-lookup"><span data-stu-id="4a563-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="4a563-114">Сведения о том, как включать, создавать и публиковать метки чувствительности для групп, приведены в разделе [Использование меток о конфиденциальности при работе с Microsoft Teams, группами Office 365 и сайтами SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="4a563-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="4a563-115">Использование меток чувствительности к командам</span><span class="sxs-lookup"><span data-stu-id="4a563-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="4a563-116">Ниже приведено несколько примеров ситуаций, в которых можно использовать метки чувствительности для групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="4a563-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="4a563-117">Параметры конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="4a563-117">Privacy setting of teams</span></span>

<span data-ttu-id="4a563-118">Вы можете создать метку чувствительности, которая при применении при создании группы позволяет пользователям создавать группы с определенными параметрами конфиденциальности (общедоступные или личные).</span><span class="sxs-lookup"><span data-stu-id="4a563-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="4a563-119">Например, вы можете создать метку под названием "конфиденциально" в центре безопасности & соответствия требованиям и настроить группы, чтобы все команды, созданные с помощью этой наклейки, должны быть закрытыми.</span><span class="sxs-lookup"><span data-stu-id="4a563-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="4a563-120">Когда пользователь создает новую группу и выберет метку " **конфиденциально** ", единственным доступным для пользователя режимом конфиденциальности является **частный**.</span><span class="sxs-lookup"><span data-stu-id="4a563-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="4a563-121">Другие параметры конфиденциальности, такие как общедоступная и общая Организации, отключены для пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a563-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Снимок экрана с меткой конфиденциальной чувствительности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="4a563-123">Точно так же, если пользователь выбирает **Общие** при создании новой команды, он может создавать только общедоступные группы или команды на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="4a563-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Снимок экрана: метка общего чувствительности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="4a563-125">После создания группы метка чувствительности отображается в правом верхнем углу каналов в группе.</span><span class="sxs-lookup"><span data-stu-id="4a563-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-channel.png)

<span data-ttu-id="4a563-127">Владелец группы может в любой момент изменить метку конфиденциальности и параметры конфиденциальности группы, выбрав команду **изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="4a563-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Снимок экрана с меткой чувствительности в канале группы](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="4a563-129">Гостевой доступ к Teams</span><span class="sxs-lookup"><span data-stu-id="4a563-129">Guest access to teams</span></span>

<span data-ttu-id="4a563-130">Вы можете указать, будет ли команда, созданная с определенной меткой, допускает гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="4a563-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="4a563-131">Команды, созданные с помощью метки, не разрешающей гостевой доступ, доступны только для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a563-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="4a563-132">Пользователи за пределами вашей организации не могут быть добавлены в группу.</span><span class="sxs-lookup"><span data-stu-id="4a563-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4a563-133">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="4a563-133">Known issues</span></span>

<span data-ttu-id="4a563-134">**Поддержка меток о конфиденциальности в центре администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4a563-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="4a563-135">В настоящее время метки чувствительности не поддерживаются в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4a563-136">Если вы используете метки чувствительности, вы не сможете указывать метки чувствительности при создании или изменении команды.</span><span class="sxs-lookup"><span data-stu-id="4a563-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="4a563-137">Метки чувствительности также не отображаются в свойствах команды и не отображаются в столбце **классификация** в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="4a563-138">**Поддержка меток чувствительности в API Team Graph, командлеты PowerShell и шаблоны**</span><span class="sxs-lookup"><span data-stu-id="4a563-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="4a563-139">В настоящее время пользователи не могут применять метки чувствительности к командам, созданным непосредственно с помощью API Graph, командлетов PowerShell и шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4a563-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="4a563-140">**Изменение меток чувствительности непосредственно в семействе веб-сайтов SharePoint для частных каналов**</span><span class="sxs-lookup"><span data-stu-id="4a563-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="4a563-141">Закрытые каналы, созданные в команде, наследуют метку чувствительности, примененную к группе.</span><span class="sxs-lookup"><span data-stu-id="4a563-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="4a563-142">Кроме того, в семействе веб-сайтов SharePoint для закрытого канала автоматически применяются одинаковые метки.</span><span class="sxs-lookup"><span data-stu-id="4a563-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="4a563-143">Если пользователь непосредственно обновляет метку чувствительности в семействе веб-сайтов SharePoint для закрытого канала, эта метка не обновляется в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="4a563-144">В этом случае пользователи будут по-прежнему видеть метку чувствительности, примененную к группе в заголовке личного канала.</span><span class="sxs-lookup"><span data-stu-id="4a563-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="4a563-145">**Временем распространения изменений, примененных к меткам чувствительности за пределами приложения Teams**</span><span class="sxs-lookup"><span data-stu-id="4a563-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="4a563-146">Изменения, внесенные в метки секретности за пределами приложения Teams, могут занимать до 24 часов, чтобы отразить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="4a563-147">Это относится к изменениям включения или отключения меток для клиента, изменения имен, параметров и политик подписей.</span><span class="sxs-lookup"><span data-stu-id="4a563-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="4a563-148">Кроме того, любые изменения метки, внесенные непосредственно в группу или на семейство веб-сайтов SharePoint, для которых может потребоваться выполнение команды, могут пройти до 24 часов, чтобы распространить его в приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="4a563-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>