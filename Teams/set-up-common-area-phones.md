---
title: Настройка лицензий на общие устройства с телефонным пространством
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
description: 'Сведения о том, как настроить общие телефоны для приемных, областей приема и конференц-залов '
ms.openlocfilehash: 4e9e96c3384fa365004d4b4b5281c10decdc5dd1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581100"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="68775-103">Настройка лицензии для телефонов общего пользования для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68775-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="68775-104">Обычные телефоны не поддерживают голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="68775-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="68775-105">Обычный телефон обычно размещается в области, например в зале ожидания или в другой области, доступной многим людям для совершения звонка; Например, на конференц-зале, на зал или на стационарном телефоне.</span><span class="sxs-lookup"><span data-stu-id="68775-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="68775-106">На телефонах с общими областями используются учетные записи, связанные с лицензией на телефон с общим регионом.</span><span class="sxs-lookup"><span data-stu-id="68775-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="68775-107">Кроме того, политика TeamsIPPhone должна быть настроена таким образом, чтобы телефон имел общую область взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="68775-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="68775-108">В приведенных ниже шагах мы поможем вам настроить учетную запись для телефонной системы, чтобы развернуть общие телефоны для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="68775-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="68775-109">Чтобы выполнить более полную конференцию собрания, в том числе голосовую конференцию, рассматривайте специальную лицензию на место для собраний с помощью устройства для помещения на собрание.</span><span class="sxs-lookup"><span data-stu-id="68775-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="68775-110">Прежде всего, вам нужно приобрести лицензию на стандартную телефонную сеть (CAP) и удостовериться, что у вас есть сертифицированный телефон.</span><span class="sxs-lookup"><span data-stu-id="68775-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="68775-111">Чтобы найти и узнать больше о сертифицированных телефонах, откройте раздел [устройства Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="68775-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="68775-112">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="68775-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="68775-113">В центре администрирования Microsoft 365 перейдите в раздел Услуги по **выставлению счетов**  >  **Purchase services** и разверните **другие планы**.</span><span class="sxs-lookup"><span data-stu-id="68775-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Снимок экрана, на котором показана плитка "обычный телефон"](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="68775-115">Нажмите **Common Area Phone**кнопку  >  **купить в прямом**месте.</span><span class="sxs-lookup"><span data-stu-id="68775-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="68775-116">На странице "Оформление заказа" нажмите кнопку **Купить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="68775-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="68775-117">Разверните **подписку на надстройку** , а затем щелкните, чтобы приобрести план звонков.</span><span class="sxs-lookup"><span data-stu-id="68775-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="68775-118">Выберите план **внутренних звонков** или **внутренний и Международный план звонков**.</span><span class="sxs-lookup"><span data-stu-id="68775-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="68775-119">Если вы используете прямую маршрутизацию Microsoft Phone System, вам не нужна лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="68775-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="68775-120">Вам не нужно добавлять лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="68775-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="68775-121">Она включена в лицензию Телефона общего пользования.</span><span class="sxs-lookup"><span data-stu-id="68775-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="68775-122">Дополнительные сведения о лицензиях можно найти [в разделе Лицензирование надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="68775-122">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="68775-123">Лицензия на телефон для общего модуля поддерживает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="68775-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="68775-124">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="68775-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="68775-125">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68775-125">Skype for Business</span></span> |   <span data-ttu-id="68775-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="68775-126">&#x2714;</span></span> |
|<span data-ttu-id="68775-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68775-127">Microsoft Teams</span></span> |   <span data-ttu-id="68775-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="68775-128">&#x2714;</span></span> |
|<span data-ttu-id="68775-129">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="68775-129">Phone System</span></span> |    <span data-ttu-id="68775-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="68775-130">&#x2714;</span></span> |
|<span data-ttu-id="68775-131">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="68775-131">Audio Conferencing</span></span> |       <span data-ttu-id="68775-132">&#x2718; &SUP1;</span><span class="sxs-lookup"><span data-stu-id="68775-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="68775-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="68775-133">Microsoft Intune</span></span> |        <span data-ttu-id="68775-134">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="68775-134">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="68775-135">Доступность в разных странах мира</span><span class="sxs-lookup"><span data-stu-id="68775-135">Worldwide Availability</span></span> |    <span data-ttu-id="68775-136">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="68775-136">&#x2714;</span></span> |
|<span data-ttu-id="68775-137">Доступность канала</span><span class="sxs-lookup"><span data-stu-id="68775-137">Channel Availability</span></span> |    <span data-ttu-id="68775-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="68775-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="68775-139">&SUP1; Телефонные телефоны, поддерживающие стандартную сеть, могут присоединяться к голосовой конференции через номер телефонного подключения, предоставленный организатором собрания</span><span class="sxs-lookup"><span data-stu-id="68775-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="68775-140">&sup2; Недоступно в облаках изолированной</span><span class="sxs-lookup"><span data-stu-id="68775-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="68775-141">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="68775-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="68775-142">В центре администрирования Microsoft 365 перейдите к разделу **Пользователи**, которые являются активными, чтобы  >  **active users**  >  **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="68775-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="68775-143">Введите имя пользователя, например "Main", для имени и "приема" для второго имени.</span><span class="sxs-lookup"><span data-stu-id="68775-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="68775-144">Введите отображаемое имя, если оно не было автоматически сгенерировано, например "основной прием".</span><span class="sxs-lookup"><span data-stu-id="68775-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="68775-145">Введите имя пользователя, например "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="68775-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="68775-146">Для обычных телефонов может потребоваться установить пароль вручную или использовать один и тот же пароль для всех распространенных телефонов.</span><span class="sxs-lookup"><span data-stu-id="68775-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="68775-147">Кроме того, вы можете подумать, как снять флажок **изменить пароль при первом входе в учетную** запись.</span><span class="sxs-lookup"><span data-stu-id="68775-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="68775-148">Назначение лицензий пользователю.</span><span class="sxs-lookup"><span data-stu-id="68775-148">Assign the licenses to the user.</span></span> <span data-ttu-id="68775-149">На этой же странице щелкните мышью и разверните **Лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="68775-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="68775-150">Включите общий телефонный номер и выберите **план внутренних звонков** либо **внутренний и Международный план звонков**.</span><span class="sxs-lookup"><span data-stu-id="68775-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Снимок экрана, на котором показано назначение лицензий](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="68775-152">Если вы используете прямую маршрутизацию Microsoft Phone System, вам не нужно назначать лицензию на план звонков.</span><span class="sxs-lookup"><span data-stu-id="68775-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="68775-153">Дополнительные сведения можно найти [в разделе Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="68775-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="68775-154">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="68775-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="68775-155">С помощью центра администрирования Teams можно назначить пользователю номер.</span><span class="sxs-lookup"><span data-stu-id="68775-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="68775-156">В центре администрирования Teams выберите номера **голосовых**  >  **телефонов**.</span><span class="sxs-lookup"><span data-stu-id="68775-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="68775-157">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="68775-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="68775-158">На странице **назначение** в поле голосовой пользователь введите имя пользователя, который будет использовать этот телефон, а затем выберите пользователя в раскрывающемся списке **выберите пользователя** .</span><span class="sxs-lookup"><span data-stu-id="68775-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="68775-159">Затем необходимо добавить адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="68775-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="68775-160">В раскрывающемся списке выберите **Поиск по городу**, **Поиск по описанию**или **Поиск по расположению** , а затем введите название города, описание или расположение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="68775-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="68775-161">После выполнения поиска просмотрите раздел **Выбор адреса для экстренного** реагирования, чтобы выбрать нужный вариант.</span><span class="sxs-lookup"><span data-stu-id="68775-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="68775-162">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="68775-162">Click **Save** and your user should look like this:</span></span>

   ![Снимок экрана, на котором показано назначение лицензий](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="68775-164">Пользователи будут показываться только в том случае, если к ним применена лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="68775-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="68775-165">Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.</span><span class="sxs-lookup"><span data-stu-id="68775-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="68775-166">Дополнительные сведения можно найти [в разделе Знакомство с телефонными номерами пользователей](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="68775-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="68775-167">Вы также можете использовать свой номер телефона с другой несущей и "портом" или передать его в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="68775-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="68775-168">Посмотрите [, как передавать номера телефонов в Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="68775-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
