---
title: Настройка автозавода для Microsoft Teams — учебник для малого бизнеса
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Узнайте, как настроить и протестировать автоотетаря для Microsoft 365 Business Voice.
ms.openlocfilehash: fef89971ad99dff15332905d6f9b98a343af6ffd
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439724"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="8eee2-103">Настройка автозавода — учебник по малому бизнесу</span><span class="sxs-lookup"><span data-stu-id="8eee2-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="8eee2-104">С помощью автозаверх можно звонить в вашу организацию и переходить в систему меню для связи с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="8eee2-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="8eee2-105">В Центре администрирования Microsoft Teams можно создавать автозаводы для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8eee2-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="8eee2-106">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="8eee2-106">Before you begin</span></span>

<span data-ttu-id="8eee2-107">Получите номера служб, необходимые для автозаполнения, чтобы получать доступ к данным с помощью прямого набора номера из-за пределов организации.</span><span class="sxs-lookup"><span data-stu-id="8eee2-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="8eee2-108">Это может быть [перенос номеров от другого поставщика или](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) запрос новых [номеров служб.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="8eee2-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="8eee2-109">Получите [телефонную систему — лицензию виртуального пользователя](../teams-add-on-licensing/virtual-user.md) для каждого автозавода, который вы планируете создать.</span><span class="sxs-lookup"><span data-stu-id="8eee2-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="8eee2-110">Эти лицензии бесплатны, поэтому мы рекомендуем получить дополнительные лицензии на случай, если вы решите внести изменения в настройку в будущем.</span><span class="sxs-lookup"><span data-stu-id="8eee2-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="8eee2-111">Если вы хотите, чтобы во время праздников [](../set-up-holidays-in-teams.md) звонки автоответа перенаводились по-разному, создайте праздники, которые вы хотите использовать перед созданием автоответа.</span><span class="sxs-lookup"><span data-stu-id="8eee2-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="8eee2-112">Выполните эти действия, чтобы настроить автостраницу</span><span class="sxs-lookup"><span data-stu-id="8eee2-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="8eee2-113">Шаг <br> 1. Номер телефона</span><span class="sxs-lookup"><span data-stu-id="8eee2-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="8eee2-114">Для каждого создающегося автозачета требуется учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="8eee2-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="8eee2-115">Эта учетная запись аналогична учетной записи пользователя, за исключением того, что она связана с автоотчетом или очередью вызовов, а не с человеком.</span><span class="sxs-lookup"><span data-stu-id="8eee2-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="8eee2-116">На этом шаге мы создадим учетную запись, назначим ее телефонной системе *Microsoft 365 —* лицензию виртуального пользователя, а затем назначим номер службы.</span><span class="sxs-lookup"><span data-stu-id="8eee2-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="8eee2-117">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="8eee2-117">Create a resource account</span></span>

<span data-ttu-id="8eee2-118">Учетную запись ресурса можно создать в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8eee2-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="8eee2-119">В Центре администрирования Teams раз щелкните **"Учетные** записи ресурсов", чтобы развернуть параметры для всей **организации.**</span><span class="sxs-lookup"><span data-stu-id="8eee2-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="8eee2-120">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8eee2-120">Click **Add**.</span></span>

3. <span data-ttu-id="8eee2-121">В области **"Добавление учетной** записи ресурса" введите отображаемого **имени,** имя пользователя и выберите "Автозачет"  для типа учетной **записи ресурса.**</span><span class="sxs-lookup"><span data-stu-id="8eee2-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Снимок экрана: добавление учетной записи ресурса в пользовательский интерфейс](../media/resource-account-add.png)

4. <span data-ttu-id="8eee2-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8eee2-123">Click **Save**.</span></span>

<span data-ttu-id="8eee2-124">Новая учетная запись появится в списке учетных записей.</span><span class="sxs-lookup"><span data-stu-id="8eee2-124">The new account will appear in the list of accounts.</span></span>

![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="8eee2-126">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="8eee2-126">Assign a license</span></span>

<span data-ttu-id="8eee2-127">Учетной записи ресурса необходимо назначить *лицензию "Телефонная система Microsoft 365 —* виртуальный пользователь".</span><span class="sxs-lookup"><span data-stu-id="8eee2-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="8eee2-128">В Центре администрирования Microsoft 365 выберите учетную запись ресурса, для которой вы хотите назначить лицензию.</span><span class="sxs-lookup"><span data-stu-id="8eee2-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="8eee2-129">На **вкладке "Лицензии и** приложения" в **области "Лицензии"** выберите **"Телефонная система Microsoft 365 — виртуальный пользователь".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="8eee2-130">Нажмите **кнопку "Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-130">Click **Save changes**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения лицензий в Центре администрирования Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="8eee2-132">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="8eee2-132">Assign a service number</span></span>

<span data-ttu-id="8eee2-133">Если вам нужно, чтобы с этим автоотчетом можно было связаться по номеру телефона, назначьте этот номер учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="8eee2-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="8eee2-134">В Центре администрирования Teams  на странице "Учетные записи ресурсов" выберите учетную запись ресурса, для которой вы хотите назначить номер службы, а затем нажмите кнопку "Назначить/отозначить". </span><span class="sxs-lookup"><span data-stu-id="8eee2-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="8eee2-135">В **dropdown (Тип номера телефона)** выберите нужный тип номера.</span><span class="sxs-lookup"><span data-stu-id="8eee2-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="8eee2-136">В поле **"Назначенное номер телефона"** найдите нужный номер и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Снимок экрана: пользовательский интерфейс назначения номера службы](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="8eee2-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8eee2-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-139">Шаг 2. Общие сведения для автосектора ></span><span class="sxs-lookup"><span data-stu-id="8eee2-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="8eee2-140">Общие сведения о <br> помощнике по шагу 2</span><span class="sxs-lookup"><span data-stu-id="8eee2-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="8eee2-141">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="8eee2-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="8eee2-142">В Центре администрирования Teams раз нажмите **кнопку "Голосовая** почта", выберите "Автоотекатарие" и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="8eee2-143">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="8eee2-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="8eee2-144">Если вы хотите назначить оператор, укажите место назначения для звонков на этот оператор.</span><span class="sxs-lookup"><span data-stu-id="8eee2-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="8eee2-145">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="8eee2-145">This is optional (but recommended).</span></span> <span data-ttu-id="8eee2-146">Параметр **"Оператор"** позволяет вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="8eee2-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="8eee2-147">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="8eee2-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="8eee2-148">Часовой пояс используется для расчета рабочих часов, если вы создаете отдельный поток зовов в нечасовом времени.</span><span class="sxs-lookup"><span data-stu-id="8eee2-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="8eee2-149">Укажите язык для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="8eee2-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="8eee2-150">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="8eee2-151">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="8eee2-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="8eee2-152">Если этот параметр включен, название каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="8eee2-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="8eee2-153">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="8eee2-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="8eee2-155">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eee2-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-156">Шаг 3. ></span><span class="sxs-lookup"><span data-stu-id="8eee2-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="8eee2-157">Шаг <br> 3. Поток зовов</span><span class="sxs-lookup"><span data-stu-id="8eee2-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="8eee2-158">Выбор параметров потока звонка</span><span class="sxs-lookup"><span data-stu-id="8eee2-158">Choose your call flow options</span></span>

1. <span data-ttu-id="8eee2-159">Выберите, хотите ли вы воспроизведения приветствия, когда автозавет отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="8eee2-160">Выбрав **"Воспроизведения звукового** файла",  вы можете добавить записанное приветствие, сохраненное как звуковое сообщение, с помощью кнопки "Отправить файл". WAV, . MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="8eee2-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="8eee2-161">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="8eee2-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="8eee2-162">Если вы **выберете** "Введите приветствие", система прочитает текст, который вы введите (до 1000 символов), когда автостраница отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Снимок экрана: параметры приветствия сообщения](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="8eee2-164">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="8eee2-165">Если вы выберете **"Отключить",** автоотетарь повесит звонок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="8eee2-166">При выборе пункта **"Перенаправление** звонка" можно выбрать одно из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="8eee2-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="8eee2-167">При выборе параметров **меню "Воспроизведения"** можно выбрать "Воспроизведения звукового файла" или "Ввести приветствие", а затем выбрать параметры меню и поиск по каталогу.  </span><span class="sxs-lookup"><span data-stu-id="8eee2-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Снимок экрана: параметры маршрутки вызовов](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="8eee2-169">Если вы хотите, чтобы для навигации использовались клавиши набора номера, в меню "Настройка" выберите, что должно происходить при нажатии клавиши набора номера.</span><span class="sxs-lookup"><span data-stu-id="8eee2-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="8eee2-170">(Если вы создаете этого автозавода в качестве каталога организации, оставьте параметры набора параметров пустыми.)</span><span class="sxs-lookup"><span data-stu-id="8eee2-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="8eee2-171">Вы можете настроить любые из этих клавиш для следующих назначений:</span><span class="sxs-lookup"><span data-stu-id="8eee2-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="8eee2-172">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="8eee2-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="8eee2-173">**Голосовое приложение** — еще один автозавод или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="8eee2-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="8eee2-174">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8eee2-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="8eee2-175">Используйте такой формат: +[код страны][код города][номер телефона]</span><span class="sxs-lookup"><span data-stu-id="8eee2-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="8eee2-176">**Голосовая почта** — это почтовый ящик голосовой почты, связанный с группой Microsoft 365, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="8eee2-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="8eee2-177">**Оператор** — оператор, задавающийся для автозавода.</span><span class="sxs-lookup"><span data-stu-id="8eee2-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="8eee2-178">Определение оператора не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8eee2-178">Defining an operator is optional.</span></span> <span data-ttu-id="8eee2-179">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="8eee2-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="8eee2-180">Мы рекомендуем установить для оператора 0.</span><span class="sxs-lookup"><span data-stu-id="8eee2-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="8eee2-181">Для каждого параметра меню укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="8eee2-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="8eee2-182">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="8eee2-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="8eee2-183">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включен голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="8eee2-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="8eee2-184">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Действия и причины".</span><span class="sxs-lookup"><span data-stu-id="8eee2-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="8eee2-185">**Перенаправление** в то место, куда должен перенаправляться звонок при выборе этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8eee2-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="8eee2-186">Если вы перенаправляете звонок к автоотправлению или очереди вызовов, выберите связанную с ним учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="8eee2-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Снимок экрана: параметры набора номера](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="8eee2-188">Если вы хотите использовать этого автостраницу в качестве каталога организации, в области поиска по каталогу выберите "Набрать **имя".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="8eee2-189">Если включить этот параметр, звоня людям, которые будут называть имя пользователя или ввести его, вы сможете ввести его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="8eee2-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="8eee2-190">Любой пользователь в Сети с лицензией на телефонную систему является подходящим пользователем, и его можно найти с помощью звонка по имени.</span><span class="sxs-lookup"><span data-stu-id="8eee2-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="8eee2-191">(Вы можете выбрать **"Звонить по расширению",** но расширение необходимо настроить в Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="8eee2-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="8eee2-192">Выбрав параметр поиска  по каталогу, нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-193">Шаг 4. Неавное время ></span><span class="sxs-lookup"><span data-stu-id="8eee2-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="8eee2-194">Шаг <br> 4.</span><span class="sxs-lookup"><span data-stu-id="8eee2-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="8eee2-195">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="8eee2-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="8eee2-196">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="8eee2-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="8eee2-197">Для работы можно установить перерывы в течение дня, а все часы, которые не считаются часами, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="8eee2-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="8eee2-198">Вы можете настроить другие параметры обработки входящих параметров обработки параметров и приветствий в течение часа.</span><span class="sxs-lookup"><span data-stu-id="8eee2-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="8eee2-199">В зависимости от настройки автозаполнения и очередей звонков может потребоваться настроить маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="8eee2-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="8eee2-200">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="8eee2-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="8eee2-201">Нажмите **кнопку "Добавить новое** время", чтобы указать несколько часов в течение заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="8eee2-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](../media/auto-attendant-business-hours.png)

<span data-ttu-id="8eee2-203">Заданные часы работы можно выбрать в параметрах маршрутки параметров перенач.</span><span class="sxs-lookup"><span data-stu-id="8eee2-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="8eee2-204">Доступны те же параметры, что и для маршрутичности параметров в часы, заданных в шаге **3 "Поток параметров параметров звонка".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="8eee2-205">Когда **все будет** готово, нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8eee2-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-206">Шаг 5. Holiday call flow ></span><span class="sxs-lookup"><span data-stu-id="8eee2-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="8eee2-207">Шаг <br> 5. Праздники</span><span class="sxs-lookup"><span data-stu-id="8eee2-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="8eee2-208">Вы можете звонить автоответам не так, как в праздники в другие дни.</span><span class="sxs-lookup"><span data-stu-id="8eee2-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="8eee2-209">(Если вы не хотите, чтобы в праздники велись другие вызовы, этот шаг можно пропустить.)</span><span class="sxs-lookup"><span data-stu-id="8eee2-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="8eee2-210">Для каждого настроенного вами праздника автостраница может настроить поток звонка.</span><span class="sxs-lookup"><span data-stu-id="8eee2-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="8eee2-211">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="8eee2-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="8eee2-212">На странице параметров звонка "Праздник" нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="8eee2-213">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="8eee2-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="8eee2-214">В **выпадаемом** окнах "Праздники" выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="8eee2-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="8eee2-215">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="8eee2-215">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры поздравительных и праздников](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="8eee2-217">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="8eee2-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="8eee2-218">Если вы перенаправили звонок, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="8eee2-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Снимок экрана: параметры действия по праздничным звонкам](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="8eee2-220">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8eee2-220">Click **Save**.</span></span>

<span data-ttu-id="8eee2-221">Повторите процедуру для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="8eee2-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Снимок экрана: параметры праздников со списком праздников](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="8eee2-223">После того как вы добавите все праздники, нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-224">Шаг 6. Выбор каталога для ></span><span class="sxs-lookup"><span data-stu-id="8eee2-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="8eee2-225">Участники каталога шага 6 <br></span><span class="sxs-lookup"><span data-stu-id="8eee2-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="8eee2-226">Область *набора определяет* пользователей, доступных в каталоге, если звоня по имени или с помощью телефонного звонка по расширению.</span><span class="sxs-lookup"><span data-stu-id="8eee2-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="8eee2-227">По умолчанию для **всех сетевых пользователей** входят все пользователи в организации, которые являются пользователями Online с лицензией на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="8eee2-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="8eee2-228">Вы можете включить или исключить  определенных  пользователей, выбрав пользовательскую группу в группе "Включить" или **"Исключить"** и выбрав одну или несколько групп Microsoft 365, списки рассылки или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="8eee2-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="8eee2-229">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="8eee2-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="8eee2-230">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="8eee2-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Снимок экрана: область набора номера с вариантами "Включить" и "Исключить"](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="8eee2-232">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="8eee2-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="8eee2-233">После настройки области набора номера нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eee2-234">Шаг 7. Назначение учетной записи ресурса ></span><span class="sxs-lookup"><span data-stu-id="8eee2-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="8eee2-235">Шаг <br> 7. Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="8eee2-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="8eee2-236">У всех автозачетных должно быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="8eee2-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="8eee2-237">Автоотчетщикам первого уровня потребуется хотя бы одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="8eee2-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="8eee2-238">При желании вы можете назначить автозаводу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="8eee2-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="8eee2-239">Добавление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="8eee2-239">To add a resource account</span></span>

1. <span data-ttu-id="8eee2-240">Нажмите **кнопку "Добавить учетную** запись" и найдите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="8eee2-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="8eee2-241">Нажмите **кнопку "Добавить"** и выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-241">Click **Add**, and then click **Add**.</span></span>

    ![Снимок экрана: панель добавления учетных записей для учетной записи ресурса](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="8eee2-243">Завершив добавление учетных записей служб, нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="8eee2-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="8eee2-245">В этом случае будет завершена настройка автоотполнеющего персонала.</span><span class="sxs-lookup"><span data-stu-id="8eee2-245">This completes the auto attendant configuration.</span></span>

---


