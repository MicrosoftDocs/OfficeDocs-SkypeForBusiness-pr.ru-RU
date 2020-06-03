---
title: Добавление, изменение и удаление мест для точек экстренного реагирования
author: lanachin
ms.author: v-lanac
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
description: Сведения о том, как добавлять, изменять и удалять место для экстренных случаев для Организации в центре администрирования Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539436"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="ed993-103">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="ed993-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="ed993-104">В зависимости от количества физических местоположений в вашей организации вы можете добавить места для зданий, полs и офисов, чтобы создать более конкретное место для экстренных случаев.</span><span class="sxs-lookup"><span data-stu-id="ed993-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="ed993-105">Более подробную информацию вы видите в разделе [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md) помощи.</span><span class="sxs-lookup"><span data-stu-id="ed993-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="ed993-106">Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ed993-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ed993-107">Вы управляете местоположениями для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed993-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="ed993-108">Добавление места в место для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="ed993-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ed993-109">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed993-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ed993-110">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="ed993-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ed993-111">В списке щелкните имя расположения, для которого вы хотите добавить место.</span><span class="sxs-lookup"><span data-stu-id="ed993-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="ed993-112">На вкладке **места** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ed993-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="ed993-113">Введите имя места, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ed993-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed993-114">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed993-114">Using PowerShell</span></span>

<span data-ttu-id="ed993-115">Просмотреть раздел [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="ed993-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="ed993-116">Изменение места для экстренных случаев</span><span class="sxs-lookup"><span data-stu-id="ed993-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ed993-117">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed993-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ed993-118">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="ed993-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ed993-119">В списке щелкните имя расположения, для которого вы хотите изменить место.</span><span class="sxs-lookup"><span data-stu-id="ed993-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="ed993-120">На вкладке **места** выберите место, которое вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="ed993-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="ed993-121">Обновите сведения о расположении и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ed993-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed993-122">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed993-122">Using PowerShell</span></span>

<span data-ttu-id="ed993-123">Смотрите раздел [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="ed993-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="ed993-124">Удаление места из места для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="ed993-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ed993-125">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed993-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ed993-126">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="ed993-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ed993-127">В списке щелкните имя расположения, для которого нужно удалить место.</span><span class="sxs-lookup"><span data-stu-id="ed993-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="ed993-128">На вкладке **места** выберите место, которое вы хотите удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ed993-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed993-129">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed993-129">Using PowerShell</span></span>

<span data-ttu-id="ed993-130">В разделе [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="ed993-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ed993-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ed993-131">Related topics</span></span>

- [<span data-ttu-id="ed993-132">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="ed993-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ed993-133">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="ed993-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ed993-134">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="ed993-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
