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
description: Узнайте, как настроить и протестировать автоотводников для Microsoft Teams.
ms.openlocfilehash: 2aef87d1a7885df01b02a5708ac1079ea8021add
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498794"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="b9356-103">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="b9356-103">Set up an auto attendant</span></span>

<span data-ttu-id="b9356-104">Автозаверяющие могут звонить в вашу организацию и переходить в систему меню, чтобы поговорить с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="b9356-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="b9356-105">Вы можете создавать автоотводы для своей организации с помощью Microsoft Teams центра администрирования или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9356-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="b9356-106">Прежде чем выполнять действия, которые вы выполните в этой [](plan-auto-attendant-call-queue.md#getting-started) [статье, ознакомьтесь](plan-auto-attendant-call-queue.md) со статьей Планирование работы с Teams и очередей вызовов и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="b9356-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="b9356-107">Автоответчики могут перенаправить звонки в одно из следующих расположений: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="b9356-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="b9356-108">**Оператор** — оператор, определенный для автозавода.</span><span class="sxs-lookup"><span data-stu-id="b9356-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="b9356-109">Определение оператора необязательно.</span><span class="sxs-lookup"><span data-stu-id="b9356-109">Defining an operator is optional.</span></span> <span data-ttu-id="b9356-110">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="b9356-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="b9356-111">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="b9356-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="b9356-112">Этот пользователь может быть пользователем в Интернете или локально, используя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9356-112">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="b9356-113">**Голосовое приложение** — другой автозаводщик или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="b9356-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="b9356-114">(Выберите учетную запись ресурса, связанную с автозаправлением или очередью вызовов при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="b9356-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="b9356-115">**Голосовая почта** — почтовый ящик голосовой почты, связанный с Microsoft 365 группой, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="b9356-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="b9356-116">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="b9356-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="b9356-117">(См. [технические сведения о внешнем переносе](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="b9356-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="b9356-118">**Объявление (звуковой файл)** — воспроизведения звукового файла.</span><span class="sxs-lookup"><span data-stu-id="b9356-118">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="b9356-119">Добавленное сообщение с объявлением, сохраненное как звуковое. WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="b9356-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="b9356-120">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="b9356-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="b9356-121">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="b9356-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="b9356-122">**Объявление (тип)** — введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="b9356-122">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="b9356-123">Текст, который должна читать система.</span><span class="sxs-lookup"><span data-stu-id="b9356-123">Text you want the system to read.</span></span> <span data-ttu-id="b9356-124">Можно ввести до 1000 символов.</span><span class="sxs-lookup"><span data-stu-id="b9356-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="b9356-125">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="b9356-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="b9356-126">При этом вам будет предложено выбрать один из этих параметров на разных этапах настройки автозаказа.</span><span class="sxs-lookup"><span data-stu-id="b9356-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

> [!NOTE]
> <span data-ttu-id="b9356-127">При выборе пункта назначения голосовой почты доступны два дополнительных параметра:</span><span class="sxs-lookup"><span data-stu-id="b9356-127">When choosing Voicemail as a destination, two additional options are available:</span></span>
> - <span data-ttu-id="b9356-128">**Транскрибация** (по умолчанию: Выключено) — если включена, голосовое сообщение будет расшифровка и включено в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b9356-128">**Transcription** (Default: Off) - when enabled, the voicemail message will be transcribed and included as part of the email.</span></span>
> - <span data-ttu-id="b9356-129">**Отключить приветствие** (по умолчанию: Выключит). Если эта возможность включена, стандартное системное сообщение "Пожалуйста, оставьте сообщение после тона.</span><span class="sxs-lookup"><span data-stu-id="b9356-129">**Suppress Greeting** (Default: Off) - when enabled, the standard system message "Please leave a message after the tone.</span></span> <span data-ttu-id="b9356-130">Когда вы закончите, повесь трубку или нажмите клавишу с hash, чтобы параметров больше".</span><span class="sxs-lookup"><span data-stu-id="b9356-130">When you have finished please hang up or press the hash key for more options."</span></span> <span data-ttu-id="b9356-131">будет подавляться.</span><span class="sxs-lookup"><span data-stu-id="b9356-131">will be suppressed.</span></span>

<span data-ttu-id="b9356-132">Чтобы настроить автозавод, в Центре администрирования Teams Разорите **голосовую** обработку , выберите Автособратники **,** а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9356-132">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b9356-133">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="b9356-133">Video demonstration</span></span>

<span data-ttu-id="b9356-134">В этом видеоролике показан простой пример создания автозавода в Teams.</span><span class="sxs-lookup"><span data-stu-id="b9356-134">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="b9356-135">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="b9356-135">General info</span></span>

![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="b9356-137">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="b9356-137">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="b9356-138">Чтобы назначить оператора, укажите место назначения для звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="b9356-138">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="b9356-139">Это необязательный (но рекомендуемый вариант).</span><span class="sxs-lookup"><span data-stu-id="b9356-139">This designation is optional (but recommended).</span></span> <span data-ttu-id="b9356-140">Установите параметр **Оператор,** чтобы разрешить вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="b9356-140">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="b9356-141">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="b9356-141">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="b9356-142">Часовой пояс используется для вычисления рабочих часов, если вы создаете отдельный поток [зовов в не часах.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="b9356-142">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="b9356-143">Укажите [поддерживаемый язык](create-a-phone-system-auto-attendant-languages.md) для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="b9356-143">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="b9356-144">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="b9356-144">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="b9356-145">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="b9356-145">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="b9356-146">Если этот параметр включен, имя каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="b9356-146">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="b9356-147">Например, можно сказать "Один" для выбора параметра меню, назначенного клавише 1, или "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="b9356-147">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="b9356-148">Если на шаге 4 выбрать язык, который не поддерживает голосовой ввод, этот параметр будет отключен.</span><span class="sxs-lookup"><span data-stu-id="b9356-148">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="b9356-149">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9356-149">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="b9356-150">Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="b9356-150">Call flow</span></span>

![Снимок экрана: параметры приветствия сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="b9356-152">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="b9356-152">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="b9356-153">Если вы **выберете "Звукозапись",** с помощью Upload файла можно добавить записанное приветствие, сохраненное в качестве звукового файла.  WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="b9356-153">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="b9356-154">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="b9356-154">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="b9356-155">Если выбрать **Введите приветствие,** система будет читать текст, который вы введите (до 1000 символов), когда автозавет ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="b9356-155">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутизов параметров маршрутизов](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="b9356-157">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="b9356-157">Choose how you want to route the call.</span></span>

<span data-ttu-id="b9356-158">Если вы **выберете Отключить,** автозаводщик повесит вызов.</span><span class="sxs-lookup"><span data-stu-id="b9356-158">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="b9356-159">Если вы выбрали **Перенаправить** звонок , вы можете выбрать одно из назначений маршрутиации зовов.</span><span class="sxs-lookup"><span data-stu-id="b9356-159">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="b9356-160">Если вы выбрали **Параметры меню**  Воспроизведения, вы  можете выбрать вариант Воспроизведения звукового файла или Ввести приветствие, а затем выбрать параметры меню и поиск по каталогу.</span><span class="sxs-lookup"><span data-stu-id="b9356-160">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="b9356-161">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="b9356-161">Menu options</span></span>

![Снимок экрана: параметры набора клавиш](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="b9356-163">Для настройки параметров набора назначьте 0–9 клавиш на телефонной клавиатуре одному из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="b9356-163">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="b9356-164">(Клавиши \* (Повтор) и (Назад) зарезервированы системой и не \# могут быть перена назначены.)</span><span class="sxs-lookup"><span data-stu-id="b9356-164">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="b9356-165">Сопоставления ключей не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="b9356-165">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="b9356-166">Можно создать меню с клавишами 0, 1 и 3, относясь к параметрам, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="b9356-166">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="b9356-167">Если вы настроили этот оператор, рекомендуем соендировать с оператором нулевые клавиши.</span><span class="sxs-lookup"><span data-stu-id="b9356-167">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="b9356-168">Если оператор не назначен ни одной клавише, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="b9356-168">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="b9356-169">Для каждого параметра меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b9356-169">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="b9356-170">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="b9356-170">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="b9356-171">Если доступны голосовые данные, для доступа к параметру вызываемая почта также может навести этот номер.</span><span class="sxs-lookup"><span data-stu-id="b9356-171">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="b9356-172">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включены голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="b9356-172">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="b9356-173">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Операции и причины".</span><span class="sxs-lookup"><span data-stu-id="b9356-173">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="b9356-174">Например, можно нажать клавишу 2, сказать "два" или "Продажи", чтобы выбрать параметр, выбранный с двумя ключами.</span><span class="sxs-lookup"><span data-stu-id="b9356-174">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="b9356-175">Этот текст также отрисовывания текста в речь при запросе подтверждения службы, который может выглядеть так: "Перена передаче звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="b9356-175">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="b9356-176">**Redirect to** (Перенаправление на) — пункт назначения маршрутиации пунктов перенаправления пунктов, используемых при выборе этого параметра.</span><span class="sxs-lookup"><span data-stu-id="b9356-176">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="b9356-177">Если вы перенаправляете учетную запись к автозаправщику или очереди вызовов, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b9356-177">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="b9356-178">Поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="b9356-178">Directory search</span></span>

<span data-ttu-id="b9356-179">При назначении пунктов назначениям набираемой клавиши рекомендуется выбрать **вариант Нет** для **поиска по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="b9356-179">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="b9356-180">Если звоняющий пытается набрать имя или расширение с помощью клавиш, которые назначены определенным пунктам назначения, он может быть неожиданно перенаправлен в определенное место, прежде чем вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="b9356-180">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="b9356-181">Мы рекомендуем создать отдельный автозаводщик для поиска по каталогу и связаться с ним с помощью клавиши набора номера.</span><span class="sxs-lookup"><span data-stu-id="b9356-181">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="b9356-182">Если вы не назначили клавиши набора номера, выберите параметр поиска по **каталогу**.</span><span class="sxs-lookup"><span data-stu-id="b9356-182">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="b9356-183">**Набрать номер по** имени. Если этот параметр включить, вызыватели смогут ввести имя пользователя или ввести его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="b9356-183">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="b9356-184">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора по имени.</span><span class="sxs-lookup"><span data-stu-id="b9356-184">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="b9356-185">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="b9356-185">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="b9356-186">**Набрать номер по расширению.** Если вы встроите этот параметр, вызывающие пользователи смогут связываться с пользователями в организации, набрав их расширения для телефона.</span><span class="sxs-lookup"><span data-stu-id="b9356-186">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="b9356-187">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора по **расширению**.</span><span class="sxs-lookup"><span data-stu-id="b9356-187">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="b9356-188">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="b9356-188">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="b9356-189">Для пользователей, которые вы хотите сделать доступными для расширения "Набор номера", необходимо добавить расширение, как часть одного [](/microsoft-365/admin/add-users/add-users) из следующих атрибутов телефонов, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в документе Добавление пользователей по одному или массово).)</span><span class="sxs-lookup"><span data-stu-id="b9356-189">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="b9356-190">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="b9356-190">OfficePhone</span></span>
- <span data-ttu-id="b9356-191">HomePhone</span><span class="sxs-lookup"><span data-stu-id="b9356-191">HomePhone</span></span>
- <span data-ttu-id="b9356-192">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="b9356-192">Mobile/MobilePhone</span></span>
- <span data-ttu-id="b9356-193">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="b9356-193">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="b9356-194">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="b9356-194">OtherTelephone</span></span>

<span data-ttu-id="b9356-195">Формат, требуемого для ввода расширения в поле номера телефона пользователя, может иметь один из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="b9356-195">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="b9356-196">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="b9356-196">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="b9356-197">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="b9356-197">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="b9356-198">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="b9356-198">*x\<extension>*</span></span>

- <span data-ttu-id="b9356-199">Пример 1. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="b9356-199">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="b9356-200">Пример 2. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="b9356-200">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="b9356-201">Пример 3. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="b9356-201">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="b9356-202">Вы можете установить расширение в центре администрирования [Microsoft 365](https://admin.microsoft.com/) или Azure Active Directory [центре администрирования](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b9356-202">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="b9356-203">Изменения, внесенные автоследникам и очередям вызовов, могут быть доступны в течение 12 часов.</span><span class="sxs-lookup"><span data-stu-id="b9356-203">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="b9356-204">Если вы хотите использовать  функции  "Набрать по имени" и "Набрать по расширению", назначьте клавишу набора главному автозаводители, чтобы связаться с автозаводом, включенным для функции "Набрать по **имени".**</span><span class="sxs-lookup"><span data-stu-id="b9356-204">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="b9356-205">В пределах этого автозавода вы можете назначить 1-й  ключ (без букв), чтобы связаться с автозаводом для набора номера по расширению.</span><span class="sxs-lookup"><span data-stu-id="b9356-205">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="b9356-206">Выбрав параметр поиска по **каталогу, выберите** **Далее.**</span><span class="sxs-lookup"><span data-stu-id="b9356-206">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="b9356-207">Поток вызовов в нечасовом времени</span><span class="sxs-lookup"><span data-stu-id="b9356-207">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](media/auto-attendant-business-hours.png)

<span data-ttu-id="b9356-209">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="b9356-209">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="b9356-210">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="b9356-210">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="b9356-211">В течение дня можно настроить часы работы с перерывом, а все часы, которые не считаются неавтными, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="b9356-211">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="b9356-212">Вы можете настроить различные параметры обработки входящих параметров обработки параметров звонка и приветствия в течение часа.</span><span class="sxs-lookup"><span data-stu-id="b9356-212">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="b9356-213">В зависимости от настройки автозаполнения и очередей звонков может потребоваться указать маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="b9356-213">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="b9356-214">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="b9356-214">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="b9356-215">Выберите **Добавить новое время,** чтобы указать несколько наборов часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="b9356-215">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="b9356-216">После того как вы указали часы работы, выберите параметры маршрутизов параметров для неавтных часов.</span><span class="sxs-lookup"><span data-stu-id="b9356-216">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="b9356-217">Доступны те же параметры, что и для маршрутизов в часы работы, которые вы указали выше.</span><span class="sxs-lookup"><span data-stu-id="b9356-217">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="b9356-218">Когда **все будет готово,** выберите Далее.</span><span class="sxs-lookup"><span data-stu-id="b9356-218">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="b9356-219">Потоки вызовов во время праздников</span><span class="sxs-lookup"><span data-stu-id="b9356-219">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравительных и праздничных приветствий](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="b9356-221">Для каждого настроенного праздника ваш автозаводщик может использовать поток [вызовов.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b9356-221">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="b9356-222">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b9356-222">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="b9356-223">На странице параметров звонка праздников выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9356-223">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="b9356-224">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="b9356-224">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="b9356-225">В области **Праздник** выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="b9356-225">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="b9356-226">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="b9356-226">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действий по праздничным звонкам](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="b9356-228">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="b9356-228">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="b9356-229">Если вы выбрали перенаправление, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="b9356-229">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="b9356-230">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9356-230">Select **Save**.</span></span>

![Снимок экрана: параметры праздников со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="b9356-232">Повторите эти процедуры для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="b9356-232">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="b9356-233">Когда вы добавите все праздники, выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9356-233">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="b9356-234">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="b9356-234">Dial scope</span></span>

![Снимок экрана: область набора номера, включаемая и исключаемая](media/auto-attendant-dial-scope.png)

<span data-ttu-id="b9356-236">Область *набора определяет,* какие пользователи доступны в каталоге, если вызываемая звонок использует по имени или по телефону по расширению.</span><span class="sxs-lookup"><span data-stu-id="b9356-236">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="b9356-237">По умолчанию **все пользователи в** Сети включают всех пользователей в организации, которые являются пользователями Online или которые находятся локально с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9356-237">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="b9356-238">Вы можете включить или исключить определенных  пользователей,  выбрав настраиваемую группу пользователей в группе Включить или Исключить и выбрав одну или несколько групп Microsoft 365, списков рассылки или групп безопасности. </span><span class="sxs-lookup"><span data-stu-id="b9356-238">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="b9356-239">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="b9356-239">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="b9356-240">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="b9356-240">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="b9356-241">Для того чтобы новый пользователь указал свое имя в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="b9356-241">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="b9356-242">После настройки области набора номера выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="b9356-242">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="b9356-243">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="b9356-243">Resource accounts</span></span>

<span data-ttu-id="b9356-244">У всех автозаводников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b9356-244">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="b9356-245">Автослужам первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="b9356-245">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="b9356-246">При желании вы можете назначить автослужбу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="b9356-246">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетных записей для учетных записей ресурсов](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="b9356-248">Чтобы добавить учетную запись ресурса, выберите **Добавить** учетную запись и найщите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="b9356-248">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="b9356-249">Выберите **Добавить**, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9356-249">Select **Add**, and then select **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="b9356-251">Завершив добавление учетных записей службы, выберите **Отправить,** чтобы завершить настройку автозаполнеющего.</span><span class="sxs-lookup"><span data-stu-id="b9356-251">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="b9356-252">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="b9356-252">External phone number transfers - technical details</span></span>

<span data-ttu-id="b9356-253">Чтобы разрешить [автоответам](plan-auto-attendant-call-queue.md#prerequisites) переводить звонки за границу, обратитесь к условиям.</span><span class="sxs-lookup"><span data-stu-id="b9356-253">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="b9356-254">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="b9356-254">In addition:</span></span>

- <span data-ttu-id="b9356-255">Для учетной записи ресурса с лицензией на план звонков [номер](calling-plans-for-office-365.md)внешнего переносного телефона должен быть введен в формате E.164 (+[код страны][код города][номер телефона]).</span><span class="sxs-lookup"><span data-stu-id="b9356-255">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="b9356-256">Для учетной записи ресурса с лицензией телефонная система и политикой прямой маршрутистики в Интернете формат номера внешнего переносимого телефона зависит от параметров [SBC.](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="b9356-256">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="b9356-257">Отображаемая исходящие телефонные номера определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b9356-257">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="b9356-258">Для номеров планов звонков отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="b9356-258">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="b9356-259">Для номеров прямой маршрутификации количество отправленных номеров основано на параметре P-Изучаемого удостоверения (PAI) в SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b9356-259">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="b9356-260">Если за установлено отключение, отображается исходный номер телефона звонивого.</span><span class="sxs-lookup"><span data-stu-id="b9356-260">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="b9356-261">Этот параметр рекомендуется использовать по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9356-261">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="b9356-262">Если включено, отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b9356-262">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="b9356-263">В гибридной Skype для бизнеса для перевода вызова автоотехнщика в ПСОП создайте нового локального пользователя с переадпорязающими звонками номером ПСОП.</span><span class="sxs-lookup"><span data-stu-id="b9356-263">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="b9356-264">Пользователь должен быть включен для Корпоративная голосовая связь и иметь назначенную голосовую политику.</span><span class="sxs-lookup"><span data-stu-id="b9356-264">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="b9356-265">Дополнительные узнать об этом можно [в](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)этой теме.</span><span class="sxs-lookup"><span data-stu-id="b9356-265">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="b9356-266">Создание автозавода с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9356-266">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="b9356-267">Вы также можете использовать PowerShell для создания и создания автоотехов.</span><span class="sxs-lookup"><span data-stu-id="b9356-267">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="b9356-268">Ниже статисты, необходимые для управления автозаправщиком.</span><span class="sxs-lookup"><span data-stu-id="b9356-268">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="b9356-269">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b9356-269">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="b9356-270">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b9356-270">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="b9356-271">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b9356-271">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="b9356-272">Get-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="b9356-272">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="b9356-273">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b9356-273">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="b9356-274">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="b9356-274">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="b9356-275">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="b9356-275">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="b9356-276">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="b9356-276">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="b9356-277">Export-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="b9356-277">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="b9356-278">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="b9356-278">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="b9356-279">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="b9356-279">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="b9356-280">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="b9356-280">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="b9356-281">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="b9356-281">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="b9356-282">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="b9356-282">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="b9356-283">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="b9356-283">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="b9356-284">Import-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="b9356-284">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="b9356-285">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="b9356-285">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="b9356-286">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b9356-286">Related topics</span></span>

[<span data-ttu-id="b9356-287">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="b9356-287">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b9356-288">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="b9356-288">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="b9356-289">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="b9356-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b9356-290">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b9356-290">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
