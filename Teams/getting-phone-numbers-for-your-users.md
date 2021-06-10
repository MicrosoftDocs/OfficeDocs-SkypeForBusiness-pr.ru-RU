---
title: Получение телефонных номеров для пользователей
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Узнайте, как получить новые, переносимые или перенести существующие номера для Teams и как показать изменения пользователям. '
ms.openlocfilehash: c80f7a54af697322665c110c14aeccaf5fa4f667
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586568"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="dbf16-103">Получение телефонных номеров для пользователей</span><span class="sxs-lookup"><span data-stu-id="dbf16-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="dbf16-104">[] Прежде чем настраивать возможности совершения и получения телефонных звонков для пользователей в организации, необходимо получить для них номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="dbf16-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="dbf16-105">Получить номера пользователей можно тремя способами:</span><span class="sxs-lookup"><span data-stu-id="dbf16-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="dbf16-106">**Используйте центр Microsoft Teams администрирования.**</span><span class="sxs-lookup"><span data-stu-id="dbf16-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="dbf16-107">В некоторых странах и регионах вы можете получить номера для пользователей с помощью Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="dbf16-107">For some countries and regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="dbf16-108">См. [получить новые номера телефонов для пользователей.](#get-new-phone-numbers-for-your-users)</span><span class="sxs-lookup"><span data-stu-id="dbf16-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>

- <span data-ttu-id="dbf16-109">**Портируйте номера, которые у вас уже есть.**</span><span class="sxs-lookup"><span data-stu-id="dbf16-109">**Port your existing numbers.**</span></span> <span data-ttu-id="dbf16-110">Вы можете переносить или переносить существующие номера у текущего поставщика услуг или оператора связи.</span><span class="sxs-lookup"><span data-stu-id="dbf16-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="dbf16-111">См. [Перевод телефонных номеров в Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) или [Управление телефонными номерами вашей организации](/microsoftteams/manage-phone-numbers-for-your-organization) для получения дополнительной информации, чтобы помочь вам сделать это.</span><span class="sxs-lookup"><span data-stu-id="dbf16-111">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="dbf16-112">**Используйте форму запроса для новых номеров.**</span><span class="sxs-lookup"><span data-stu-id="dbf16-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="dbf16-113">Иногда (в зависимости от страны или региона) вы не сможете получить новые номера телефонов с помощью Центра администрирования Microsoft Teams или вам нужны конкретные телефонные номера или коды областей.</span><span class="sxs-lookup"><span data-stu-id="dbf16-113">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams Admin Center or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="dbf16-114">Для получения дополнительных сведений см. статью [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="dbf16-114">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbf16-115">Если вам нужна помощь по настройке номеров телефонов для организации, обратитесь в службу поддержки продуктов : [справка для администраторов.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)</span><span class="sxs-lookup"><span data-stu-id="dbf16-115">If you need help setting up phone numbers for your organization, please [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="dbf16-116">Получение новых номеров телефонов для пользователей</span><span class="sxs-lookup"><span data-stu-id="dbf16-116">Get new phone numbers for your users</span></span>

<span data-ttu-id="dbf16-117">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="dbf16-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="dbf16-118">Вы должны быть администратором службы Teams, чтобы вносить эти изменения.</span><span class="sxs-lookup"><span data-stu-id="dbf16-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="dbf16-119">Сведения о получении ролей и разрешений администратора см. в статье [Управление Teams с помощью ролей администратора Teams](./using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dbf16-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="dbf16-120">Перейдите в центр Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="dbf16-120">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="dbf16-121">В области навигации слева перейдите в Телефон  >  **голосовой Телефон** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dbf16-121">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="dbf16-122">Введите название заказа и добавьте описание.</span><span class="sxs-lookup"><span data-stu-id="dbf16-122">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="dbf16-123">На странице Расположение и количество сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="dbf16-123">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="dbf16-124">В **области Страна или регион** выберите страну или регион.</span><span class="sxs-lookup"><span data-stu-id="dbf16-124">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="dbf16-125">В **области Тип номера** выберите Пользователь **(подписчик).**</span><span class="sxs-lookup"><span data-stu-id="dbf16-125">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="dbf16-126">В **области Расположение** выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="dbf16-126">Under **Location**, select a location.</span></span> <span data-ttu-id="dbf16-127">Если вам нужно создать новое расположение, нажмите **кнопку Добавить расположение.**</span><span class="sxs-lookup"><span data-stu-id="dbf16-127">If you need to create a new location, click **Add a location**.</span></span>
    4. <span data-ttu-id="dbf16-128">В **области Код области** выберите код области.</span><span class="sxs-lookup"><span data-stu-id="dbf16-128">Under **Area code**, select an area code.</span></span>
    5. <span data-ttu-id="dbf16-129">В **области Количество** введите нужное количество номеров для  организации и нажмите кнопку Далее, чтобы выбрать номера.</span><span class="sxs-lookup"><span data-stu-id="dbf16-129">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="dbf16-130">Выберите нужные числа.</span><span class="sxs-lookup"><span data-stu-id="dbf16-130">Select the numbers you want.</span></span> <span data-ttu-id="dbf16-131">У вас есть 10 минут, чтобы выбрать номера телефонов и разместить заказ.</span><span class="sxs-lookup"><span data-stu-id="dbf16-131">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="dbf16-132">Если на это нужно больше 10 минут, номера телефонов будут возвращены в пул номеров.</span><span class="sxs-lookup"><span data-stu-id="dbf16-132">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="dbf16-133">Когда вы будете готовы разместить заказ, нажмите кнопку **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="dbf16-133">When you're ready to place your order, click **Place order**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dbf16-134">Количество телефонных номеров для пользователей (подписчиков) равно общему количеству лицензий **Тарифного плана внутренних звонков** и/или **Тарифного плана внутренних и международных звонков**, умноженного на 1,1, плюс 10 дополнительных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="dbf16-134">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="dbf16-135">Например, при наличии в общей совокупности 50 пользователей с тарифным планом внутренних и/или внутренних и международных звонков вы можете получить **65** телефонных номеров **(50 x 1,1 + 10)**.</span><span class="sxs-lookup"><span data-stu-id="dbf16-135">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="dbf16-136">Подробные сведения см. в статьи Сколько [номеров телефонов можно получить?](./how-many-phone-numbers-can-you-get.md).</span><span class="sxs-lookup"><span data-stu-id="dbf16-136">For details, see [How many phone numbers can you get?](./how-many-phone-numbers-can-you-get.md).</span></span> <span data-ttu-id="dbf16-137">Если вам нужно получить больше номеров телефонов, обратитесь в службу поддержки продуктов для [бизнеса: справка для администраторов.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="dbf16-137">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="dbf16-138">Перенос номеров от вашего поставщика услуг или оператора телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="dbf16-138">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="dbf16-139">Если вам нужно 999 или менее номеров телефонов для пользователей, воспользуйтесь мастером переноса в Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="dbf16-139">If you need 999 or fewer phone numbers for your users, use the porting wizard in the Microsoft Teams Admin Center.</span></span> <span data-ttu-id="dbf16-140">Выполните действия, которые выполните в области Перенос [номеров телефонов Teams.](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="dbf16-140">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="dbf16-141">Если ваша страна или регион не указаны в [](phone-number-calling-plans/manually-submit-port-order.md) мастере переноса, вы [](/microsoftteams/manage-phone-numbers-for-your-organization) можете вручную отправить заказ на перенос номеров или скачать правильное досье (LOA) в ссылке Управление номерами телефонов для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dbf16-141">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA).</span></span>

- <span data-ttu-id="dbf16-142">Если вам нужно перенести более 999 номеров телефонов, вы [](/microsoftteams/manage-phone-numbers-for-your-organization) можете вручную отправить заказ на перенос номеров или скачать соответствующее досье и отправить его в службу службы ЗВОНКОВ, чтобы перенести все номера, в ссылку Управление телефонными номерами для вашей организации. [](phone-number-calling-plans/manually-submit-port-order.md) [](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)</span><span class="sxs-lookup"><span data-stu-id="dbf16-142">If you need to port more than 999 phone numbers, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA) and then send it to [the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to get all your numbers transferred.</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="dbf16-143">Просмотр телефонных номеров для организации</span><span class="sxs-lookup"><span data-stu-id="dbf16-143">View the phone numbers for your organization</span></span>

<span data-ttu-id="dbf16-144">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="dbf16-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="dbf16-145">В левой области навигации Центра администрирования перейдите в Телефон голосовой связи, чтобы просмотреть номера для организации, включая расположение, тип номера и  >   сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="dbf16-145">In the left navigation of the admin center, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="dbf16-146">Назначение номеров телефонов пользователям</span><span class="sxs-lookup"><span data-stu-id="dbf16-146">Assign phone numbers to users</span></span>

<span data-ttu-id="dbf16-147">После получения номеров телефонов необходимо назначить номера каждому пользователю.</span><span class="sxs-lookup"><span data-stu-id="dbf16-147">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="dbf16-148">Дополнительные [сведения см.](./assign-change-or-remove-a-phone-number-for-a-user.md) в записи Назначение, изменение и удаление номера телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbf16-148">See [Assign, change, or remove a phone number for a user](./assign-change-or-remove-a-phone-number-for-a-user.md) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="dbf16-149">Если вам нужно получить больше номеров телефонов, обратитесь в службу поддержки продуктов для [бизнеса: справка для администраторов.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="dbf16-149">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbf16-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbf16-150">Related topics</span></span>

[<span data-ttu-id="dbf16-151">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="dbf16-151">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="dbf16-152">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="dbf16-152">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="dbf16-153">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="dbf16-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="dbf16-154">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="dbf16-154">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="dbf16-155">[Заявление об отказе от ответственности экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="dbf16-155">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>