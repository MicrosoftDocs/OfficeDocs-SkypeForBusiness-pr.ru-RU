---
title: Настройка общей лицензии Телефон области
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
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
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Узнайте, как настроить общие телефоны с областями для проведения док-комнат, приемных и конференц-залов '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117117"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="0e1a1-103">Настройка лицензии для телефонов общего пользования для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e1a1-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="0e1a1-104">Обычные телефоны с регионами не поддерживают голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="0e1a1-105">Стандартный телефон с районами обычно находится в таких же зонах, как "lobby" или в другой области, в которую может позвонить большое количество людей. Например, это может быть приемная, зал "зал", конференц-телефон.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="0e1a1-106">Распространенные телефоны с регионами, в которые были вписаны учетные записи, привязанные к общей Телефон лицензии.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="0e1a1-107">Для общего пользовательского интерфейса телефона также должна быть настроена политика TeamsIPPhone.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="0e1a1-108">Далее мы поможем вам настроить учетную запись для телефонная система для развертывания общих телефонов для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="0e1a1-109">Чтобы получить более полное пространство для собраний, включая аудиоконференцию, можно приобрести специальную лицензию Конференц-зал с устройством комнаты для собраний.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="0e1a1-110">Сначала необходимо приобрести общую лицензию Телефон (CAP) и убедиться, что у вас есть сертифицированный телефон.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="0e1a1-111">Чтобы найти сертифицированные телефоны и узнать больше о них, перейдите на Microsoft Teams [устройства.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="0e1a1-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="0e1a1-112">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="0e1a1-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="0e1a1-113">В Центре Microsoft 365 вы можете перейти в список Приобретение служб вы выставлением счета, а   >   затем развернуть **другие планы.**</span><span class="sxs-lookup"><span data-stu-id="0e1a1-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Снимок экрана: плитка Телефон области](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="0e1a1-115">Выберите **Common Area Телефон** Купить  >  **.**</span><span class="sxs-lookup"><span data-stu-id="0e1a1-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="0e1a1-116">На странице "Регистрация" нажмите **кнопку Купить**.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="0e1a1-117">**Разойдитесь на подписки на** надстройки и щелкните, чтобы приобрести план звонков.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="0e1a1-118">Выберите план внутренних **звонков или** план внутренних и **международных звонков.**</span><span class="sxs-lookup"><span data-stu-id="0e1a1-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="0e1a1-119">Если вы используете Телефон (Майкрософт) прямой маршрутизов, лицензия на план звонков не требуется.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="0e1a1-120">Вам не нужно добавлять телефонная система лицензию.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="0e1a1-121">Она включена в лицензию Телефона общего пользования.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="0e1a1-122">Дополнительные сведения о лицензиях см. в Microsoft Teams [лицензировании надстройки.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="0e1a1-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="0e1a1-123">Общая лицензия Телефон области поддерживает:</span><span class="sxs-lookup"><span data-stu-id="0e1a1-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="0e1a1-124">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="0e1a1-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="0e1a1-125">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e1a1-125">Skype for Business</span></span> |   <span data-ttu-id="0e1a1-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-126">&#x2714;</span></span> |
|<span data-ttu-id="0e1a1-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e1a1-127">Microsoft Teams</span></span> |   <span data-ttu-id="0e1a1-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-128">&#x2714;</span></span> |
|<span data-ttu-id="0e1a1-129">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="0e1a1-129">Phone System</span></span> |    <span data-ttu-id="0e1a1-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-130">&#x2714;</span></span> |
|<span data-ttu-id="0e1a1-131">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="0e1a1-131">Audio Conferencing</span></span> |       <span data-ttu-id="0e1a1-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="0e1a1-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0e1a1-133">Microsoft Intune</span></span> |    <span data-ttu-id="0e1a1-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-134">&#x2718;</span></span> |
|<span data-ttu-id="0e1a1-135">Доступность по всему миру</span><span class="sxs-lookup"><span data-stu-id="0e1a1-135">Worldwide Availability</span></span> |       <span data-ttu-id="0e1a1-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="0e1a1-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="0e1a1-137">Доступность канала</span><span class="sxs-lookup"><span data-stu-id="0e1a1-137">Channel Availability</span></span> |    <span data-ttu-id="0e1a1-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="0e1a1-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="0e1a1-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span><span class="sxs-lookup"><span data-stu-id="0e1a1-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="0e1a1-140">&sup2; Недоступны в независимых облаках</span><span class="sxs-lookup"><span data-stu-id="0e1a1-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="0e1a1-141">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="0e1a1-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="0e1a1-142">В центре Microsoft 365 администрирования перейдите к **пользователям,** активным  >  **пользователям которых нужно** добавить  >  **пользователя**.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="0e1a1-143">Введите имя пользователя, например "Основной", для имени и "Прием" для второго.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="0e1a1-144">Введите отображаемую фамилию, если она не будет автоматически сгенерироваться, например "Основной прием".</span><span class="sxs-lookup"><span data-stu-id="0e1a1-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="0e1a1-145">Введите имя пользователя, например "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="0e1a1-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="0e1a1-146">Для общих телефонов в области зоны можно установить пароль вручную или использовать один и тот же пароль для всех общих телефонов.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="0e1a1-147">Кроме того, вы можете  сменить этот пароль при первом входе.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="0e1a1-148">Назначьте лицензии пользователю.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-148">Assign the licenses to the user.</span></span> <span data-ttu-id="0e1a1-149">На этой же странице щелкните мышью и разверните **Лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="0e1a1-150">Включив общую область Телефон выберите  план внутренних звонков или план внутренних и **международных звонков.**</span><span class="sxs-lookup"><span data-stu-id="0e1a1-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Снимок экрана: назначение лицензии](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="0e1a1-152">Если вы используете Телефон (Майкрософт), назначать лицензию на план звонков не нужно.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="0e1a1-153">Дополнительные сведения см. в [том, как назначить лицензии пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="0e1a1-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="0e1a1-154">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="0e1a1-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="0e1a1-155">Используйте центр Teams администрирования, чтобы назначить номер пользователю.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="0e1a1-156">В Центре Teams выберите Номера **голосовой** Телефон  >  **голосовой Телефон**.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="0e1a1-157">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="0e1a1-158">На странице **Назначение** в поле Пользователь голосовой связи введите имя пользователя, который будет использовать  телефон, а затем выберите его в списке Выберите пользователя голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="0e1a1-159">Затем нужно добавить адрес для экстренного устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="0e1a1-160">В **списке выберите** Поиск по  городу, Поиск по описанию или Поиск по расположению, а затем введите в текстовое поле город, описание или расположение. </span><span class="sxs-lookup"><span data-stu-id="0e1a1-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="0e1a1-161">После поиска в области **Выберите адрес для** экстренного обращения выберите нужный адрес.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="0e1a1-162">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0e1a1-162">Click **Save** and your user should look like this:</span></span>

   ![Снимок экрана: назначение лицензии](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="0e1a1-164">Пользователи будут показываться только в том случае, если телефонная система лицензии.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="0e1a1-165">Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="0e1a1-166">Дополнительные сведения см. [в сведениях Получение номеров телефонов для пользователей.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="0e1a1-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="0e1a1-167">Вы также можете перенести номер телефона другого оператора и перенести его в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e1a1-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0e1a1-168">См. [перенос номеров телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0e1a1-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>