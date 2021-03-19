---
title: Метки конфиденциальности для Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: Узнайте, как использовать метки конфиденциальности для защиты команд в Microsoft Teams.
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875109"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="7be54-103">Метки конфиденциальности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7be54-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="7be54-104">[Метки конфиденциальности позволяют](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) администраторам Teams защищать и регулировать доступ к конфиденциальному контенту организации, созданному во время совместной работы в командах.</span><span class="sxs-lookup"><span data-stu-id="7be54-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="7be54-105">После настройки меток конфиденциальности в связанных с ними политиках в Центре соответствия требованиям Майкрософт [эти](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)метки можно применять к командам в организации.</span><span class="sxs-lookup"><span data-stu-id="7be54-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="7be54-106">Метки конфиденциальности в настоящее время неподтверчены для клиентов, использующих skUS Teams для образования.</span><span class="sxs-lookup"><span data-stu-id="7be54-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="7be54-107">Дополнительные информацию о лицензировании см. в описании [службы Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="7be54-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="7be54-108">В чем разница между метами конфиденциальности и метами классификации Teams?</span><span class="sxs-lookup"><span data-stu-id="7be54-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="7be54-109">Метки конфиденциальности отличаются от меток классификации, также известных как классификация групп Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7be54-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="7be54-110">Метки классификации — это текстовые строки, которые можно связывать с группой Microsoft 365, но не связанные с ними фактические политики.</span><span class="sxs-lookup"><span data-stu-id="7be54-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="7be54-111">Метки классификации используются как метаданные, а затем для применения политик необходимо использовать другие методы, например внутренние средства и сценарии.</span><span class="sxs-lookup"><span data-stu-id="7be54-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="7be54-112">Преимущество меток конфиденциальности состоит в том, что их политики автоматически применяются на основе сочетания платформ Microsoft 365 Groups, Центра соответствия требованиям и служб Teams.</span><span class="sxs-lookup"><span data-stu-id="7be54-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="7be54-113">Метки конфиденциальности обеспечивают мощную поддержку инфраструктуры для защиты конфиденциальных данных организации и обеспечения соответствия внутренним политикам или нормативным актам.</span><span class="sxs-lookup"><span data-stu-id="7be54-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="7be54-114">Если вы используете метки классификации, дополнительные сведения и инструкции по их переносу на метки конфиденциальности см. в следующей документации: классификация группы [Azure AD.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="7be54-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="7be54-115">Примеры сценариев меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7be54-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="7be54-116">Примеры сценариев использования меток конфиденциальности в Teams в организации:</span><span class="sxs-lookup"><span data-stu-id="7be54-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="7be54-117">Настройка уровня конфиденциальности (открытого или закрытого) для команд</span><span class="sxs-lookup"><span data-stu-id="7be54-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="7be54-118">Управление гостевом доступом к командам</span><span class="sxs-lookup"><span data-stu-id="7be54-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="7be54-119">Настройка уровня конфиденциальности для команд</span><span class="sxs-lookup"><span data-stu-id="7be54-119">Set the privacy level for teams</span></span>

<span data-ttu-id="7be54-120">Вы можете создать и настроить метку конфиденциальности, которая при ее применении позволяет пользователям создавать команды с определенным параметром конфиденциальности (общедоступный или закрытый).</span><span class="sxs-lookup"><span data-stu-id="7be54-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="7be54-121">Например, вы создаете и публикуете метку конфиденциальности "Конфиденциально", которая имеет параметр конфиденциальности **"Частная".**</span><span class="sxs-lookup"><span data-stu-id="7be54-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="7be54-122">В результате любая команда, созданная с этой меткой, должна быть закрытой.</span><span class="sxs-lookup"><span data-stu-id="7be54-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="7be54-123">Когда пользователь создает команду и выбирает  метку "Конфиденциально", для него доступен только параметр **конфиденциальности "Частное".**</span><span class="sxs-lookup"><span data-stu-id="7be54-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="7be54-124">Другие параметры конфиденциальности, такие как "Общедоступный" и "Все организации", недоступны для выбора:</span><span class="sxs-lookup"><span data-stu-id="7be54-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Снимок экрана: метка конфиденциальности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="7be54-126">Аналогично вы создаете и публикуете метку конфиденциальности с именем "Общие", для параметра конфиденциальности метки настроен параметр "Общеординированная". </span><span class="sxs-lookup"><span data-stu-id="7be54-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="7be54-127">Когда пользователь создает новую команду, он может создавать общедоступные и общедоступные команды, только выбрав эту метку:</span><span class="sxs-lookup"><span data-stu-id="7be54-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Снимок экрана: метка общей конфиденциальности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="7be54-129">Когда группа будет создана, метка конфиденциальности будет видна в ее верхнем правом углу.</span><span class="sxs-lookup"><span data-stu-id="7be54-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> <span data-ttu-id="7be54-130">Обратите внимание, что если вы используете иерархические родительские метки детей, такие как "Конфиденциально\Финансы", то в заглавном канале будет показываться только родительская метка.</span><span class="sxs-lookup"><span data-stu-id="7be54-130">Note that if you are using hierarchical parent child labels such as "Confidential\Finance" then only the parent label will be showin the channel header.</span></span>


![Снимок экрана: метка конфиденциальности в канале группы](media/sensitivity-labels-channel.png)

<span data-ttu-id="7be54-132">Владелец команды может в любое время изменить метку конфиденциальности и параметр конфиденциальности команды, перейдите в команду и нажмите кнопку "Изменить **команду".**</span><span class="sxs-lookup"><span data-stu-id="7be54-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Снимок экрана: метка конфиденциальности в свойствах группы](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="7be54-134">Управление гостевом доступом к командам</span><span class="sxs-lookup"><span data-stu-id="7be54-134">Control guest access to teams</span></span>

<span data-ttu-id="7be54-135">Метки конфиденциальности можно использовать для управления гостевом доступом к командам.</span><span class="sxs-lookup"><span data-stu-id="7be54-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="7be54-136">Команды, созданные с меткой, которая не разрешает гостевой доступ, доступны только пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be54-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="7be54-137">Людей за пределами организации добавить в команду нельзя.</span><span class="sxs-lookup"><span data-stu-id="7be54-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="7be54-138">Центр администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7be54-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="7be54-139">Метки конфиденциальности можно применять при создании или редактировании группы в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7be54-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="7be54-140">Метки конфиденциальности также видны в свойствах группы и  в столбце **"Классификация"** на странице "Управление командами" Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7be54-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="7be54-141">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7be54-141">Limitations</span></span>

<span data-ttu-id="7be54-142">Прежде чем использовать метки конфиденциальности для Teams, следует помнить о следующих ограничениях:</span><span class="sxs-lookup"><span data-stu-id="7be54-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="7be54-143">**Родительские имена не отображаются для подлябелей**</span><span class="sxs-lookup"><span data-stu-id="7be54-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="7be54-144">Teams поддерживает подлябели, но не отображает имя родительской метки.</span><span class="sxs-lookup"><span data-stu-id="7be54-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="7be54-145">Например, **"Конфиденциально** \\ **все сотрудники"** отображается как **"Все сотрудники".**</span><span class="sxs-lookup"><span data-stu-id="7be54-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="7be54-146">**Метки конфиденциальности не поддерживаются API Teams Graph, командлетами PowerShell и шаблонами**</span><span class="sxs-lookup"><span data-stu-id="7be54-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="7be54-147">Пользователи не смогут применять метки конфиденциальности к командам, созданным непосредственно с помощью API Teams Graph, командлетов Teams PowerShell и шаблонов Teams.</span><span class="sxs-lookup"><span data-stu-id="7be54-147">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="7be54-148">**Поддержка частных каналов**</span><span class="sxs-lookup"><span data-stu-id="7be54-148">**Support for private channels**</span></span>
    
    <span data-ttu-id="7be54-149">Закрытые каналы, созданные в команде, наследуют метку конфиденциальности, примененную к группе.</span><span class="sxs-lookup"><span data-stu-id="7be54-149">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="7be54-150">Та же метка автоматически применяется в коллекции веб-сайтов SharePoint для частного канала.</span><span class="sxs-lookup"><span data-stu-id="7be54-150">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="7be54-151">Однако если пользователь изменяет метку конфиденциальности непосредственно на сайте SharePoint для частного канала, это изменение метки не отражается в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="7be54-151">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="7be54-152">В этом сценарии пользователи будут по-прежнему видеть исходную метку конфиденциальности, примененную к группе, в заглавном канале частного канала.</span><span class="sxs-lookup"><span data-stu-id="7be54-152">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="7be54-153">Создание и настройка меток конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="7be54-153">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="7be54-154">Чтобы создать и настроить метки конфиденциальности для Teams, воспользуйтесь инструкциями из документации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7be54-154">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="7be54-155">[Используйте метки конфиденциальности для защиты контента в Microsoft Teams, группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="7be54-155">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
