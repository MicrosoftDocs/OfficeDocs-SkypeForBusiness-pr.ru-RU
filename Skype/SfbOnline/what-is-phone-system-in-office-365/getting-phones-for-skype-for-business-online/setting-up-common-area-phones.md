---
title: Настройка телефонов общего пользования
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Изучите шаги развертывания, чтобы получить правильное встроенное ПО, обновлять его при необходимости, назначать лицензии и настраивать параметры для телефонов общего пользования.
ms.openlocfilehash: 25605e7538792080213eebb898e612be6ce5bfab
ms.sourcegitcommit: bdf9946b7c65ef7985d6b03a1479ea3a5c17a304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "19426804"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="75b50-103">Настройка телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="75b50-103">Set up common area phones</span></span>
<span data-ttu-id="75b50-104">Телефон общего пользования (CAP) обычно размещается в холле или другом общедоступном месте.</span><span class="sxs-lookup"><span data-stu-id="75b50-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="75b50-105">Например, телефон приемной, домофон, телефон для конференц-залов и другие CAP настраиваются скорее как устройства, чем как пользователи, и автоматически входят в сеть.</span><span class="sxs-lookup"><span data-stu-id="75b50-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="75b50-106">В приведенных ниже шагах мы поможем вам настроить учетную запись для телефонной системы с тарифными планами, чтобы вы могли развернуть эти типы телефонов в своей организации.</span><span class="sxs-lookup"><span data-stu-id="75b50-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="75b50-107">Предварительные требования для телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="75b50-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="75b50-108">В первую очередь необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="75b50-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="75b50-109">Приобрести лицензию на телефон общего пользования и тарифный план.</span><span class="sxs-lookup"><span data-stu-id="75b50-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="75b50-110">Найти и приобрести одобренные телефоны (вы можете просмотреть их список[здесь](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="75b50-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="75b50-111">Обновить встроенное ПО на телефонах (см. поддерживаемые встроенные ПО [в этой теме](getting-phones-for-skype-for-business-online.md)).</span><span class="sxs-lookup"><span data-stu-id="75b50-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="75b50-112">Вы можете проверить встроенное ПО на телефоне, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="75b50-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="75b50-113">**Телефоны Polycom VVX**: выберите **Настройки** > **Состояние** > **Платформа** > **Приложение** > **Основные**.</span><span class="sxs-lookup"><span data-stu-id="75b50-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="75b50-114">**Телефоны Yealink**: выберите**Состояние** на главном экране телефона.</span><span class="sxs-lookup"><span data-stu-id="75b50-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="75b50-115">**Телефоны AudioCodes**: выберите **Меню** > **Состояние устройства** > **Версия встроенного ПО** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="75b50-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="75b50-116">**Телефоны Lync Phone Edition (LPE)**: выберите **Меню** > **Сведения о системе** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="75b50-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="75b50-117">Служба Skype для бизнеса управляет обновлением встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="75b50-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="75b50-118">Обновление для каждого сертифицированного телефона Skype для бизнеса загружается на сервер обновлений Skype для бизнеса, а на всех устройствах обновление включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75b50-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="75b50-119">В зависимости от периода неактивности телефона и интервалов опроса последние версии сертифицированных сборок автоматически загружаются и устанавливаются на телефоны.</span><span class="sxs-lookup"><span data-stu-id="75b50-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="75b50-120">Чтобы отключить обновление устройства, выполните командлет [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) и присвойте параметру *EnableDeviceUpdate* значение `false`.</span><span class="sxs-lookup"><span data-stu-id="75b50-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="75b50-121">Настройка телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="75b50-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="75b50-122">Вам потребуется выполнить следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="75b50-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="75b50-123">Шаг 1. Приобретение лицензий</span><span class="sxs-lookup"><span data-stu-id="75b50-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="75b50-124">В Центре администрирования Office 365 перейдите в **Выставление счетов** > **Приобретение услуг** и добавьте **Другие планы**.</span><span class="sxs-lookup"><span data-stu-id="75b50-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="75b50-126">Нажмите на **Телефон общего пользования** > **Купить**, на странице **Оформление заказа** нажмите кнопку **Купить**.</span><span class="sxs-lookup"><span data-stu-id="75b50-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="75b50-127">Щелкните мышью, чтобы развернуть **Подписки на надстройки**, а затем щелкните снова для покупки тарифного плана.</span><span class="sxs-lookup"><span data-stu-id="75b50-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="75b50-128">Выберите либо **План для местных звонков**, либо **План для местных и международных звонков**.</span><span class="sxs-lookup"><span data-stu-id="75b50-128">Domestic Calling Plan, or Domestic and International Calling Plan</span></span>

> [!Note]
> <span data-ttu-id="75b50-129">Вам не нужна лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="75b50-129">You don't need a Phone System license.</span></span> <span data-ttu-id="75b50-130">Она включена в лицензию **Телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="75b50-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="75b50-131">Узнайте больше о лицензиях в статье [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-131">For more information, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="75b50-132">Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="75b50-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="75b50-133">В центре администрирования Office 365 перейдите в раздел **Пользователи** > **Активные пользователи** > **Добавление пользователя**.</span><span class="sxs-lookup"><span data-stu-id="75b50-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="75b50-134">В поле **Имя пользователя** укажите, например, "Основная", а в графе для фамилии — "Приемная".</span><span class="sxs-lookup"><span data-stu-id="75b50-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="75b50-135">В поле **Отображаемое имя**, если оно не заполнилось автоматически, укажите, например, "Главная Приемная".</span><span class="sxs-lookup"><span data-stu-id="75b50-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="75b50-136">В поле**Имя пользователя** укажите, например, "MainReception" или "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="75b50-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="75b50-137">Можно установить отдельный пароль вручную для каждого телефона общего пользования или использовать один пароль для всех телефонов.</span><span class="sxs-lookup"><span data-stu-id="75b50-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="75b50-138">Кроме того, можно отменить выбор пункта **Потребовать смену пароля при первом входе пользователя**.</span><span class="sxs-lookup"><span data-stu-id="75b50-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="75b50-139">ВНИМАНИЕ!!</span><span class="sxs-lookup"><span data-stu-id="75b50-139">WAIT!!</span></span> <span data-ttu-id="75b50-140">Не нажимайте **Добавить**!!</span><span class="sxs-lookup"><span data-stu-id="75b50-140">Don't click **Add**!!</span></span> <span data-ttu-id="75b50-141">Если вы все-таки нажали **Добавить**, сделайте следующее: перейдите в Центр администрирования Office 365 **Пользователи** > **Активные пользователи** и найдите пользователя.</span><span class="sxs-lookup"><span data-stu-id="75b50-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="75b50-142">После этого на странице информации о пользователе нажмите **Лицензии продуктов**, а затем —**Изменить**.</span><span class="sxs-lookup"><span data-stu-id="75b50-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="75b50-143">На странице **Лицензии продуктов** включите опцию **Телефон общего пользования** и выберите либо **План для местных звонков**, либо **План для международных** и местных звонков.</span><span class="sxs-lookup"><span data-stu-id="75b50-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="75b50-144">Если вы все еще на этой странице, назначьте лицензии этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="75b50-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="75b50-145">На этой же странице щелкните мышью и разверните **Лицензии продуктов**.</span><span class="sxs-lookup"><span data-stu-id="75b50-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="75b50-146">Включите следующие опции:</span><span class="sxs-lookup"><span data-stu-id="75b50-146">Turn on the following:</span></span>
    - <span data-ttu-id="75b50-147">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="75b50-147">Common Area Phone</span></span>
    - <span data-ttu-id="75b50-148">Общего Пользования sedGlossaryTerm">Телефон**** ** **</span><span class="sxs-lookup"><span data-stu-id="75b50-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="75b50-149">Назначение лицензий будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="75b50-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="75b50-151">Приводим к вашему сведению, что в лицензию **Телефона общего пользования** включен План 2 Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="75b50-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="75b50-152">Узнайте больше в статье [Добавление пользователей](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="75b50-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="75b50-153">Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="75b50-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="75b50-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Назначьте номер телефона пользователю, используя **Центр администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="75b50-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="75b50-155">В Центре администрирования Office 365 перейдите в раздел **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="75b50-155">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="75b50-156">Далее: **Центр администрирования Skype для бизнеса** >  **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="75b50-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="75b50-157">Выберите номер телефона из списка и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="75b50-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="75b50-158">На странице **Назначить** в поле **Пользователь голосовой связи** введите имя пользователя телефона, а затем выберите пользователя в выпадающем списке **Выбор пользователя голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="75b50-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="75b50-159">Пока вы находитесь на этой странице, необходимо добавить адрес для обращения в экстренных случаях.</span><span class="sxs-lookup"><span data-stu-id="75b50-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="75b50-160">Во время поиска выберите нужный адрес под пунктом **Выбор адреса для обращения в экстренных случаях**.</span><span class="sxs-lookup"><span data-stu-id="75b50-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="75b50-161">Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="75b50-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="75b50-163">Пользователи будут отображаться, только если на них распространяется лицензия **Телефонная система**.</span><span class="sxs-lookup"><span data-stu-id="75b50-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="75b50-164">Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.</span><span class="sxs-lookup"><span data-stu-id="75b50-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="75b50-165">Узнайте больше в статье [Получение телефонных номеров для ваших пользователей](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="75b50-166">При необходимости номера телефонов других операторов можно "*портировать*" или передать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="75b50-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="75b50-167">См. [Передача номеров телефонов в Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-167">See [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) for more information.</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="75b50-168">Шаг 4. Настройка телефона</span><span class="sxs-lookup"><span data-stu-id="75b50-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="75b50-169">**Настройка режима в телефоне**</span><span class="sxs-lookup"><span data-stu-id="75b50-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="75b50-170">В вашем телефоне необходимо включить **Режим телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="75b50-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="75b50-171">Убедитесь, есть ли в нем такой режим.</span><span class="sxs-lookup"><span data-stu-id="75b50-171">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="75b50-172">**Ниже приведен пример настройки телефона Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="75b50-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="75b50-173">Включите режим телефона общего пользования для Polycom VVX, выполнив следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="75b50-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="75b50-174">Подключитесь к веб-интерфейсу через веб-обозреватель, чтобы включить режим CAP.</span><span class="sxs-lookup"><span data-stu-id="75b50-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="75b50-175">Затем откройте меню **Параметры** и в пункте **Параметры Skype для бизнеса** выберите **Телефон общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="75b50-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="75b50-176">Нажмите **Да** для сохранения параметров.</span><span class="sxs-lookup"><span data-stu-id="75b50-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="75b50-177">Теперь режим CAP включен, и вы можете настроить телефон, используя его дисплей.</span><span class="sxs-lookup"><span data-stu-id="75b50-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="75b50-178">Дисплей должен показывать **CAP включен**.</span><span class="sxs-lookup"><span data-stu-id="75b50-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="75b50-179">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="75b50-179">Then do the following:</span></span>

    1. <span data-ttu-id="75b50-180">Выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="75b50-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="75b50-181">Затем выберите**Дополнительные**.</span><span class="sxs-lookup"><span data-stu-id="75b50-181">Select **Advanced Request**.</span></span>
    3. <span data-ttu-id="75b50-182">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="75b50-182">Enter the password.</span></span>
    4. <span data-ttu-id="75b50-183">В пункте **Параметры администрирования** выберите **Параметры телефона общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="75b50-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="75b50-184">Включите **CAP** и **Режим администратора CAP**.</span><span class="sxs-lookup"><span data-stu-id="75b50-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="75b50-185">Нажмите **Сохранить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="75b50-185">Click **Save Config**.</span></span>

- <span data-ttu-id="75b50-186">Теперь телефон готов, и вы можете выполнить вход на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="75b50-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="75b50-187">Войдите, выбрав **Параметры** > **Функции** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="75b50-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="75b50-188">Выберите **Учетные данные пользователя**, а затем — **Интернет-вход (CAP)**, чтобы генерировать код.</span><span class="sxs-lookup"><span data-stu-id="75b50-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="75b50-189">Перейдите на [портал подготовки](http://aka.ms/skypecap) и войдите в систему как **администратор**.</span><span class="sxs-lookup"><span data-stu-id="75b50-189">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="75b50-190">Введите отображаемое имя (например, Главная Приемная).</span><span class="sxs-lookup"><span data-stu-id="75b50-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="75b50-191">Если отмечена опция **Искать только телефоны общего пользования**, снимите флажок и выполните поиск повторно.</span><span class="sxs-lookup"><span data-stu-id="75b50-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="75b50-192">В окне кода сопряжения введите код, который отображается на телефоне, и нажмите **Подготовка**.</span><span class="sxs-lookup"><span data-stu-id="75b50-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="75b50-193">После этого действия телефон должен автоматически войти в систему.</span><span class="sxs-lookup"><span data-stu-id="75b50-193">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="75b50-194">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="75b50-194">Related topics</span></span>

- <span data-ttu-id="75b50-195">Узнайте больше о доступных телефонах в статье [Развертывание телефонов Skype для бизнеса Online](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="75b50-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="75b50-196">Телефоны, поддерживаемые в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75b50-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


