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
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806279"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="4f232-103">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="4f232-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="4f232-104">В зависимости от числа физических расположений в организации вы можете добавить здания, этажи и офисы, чтобы создать более конкретное местоположение для экстренного нахождения.</span><span class="sxs-lookup"><span data-stu-id="4f232-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="4f232-105">Дополнительные [сведения см. в подмносях "Управление](what-are-emergency-locations-addresses-and-call-routing.md) экстренным вызовом".</span><span class="sxs-lookup"><span data-stu-id="4f232-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="4f232-106">Чтобы узнать, как получить план звонков и сколько они стоят, см. лицензирование [надстройки Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="4f232-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="4f232-107">Вы управляете местоположениями для экстренного помощи в организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f232-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="4f232-108">Добавление места для экстренного нахождения</span><span class="sxs-lookup"><span data-stu-id="4f232-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4f232-109">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f232-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4f232-110">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="4f232-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4f232-111">В списке щелкните название расположения, для которого вы хотите добавить место.</span><span class="sxs-lookup"><span data-stu-id="4f232-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="4f232-112">На вкладке **"Места"** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="4f232-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="4f232-113">Введите имя места и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="4f232-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4f232-114">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f232-114">Using PowerShell</span></span>

<span data-ttu-id="4f232-115">См. [new-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="4f232-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="4f232-116">Изменение места для экстренного размещения</span><span class="sxs-lookup"><span data-stu-id="4f232-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4f232-117">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f232-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4f232-118">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="4f232-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4f232-119">В списке щелкните имя расположения, для которого вы хотите изменить место.</span><span class="sxs-lookup"><span data-stu-id="4f232-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="4f232-120">На **вкладке "Места"** выберите место, которое нужно изменить, и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="4f232-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="4f232-121">Обновив сведения о месте, нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="4f232-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4f232-122">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f232-122">Using PowerShell</span></span>

<span data-ttu-id="4f232-123">См. [set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="4f232-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="4f232-124">Удаление места из местоположения для экстренного экстренного ситуация</span><span class="sxs-lookup"><span data-stu-id="4f232-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4f232-125">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f232-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4f232-126">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="4f232-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4f232-127">В списке щелкните название расположения, из которого вы хотите удалить место.</span><span class="sxs-lookup"><span data-stu-id="4f232-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="4f232-128">На **вкладке "Места"** выберите место, которое нужно удалить, и нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="4f232-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4f232-129">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f232-129">Using PowerShell</span></span>

<span data-ttu-id="4f232-130">См. [remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="4f232-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4f232-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4f232-131">Related topics</span></span>

- [<span data-ttu-id="4f232-132">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="4f232-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="4f232-133">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="4f232-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="4f232-134">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="4f232-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
