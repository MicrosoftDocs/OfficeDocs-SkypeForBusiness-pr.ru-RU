---
title: Настройка лицензии общего зоны телефона
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
description: 'Узнайте, как настроить общие телефоны с областями для достройки, приемных и конференц-залов '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476714"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="64607-103">Настройка лицензии для телефонов общего пользования для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64607-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="64607-104">Обычные телефоны с зонами не поддерживают голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="64607-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="64607-105">Общий телефон с общей площадью обычно находится в таких участках, как "вести", или в другой области, в которую может позвонить большое количество людей. Например, это может быть приемная, зал залов или конференц-телефон.</span><span class="sxs-lookup"><span data-stu-id="64607-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="64607-106">Обычные телефоны с регионами, в которые были вписаны учетные записи, привязанные к общей лицензии на area Phone.</span><span class="sxs-lookup"><span data-stu-id="64607-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="64607-107">Политика TeamsIPPhone также должна иметь общую область работы с телефоном.</span><span class="sxs-lookup"><span data-stu-id="64607-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="64607-108">Ниже мы поможем вам настроить учетную запись телефонной системы для развертывания общих телефонных телефонов в организации.</span><span class="sxs-lookup"><span data-stu-id="64607-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="64607-109">Для более простого проведения собраний, включая аудиоконференцию, приобретите лицензию на выделенную комнату для собраний с устройством комнаты для собраний.</span><span class="sxs-lookup"><span data-stu-id="64607-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="64607-110">Сначала необходимо приобрести лицензию на общий телефон с общей площадью (CAP) и убедиться, что у вас есть сертифицированный телефон.</span><span class="sxs-lookup"><span data-stu-id="64607-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="64607-111">Чтобы найти сертифицированные телефоны и узнать больше о них, перейдите на устройства [Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="64607-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="64607-112">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="64607-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="64607-113">В Центре администрирования Microsoft 365 перейдите в службы покупки вы выставлений счета, а затем   >   разйдите в список **"Другие планы".**</span><span class="sxs-lookup"><span data-stu-id="64607-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Снимок экрана: плитка "Общий телефон с общей областью"](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="64607-115">Выберите **Common Area Phone** Buy  >  **now.**</span><span class="sxs-lookup"><span data-stu-id="64607-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="64607-116">На странице "Регистрация" нажмите кнопку **"Купить".**</span><span class="sxs-lookup"><span data-stu-id="64607-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="64607-117">Раз **развернуть подписки на надстройки,** а затем щелкните, чтобы приобрести план звонков.</span><span class="sxs-lookup"><span data-stu-id="64607-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="64607-118">Выберите план внутренних **или международных** и только внутренних **звонков.**</span><span class="sxs-lookup"><span data-stu-id="64607-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="64607-119">Если вы используете прямую маршрутику по системе Microsoft Phone, лицензия на план звонков не требуется.</span><span class="sxs-lookup"><span data-stu-id="64607-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="64607-120">Вам не нужно добавлять лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="64607-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="64607-121">Она включена в лицензию Телефона общего пользования.</span><span class="sxs-lookup"><span data-stu-id="64607-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="64607-122">Дополнительные сведения о лицензиях см. в лицензировании надстройки [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="64607-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="64607-123">Общая лицензия на area Phone поддерживает:</span><span class="sxs-lookup"><span data-stu-id="64607-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="64607-124">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="64607-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="64607-125">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="64607-125">Skype for Business</span></span> |   <span data-ttu-id="64607-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="64607-126">&#x2714;</span></span> |
|<span data-ttu-id="64607-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64607-127">Microsoft Teams</span></span> |   <span data-ttu-id="64607-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="64607-128">&#x2714;</span></span> |
|<span data-ttu-id="64607-129">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="64607-129">Phone System</span></span> |    <span data-ttu-id="64607-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="64607-130">&#x2714;</span></span> |
|<span data-ttu-id="64607-131">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="64607-131">Audio Conferencing</span></span> |       <span data-ttu-id="64607-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="64607-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="64607-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="64607-133">Microsoft Intune</span></span> |    <span data-ttu-id="64607-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="64607-134">&#x2718;</span></span> |
|<span data-ttu-id="64607-135">Доступность по всему миру</span><span class="sxs-lookup"><span data-stu-id="64607-135">Worldwide Availability</span></span> |       <span data-ttu-id="64607-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="64607-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="64607-137">Доступность канала</span><span class="sxs-lookup"><span data-stu-id="64607-137">Channel Availability</span></span> |    <span data-ttu-id="64607-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="64607-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="64607-139">&sup1; Обычные телефоны с зонами могут присоединяться к аудиоконференции с помощью телефонного номера, предоставленного организатором собрания</span><span class="sxs-lookup"><span data-stu-id="64607-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="64607-140">&sup2; Недоступны в независимых облаках</span><span class="sxs-lookup"><span data-stu-id="64607-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="64607-141">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="64607-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="64607-142">В Центре администрирования Microsoft 365 перейдите к **пользователям,** которые активно  >  **добавляют**  >  **пользователя.**</span><span class="sxs-lookup"><span data-stu-id="64607-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="64607-143">Введите имя пользователя, например "Main", для первого имени и "Приемная" для второго имени.</span><span class="sxs-lookup"><span data-stu-id="64607-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="64607-144">Введите отображаемом имя, если оно не сгенерирует его автоматически, например "Главная приемная".</span><span class="sxs-lookup"><span data-stu-id="64607-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="64607-145">Введите имя пользователя, например "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="64607-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="64607-146">Для телефонов с общими зонами можно установить пароль вручную или использовать один и тот же пароль для всех общих телефонов.</span><span class="sxs-lookup"><span data-stu-id="64607-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="64607-147">Кроме того, может потребоваться  сменить пароль при первом входе.</span><span class="sxs-lookup"><span data-stu-id="64607-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="64607-148">Назначьте лицензии пользователю.</span><span class="sxs-lookup"><span data-stu-id="64607-148">Assign the licenses to the user.</span></span> <span data-ttu-id="64607-149">На этой же странице щелкните мышью и разверните **Лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="64607-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="64607-150">Включив общий телефон в  регионе, выберите план внутренних или международных и **только внутренних звонков.**</span><span class="sxs-lookup"><span data-stu-id="64607-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Снимок экрана: назначение лицензии](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="64607-152">Если вы используете прямую маршрутику по системе Microsoft Phone, назначать лицензию на план звонков не требуется.</span><span class="sxs-lookup"><span data-stu-id="64607-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="64607-153">Дополнительные сведения см. [в сведениях о назначении лицензий пользователям.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="64607-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="64607-154">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="64607-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="64607-155">В Центре администрирования Teams назначьте номер пользователю.</span><span class="sxs-lookup"><span data-stu-id="64607-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="64607-156">В Центре администрирования Teams выберите номера  >  **голосовых телефонов.**</span><span class="sxs-lookup"><span data-stu-id="64607-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="64607-157">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="64607-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="64607-158">На странице **"Назначение"** в поле "Пользователь голосовой связи" введите имя пользователя, который  будет использовать телефон, а затем выберите его в списке "Выбор пользователя голосовой связи".</span><span class="sxs-lookup"><span data-stu-id="64607-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="64607-159">Затем нужно добавить адрес для экстренного устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="64607-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="64607-160">В **списке** выберите "Поиск  по городу", "Поиск по описанию" или "Поиск по расположению", а затем введите в текстовом поле город, описание или расположение.</span><span class="sxs-lookup"><span data-stu-id="64607-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="64607-161">После поиска выберите  нужный адрес в области "Выберите адрес для экстренного помощи".</span><span class="sxs-lookup"><span data-stu-id="64607-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="64607-162">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="64607-162">Click **Save** and your user should look like this:</span></span>

   ![Снимок экрана: назначение лицензии](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="64607-164">Пользователи будут показываться, только если у них есть лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="64607-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="64607-165">Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.</span><span class="sxs-lookup"><span data-stu-id="64607-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="64607-166">Дополнительные сведения см. [в сведениях о получении номеров телефонов для пользователей.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="64607-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="64607-167">Вы также можете перенести номер телефона, который у вас есть у другого оператора, в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="64607-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="64607-168">См. [передачу номеров телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="64607-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
