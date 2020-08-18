---
title: Добавление, изменение и удаление местоположений для экстренных случаев
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
description: 'Сведения о том, как добавить, изменить или удалить расположение для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 762246630d245acf92c16aff8df2c9392a307b07
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788573"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="b21a6-103">Добавление, изменение и удаление местоположения организации для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="b21a6-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="b21a6-104">Место для экстренного реагирования должно быть связано с номером телефона, но это может отличаться в зависимости от стран и регионов.</span><span class="sxs-lookup"><span data-stu-id="b21a6-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="b21a6-105">Например, в США вы должны ассоциировать место, когда вы назначаете пользователю номер телефона.</span><span class="sxs-lookup"><span data-stu-id="b21a6-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="b21a6-106">В Великобритании вы должны связать место с телефонным номером, если вы получаете номера телефонов от Microsoft 365 или Office 365 или переадресовать номера телефонов, предоставленные текущим поставщиком услуг.</span><span class="sxs-lookup"><span data-stu-id="b21a6-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="b21a6-107">Вне зависимости от того, где находится ваша страна или регион, вы можете добавить место или места в место для экстренного реагирования и удалить место для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="b21a6-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="b21a6-108">В зависимости от количества физических местоположений в вашей организации вы можете создавать места для зданий, этажей и офисов.</span><span class="sxs-lookup"><span data-stu-id="b21a6-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="b21a6-109">Смотрите [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md)помощи.</span><span class="sxs-lookup"><span data-stu-id="b21a6-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="b21a6-110">Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="b21a6-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="b21a6-111">Вы управляете местоположениями для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b21a6-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="b21a6-112">Добавление места для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="b21a6-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b21a6-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b21a6-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b21a6-114">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="b21a6-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b21a6-115">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-115">Click **Add**.</span></span>
3. <span data-ttu-id="b21a6-116">Введите имя и описание местоположения.</span><span class="sxs-lookup"><span data-stu-id="b21a6-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="b21a6-117">Выберите страну или регион, а затем введите адрес.</span><span class="sxs-lookup"><span data-stu-id="b21a6-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b21a6-118">В Бельгии, Франции, Германии, Ирландии, Нидерланды и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 или Office 365 адрес, указанный в местоположении для экстренного реагирования, который используется для получения номера, должен совпадать с кодом города номера телефона.</span><span class="sxs-lookup"><span data-stu-id="b21a6-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="b21a6-119">Если адрес не найден и вы хотите изменить адрес вручную, включите **параметр изменить адрес вручную**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="b21a6-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b21a6-121">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b21a6-121">Using PowerShell</span></span>

<span data-ttu-id="b21a6-122">Просмотреть раздел [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="b21a6-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="b21a6-123">Изменение местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="b21a6-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b21a6-124">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b21a6-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b21a6-125">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="b21a6-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b21a6-126">Выберите в списке расположение, которое вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="b21a6-127">Внесите нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="b21a6-127">Make the changes you want.</span></span>
4. <span data-ttu-id="b21a6-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b21a6-129">Сведения об адресе можно изменить только в том случае, если адрес не прошел проверку.</span><span class="sxs-lookup"><span data-stu-id="b21a6-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="b21a6-130">Если адрес уже прошел проверку и вам нужно изменить адрес, удалите его, а затем создайте новое расположение с правильным адресом.</span><span class="sxs-lookup"><span data-stu-id="b21a6-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b21a6-131">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b21a6-131">Using PowerShell</span></span>

<span data-ttu-id="b21a6-132">Смотрите раздел [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="b21a6-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="b21a6-133">Удаление местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="b21a6-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b21a6-134">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b21a6-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b21a6-135">В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="b21a6-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b21a6-136">Выберите в списке место, которое вы хотите удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b21a6-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b21a6-137">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b21a6-137">Using PowerShell</span></span>

<span data-ttu-id="b21a6-138">В разделе [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="b21a6-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b21a6-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b21a6-139">Related topics</span></span>

- [<span data-ttu-id="b21a6-140">Управление вызовом экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b21a6-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="b21a6-141">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="b21a6-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="b21a6-142">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="b21a6-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="b21a6-143">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="b21a6-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
