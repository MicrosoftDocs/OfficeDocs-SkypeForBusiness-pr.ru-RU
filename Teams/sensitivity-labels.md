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
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593867"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="56d33-103">Метки конфиденциальности для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56d33-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="56d33-104">[Метки конфиденциальности](/microsoft-365/compliance/sensitivity-labels) позволяют администраторам Teams защищать и регулировать доступ к конфиденциальному контенту организации, созданному во время совместной работы в командах.</span><span class="sxs-lookup"><span data-stu-id="56d33-104">[Sensitivity labels](/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="56d33-105">После настройки меток конфиденциальности в связанных [](/microsoft-365/compliance/go-to-the-securitycompliance-center)с ними политиках в Центре соответствия требованиям Майкрософт эти метки можно применять к командам в организации.</span><span class="sxs-lookup"><span data-stu-id="56d33-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="56d33-106">Метки конфиденциальности в настоящее время неподтверчены в командах класса для клиентов, использующих Teams для образования.</span><span class="sxs-lookup"><span data-stu-id="56d33-106">Sensitivity labels are currently unsupported in class teams for customers using Teams Education SKUs.</span></span> <span data-ttu-id="56d33-107">Дополнительные информацию о лицензировании см. в Microsoft Teams [службы.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="56d33-107">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="56d33-108">В чем разница между метами конфиденциальности и Teams классификацией?</span><span class="sxs-lookup"><span data-stu-id="56d33-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="56d33-109">Метки конфиденциальности отличаются от меток классификации, также известных как классификация группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56d33-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="56d33-110">Метки классификации — это текстовые строки, которые могут быть связаны с группой Microsoft 365, но не имеют фактических политик, связанных с ними.</span><span class="sxs-lookup"><span data-stu-id="56d33-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="56d33-111">Метки классификации используются как метаданные, а затем для применения политик необходимо использовать другие методы, например внутренние средства и сценарии.</span><span class="sxs-lookup"><span data-stu-id="56d33-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="56d33-112">Преимущество использования меток конфиденциальности в том, что их политики автоматически применяются сквозные путем сочетания платформы Microsoft 365 Groups, центра соответствия требованиям и Teams служб.</span><span class="sxs-lookup"><span data-stu-id="56d33-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="56d33-113">Метки конфиденциальности обеспечивают мощную поддержку инфраструктуры для защиты конфиденциальных данных организации и обеспечения соответствия внутренним политикам и нормативным актам.</span><span class="sxs-lookup"><span data-stu-id="56d33-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="56d33-114">Если вы используете метки классификации, дополнительные сведения и инструкции по их переносу на метки конфиденциальности см. в следующей документации: классификация группы [Azure AD.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="56d33-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="56d33-115">Примеры сценариев меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="56d33-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="56d33-116">Примеры сценариев использования меток конфиденциальности с Teams организации:</span><span class="sxs-lookup"><span data-stu-id="56d33-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="56d33-117">Настройка уровня конфиденциальности (открытого или закрытого) для команд</span><span class="sxs-lookup"><span data-stu-id="56d33-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="56d33-118">Управление гостевом доступом к командам</span><span class="sxs-lookup"><span data-stu-id="56d33-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="56d33-119">Настройка уровня конфиденциальности для команд</span><span class="sxs-lookup"><span data-stu-id="56d33-119">Set the privacy level for teams</span></span>

<span data-ttu-id="56d33-120">Вы можете создать и настроить метку конфиденциальности, которая при ее применении позволяет пользователям создавать команды с определенными настройками конфиденциальности (общедоступными или частными).</span><span class="sxs-lookup"><span data-stu-id="56d33-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="56d33-121">Например, вы создаете и публикуете метку конфиденциальности "Конфиденциальная", для параметра конфиденциальности метки настроена частная **.**</span><span class="sxs-lookup"><span data-stu-id="56d33-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="56d33-122">В результате любая команда, созданная с помощью этой метки, должна быть закрытой.</span><span class="sxs-lookup"><span data-stu-id="56d33-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="56d33-123">Когда пользователь создает новую команду и  выбирает метку Конфиденциально, для него доступен только параметр **конфиденциальности Частный.**</span><span class="sxs-lookup"><span data-stu-id="56d33-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="56d33-124">Другие параметры конфиденциальности, такие как "Общедоступный" и "В масштабе организации", недоступны для выбора:</span><span class="sxs-lookup"><span data-stu-id="56d33-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Снимок экрана: метка конфиденциальности](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="56d33-126">Кроме того, вы создаете и публикуете метку конфиденциальности "Общие", для параметра конфиденциальности метки настроена как **общеординированная.**</span><span class="sxs-lookup"><span data-stu-id="56d33-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="56d33-127">Когда пользователь создает новую команду, он может создавать общедоступные и общедоступные команды только при выборе этой метки:</span><span class="sxs-lookup"><span data-stu-id="56d33-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Снимок экрана: метка общей конфиденциальности](media/sensitivity-labels-general-example.png)

<span data-ttu-id="56d33-129">Когда группа будет создана, метка конфиденциальности будет видна в правом верхнем углу каналов команды.</span><span class="sxs-lookup"><span data-stu-id="56d33-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> 

> [!NOTE]
> <span data-ttu-id="56d33-130">Если вы используете иерархические метки родительского ребенка, например "Конфиденциально\Финансы", то в заглавном канале будет показана только метка родительского ребенка.</span><span class="sxs-lookup"><span data-stu-id="56d33-130">If you are using hierarchical parent-child labels such as "Confidential\Finance", then only the parent label will be shown in the channel header.</span></span>

![Снимок экрана: метка конфиденциальности в канале команды](media/sensitivity-labels-channel.png)

<span data-ttu-id="56d33-132">Владелец команды может изменить метку конфиденциальности и параметр конфиденциальности группы в любое время, перейдите в команду и нажмите кнопку **Изменить команду**.</span><span class="sxs-lookup"><span data-stu-id="56d33-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Снимок экрана: метка конфиденциальности в свойствах группы](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="56d33-134">Управление гостевом доступом к командам</span><span class="sxs-lookup"><span data-stu-id="56d33-134">Control guest access to teams</span></span>

<span data-ttu-id="56d33-135">Метки конфиденциальности можно использовать для управления гостевом доступом к командам.</span><span class="sxs-lookup"><span data-stu-id="56d33-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="56d33-136">Teams с меткой, которая не разрешает гостевой доступ, доступна только пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="56d33-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="56d33-137">Людей за пределами организации добавить в команду нельзя.</span><span class="sxs-lookup"><span data-stu-id="56d33-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="56d33-138">Microsoft Teams центре администрирования</span><span class="sxs-lookup"><span data-stu-id="56d33-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="56d33-139">Метки конфиденциальности можно применять при создании или редактировании группы в Microsoft Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="56d33-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="56d33-140">Метки конфиденциальности также видны в свойствах  группы и в столбце Классификация на странице **Управление** группами Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="56d33-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="56d33-141">Ограничения</span><span class="sxs-lookup"><span data-stu-id="56d33-141">Limitations</span></span>

<span data-ttu-id="56d33-142">Перед использованием меток конфиденциальности для Teams следует помнить о следующих ограничениях:</span><span class="sxs-lookup"><span data-stu-id="56d33-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="56d33-143">**Родительские имена не отображаются для подлябелей**</span><span class="sxs-lookup"><span data-stu-id="56d33-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="56d33-144">Teams поддерживает подлябели, но не отображает имя родительской метки.</span><span class="sxs-lookup"><span data-stu-id="56d33-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="56d33-145">Например, в **режиме Конфиденциально** \\ **все сотрудники** отображается **"Все сотрудники".**</span><span class="sxs-lookup"><span data-stu-id="56d33-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="56d33-146">**Метки конфиденциальности не поддерживаются API Teams Graph, powerShell и шаблонами**</span><span class="sxs-lookup"><span data-stu-id="56d33-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="56d33-147">Пользователи не смогут указывать метки конфиденциальности при создании команд непосредственно с помощью API Teams Graph, командлетов Teams PowerShell и Teams шаблонов.</span><span class="sxs-lookup"><span data-stu-id="56d33-147">Users won't be able to specify sensitivity labels while creating teams directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span> <span data-ttu-id="56d33-148">Однако современные Graph API и powerShell позволяют создавать группы с метами.</span><span class="sxs-lookup"><span data-stu-id="56d33-148">However Modern Groups Graph APIs and PowerShell cmdlets do allow creation of groups with labels.</span></span> <span data-ttu-id="56d33-149">Чтобы пользователи могли сначала создавать группы с метами с помощью API групп Graph API или powerShell, а затем преобразовывать их в Teams.</span><span class="sxs-lookup"><span data-stu-id="56d33-149">So users can first create Groups with labels using Groups Graph APIs or PowerShell cmdlets and then convert these Groups in to Teams.</span></span>

- <span data-ttu-id="56d33-150">**Поддержка частных каналов**</span><span class="sxs-lookup"><span data-stu-id="56d33-150">**Support for private channels**</span></span>
    
    <span data-ttu-id="56d33-151">Закрытые каналы, созданные в команде, наследуют метку конфиденциальности, примененную к команде.</span><span class="sxs-lookup"><span data-stu-id="56d33-151">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="56d33-152">Та же метка автоматически применяется на SharePoint для частного канала.</span><span class="sxs-lookup"><span data-stu-id="56d33-152">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="56d33-153">Однако если пользователь изменяет метку конфиденциальности непосредственно на SharePoint для частного канала, это изменение метки не отражается в Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="56d33-153">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="56d33-154">В этом случае пользователи будут по-прежнему видеть исходную метку конфиденциальности, примененную к команде, в заглавном канале частного канала.</span><span class="sxs-lookup"><span data-stu-id="56d33-154">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="56d33-155">Создание и настройка меток конфиденциальности для Teams</span><span class="sxs-lookup"><span data-stu-id="56d33-155">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="56d33-156">Чтобы создать и настроить метки конфиденциальности для Teams, воспользуйтесь инструкциями в документации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56d33-156">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="56d33-157">Используйте метки конфиденциальности для защиты содержимого в [Microsoft Teams, Microsoft 365 группах и SharePoint сайтах.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="56d33-157">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
