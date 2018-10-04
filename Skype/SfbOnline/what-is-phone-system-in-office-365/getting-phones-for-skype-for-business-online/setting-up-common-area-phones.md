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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Познакомьтесь с действиями развертывания для получения микропрограммы, при необходимости обновите ее, назначение лицензий и настройка параметров для телефонов общего пользования.
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370678"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="c5178-103">Настройка телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="c5178-103">Set up common area phones</span></span>
<span data-ttu-id="c5178-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="c5178-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="c5178-107">Предварительные требования для телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="c5178-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="c5178-108">В первую очередь необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="c5178-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="c5178-109">Приобрести лицензию на телефон общего пользования и тарифный план.</span><span class="sxs-lookup"><span data-stu-id="c5178-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="c5178-110">Найти и приобрести одобренные телефоны (вы можете просмотреть их список[здесь](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="c5178-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="c5178-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="c5178-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="c5178-113">**Телефоны Polycom VVX**: переход к **параметрам** > **состояние** > **платформы** > **приложения** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="c5178-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="c5178-114">**Телефоны Yealink**: перейти к **состоянию** на экране основной телефон.</span><span class="sxs-lookup"><span data-stu-id="c5178-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="c5178-115">**Телефоны AudioCodes**: Откройте **меню** > **Состояние устройства** > **версия микропрограммы** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="c5178-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="c5178-116">**Телефоны Lync Phone Edition (LPE)**: В **меню** > **Сведения о системе** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="c5178-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="c5178-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="c5178-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="c5178-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="c5178-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="c5178-121">Настройка телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="c5178-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="c5178-122">Вам потребуется выполнить следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="c5178-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="c5178-123">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="c5178-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="c5178-124">В Центре администрирования Office 365 перейдите в **Выставление счетов** > **Приобретение услуг** и добавьте **Другие планы**.</span><span class="sxs-lookup"><span data-stu-id="c5178-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="c5178-126">Нажмите на **Телефон общего пользования** > **Купить**, на странице **Оформление заказа** нажмите кнопку **Купить**.</span><span class="sxs-lookup"><span data-stu-id="c5178-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="c5178-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="c5178-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="c5178-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="c5178-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="c5178-131">Дополнительные сведения о лицензии в разделе [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c5178-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="c5178-132">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="c5178-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="c5178-133">В центре администрирования Office 365 перейдите в раздел **Пользователи** > **Активные пользователи** > **Добавление пользователя**.</span><span class="sxs-lookup"><span data-stu-id="c5178-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="c5178-134">В поле **Имя пользователя** укажите, например, "Основная", а в графе для фамилии — "Приемная".</span><span class="sxs-lookup"><span data-stu-id="c5178-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="c5178-135">В поле **Отображаемое имя**, если оно не заполнилось автоматически, укажите, например, "Главная Приемная".</span><span class="sxs-lookup"><span data-stu-id="c5178-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="c5178-136">В поле**Имя пользователя** укажите, например, "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="c5178-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="c5178-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="c5178-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="c5178-p108">WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="c5178-p108">WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="c5178-p109">If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:</span><span class="sxs-lookup"><span data-stu-id="c5178-p109">If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:</span></span>
   - <span data-ttu-id="c5178-147">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="c5178-147">Common Area Phone</span></span>
   - <span data-ttu-id="c5178-148">Общего Пользования sedGlossaryTerm">Телефон\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c5178-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="c5178-149">Назначение лицензий будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5178-149">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="c5178-151">Приводим к вашему сведению, что в лицензию **Телефона общего пользования** включен План 2 Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c5178-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="c5178-152">Узнайте больше в статье [Добавление пользователей](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="c5178-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="c5178-153">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="c5178-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="c5178-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Назначьте номер телефона пользователю, используя **Центр администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c5178-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="c5178-155">В центре администрирования Office 365 > **центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c5178-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="c5178-156">Далее: **Центр администрирования Skype для бизнеса** >  **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="c5178-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="c5178-157">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="c5178-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="c5178-158">На странице **Назначить** в поле **Пользователь голосовой связи** введите имя пользователя телефона, а затем выберите пользователя в выпадающем списке **Выбор пользователя голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c5178-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="c5178-p110">While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.</span><span class="sxs-lookup"><span data-stu-id="c5178-p110">While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="c5178-161">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5178-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="c5178-p111">Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.</span><span class="sxs-lookup"><span data-stu-id="c5178-p111">Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="c5178-165">Узнайте больше в статье [Получение телефонных номеров для ваших пользователей](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="c5178-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="c5178-p112">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="c5178-p112">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="c5178-168">Шаг 4. Настройка телефона</span><span class="sxs-lookup"><span data-stu-id="c5178-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="c5178-169">**Настройка режима в телефоне**</span><span class="sxs-lookup"><span data-stu-id="c5178-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="c5178-p113">The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.</span><span class="sxs-lookup"><span data-stu-id="c5178-p113">The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="c5178-172">**Ниже приведен пример настройки телефона Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="c5178-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="c5178-173">Включите режим телефона общего пользования для Polycom VVX, выполнив следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="c5178-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="c5178-174">Подключитесь к веб-интерфейсу через веб-обозреватель, чтобы включить режим CAP.</span><span class="sxs-lookup"><span data-stu-id="c5178-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="c5178-175">Затем откройте меню **Параметры** и в пункте **Параметры Skype для бизнеса** выберите **Телефон общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="c5178-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="c5178-176">Нажмите **Да** для сохранения параметров.</span><span class="sxs-lookup"><span data-stu-id="c5178-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="c5178-p114">Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:</span><span class="sxs-lookup"><span data-stu-id="c5178-p114">Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:</span></span>

    1. <span data-ttu-id="c5178-180">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c5178-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="c5178-181">Выберите **Дополнительные**.</span><span class="sxs-lookup"><span data-stu-id="c5178-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="c5178-182">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="c5178-182">Enter the password.</span></span>
    4. <span data-ttu-id="c5178-183">В пункте **Параметры администрирования** выберите **Параметры телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="c5178-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="c5178-184">Включите **CAP** и **Режим администратора CAP**.</span><span class="sxs-lookup"><span data-stu-id="c5178-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="c5178-185">Нажмите **Сохранить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="c5178-185">Click **Save Config**.</span></span>

- <span data-ttu-id="c5178-186">Теперь телефон готов, и вы можете выполнить вход на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="c5178-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="c5178-187">Войдите, выбрав **Параметры** > **Функции** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c5178-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="c5178-188">Выберите **Учетные данные пользователя**, а затем — **Интернет-вход (CAP)**, чтобы генерировать код.</span><span class="sxs-lookup"><span data-stu-id="c5178-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="c5178-189">Перейдите на [портал подготовки](https://aka.ms/skypecap) и войдите в систему как **администратор**.</span><span class="sxs-lookup"><span data-stu-id="c5178-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="c5178-190">Введите отображаемое имя (например, Главная Приемная).</span><span class="sxs-lookup"><span data-stu-id="c5178-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="c5178-191">Если отмечена опция **Искать только телефоны общего пользования**, снимите флажок и выполните поиск повторно.</span><span class="sxs-lookup"><span data-stu-id="c5178-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="c5178-192">В окне кода сопряжения введите код, который отображается на телефоне, и нажмите **Подготовка**.</span><span class="sxs-lookup"><span data-stu-id="c5178-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="c5178-193">После этого действия телефон должен автоматически войти в систему.</span><span class="sxs-lookup"><span data-stu-id="c5178-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="c5178-p115">The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span><span class="sxs-lookup"><span data-stu-id="c5178-p115">The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="c5178-198">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c5178-198">Related topics</span></span>

- <span data-ttu-id="c5178-199">Узнайте больше о доступных телефонах в статье [Развертывание телефонов Skype для бизнеса Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="c5178-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="c5178-200">Телефоны, поддерживаемые в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c5178-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


