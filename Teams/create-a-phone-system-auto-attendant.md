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
description: Узнайте, как настроить и протестировать автоотводников для крупных организаций в Microsoft Teams.
ms.openlocfilehash: 270a2e613e387b797cb70914ad400da80b15b1ca
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628948"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="85124-103">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="85124-103">Set up an auto attendant</span></span>

<span data-ttu-id="85124-104">Автозаверяющие могут звонить в вашу организацию и переходить в систему меню, чтобы поговорить с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="85124-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="85124-105">Вы можете создавать автоспутники в центре администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85124-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

> [!TIP]
> <span data-ttu-id="85124-106">Эта статья посвящена крупным организациям.</span><span class="sxs-lookup"><span data-stu-id="85124-106">This article is large organizations.</span></span> <span data-ttu-id="85124-107">Если ваша организация является мастером по организации, ознакомьтесь с учебным учебником Настройка автозавода [для малого](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) бизнеса.</span><span class="sxs-lookup"><span data-stu-id="85124-107">If your organization is a smaall business, read [Set up an auto attendant - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) instead.</span></span>

<span data-ttu-id="85124-108">Прежде чем выполнять действия, которые вы выполните в этой [](plan-auto-attendant-call-queue.md#getting-started) [статье, ознакомьтесь](plan-auto-attendant-call-queue.md) со статьей Планирование работы с Teams и очередей вызовов и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="85124-108">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="85124-109">Автоответчики могут перенаправить звонки в одно из следующих расположений: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="85124-109">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="85124-110">**Оператор** — оператор, определенный для автозавода.</span><span class="sxs-lookup"><span data-stu-id="85124-110">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="85124-111">Определение оператора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="85124-111">Defining an operator is optional.</span></span> <span data-ttu-id="85124-112">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="85124-112">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="85124-113">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="85124-113">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="85124-114">Этот пользователь может быть пользователем в Интернете или локально, используя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="85124-114">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="85124-115">**Голосовое приложение** — другой автозаводщик или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="85124-115">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="85124-116">(Выберите учетную запись ресурса, связанную с автозаправлением или очередью вызовов при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="85124-116">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="85124-117">**Голосовая почта** — почтовый ящик голосовой почты, связанный с Microsoft 365 группой, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="85124-117">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="85124-118">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="85124-118">**External phone number** - any phone number.</span></span> <span data-ttu-id="85124-119">(См. [технические сведения о внешнем переносе](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="85124-119">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="85124-120">**Объявление (звуковой файл)** — воспроизведения звукового файла.</span><span class="sxs-lookup"><span data-stu-id="85124-120">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="85124-121">Добавленное сообщение с объявлением, сохраненное как звуковое. WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="85124-121">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="85124-122">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="85124-122">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="85124-123">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="85124-123">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="85124-124">**Объявление (тип)** — введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="85124-124">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="85124-125">Текст, который должна читать система.</span><span class="sxs-lookup"><span data-stu-id="85124-125">Text you want the system to read.</span></span> <span data-ttu-id="85124-126">Можно ввести до 1000 символов.</span><span class="sxs-lookup"><span data-stu-id="85124-126">You can enter up to 1000 characters.</span></span> <span data-ttu-id="85124-127">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="85124-127">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="85124-128">При этом вам будет предложено выбрать один из этих параметров на разных этапах настройки автозаказа.</span><span class="sxs-lookup"><span data-stu-id="85124-128">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

> [!NOTE]
> <span data-ttu-id="85124-129">При выборе пункта назначения голосовой почты доступны два дополнительных параметра:</span><span class="sxs-lookup"><span data-stu-id="85124-129">When choosing Voicemail as a destination, two additional options are available:</span></span>
> - <span data-ttu-id="85124-130">**Транскрибация** (по умолчанию: Выключено) — если включена, голосовое сообщение будет расшифровка и включено в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="85124-130">**Transcription** (Default: Off) - when enabled, the voicemail message will be transcribed and included as part of the email.</span></span>
> - <span data-ttu-id="85124-131">**Отключить приветствие** (по умолчанию: Выключит). Если эта возможность включена, стандартное системное сообщение "Пожалуйста, оставьте сообщение после тона.</span><span class="sxs-lookup"><span data-stu-id="85124-131">**Suppress Greeting** (Default: Off) - when enabled, the standard system message "Please leave a message after the tone.</span></span> <span data-ttu-id="85124-132">Когда вы закончите, повесь трубку или нажмите клавишу с hash, чтобы параметров больше".</span><span class="sxs-lookup"><span data-stu-id="85124-132">When you have finished please hang up or press the hash key for more options."</span></span> <span data-ttu-id="85124-133">будет подавляться.</span><span class="sxs-lookup"><span data-stu-id="85124-133">will be suppressed.</span></span>

<span data-ttu-id="85124-134">Чтобы настроить автозавод, в Центре администрирования Teams Разорите **голосовую** обработку , выберите Автособратники **,** а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="85124-134">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="85124-135">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="85124-135">Video demonstration</span></span>

<span data-ttu-id="85124-136">В этом видеоролике показан простой пример создания автозавода в Teams.</span><span class="sxs-lookup"><span data-stu-id="85124-136">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="85124-137">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="85124-137">General info</span></span>

![Снимок экрана: параметры автозавода для ввода имени, оператора, часового пояса, языка и голосового ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="85124-139">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="85124-139">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="85124-140">Чтобы назначить оператора, укажите место назначения для звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="85124-140">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="85124-141">Это необязательный (но рекомендуемый вариант).</span><span class="sxs-lookup"><span data-stu-id="85124-141">This designation is optional (but recommended).</span></span> <span data-ttu-id="85124-142">Установите параметр **Оператор,** чтобы разрешить вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="85124-142">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="85124-143">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="85124-143">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="85124-144">Часовой пояс используется для вычисления рабочих часов, если вы создаете отдельный поток [зовов в не часах.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="85124-144">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="85124-145">Укажите [поддерживаемый язык](create-a-phone-system-auto-attendant-languages.md) для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="85124-145">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="85124-146">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="85124-146">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="85124-147">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="85124-147">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="85124-148">Если этот параметр включен, имя каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="85124-148">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="85124-149">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="85124-149">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="85124-150">Если на шаге 4 выбрать язык, который не поддерживает голосовой ввод, этот параметр будет отключен.</span><span class="sxs-lookup"><span data-stu-id="85124-150">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="85124-151">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85124-151">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="85124-152">Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="85124-152">Call flow</span></span>

![Снимок экрана: параметры приветствия сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="85124-154">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="85124-154">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="85124-155">Если вы выбрали **"Воспроизведения звукового** файла", с помощью Upload файла можно добавить записанное приветствие, сохраненное как звуковое.  WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="85124-155">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="85124-156">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="85124-156">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="85124-157">Если выбрать **Введите приветствие,** система будет читать текст, который вы введите (до 1000 символов), когда автозавет ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="85124-157">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутизов параметров маршрутизов](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="85124-159">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="85124-159">Choose how you want to route the call.</span></span>

<span data-ttu-id="85124-160">Если вы **выберете Отключить,** автозаводщик повесит вызов.</span><span class="sxs-lookup"><span data-stu-id="85124-160">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="85124-161">Если вы выбрали **Перенаправить** звонок , вы можете выбрать одно из назначений маршрутиации зовов.</span><span class="sxs-lookup"><span data-stu-id="85124-161">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="85124-162">Если вы выбрали **Параметры меню**  Воспроизведения, вы  можете выбрать вариант Воспроизведения звукового файла или Ввести приветствие, а затем выбрать параметры меню и поиск по каталогу.</span><span class="sxs-lookup"><span data-stu-id="85124-162">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="85124-163">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="85124-163">Menu options</span></span>

![Снимок экрана: параметры набора клавиш](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="85124-165">Для настройки параметров набора назначьте 0–9 клавиш на телефонной клавиатуре одному из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="85124-165">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="85124-166">(Клавиши \* (Повтор) и (Назад) зарезервированы системой и не \# могут быть перена назначены.)</span><span class="sxs-lookup"><span data-stu-id="85124-166">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="85124-167">Сопоставления ключей не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="85124-167">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="85124-168">Можно создать меню с клавишами 0, 1 и 3, относясь к параметрам, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="85124-168">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="85124-169">Мы рекомендуем сопоставление нулевого ключа с оператором, если вы его настроили.</span><span class="sxs-lookup"><span data-stu-id="85124-169">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="85124-170">Если оператор не назначен ни одной клавише, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="85124-170">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="85124-171">Для каждого параметра меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="85124-171">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="85124-172">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="85124-172">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="85124-173">Если доступны голосовые данные, для доступа к параметру вызываемая почта также может навести этот номер.</span><span class="sxs-lookup"><span data-stu-id="85124-173">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="85124-174">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включены голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="85124-174">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="85124-175">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Операции и причины".</span><span class="sxs-lookup"><span data-stu-id="85124-175">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="85124-176">Например, можно нажать клавишу 2, сказать "два" или "Продажи", чтобы выбрать параметр, который будет соекупно с двумя ключами.</span><span class="sxs-lookup"><span data-stu-id="85124-176">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="85124-177">Этот текст также отрисовывания текста в речь при запросе подтверждения службы, который может выглядеть так: "Перена передаче звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="85124-177">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="85124-178">**Redirect to** (Перенаправление на) — пункт назначения маршрутиации пунктов перенаправления пунктов, используемых при выборе этого параметра.</span><span class="sxs-lookup"><span data-stu-id="85124-178">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="85124-179">Если вы перенаправляете учетную запись к автозаправщику или очереди вызовов, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="85124-179">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="85124-180">Поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="85124-180">Directory search</span></span>

<span data-ttu-id="85124-181">При назначении пунктов назначения набираемых клавиш рекомендуется выбрать **вариант Нет** для поиска **по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="85124-181">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="85124-182">Если звоняющий пытается набрать имя или расширение с помощью клавиш, которые назначены определенным пунктам назначения, он может быть неожиданно перенаправлен в определенное место, прежде чем вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="85124-182">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="85124-183">Мы рекомендуем создать отдельный автозаводщик для поиска по каталогу и связаться с ним с помощью клавиши набора номера.</span><span class="sxs-lookup"><span data-stu-id="85124-183">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="85124-184">Если вы не назначили клавиши набора номера, выберите параметр поиска по **каталогу**.</span><span class="sxs-lookup"><span data-stu-id="85124-184">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="85124-185">**Набрать номер по** имени. Если этот параметр включить, звоня люди смогут ввести имя пользователя или ввести его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="85124-185">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="85124-186">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="85124-186">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="85124-187">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="85124-187">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="85124-188">**Набрать номер по расширению.** Если вы встроите этот параметр, вызывающие пользователи смогут связываться с пользователями в организации, набрав их расширения для телефона.</span><span class="sxs-lookup"><span data-stu-id="85124-188">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="85124-189">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора по **расширению**.</span><span class="sxs-lookup"><span data-stu-id="85124-189">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="85124-190">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="85124-190">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="85124-191">Для пользователей, которые вы хотите сделать доступными для расширения "Набор номера", необходимо добавить расширение, как часть одного [](/microsoft-365/admin/add-users/add-users) из следующих атрибутов телефонов, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в документе Добавление пользователей по одному или массово.)</span><span class="sxs-lookup"><span data-stu-id="85124-191">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="85124-192">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="85124-192">OfficePhone</span></span>
- <span data-ttu-id="85124-193">HomePhone</span><span class="sxs-lookup"><span data-stu-id="85124-193">HomePhone</span></span>
- <span data-ttu-id="85124-194">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="85124-194">Mobile/MobilePhone</span></span>
- <span data-ttu-id="85124-195">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="85124-195">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="85124-196">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="85124-196">OtherTelephone</span></span>

<span data-ttu-id="85124-197">Формат, требуемого для ввода расширения в поле номера телефона пользователя, может иметь один из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="85124-197">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="85124-198">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="85124-198">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="85124-199">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="85124-199">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="85124-200">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="85124-200">*x\<extension>*</span></span>

- <span data-ttu-id="85124-201">Пример 1. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="85124-201">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="85124-202">Пример 2. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="85124-202">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="85124-203">Пример 3. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="85124-203">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="85124-204">Расширение можно настроить в центре администрирования [Microsoft 365](https://admin.microsoft.com/) или Azure Active Directory [центре администрирования](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="85124-204">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="85124-205">Изменения, внесенные автоследникам и очередям вызовов, могут быть доступны в течение 12 часов.</span><span class="sxs-lookup"><span data-stu-id="85124-205">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="85124-206">Если вы хотите использовать  функции  "Набрать по имени" и "Набрать по расширению", назначьте клавишу набора главному автозаводители, чтобы связаться с автозаводом, включенным для функции "Набрать по **имени".**</span><span class="sxs-lookup"><span data-stu-id="85124-206">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="85124-207">В пределах этого автозавода вы можете назначить 1 -клавишу (не связанную с ней буквами), чтобы связаться с автосберегом для набора номера **по расширению.**</span><span class="sxs-lookup"><span data-stu-id="85124-207">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="85124-208">Выбрав параметр поиска по **каталогу, выберите** **Далее.**</span><span class="sxs-lookup"><span data-stu-id="85124-208">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="85124-209">Поток вызовов в нечасовом времени</span><span class="sxs-lookup"><span data-stu-id="85124-209">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](media/auto-attendant-business-hours.png)

<span data-ttu-id="85124-211">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="85124-211">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="85124-212">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="85124-212">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="85124-213">В течение дня можно настроить часы работы с перерывом, а все часы, которые не считаются неавтными, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="85124-213">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="85124-214">Вы можете настроить различные параметры обработки входящих параметров обработки параметров звонка и приветствия в течение часа.</span><span class="sxs-lookup"><span data-stu-id="85124-214">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="85124-215">В зависимости от настройки автозаполнения и очередей звонков может потребоваться указать маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="85124-215">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="85124-216">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="85124-216">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="85124-217">Выберите **Добавить новое время,** чтобы указать несколько наборов часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="85124-217">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="85124-218">После того как вы указали часы работы, выберите параметры маршрутизов параметров для параметров в нечасовом времени.</span><span class="sxs-lookup"><span data-stu-id="85124-218">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="85124-219">Доступны те же параметры, что и для маршрутизов параметров в часы работы, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="85124-219">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="85124-220">Когда **все будет готово,** выберите Далее.</span><span class="sxs-lookup"><span data-stu-id="85124-220">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="85124-221">Потоки вызовов во время праздников</span><span class="sxs-lookup"><span data-stu-id="85124-221">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравительных и праздничных приветствий](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="85124-223">Для каждого настроенного праздника ваш автозаводщик может использовать поток [вызовов.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="85124-223">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="85124-224">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="85124-224">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="85124-225">На странице параметров звонка праздников выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="85124-225">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="85124-226">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="85124-226">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="85124-227">В области **Праздник** выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="85124-227">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="85124-228">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="85124-228">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действий по праздничным звонкам](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="85124-230">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="85124-230">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="85124-231">Если вы решили перенаправить звонок, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="85124-231">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="85124-232">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="85124-232">Select **Save**.</span></span>

![Снимок экрана: параметры праздников со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="85124-234">Повторите эти процедуры для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="85124-234">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="85124-235">Когда вы добавите все праздники, выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85124-235">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="85124-236">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="85124-236">Dial scope</span></span>

![Снимок экрана: область набора номера, включаемая и исключаемая](media/auto-attendant-dial-scope.png)

<span data-ttu-id="85124-238">Область *набора номера* определяет пользователей, доступных в каталоге, если вызываемая звонок использует по имени или по телефону по расширению.</span><span class="sxs-lookup"><span data-stu-id="85124-238">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="85124-239">По умолчанию **все пользователи в** Сети включают всех пользователей в организации, которые являются пользователями Online или которые находятся локально с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="85124-239">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="85124-240">Вы можете включить или исключить определенных  пользователей,  выбрав настраиваемую группу пользователей в группе Включить или Исключить и выбрав одну или несколько групп Microsoft 365, списков рассылки или групп безопасности. </span><span class="sxs-lookup"><span data-stu-id="85124-240">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="85124-241">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="85124-241">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="85124-242">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="85124-242">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="85124-243">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="85124-243">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="85124-244">После настройки области набора номера выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="85124-244">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="85124-245">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="85124-245">Resource accounts</span></span>

<span data-ttu-id="85124-246">У всех автозаводников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="85124-246">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="85124-247">Автослужам первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="85124-247">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="85124-248">При желании вы можете назначить автослужбу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="85124-248">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетных записей для учетных записей ресурса](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="85124-250">Чтобы добавить учетную запись ресурса, выберите **Добавить** учетную запись и найщите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="85124-250">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="85124-251">Выберите **Добавить**, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="85124-251">Select **Add**, and then select **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="85124-253">Завершив добавление учетных записей службы, выберите **Отправить,** чтобы завершить настройку автозаполнеющего.</span><span class="sxs-lookup"><span data-stu-id="85124-253">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="85124-254">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="85124-254">External phone number transfers - technical details</span></span>

<span data-ttu-id="85124-255">Чтобы разрешить [автоответам](plan-auto-attendant-call-queue.md#prerequisites) переводить звонки за границу, обратитесь к условиям.</span><span class="sxs-lookup"><span data-stu-id="85124-255">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="85124-256">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="85124-256">In addition:</span></span>

- <span data-ttu-id="85124-257">Для учетной записи ресурса с лицензией на план звонков [номер](calling-plans-for-office-365.md)внешнего переносного телефона должен быть введен в формате E.164 (+[код страны][код города][номер телефона]).</span><span class="sxs-lookup"><span data-stu-id="85124-257">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="85124-258">Для учетной записи ресурса с лицензией телефонная система и политикой прямой маршрутистики в Интернете формат номера внешнего переносимого телефона зависит от параметров [SBC.](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="85124-258">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="85124-259">Отображаемая исходящие телефонные номера определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="85124-259">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="85124-260">Для номеров планов звонков отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="85124-260">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="85124-261">Для номеров прямой маршрутификации количество отправленных номеров основано на параметре P-Изучаемого удостоверения (PAI) в SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="85124-261">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="85124-262">Если за установлено отключение, отображается исходный номер телефона звонивого.</span><span class="sxs-lookup"><span data-stu-id="85124-262">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="85124-263">Этот параметр рекомендуется использовать по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85124-263">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="85124-264">Если включено, отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="85124-264">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="85124-265">В гибридной Skype для бизнеса для перевода вызова автоотехнщика в ПСОП создайте нового локального пользователя с переадпорязающими звонками номером ПСОП.</span><span class="sxs-lookup"><span data-stu-id="85124-265">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="85124-266">Пользователь должен быть включен для Корпоративная голосовая связь и иметь назначенную голосовую политику.</span><span class="sxs-lookup"><span data-stu-id="85124-266">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="85124-267">Дополнительные узнать об этом можно [в](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)этой теме.</span><span class="sxs-lookup"><span data-stu-id="85124-267">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="85124-268">Создание автозавода с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="85124-268">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="85124-269">Вы также можете использовать PowerShell для создания и создания автоотводников.</span><span class="sxs-lookup"><span data-stu-id="85124-269">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="85124-270">Ниже статисты, необходимые для управления автозаправщиком.</span><span class="sxs-lookup"><span data-stu-id="85124-270">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="85124-271">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="85124-271">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="85124-272">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="85124-272">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="85124-273">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="85124-273">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="85124-274">Get-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="85124-274">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="85124-275">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="85124-275">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="85124-276">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="85124-276">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="85124-277">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="85124-277">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="85124-278">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="85124-278">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="85124-279">Export-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="85124-279">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="85124-280">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="85124-280">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="85124-281">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="85124-281">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="85124-282">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="85124-282">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="85124-283">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="85124-283">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="85124-284">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="85124-284">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="85124-285">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="85124-285">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="85124-286">Import-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="85124-286">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="85124-287">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="85124-287">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="85124-288">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="85124-288">Related topics</span></span>

[<span data-ttu-id="85124-289">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="85124-289">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="85124-290">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="85124-290">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="85124-291">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="85124-291">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="85124-292">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="85124-292">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
