---
title: Добавление, изменение и удаление местоположения организации для экстренного реагирования
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
f1keywords: None
description: 'Сведения о том, как добавить, изменить или удалить расположение для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams. '
ms.openlocfilehash: ddef21811f4317f1ac10d5eb7d94bd67f1faaaad
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568701"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="0d745-103">Добавление, изменение и удаление местоположения организации для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="0d745-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="0d745-104">Место для экстренного реагирования должно быть связано с номером телефона, но это может отличаться в зависимости от стран и регионов.</span><span class="sxs-lookup"><span data-stu-id="0d745-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="0d745-105">Например, в США вы должны ассоциировать место, когда вы назначаете пользователю номер телефона.</span><span class="sxs-lookup"><span data-stu-id="0d745-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="0d745-106">В Великобритании вы должны связать место с телефонным номером при получении номеров телефонов из Office 365 или передать номера из вашего текущего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="0d745-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="0d745-107">Вне зависимости от того, где находится ваша страна или регион, вы можете добавить место или места в место для экстренного реагирования и удалить место для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="0d745-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="0d745-108">В зависимости от количества физических местоположений в вашей организации вы можете создавать места для зданий, этажей и офисов.</span><span class="sxs-lookup"><span data-stu-id="0d745-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="0d745-109">Посмотрите [, что такое местоположения для экстренного реагирования, адреса и маршрутизация звонков](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="0d745-109">See [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="0d745-110">Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0d745-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="0d745-111">Добавление места для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="0d745-111">Add an emergency location</span></span>

1. <span data-ttu-id="0d745-112">В левой области навигации центра администрирования Microsoft Teams **выберите пункты** > **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="0d745-112">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0d745-113">Нажмите кнопку **Добавить расположение**.</span><span class="sxs-lookup"><span data-stu-id="0d745-113">Click **Add Location**.</span></span>
3. <span data-ttu-id="0d745-114">Введите имя и описание местоположения.</span><span class="sxs-lookup"><span data-stu-id="0d745-114">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="0d745-115">Выберите страну или регион, а затем введите адрес.</span><span class="sxs-lookup"><span data-stu-id="0d745-115">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d745-116">В бельгийском, Франции, Германии, Ирландии, Нидерландов и Испании важно понимать, что для успешной активации номера телефона в Office 365 адрес, указанный в местоположении для экстренного реагирования, который используется для получения номера, должен соответствовать номеру телефона. код города.</span><span class="sxs-lookup"><span data-stu-id="0d745-116">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that  to successfully activate a phone number in Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number’s area code.</span></span>
5. <span data-ttu-id="0d745-117">Если адрес не найден и вы хотите изменить адрес вручную, включите **параметр Разрешить изменение формы адреса вручную, если выбранный адрес не удается найти**.</span><span class="sxs-lookup"><span data-stu-id="0d745-117">If the address isn't found and you want to manually edit the address, turn on **Let me edit the address form manually if the address selected can't be found**.</span></span>
6. <span data-ttu-id="0d745-118">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0d745-118">Click **Save**.</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="0d745-119">Изменение местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="0d745-119">Change an emergency location</span></span>

1. <span data-ttu-id="0d745-120">В левой области навигации центра администрирования Microsoft Teams **выберите пункты** > **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="0d745-120">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0d745-121">Выберите в списке расположение, которое вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="0d745-121">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="0d745-122">Внесите нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="0d745-122">Make the changes you want.</span></span>
4. <span data-ttu-id="0d745-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0d745-123">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0d745-124">Сведения об адресе можно изменить только в том случае, если адрес не прошел проверку.</span><span class="sxs-lookup"><span data-stu-id="0d745-124">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="0d745-125">Если адрес уже прошел проверку и вам нужно изменить адрес, удалите его, а затем создайте новое расположение с правильным адресом.</span><span class="sxs-lookup"><span data-stu-id="0d745-125">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="0d745-126">Удаление местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="0d745-126">Remove an emergency location</span></span>

1. <span data-ttu-id="0d745-127">В левой области навигации центра администрирования Microsoft Teams **выберите пункты** > **адреса для экстренного**реагирования.</span><span class="sxs-lookup"><span data-stu-id="0d745-127">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="0d745-128">Выберите в списке место, которое вы хотите удалить, и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="0d745-128">In the list, select the location that you want to remove, and then click **Delete**</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0d745-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0d745-129">Related topics</span></span>

<span data-ttu-id="0d745-130">-[Что такое места для экстренного реагирования, места и маршрут звонков?](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="0d745-130">-[What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md)</span></span>
- [<span data-ttu-id="0d745-131">Добавление, изменение и удаление места для расположения для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="0d745-131">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="0d745-132">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="0d745-132">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="0d745-133">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="0d745-133">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
