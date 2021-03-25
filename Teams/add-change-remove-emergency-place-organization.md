---
title: Добавление, изменение и удаление мест для экстренного размещения
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Узнайте, как добавить, изменить или удалить расположение для экстренного решения для вашей организации в Центре администрирования Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121507"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="79189-103">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="79189-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="79189-104">В зависимости от числа физических расположений в организации вы можете добавить здания, этажи и офисы, чтобы создать более конкретное местоположение для экстренного нахождения.</span><span class="sxs-lookup"><span data-stu-id="79189-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="79189-105">Дополнительные [сведения см. в подмносях "Управление](what-are-emergency-locations-addresses-and-call-routing.md) экстренным вызовом".</span><span class="sxs-lookup"><span data-stu-id="79189-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="79189-106">Чтобы узнать, как получить план звонков и сколько они стоят, см. лицензирование [надстройки Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="79189-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="79189-107">Вы управляете местоположениями в организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79189-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="79189-108">Добавление места для экстренного нахождения</span><span class="sxs-lookup"><span data-stu-id="79189-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="79189-109">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79189-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="79189-110">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="79189-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="79189-111">В списке щелкните название расположения, для которого вы хотите добавить место.</span><span class="sxs-lookup"><span data-stu-id="79189-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="79189-112">На вкладке **"Места"** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="79189-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="79189-113">Введите имя места и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="79189-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="79189-114">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="79189-114">Using PowerShell</span></span>

<span data-ttu-id="79189-115">См. [new-CsOnlineLisLocation.](/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="79189-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="79189-116">Изменение места для экстренного расположения</span><span class="sxs-lookup"><span data-stu-id="79189-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="79189-117">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79189-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="79189-118">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="79189-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="79189-119">В списке щелкните имя расположения, для которого вы хотите изменить место.</span><span class="sxs-lookup"><span data-stu-id="79189-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="79189-120">На **вкладке "Места"** выберите место, которое нужно изменить, и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="79189-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="79189-121">Обновив сведения о месте, нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="79189-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="79189-122">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="79189-122">Using PowerShell</span></span>

<span data-ttu-id="79189-123">См. [set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="79189-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="79189-124">Удаление места из местоположения для экстренного помощи</span><span class="sxs-lookup"><span data-stu-id="79189-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="79189-125">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79189-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="79189-126">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="79189-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="79189-127">В списке щелкните название расположения, из которого вы хотите удалить место.</span><span class="sxs-lookup"><span data-stu-id="79189-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="79189-128">На **вкладке "Места"** выберите место, которое нужно удалить, и нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="79189-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="79189-129">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="79189-129">Using PowerShell</span></span>

<span data-ttu-id="79189-130">См. [remove-CsOnlineLisLocation.](/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="79189-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="79189-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="79189-131">Related topics</span></span>

- [<span data-ttu-id="79189-132">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="79189-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="79189-133">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="79189-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="79189-134">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="79189-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)