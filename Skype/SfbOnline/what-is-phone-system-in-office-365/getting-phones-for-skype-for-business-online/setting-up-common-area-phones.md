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
description: Познакомьтесь с действиями развертывания для получения микропрограммы, при необходимости обновите ее, назначение лицензий и настройка параметров для телефонов общего пользования.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="33398-103">Настройка телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="33398-103">Set up common area phones</span></span>
<span data-ttu-id="33398-104">Телефон общего пользования (узел) обычно переводится в область, например зал ожидания или другой области, доступные для много людей.</span><span class="sxs-lookup"><span data-stu-id="33398-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="33398-105">Например, телефонов области приема, телефона помещения двери телефон или собрания, CAPs настраиваются как устройства, а не пользователей и автоматический вход в сеть.</span><span class="sxs-lookup"><span data-stu-id="33398-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="33398-106">В приведенные ниже действия будут поможет вам настроить учетную запись для телефонной системы с помощью вызова планы, можно развернуть эти типы телефоны для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="33398-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="33398-107">Необходимые условия для телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="33398-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="33398-108">Первое, что необходимо выполнить, чтобы убедиться в том, что у вас есть следующие:</span><span class="sxs-lookup"><span data-stu-id="33398-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="33398-109">Приобрести лицензии телефон общего пользования и вызов планирование.</span><span class="sxs-lookup"><span data-stu-id="33398-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="33398-110">Поиск и приобрести утвержденных телефоны (просмотреть список [здесь](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="33398-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="33398-111">Обновление встроенного по на телефоны (см. поддерживается встроенного [в этом разделе](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="33398-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="33398-112">Вы можете проверить встроенного по на телефоне можно таким образом:</span><span class="sxs-lookup"><span data-stu-id="33398-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="33398-113">**Телефоны Polycom VVX**: переход к **параметрам** > **состояние** > **платформы** > **приложения** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="33398-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="33398-114">**Телефоны Yealink**: перейти к **состоянию** на экране основной телефон.</span><span class="sxs-lookup"><span data-stu-id="33398-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="33398-115">**Телефоны AudioCodes**: Откройте **меню** > **Состояние устройства** > **версия микропрограммы** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="33398-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="33398-116">**Телефоны Lync Phone Edition (LPE)**: В **меню** > **Сведения о системе** на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="33398-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="33398-117">Служба Skype для бизнеса управляет обновлением встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="33398-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="33398-118">Обновление для каждого сертифицированного телефона Skype для бизнеса загружается на сервер обновлений Skype для бизнеса, а на всех устройствах обновление включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33398-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="33398-119">В зависимости от периода неактивности телефона и интервалов опроса на телефоны автоматически загружаются и устанавливаются последние версии сертифицированных сборок.</span><span class="sxs-lookup"><span data-stu-id="33398-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="33398-120">Параметры обновления устройства можно отключить с помощью командлета [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) , для параметра *EnableDeviceUpdate* `false`.</span><span class="sxs-lookup"><span data-stu-id="33398-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="33398-121">Настройка телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="33398-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="33398-122">Необходимо будет выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33398-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="33398-123">Настройка учетной записи пользователя для телефона</span><span class="sxs-lookup"><span data-stu-id="33398-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="33398-124">Шаг 1 - приобрести лицензии</span><span class="sxs-lookup"><span data-stu-id="33398-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="33398-125">В центре администрирования Office 365 перейдите **по выставлению счетов** > **приобретение служб**, и добавьте **другие планы**.</span><span class="sxs-lookup"><span data-stu-id="33398-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![Ограничение license.png](../../images/cap-license.png)
2. <span data-ttu-id="33398-127">Щелкните на **Телефон общего пользования** > **купить** > на странице щелкните **оформления заказа** на **купить**.</span><span class="sxs-lookup"><span data-stu-id="33398-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="33398-128">Щелкните, чтобы развернуть **дополнительный компонент подписки** и нажмите кнопку на приобрести вызов планирование.</span><span class="sxs-lookup"><span data-stu-id="33398-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="33398-129">Выберите **Внутренний вызов план** или **Планирование внутренних и международных звонков**.</span><span class="sxs-lookup"><span data-stu-id="33398-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="33398-130">Не требуется лицензия телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="33398-130">You don't need a Phone System license.</span></span> <span data-ttu-id="33398-131">Он включен с лицензией **Телефон общего пользования** .</span><span class="sxs-lookup"><span data-stu-id="33398-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="33398-132">Дополнительные сведения о лицензии в разделе [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="33398-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="33398-133">Шаг 2 — Создание учетной записи пользователя для телефона и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="33398-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="33398-134">В центре администрирования Office 365 перейдите к **пользователям** > **Активных пользователей** > **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="33398-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="33398-135">Поместите в **имя пользователя** , например «Главная» для имени и «Прием» для второго имени.</span><span class="sxs-lookup"><span data-stu-id="33398-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="33398-136">Поместите в **отображаемое имя** , если она не автоматически заполнять одно как «Main прием».</span><span class="sxs-lookup"><span data-stu-id="33398-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="33398-137">Поместите в поле **имя пользователя** , такой как «MainReception» или «Mainlobby».</span><span class="sxs-lookup"><span data-stu-id="33398-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="33398-138">Для телефонов общего пользования можно вручную задать пароль или использовать тот же пароль для всех вы телефонов общего пользования.</span><span class="sxs-lookup"><span data-stu-id="33398-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="33398-139">Кроме того вы можете подумать об отключении параметра **пользователь изменить пароль при первом входе в**.</span><span class="sxs-lookup"><span data-stu-id="33398-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="33398-140">ПОДОЖДИТЕ!</span><span class="sxs-lookup"><span data-stu-id="33398-140">WAIT!!</span></span> <span data-ttu-id="33398-141">Не нажмите кнопку **Добавить**!</span><span class="sxs-lookup"><span data-stu-id="33398-141">Don't click **Add**!!</span></span> <span data-ttu-id="33398-142">Всего Если нажмите кнопку **Добавить** действие это: центра администрирования Office 365 > **Пользователи** > **активных пользователей** и затем найти пользователя.</span><span class="sxs-lookup"><span data-stu-id="33398-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="33398-143">На странице свойств пользователя, нажмите кнопку **лицензий продукта** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33398-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="33398-144">На странице **лицензий на продукт** включите **Телефон общего пользования** и выбрать либо **Планирование внутренних звонков** или внутренний и **International вызов планирование**.</span><span class="sxs-lookup"><span data-stu-id="33398-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="33398-145">Если вы по-прежнему существуют, ему назначены лицензии.</span><span class="sxs-lookup"><span data-stu-id="33398-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="33398-146">На той же странице щелкните и разверните **лицензий на продукт**.</span><span class="sxs-lookup"><span data-stu-id="33398-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="33398-147">Включите следующее:</span><span class="sxs-lookup"><span data-stu-id="33398-147">Turn on the following:</span></span>
    - <span data-ttu-id="33398-148">Телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="33398-148">Common Area Phone</span></span>
    - <span data-ttu-id="33398-149">Затем необходимо выбрать либо **Планирование внутренних звонков** или внутренний и **International вызов планирование**.</span><span class="sxs-lookup"><span data-stu-id="33398-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="33398-150">Назначение лицензий, будет иметь вид:</span><span class="sxs-lookup"><span data-stu-id="33398-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="33398-152">Чтобы вы знали Скайп для бизнеса (план 2) входит в состав лицензии **Телефон общего пользования** .</span><span class="sxs-lookup"><span data-stu-id="33398-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="33398-153">Для получения дополнительных сведений см [Добавить пользователя](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="33398-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="33398-154">Шаг 3 - назначить номер телефона для пользователя</span><span class="sxs-lookup"><span data-stu-id="33398-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="33398-155">![sfb логотип 30x30.png](../../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="33398-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="33398-156">В центре администрирования Office 365 > **центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="33398-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="33398-157">В **Скайп по центру администрирования Business** >  **голосовой связи** > **телефонных номеров**.</span><span class="sxs-lookup"><span data-stu-id="33398-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="33398-158">Выберите номер телефонных номеров в списке и нажмите кнопку **назначить**.</span><span class="sxs-lookup"><span data-stu-id="33398-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="33398-159">На странице " **Назначение** " в поле **голосовой связи пользователя** введите имя пользователя, который используется для телефона, то выберите пользователя в списке **выберите пользователя голосовой связи** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="33398-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="33398-160">Во время завершения работы необходимо добавить экстренных адрес.</span><span class="sxs-lookup"><span data-stu-id="33398-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="33398-161">Когда выполняется поиск, найдите раздел **выберите экстренных адрес** на выберите нужную для вас.</span><span class="sxs-lookup"><span data-stu-id="33398-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="33398-162">Нажмите кнопку **Сохранить** и пользователь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33398-162">Click **Save** and your user should look like this:</span></span>

    ![Ограничение пользователей number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="33398-164">Пользователи будут отображаются только при наличии применена лицензия **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="33398-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="33398-165">Если вы только что устранена, в некоторых случаях предпринимается немного для пользователя отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="33398-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="33398-166">Дополнительные материалы в разделе [Приступая к номера телефонов для пользователей](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="33398-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="33398-167">Если вам интересно, вы также можете номер телефона с другого поставщика и «*порт*» или переносе их по Office 365.</span><span class="sxs-lookup"><span data-stu-id="33398-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="33398-168">Отображается, [передачи телефонных номеров в Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="33398-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="33398-169">Шаг 4 - настройки телефона</span><span class="sxs-lookup"><span data-stu-id="33398-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="33398-170">**Настройка режима на телефоне**</span><span class="sxs-lookup"><span data-stu-id="33398-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="33398-171">Телефон или телефоны, у вас есть должен иметь включен режим телефон общего пользования.</span><span class="sxs-lookup"><span data-stu-id="33398-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="33398-172">Можно проверить, чтобы убедиться в том, что они выполняют.</span><span class="sxs-lookup"><span data-stu-id="33398-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="33398-173">**Ниже приведен пример для настройке телефон Polycom VVX**</span><span class="sxs-lookup"><span data-stu-id="33398-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="33398-174">Включение режима телефонов общей области для Polycom VVX, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33398-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="33398-175">В браузере, чтобы можно было включить режим БОЛТЫ подключение к веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="33398-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="33398-176">Затем перейти **параметру** и в параметре **Скайп для параметра бизнеса** , выберите **Телефон общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="33398-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="33398-177">Нажмите кнопку **Да,** чтобы сохранить параметры.</span><span class="sxs-lookup"><span data-stu-id="33398-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="33398-178">Теперь, когда включен режим БОЛТЫ, настройте телефон, с помощью телефона отображаются.</span><span class="sxs-lookup"><span data-stu-id="33398-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="33398-179">Отображение должно отобразиться **CaAP включен**.</span><span class="sxs-lookup"><span data-stu-id="33398-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="33398-180">Затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="33398-180">Then do the following:</span></span>

    1. <span data-ttu-id="33398-181">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="33398-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="33398-182">Выберите **Дополнительные**.</span><span class="sxs-lookup"><span data-stu-id="33398-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="33398-183">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="33398-183">Enter the password.</span></span>
    4. <span data-ttu-id="33398-184">В **Параметры администрирования**выберите **Общие параметры телефона зоны**.</span><span class="sxs-lookup"><span data-stu-id="33398-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="33398-185">Включите **БОЛТЫ** и **режим БОЛТЫ администратором**.</span><span class="sxs-lookup"><span data-stu-id="33398-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="33398-186">Нажмите кнопку **Сохранить настройки**.</span><span class="sxs-lookup"><span data-stu-id="33398-186">Click **Save Config**.</span></span>

- <span data-ttu-id="33398-187">Да теперь телефон готов, можно выполнить вход на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="33398-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="33398-188">Вход, выбрав **Параметры** > **функции** > **Скайп для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="33398-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="33398-189">Выберите **Учетные данные пользователя**и выберите **веб - вход (узел)** для генерации кода.</span><span class="sxs-lookup"><span data-stu-id="33398-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="33398-190">Перейдите к [подготовки портала](http://aka.ms/skypecap)и войдите в качестве **администратора**.</span><span class="sxs-lookup"><span data-stu-id="33398-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="33398-191">Введите отображаемое имя (например, для приема Main).</span><span class="sxs-lookup"><span data-stu-id="33398-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="33398-192">Если установлен флажок **поиска для телефонов общего пользования только** , снимите флажок и выполните поиск еще раз. "</span><span class="sxs-lookup"><span data-stu-id="33398-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="33398-193">В окне код связывания введите код, отображаемые на телефоне и щелкните **подготовить к работе**.</span><span class="sxs-lookup"><span data-stu-id="33398-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="33398-194">После этого последний шаг телефон должен автоматический вход в систему.</span><span class="sxs-lookup"><span data-stu-id="33398-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="33398-195">See also</span><span class="sxs-lookup"><span data-stu-id="33398-195">Related topics</span></span>

- <span data-ttu-id="33398-196">Дополнительные сведения о доступных телефонов представлены в [Развертывание Скайп для бизнеса в Интернет телефонов](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="33398-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="33398-197">Телефоны, поддерживаемые в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="33398-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


