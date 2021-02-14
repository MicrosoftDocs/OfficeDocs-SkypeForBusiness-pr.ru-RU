---
title: Настройка телефонов общего пользования
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Узнайте о действиях по развертыванию, чтобы получить правильное постройное ПО, при необходимости обновить его, назначить лицензии и настроить параметры для общих телефонов с зонами.
ms.openlocfilehash: 02cab34b4a1f220e8f28ceeee794470191582704
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220409"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="dcebb-103">Настройка телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="dcebb-103">Set up common area phones</span></span>
<span data-ttu-id="dcebb-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="dcebb-107">Предварительные требования для телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="dcebb-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="dcebb-108">В первую очередь необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="dcebb-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="dcebb-109">Приобрести лицензию на телефон общего пользования и тарифный план.</span><span class="sxs-lookup"><span data-stu-id="dcebb-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="dcebb-110">Найти и приобрести одобренные телефоны (вы можете просмотреть их список[здесь](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="dcebb-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="dcebb-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="dcebb-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="dcebb-113">**Телефоны Polycom VVX:** перейдите в **параметры** основные приложения  >    >  **платформы**  >    >  состояния.</span><span class="sxs-lookup"><span data-stu-id="dcebb-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="dcebb-114">**Телефоны Yealink:** перейдите в **состояние** на главном экране телефона.</span><span class="sxs-lookup"><span data-stu-id="dcebb-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="dcebb-115">**AudioCodes phones:** Go to **Menu**  >  **Device Status**  >  **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="dcebb-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="dcebb-116">**Телефоны Lync Phone Edition (LPE): на start-экране** перейдите в меню   >  **"Сведения** о системе".</span><span class="sxs-lookup"><span data-stu-id="dcebb-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="dcebb-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="dcebb-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="dcebb-121">Настройка телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="dcebb-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="dcebb-122">Вам потребуется выполнить следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="dcebb-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="dcebb-123">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="dcebb-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="dcebb-124">В Центре администрирования перейдите **в** службы покупки вы выставлений счета и добавьте  >  другие **планы.**</span><span class="sxs-lookup"><span data-stu-id="dcebb-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="dcebb-126">Нажмите на **Телефон общего пользования** > **Купить**, на странице **Оформление заказа** нажмите кнопку **Купить**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="dcebb-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="dcebb-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="dcebb-131">Дополнительные сведения о лицензиях см. в лицензировании надстройок Skype для бизнеса и [Microsoft Teams.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="dcebb-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="dcebb-132">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="dcebb-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="dcebb-133">В Центре администрирования перейдите в **группу "Пользователи,**  >  **активные**  >  **пользователи: добавление пользователя".**</span><span class="sxs-lookup"><span data-stu-id="dcebb-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="dcebb-134">В поле **Имя пользователя** укажите, например, "Основная", а в графе для фамилии — "Приемная".</span><span class="sxs-lookup"><span data-stu-id="dcebb-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="dcebb-135">В поле **Отображаемое имя**, если оно не заполнилось автоматически, укажите, например, "Главная Приемная".</span><span class="sxs-lookup"><span data-stu-id="dcebb-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="dcebb-136">В поле **Имя пользователя** укажите, например, "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="dcebb-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="dcebb-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="dcebb-139">Если вы все еще на этой странице, назначьте лицензии этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="dcebb-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="dcebb-140">На этой же странице щелкните мышью и разверните **Лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="dcebb-141">Включите следующие опции:</span><span class="sxs-lookup"><span data-stu-id="dcebb-141">Turn on the following:</span></span>
   - <span data-ttu-id="dcebb-142">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="dcebb-142">Common Area Phone</span></span>
   - <span data-ttu-id="dcebb-143">Общего Пользования sedGlossaryTerm">Телефон</span><span class="sxs-lookup"><span data-stu-id="dcebb-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="dcebb-144">Назначение лицензий будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dcebb-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="dcebb-146">Приводим к вашему сведению, что в лицензию **Телефона общего пользования** включен План 2 Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dcebb-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="dcebb-147">Узнайте больше в статье [Добавление пользователей](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="dcebb-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="dcebb-148">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="dcebb-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="dcebb-149">![Значок с логотипом Skype для бизнеса : назначение номера телефона пользователю в Центре администрирования ](../../images/sfb-logo-30x30.png) **Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="dcebb-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="dcebb-150">В Центре администрирования > **центры**  >  **администрирования Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="dcebb-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="dcebb-151">Далее: **Центр администрирования Skype для бизнеса** >  **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="dcebb-152">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="dcebb-153">На странице **Назначить** в поле **Пользователь голосовой связи** введите имя пользователя телефона, а затем выберите пользователя в выпадающем списке **Выбор пользователя голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="dcebb-154">Пока вы находитесь на этой странице, необходимо добавить адрес для обращения в экстренных случаях.</span><span class="sxs-lookup"><span data-stu-id="dcebb-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="dcebb-155">Во время поиска выберите нужный адрес под пунктом **Выбор адреса для обращения в экстренных случаях**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="dcebb-156">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dcebb-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="dcebb-158">Пользователи будут отображаться, только если на них распространяется лицензия **Телефонная система**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="dcebb-159">Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.</span><span class="sxs-lookup"><span data-stu-id="dcebb-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="dcebb-160">Узнайте больше в статье [Получение телефонных номеров для ваших пользователей](/microsoftteams/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="dcebb-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="dcebb-161">Если вас интересует этот вопрос, вы также можете перенести номертелефона другого оператора связи или перенести его в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcebb-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="dcebb-162">См. [передачу номеров телефонов в Teams.](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)</span><span class="sxs-lookup"><span data-stu-id="dcebb-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="dcebb-163">Шаг 4. Настройка телефона</span><span class="sxs-lookup"><span data-stu-id="dcebb-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="dcebb-164">**Настройка режима в телефоне**</span><span class="sxs-lookup"><span data-stu-id="dcebb-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="dcebb-165">В вашем телефоне необходимо включить **Режим телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="dcebb-166">Убедитесь, есть ли в нем такой режим.</span><span class="sxs-lookup"><span data-stu-id="dcebb-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="dcebb-167">**Ниже приведен пример настройки телефона Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="dcebb-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="dcebb-168">Включите режим телефона общего пользования для Polycom VVX, выполнив следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="dcebb-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="dcebb-169">Подключитесь к веб-интерфейсу через веб-обозреватель, чтобы включить режим CAP.</span><span class="sxs-lookup"><span data-stu-id="dcebb-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="dcebb-170">Затем откройте меню **Параметры** и в пункте **Параметры Skype для бизнеса** выберите **Телефон общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="dcebb-171">Нажмите **Да** для сохранения параметров.</span><span class="sxs-lookup"><span data-stu-id="dcebb-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="dcebb-172">Теперь режим CAP включен, и вы можете настроить телефон, используя его дисплей.</span><span class="sxs-lookup"><span data-stu-id="dcebb-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="dcebb-173">Дисплей должен показывать **CAP включен**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="dcebb-174">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dcebb-174">Then do the following:</span></span>

    1. <span data-ttu-id="dcebb-175">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="dcebb-176">Выберите **"Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="dcebb-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="dcebb-177">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="dcebb-177">Enter the password.</span></span>
    4. <span data-ttu-id="dcebb-178">В пункте **Параметры администрирования** выберите **Параметры телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="dcebb-179">Включите **CAP** и **Режим администратора CAP**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="dcebb-180">Нажмите **Сохранить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-180">Click **Save Config**.</span></span>

- <span data-ttu-id="dcebb-181">Теперь телефон готов, и вы можете выполнить вход на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="dcebb-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="dcebb-182">Войдите, выбрав **Параметры** > **Функции** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="dcebb-183">Выберите **Учетные данные пользователя**, а затем — **Интернет-вход (CAP)**, чтобы генерировать код.</span><span class="sxs-lookup"><span data-stu-id="dcebb-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="dcebb-184">Перейдите на [портал подготовки](https://aka.ms/skypecap) и войдите в систему как **администратор**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="dcebb-185">Введите отображаемое имя (например, Главная Приемная).</span><span class="sxs-lookup"><span data-stu-id="dcebb-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="dcebb-186">Если отмечена опция **Искать только телефоны общего пользования**, снимите флажок и выполните поиск повторно.</span><span class="sxs-lookup"><span data-stu-id="dcebb-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="dcebb-187">В окне кода сопряжения введите код, который отображается на телефоне, и нажмите **Подготовка**.</span><span class="sxs-lookup"><span data-stu-id="dcebb-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="dcebb-188">После этого действия телефон должен автоматически войти в систему.</span><span class="sxs-lookup"><span data-stu-id="dcebb-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="dcebb-189">Сайт подготовки CAP заявляет о сбросе пароля учетной записи CAP на случайный пароль.</span><span class="sxs-lookup"><span data-stu-id="dcebb-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="dcebb-190">Обратите внимание, что учетная запись, на которую ссылается CAP, представляет собой учетную запись Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="dcebb-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="dcebb-191">Если вы создали учетную запись только в AAD, процесс не будет сложным.</span><span class="sxs-lookup"><span data-stu-id="dcebb-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="dcebb-192">Если вы синхронизировали локальное каталог Active Directory с AAD и используете стороннее IDP или ADFS, подготовка CAP не будет работать.</span><span class="sxs-lookup"><span data-stu-id="dcebb-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="dcebb-193">В этом случае для подстановки CAP вам потребуется использовать только учетную запись Microsoft 365, Office 365 или Azure Active Directory (например, учетную запись с доменом **onmicrosoft.com).**</span><span class="sxs-lookup"><span data-stu-id="dcebb-193">In this case, you need to use a Microsoft 365 or Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="dcebb-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dcebb-194">Related topics</span></span>

- <span data-ttu-id="dcebb-195">Узнайте больше о доступных телефонах в статье [Развертывание телефонов Skype для бизнеса Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="dcebb-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="dcebb-196">Телефоны, поддерживаемые в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="dcebb-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


