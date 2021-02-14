---
title: Добавление, изменение и удаление местоположений для экстренного устранения
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
description: 'Узнайте, как добавить, изменить или удалить расположение для экстренного устранения экстренных служб для вашей организации в Центре администрирования Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799949"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="3ac68-103">Добавление, изменение и удаление местоположения организации для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="3ac68-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="3ac68-104">С номером телефона должно быть связано местоположение для экстренного помощи, но время может различаться в зависимости от страны и региона.</span><span class="sxs-lookup"><span data-stu-id="3ac68-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="3ac68-105">Например, в США при назначении пользователю телефонного номера необходимо связать местоположение для экстренного помощи.</span><span class="sxs-lookup"><span data-stu-id="3ac68-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="3ac68-106">Если вы хотите получить телефонные номера в Microsoft 365 или Office 365 или перенести их у текущего поставщика услуг, вам потребуется связать местоположение для экстренного помощи с номером телефона в Великобритании.</span><span class="sxs-lookup"><span data-stu-id="3ac68-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="3ac68-107">Независимо от страны и региона вы можете добавить место или место в местоположение для экстренного помощи и удалить его.</span><span class="sxs-lookup"><span data-stu-id="3ac68-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="3ac68-108">В зависимости от числа физических мест в организации можно создавать расположения для зданий, этажей и офисов.</span><span class="sxs-lookup"><span data-stu-id="3ac68-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="3ac68-109">См. [управление экстренным вызовом.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="3ac68-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="3ac68-110">Чтобы узнать, как получить план звонков и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="3ac68-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="3ac68-111">Вы управляете местоположениями в организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ac68-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="3ac68-112">Добавление местоположения для экстренного помощи</span><span class="sxs-lookup"><span data-stu-id="3ac68-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ac68-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ac68-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ac68-114">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="3ac68-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ac68-115">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3ac68-115">Click **Add**.</span></span>
3. <span data-ttu-id="3ac68-116">Введите имя и описание расположения.</span><span class="sxs-lookup"><span data-stu-id="3ac68-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="3ac68-117">Выберите страну или регион и введите адрес.</span><span class="sxs-lookup"><span data-stu-id="3ac68-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ac68-118">В Бельгии, Франции, Германии, Ирландии, Нидерландах и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 или Office 365 адрес, за используемый для получения номера, должен соответствовать коду города.</span><span class="sxs-lookup"><span data-stu-id="3ac68-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="3ac68-119">Если адрес не найден и вы хотите изменить его вручную, включите редактирование **адреса вручную.**</span><span class="sxs-lookup"><span data-stu-id="3ac68-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="3ac68-120">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3ac68-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ac68-121">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ac68-121">Using PowerShell</span></span>

<span data-ttu-id="3ac68-122">См. [new-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="3ac68-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="3ac68-123">Изменение местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="3ac68-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ac68-124">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ac68-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ac68-125">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="3ac68-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ac68-126">В списке выберите расположение, которое вы хотите изменить, и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="3ac68-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="3ac68-127">Внести нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="3ac68-127">Make the changes you want.</span></span>
4. <span data-ttu-id="3ac68-128">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3ac68-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ac68-129">Вы можете изменить адрес расположения, только если адрес не проверен.</span><span class="sxs-lookup"><span data-stu-id="3ac68-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="3ac68-130">Если адрес уже проверен и вам нужно изменить его, удалите расположение, а затем создайте новое расположение с правильным адресом.</span><span class="sxs-lookup"><span data-stu-id="3ac68-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ac68-131">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ac68-131">Using PowerShell</span></span>

<span data-ttu-id="3ac68-132">См. [set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="3ac68-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="3ac68-133">Удаление местоположения для экстренного устранения</span><span class="sxs-lookup"><span data-stu-id="3ac68-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ac68-134">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ac68-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ac68-135">В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**</span><span class="sxs-lookup"><span data-stu-id="3ac68-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ac68-136">В списке выберите расположение, которое вы хотите удалить, и нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="3ac68-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ac68-137">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ac68-137">Using PowerShell</span></span>

<span data-ttu-id="3ac68-138">См. [remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="3ac68-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ac68-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3ac68-139">Related topics</span></span>

- [<span data-ttu-id="3ac68-140">Управление экстренным вызовом</span><span class="sxs-lookup"><span data-stu-id="3ac68-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="3ac68-141">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="3ac68-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="3ac68-142">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="3ac68-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="3ac68-143">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="3ac68-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
