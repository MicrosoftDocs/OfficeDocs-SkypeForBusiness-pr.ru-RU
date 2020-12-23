---
title: Настройка автозавода для Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: Узнайте, как настроить и протестировать автоотетаря в Microsoft Teams.
ms.openlocfilehash: 203a05e19ffce4154c123cbb700ca59e0b75a63a
ms.sourcegitcommit: 660d0d65892408d0bb4ac1a870c88b11a7c6841e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49530569"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="965d3-103">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="965d3-103">Set up an auto attendant</span></span>

<span data-ttu-id="965d3-104">Автозаверяющие могут звонить в вашу организацию и переходить в систему меню для связи с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="965d3-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="965d3-105">Вы можете создать автоотетаря для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="965d3-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="965d3-106">Прежде чем выполнять действия, которые вы выполните в [](plan-auto-attendant-call-queue.md#getting-started) этой статье, убедитесь в том, что вы прочитали "План" для автоотетаря [Teams](plan-auto-attendant-call-queue.md) и очередей вызовов, а затем следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="965d3-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="965d3-107">Автоответчики могут перенаправять звонки в одно из следующих расположений на основе данных, вводимых вызывающим звонителями: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="965d3-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="965d3-108">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="965d3-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="965d3-109">Это может быть пользователь в Сети или пользователь, который использует сервер Skype для бизнеса Server, который является пользователем локальной сети.</span><span class="sxs-lookup"><span data-stu-id="965d3-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="965d3-110">**Голосовое приложение** — еще один автозавод или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="965d3-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="965d3-111">(Выберите учетную запись ресурса, связанную с автостраницой или очередью вызовов, при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="965d3-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="965d3-112">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="965d3-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="965d3-113">(См. [технические сведения о внешнем переносе).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="965d3-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="965d3-114">**Голосовая почта** — это почтовый ящик голосовой почты, связанный с группой Microsoft 365, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="965d3-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="965d3-115">**Оператор** — оператор, задавающийся для автозавода.</span><span class="sxs-lookup"><span data-stu-id="965d3-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="965d3-116">Определение оператора не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="965d3-116">Defining an operator is optional.</span></span> <span data-ttu-id="965d3-117">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="965d3-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="965d3-118">Вам будет предложено выбрать один из этих параметров на разных этапах настройки автозаказа.</span><span class="sxs-lookup"><span data-stu-id="965d3-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="965d3-119">Чтобы настроить автостраницу, в Центре администрирования Teams раз нажмите **кнопку**"Автозаметки" и выберите команду **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="965d3-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="965d3-120">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="965d3-120">General info</span></span>

![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="965d3-122">Введите имя автозавода в поле вверху.</span><span class="sxs-lookup"><span data-stu-id="965d3-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="965d3-123">Если вы хотите назначить оператор, укажите место назначения для звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="965d3-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="965d3-124">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="965d3-124">This is optional (but recommended).</span></span> <span data-ttu-id="965d3-125">Параметр **"Оператор"** позволяет вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="965d3-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="965d3-126">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="965d3-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="965d3-127">Часовой пояс используется для расчета рабочих часов, если вы создаете отдельный поток [зовов для после часа.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="965d3-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="965d3-128">Укажите язык для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="965d3-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="965d3-129">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="965d3-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="965d3-130">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="965d3-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="965d3-131">Если этот параметр включен, название каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="965d3-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="965d3-132">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="965d3-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="965d3-133">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="965d3-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="965d3-134">Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="965d3-134">Call flow</span></span>

![Снимок экрана: параметры приветствия сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="965d3-136">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="965d3-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="965d3-137">Выбрав **"Воспроизведения звукового** файла",  вы можете добавить записанное приветствие, сохраненное как звуковое сообщение, с помощью кнопки "Отправить файл". WAV, . MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="965d3-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="965d3-138">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="965d3-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="965d3-139">Если вы **выберете** "Введите приветствие", система прочитает текст, который вы введите (до 1000 символов), когда автостраница отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="965d3-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутки вызовов](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="965d3-141">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="965d3-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="965d3-142">Если вы выберете **"Отключить",** автоотетарь повесит звонок.</span><span class="sxs-lookup"><span data-stu-id="965d3-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="965d3-143">При выборе пункта **"Перенаправление** звонка" можно выбрать одно из назначений маршрутиации.</span><span class="sxs-lookup"><span data-stu-id="965d3-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="965d3-144">Если **выбраны** параметры меню "Воспроизведения", можно  выбрать "Воспроизведения звукового файла" или "Ввести приветствие", а затем выбрать параметры меню и поиск по каталогу. </span><span class="sxs-lookup"><span data-stu-id="965d3-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="965d3-145">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="965d3-145">Menu options</span></span>

![Снимок экрана: параметры набора номера](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="965d3-147">Для настройки параметров набора можно назначить 0–9 клавиш на телефонной клавиатуре одному из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="965d3-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="965d3-148">(Клавиши \* (Повтор) и (Назад) зарезервированы системой и не \# могут быть перенаписаны.)</span><span class="sxs-lookup"><span data-stu-id="965d3-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="965d3-149">Сопоставление ключей не должно быть непрерывным.</span><span class="sxs-lookup"><span data-stu-id="965d3-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="965d3-150">Например, можно создать меню с клавишами 0, 1 и 3, относясь к параметрам, в то время как клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="965d3-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="965d3-151">Если вы его настроили, мы рекомендуем соендуть ключ 0 с оператором.</span><span class="sxs-lookup"><span data-stu-id="965d3-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="965d3-152">Если оператор не назначен никакой клавише, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="965d3-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="965d3-153">Для каждого параметра меню укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="965d3-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="965d3-154">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="965d3-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="965d3-155">Если голосовой ввод доступен, вызыватели также могут прогонать этот номер, чтобы получить доступ к параметру.</span><span class="sxs-lookup"><span data-stu-id="965d3-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="965d3-156">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включен голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="965d3-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="965d3-157">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Действия и причины".</span><span class="sxs-lookup"><span data-stu-id="965d3-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="965d3-158">Например, звонок может нажать 2, сказать "два" или сказать "Продажи", чтобы выбрать параметр, выбранный с клавишей 2.</span><span class="sxs-lookup"><span data-stu-id="965d3-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="965d3-159">Этот текст также отрисовывается текстом в речь при запросе на подтверждение службы, например", например "Перена передача звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="965d3-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="965d3-160">**Redirect to** - the call routing destination used when callers choose this option.</span><span class="sxs-lookup"><span data-stu-id="965d3-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="965d3-161">Если вы перенаправляете звонок к автоотправлению или очереди вызовов, выберите связанную с ним учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="965d3-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="965d3-162">Поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="965d3-162">Directory search</span></span>

<span data-ttu-id="965d3-163">При назначении клавиш набора номера назначениям рекомендуется выбрать вариант **"Нет"** для поиска **по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="965d3-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="965d3-164">Если звоняющий пытается набрать имя или расширение с помощью клавиш, которые назначены определенным назначениям, он может быть неожиданно перенаправлен в назначение до того, как закончит вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="965d3-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="965d3-165">Мы рекомендуем создать отдельного автозавода для поиска по каталогу и создать ссылку на него с помощью набора номера.</span><span class="sxs-lookup"><span data-stu-id="965d3-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="965d3-166">Если вы не назначили наберите клавиши, выберите параметр поиска **по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="965d3-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="965d3-167">**Звонок по имени.** Если этот параметр заданной опцией, звоня люди, звонят по имени пользователя или введите его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="965d3-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="965d3-168">Любой пользователь в Сети с лицензией на телефонную систему или любой пользователь, который работает локально с помощью Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью звонка по имени.</span><span class="sxs-lookup"><span data-stu-id="965d3-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="965d3-169">(На странице "Область набора номера" можно установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="965d3-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="965d3-170">**Подключаться по расширению—** если этот параметр заданной опцией, пользователи смогут связываться с пользователями в организации, набрав их расширения для телефона.</span><span class="sxs-lookup"><span data-stu-id="965d3-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="965d3-171">Любой пользователь в Сети с лицензией на телефонную систему или любой пользователь, который работает локально с помощью Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью телефонного **набора по расширению.**</span><span class="sxs-lookup"><span data-stu-id="965d3-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="965d3-172">(На странице "Область набора номера" можно установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="965d3-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="965d3-173">У пользователей, для пользователей, которые хотите сделать доступными для расширения "Звонок по", должен быть задано расширение, [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) как часть одного из указанных ниже атрибутов телефона, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в дополнительных сведениях о добавлении пользователей по одному или массово).)</span><span class="sxs-lookup"><span data-stu-id="965d3-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="965d3-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="965d3-174">OfficePhone</span></span>
- <span data-ttu-id="965d3-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="965d3-175">HomePhone</span></span>
- <span data-ttu-id="965d3-176">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="965d3-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="965d3-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="965d3-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="965d3-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="965d3-178">OtherTelephone</span></span>

<span data-ttu-id="965d3-179">Для ввода расширения в поле номера телефона пользователя требуется формат *+ \<phone number> ;ext= \<extension>* или *+ \<phone number> ;x. \<extension>*</span><span class="sxs-lookup"><span data-stu-id="965d3-179">The required format to enter the extension in the user phone number field is either *+\<phone number>;ext=\<extension>* or *+\<phone number>;x\<extension>*.</span></span>
<span data-ttu-id="965d3-180">Пример: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678".</span><span class="sxs-lookup"><span data-stu-id="965d3-180">Example: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678".</span></span>

<span data-ttu-id="965d3-181">Расширение можно настроить в Центре администрирования [Microsoft 365](https://admin.microsoft.com/) или [Центре администрирования Azure Active Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="965d3-181">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="965d3-182">Для того чтобы изменения были доступны автоотводам и очередям вызовов, может занять до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="965d3-182">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="965d3-183">Если вы хотите использовать  функции  "Набрать по имени" и "Набрать по расширению", назначьте ему клавишу набора для основного автозавода, чтобы связаться с автозаводом, включенным для функции "Набрать по **имени".**</span><span class="sxs-lookup"><span data-stu-id="965d3-183">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="965d3-184">Вы можете назначить клавишу 1 (не связанную с ней буквами), чтобы связаться с автозаводом по набору. </span><span class="sxs-lookup"><span data-stu-id="965d3-184">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="965d3-185">Выбрав параметр поиска в **каталоге,** нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="965d3-185">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="965d3-186">Поток вызовов в нечасовом времени</span><span class="sxs-lookup"><span data-stu-id="965d3-186">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](media/auto-attendant-business-hours.png)

<span data-ttu-id="965d3-188">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="965d3-188">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="965d3-189">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="965d3-189">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="965d3-190">Для работы можно установить перерывы в течение дня, а все часы, которые не считаются часами, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="965d3-190">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="965d3-191">Вы можете настроить другие параметры обработки входящих параметров обработки параметров и приветствий в течение часа.</span><span class="sxs-lookup"><span data-stu-id="965d3-191">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="965d3-192">В зависимости от настройки автозаполнения и очередей звонков может потребоваться настроить маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="965d3-192">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="965d3-193">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="965d3-193">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="965d3-194">Нажмите **кнопку "Добавить новое** время", чтобы указать несколько часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="965d3-194">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="965d3-195">После того как вы указали часы работы, выберите параметры маршрутизов для неавных часов.</span><span class="sxs-lookup"><span data-stu-id="965d3-195">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="965d3-196">Доступны те же параметры, что и для маршрутизов в часы, которые вы указали выше.</span><span class="sxs-lookup"><span data-stu-id="965d3-196">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="965d3-197">Когда **все будет** готово, нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="965d3-197">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="965d3-198">Потоки вызовов во время праздников</span><span class="sxs-lookup"><span data-stu-id="965d3-198">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравительных и праздников](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="965d3-200">Для каждого настроенного праздника автозавод может быть настроен поток [звонка.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="965d3-200">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="965d3-201">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="965d3-201">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="965d3-202">На странице параметров звонка "Праздник" нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="965d3-202">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="965d3-203">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="965d3-203">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="965d3-204">В **выпадаемом** окнах "Праздники" выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="965d3-204">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="965d3-205">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="965d3-205">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действия по праздничным звонкам](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="965d3-207">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="965d3-207">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="965d3-208">Если вы перенаправили звонок, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="965d3-208">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="965d3-209">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="965d3-209">Click **Save**.</span></span>

![Снимок экрана: параметры праздников со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="965d3-211">Повторите процедуру для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="965d3-211">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="965d3-212">После того как вы добавите все праздники, нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="965d3-212">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="965d3-213">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="965d3-213">Dial scope</span></span>

![Снимок экрана: область набора номера с вариантами "Включить" и "Исключить"](media/auto-attendant-dial-scope.png)

<span data-ttu-id="965d3-215">Область *набора определяет* пользователей, доступных в каталоге, если звоня по имени или по телефону.</span><span class="sxs-lookup"><span data-stu-id="965d3-215">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="965d3-216">По умолчанию **для** всех сетевых пользователей входят все пользователи в организации, которые являются пользователями Online с лицензией на телефонную систему или локально с использованием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="965d3-216">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="965d3-217">Вы можете включить или исключить  определенных  пользователей, выбрав пользовательскую группу в группе "Включить" или **"Исключить"** и выбрав одну или несколько групп Microsoft 365, списки рассылки или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="965d3-217">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="965d3-218">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="965d3-218">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="965d3-219">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="965d3-219">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="965d3-220">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="965d3-220">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="965d3-221">После настройки области набора номера нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="965d3-221">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="965d3-222">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="965d3-222">Resource accounts</span></span>

<span data-ttu-id="965d3-223">У всех автосуммников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="965d3-223">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="965d3-224">Автослужбу первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="965d3-224">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="965d3-225">При желании вы можете назначить автозаводу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="965d3-225">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетных записей для учетной записи ресурса](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="965d3-227">Чтобы добавить учетную запись ресурса, нажмите кнопку **"Добавить** учетную запись" и найдите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="965d3-227">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="965d3-228">Нажмите **кнопку "Добавить"** и выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="965d3-228">Click **Add**, and then click **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="965d3-230">Завершив добавление учетных записей служб, нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="965d3-230">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="965d3-231">В этом случае будет завершена настройка автоотполнеющего персонала.</span><span class="sxs-lookup"><span data-stu-id="965d3-231">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="965d3-232">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="965d3-232">External phone number transfers - technical details</span></span>

<span data-ttu-id="965d3-233">Чтобы разрешить [](plan-auto-attendant-call-queue.md#prerequisites) автоответам переводить звонки внешним пользователям, обратитесь к необходимым условиям.</span><span class="sxs-lookup"><span data-stu-id="965d3-233">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="965d3-234">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="965d3-234">In addition:</span></span>

- <span data-ttu-id="965d3-235">Для учетной записи ресурса с номером плана звонков номер телефона для внешнего переноса должен быть введен в формате E.164 (+[код страны][код города][номер телефона]). [](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="965d3-235">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="965d3-236">Для учетной записи ресурса с прямым маршрутным номером внешний формат [](direct-routing-connect-the-sbc.md) номера телефона для передачи зависит от параметров граничного контроллера сеанса.</span><span class="sxs-lookup"><span data-stu-id="965d3-236">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="965d3-237">Отображаемая исходящие телефонные номера определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="965d3-237">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="965d3-238">Для номеров планов звонков отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="965d3-238">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="965d3-239">Для прямых номеров маршрутов число отправленных основано на параметре P-Утвердилось-Identity (PAI) в SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="965d3-239">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="965d3-240">Если установлено отключение, отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="965d3-240">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="965d3-241">Это значение задается по умолчанию и рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="965d3-241">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="965d3-242">Если установлено "Включено", отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="965d3-242">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="965d3-243">В гибридной среде Skype для бизнеса создайте нового локального пользователя с настроенной для переадстройки звонков номером ПС.</span><span class="sxs-lookup"><span data-stu-id="965d3-243">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="965d3-244">Пользователю должно быть включено Корпоративная голосовая связь и ему назначена голосовая политика.</span><span class="sxs-lookup"><span data-stu-id="965d3-244">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="965d3-245">Дополнительные узнать см. в перенастройке [автоза передачи вызовов в ПСОП.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="965d3-245">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="965d3-246">Создание автозавода с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="965d3-246">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="965d3-247">Вы также можете использовать PowerShell для создания и создания автоотетарей.</span><span class="sxs-lookup"><span data-stu-id="965d3-247">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="965d3-248">Ниже статисты, необходимые для управления автозаправщиком.</span><span class="sxs-lookup"><span data-stu-id="965d3-248">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="965d3-249">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="965d3-249">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="965d3-250">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="965d3-250">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="965d3-251">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="965d3-251">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="965d3-252">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="965d3-252">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="965d3-253">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="965d3-253">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="965d3-254">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="965d3-254">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="965d3-255">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="965d3-255">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="965d3-256">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="965d3-256">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="965d3-257">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="965d3-257">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="965d3-258">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="965d3-258">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="965d3-259">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="965d3-259">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="965d3-260">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="965d3-260">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="965d3-261">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="965d3-261">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="965d3-262">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="965d3-262">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="965d3-263">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="965d3-263">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="965d3-264">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="965d3-264">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="965d3-265">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="965d3-265">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="965d3-266">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="965d3-266">Related topics</span></span>

[<span data-ttu-id="965d3-267">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="965d3-267">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="965d3-268">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="965d3-268">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="965d3-269">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="965d3-269">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="965d3-270">Пример для малого бизнеса: настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="965d3-270">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="965d3-271">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="965d3-271">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
