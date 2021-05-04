---
title: Настройка Голосовая связь Microsoft 365 бизнес телефонов
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Узнайте, как настроить Голосовая связь Microsoft 365 бизнес для пользователей и служб в организации.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130119"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="e544f-103">Шаг 2. Настройка номеров голосовых телефонов для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e544f-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="e544f-104">Перед тем как настроить пользователей или автоследников в организации, необходимо получить для них номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="e544f-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="e544f-105">Существует несколько типов номеров телефонов, но на этом этапе необходимо добавить следующие типы номеров:</span><span class="sxs-lookup"><span data-stu-id="e544f-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="e544f-106">**Номера служб** Эти номера используются для автозаписей, аудиоконференций и очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="e544f-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="e544f-107">Они могут быть платными или бесплатными номерами, а также обрабатывать большое количество звонков одновременно.</span><span class="sxs-lookup"><span data-stu-id="e544f-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="e544f-108">Номер телефона вашей компании должен быть номером службы, так как он будет назначен автозаводителу на более позднем этапе.</span><span class="sxs-lookup"><span data-stu-id="e544f-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="e544f-109">**Номера подписчиков** Эти номера используются для обычных пользователей, чтобы они могли звонить и принимать телефонные звонки.</span><span class="sxs-lookup"><span data-stu-id="e544f-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e544f-110">Даже если вы хотите использовать существующие телефонные номера, необходимо создать и назначить временные номера телефонов основной телефонной линии компании и пользователям.</span><span class="sxs-lookup"><span data-stu-id="e544f-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="e544f-111">Вы сможете заменить эти временные номера существующими номерами телефонов на более позднем этапе.</span><span class="sxs-lookup"><span data-stu-id="e544f-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="e544f-112">Для того чтобы новые телефонные номера стали доступны в новой Teams, может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="e544f-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="e544f-113">Настройка номера службы</span><span class="sxs-lookup"><span data-stu-id="e544f-113">Set up a service number</span></span>

<span data-ttu-id="e544f-114">Номер службы, который вы настроили сейчас, будет использоваться на более позднем этапе для основного номера телефона вашей компании.</span><span class="sxs-lookup"><span data-stu-id="e544f-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="e544f-115">Перейдите в центр Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="e544f-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="e544f-116">В области навигации слева перейдите в Телефон  >  **голосовой Телефон** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e544f-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="e544f-117">Введите название заказа и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="e544f-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="e544f-118">На странице Расположение и количество сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e544f-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="e544f-119">В **области Страна или регион** выберите страну или регион.</span><span class="sxs-lookup"><span data-stu-id="e544f-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="e544f-120">В **области Тип номера** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e544f-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="e544f-121">**Автоотекатарь (платный)** Обычный, не бесплатный, номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e544f-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="e544f-122">Плата за междугородние и междугородние вызовы взимается с вызываемой.</span><span class="sxs-lookup"><span data-stu-id="e544f-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="e544f-123">**Автоотекатарь (бесплатный)** Бесплатный (США и Канада) или бесплатный номер телефона (Соединенное Королевство).</span><span class="sxs-lookup"><span data-stu-id="e544f-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="e544f-124">Плата за длинные расстояния взимается с вашей компанией.</span><span class="sxs-lookup"><span data-stu-id="e544f-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="e544f-125">Чтобы выбрать этот параметр, необходимо приобрести кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="e544f-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="e544f-126">Дополнительные сведения см. в [этой Голосовая связь Microsoft 365 бизнес.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="e544f-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="e544f-127">В **области Количество** выберите **1**.</span><span class="sxs-lookup"><span data-stu-id="e544f-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="e544f-128">Если вы получили сообщение У **вас** недостаточно лицензий для запроса дополнительных номеров этого типа , убедитесь, что вы приобрели лицензии на голосовую голосовую связи для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e544f-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="e544f-129">Дополнительные сведения см. в [этой Голосовая связь Microsoft 365 бизнес.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="e544f-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="e544f-130">В **пункте** Расположение введите имя расположения, которое вы создали, в [шаге Настройка расположений для экстренного](set-up-emergency-locations.md) нахождения.</span><span class="sxs-lookup"><span data-stu-id="e544f-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="e544f-131">В **области Код области** выберите код  области, а затем нажмите кнопку Далее, чтобы выбрать номера</span><span class="sxs-lookup"><span data-stu-id="e544f-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="e544f-132">Выберите нужное число.</span><span class="sxs-lookup"><span data-stu-id="e544f-132">Select the number you want.</span></span> <span data-ttu-id="e544f-133">У вас есть 10 минут, чтобы выбрать номер телефона и разместить заказ.</span><span class="sxs-lookup"><span data-stu-id="e544f-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="e544f-134">Если на это нужно больше 10 минут, номер телефона будет возвращен в пул номеров.</span><span class="sxs-lookup"><span data-stu-id="e544f-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="e544f-135">Когда вы будете готовы разместить заказ, нажмите кнопку **Заказать** и нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="e544f-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="e544f-136">Настройка номеров телефонов для пользователей</span><span class="sxs-lookup"><span data-stu-id="e544f-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="e544f-137">Перейдите в центр Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="e544f-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="e544f-138">В области навигации слева перейдите в Телефон  >  **голосовой Телефон** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e544f-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="e544f-139">Введите название заказа и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="e544f-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="e544f-140">На странице Расположение и количество сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e544f-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="e544f-141">В **области Страна или регион** выберите страну или регион.</span><span class="sxs-lookup"><span data-stu-id="e544f-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="e544f-142">В **области Тип номера** выберите Пользователь **(подписчик).**</span><span class="sxs-lookup"><span data-stu-id="e544f-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="e544f-143">В **области Количество** введите нужное количество номеров для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e544f-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="e544f-144">В **области Расположение** выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="e544f-144">Under **Location**, select a location.</span></span> <span data-ttu-id="e544f-145">Вы можете выбрать расположение для экстренного [](set-up-emergency-locations.md) ситуация, добавленное на этапе Настройка расположений для экстренного ситуация, или, если вам нужно создать новое расположение для другого офиса или домашнего офиса, нажмите кнопку Добавить **расположение.**</span><span class="sxs-lookup"><span data-stu-id="e544f-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="e544f-146">В **области Код области** выберите код  области, а затем нажмите кнопку Далее, чтобы выбрать номера.</span><span class="sxs-lookup"><span data-stu-id="e544f-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="e544f-147">Выберите нужные числа.</span><span class="sxs-lookup"><span data-stu-id="e544f-147">Select the numbers you want.</span></span> <span data-ttu-id="e544f-148">У вас есть 10 минут, чтобы выбрать номера телефонов и разместить заказ.</span><span class="sxs-lookup"><span data-stu-id="e544f-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="e544f-149">Если на это нужно больше 10 минут, номера телефонов будут возвращены в пул номеров.</span><span class="sxs-lookup"><span data-stu-id="e544f-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="e544f-150">Когда вы будете готовы разместить заказ, нажмите кнопку **Заказать** и нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="e544f-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e544f-151">Следующий шаг: назначение лицензий Teams пользователям</span><span class="sxs-lookup"><span data-stu-id="e544f-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
