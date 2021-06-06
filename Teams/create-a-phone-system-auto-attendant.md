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
description: Узнайте, как настроить и проверить автоотводщики для крупных организаций в Microsoft Teams.
ms.openlocfilehash: cc4d0de8fd1d6c643f23b6e8215f0f7a343b2a8f
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777809"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="04198-103">Настройка автозавода</span><span class="sxs-lookup"><span data-stu-id="04198-103">Set up an auto attendant</span></span>

<span data-ttu-id="04198-104">Автозаверяющие могут звонить в вашу организацию и переходить в систему меню, чтобы поговорить с нужным отделом, очередью вызовов, человеком или оператором.</span><span class="sxs-lookup"><span data-stu-id="04198-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="04198-105">Вы можете создавать автоотводы для своей организации с помощью Microsoft Teams центра администрирования или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04198-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

> [!TIP]
> <span data-ttu-id="04198-106">Эта статья посвящена крупным организациям.</span><span class="sxs-lookup"><span data-stu-id="04198-106">This article is for large organizations.</span></span> <span data-ttu-id="04198-107">Если ваша организация — малый бизнес, ознакомьтесь с учебным учебником Настройка автозавода [для малого](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) бизнеса.</span><span class="sxs-lookup"><span data-stu-id="04198-107">If your organization is a small business, read [Set up an auto attendant - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) instead.</span></span>

<span data-ttu-id="04198-108">Прежде чем выполнять действия, которые вы выполните в этой [](plan-auto-attendant-call-queue.md#getting-started) [статье, ознакомьтесь](plan-auto-attendant-call-queue.md) со статьей Планирование работы с Teams и очередей вызовов и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="04198-108">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="04198-109">Автоответчики могут перенаправить звонки в одно из следующих расположений: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="04198-109">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="04198-110">**Оператор** — оператор, определенный для автозавода.</span><span class="sxs-lookup"><span data-stu-id="04198-110">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="04198-111">Определение оператора необязательно.</span><span class="sxs-lookup"><span data-stu-id="04198-111">Defining an operator is optional.</span></span> <span data-ttu-id="04198-112">Оператор можно определить как любой другой пункт назначения в этом списке.</span><span class="sxs-lookup"><span data-stu-id="04198-112">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="04198-113">**Человек в организации —** это человек в вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="04198-113">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="04198-114">Этот пользователь может быть пользователем в Интернете или локально, используя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="04198-114">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="04198-115">**Голосовое приложение** — еще один автозаводщик или очередь вызовов.</span><span class="sxs-lookup"><span data-stu-id="04198-115">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="04198-116">(Выберите учетную запись ресурса, связанную с автоотправлением или очередью вызовов при выборе этого назначения.)</span><span class="sxs-lookup"><span data-stu-id="04198-116">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="04198-117">**Голосовая почта** — почтовый ящик голосовой почты, связанный с Microsoft 365 группой, которую вы указали.</span><span class="sxs-lookup"><span data-stu-id="04198-117">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="04198-118">Вы можете выбрать транскрибацию голосовой почты и сообщение "Пожалуйста, оставьте сообщение после сигнала".</span><span class="sxs-lookup"><span data-stu-id="04198-118">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="04198-119">системный запрос.</span><span class="sxs-lookup"><span data-stu-id="04198-119">system prompt.</span></span>
- <span data-ttu-id="04198-120">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="04198-120">**External phone number** - any phone number.</span></span> <span data-ttu-id="04198-121">(См. [технические сведения о внешнем переносе).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="04198-121">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="04198-122">**Объявление (звуковой файл)** — воспроизведения звукового файла.</span><span class="sxs-lookup"><span data-stu-id="04198-122">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="04198-123">Опубликованное сообщение с объявлением, сохраненное как звуковое. WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="04198-123">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="04198-124">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="04198-124">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="04198-125">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="04198-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="04198-126">**Объявление (тип)** — введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="04198-126">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="04198-127">Текст, который должна читать система.</span><span class="sxs-lookup"><span data-stu-id="04198-127">Text you want the system to read.</span></span> <span data-ttu-id="04198-128">Можно ввести до 1000 символов.</span><span class="sxs-lookup"><span data-stu-id="04198-128">You can enter up to 1000 characters.</span></span> <span data-ttu-id="04198-129">Система воспроизводит объявление, а затем возвращается в меню автозапуска.</span><span class="sxs-lookup"><span data-stu-id="04198-129">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="04198-130">При этом вам будет предложено выбрать один из этих параметров на разных этапах настройки автозаказа.</span><span class="sxs-lookup"><span data-stu-id="04198-130">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="04198-131">Чтобы настроить автоотображающий, в Центре администрирования Teams **Разорите голосовую** обработку , выберите Автоотображающие **,** а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="04198-131">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="04198-132">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="04198-132">Video demonstration</span></span>

<span data-ttu-id="04198-133">В этом видео показано, как создать автоотводщик в Teams.</span><span class="sxs-lookup"><span data-stu-id="04198-133">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="04198-134">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="04198-134">General info</span></span>

![Снимок экрана: параметры автозавода для имени, оператора, часового пояса, языка и голосового ввода](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="04198-136">Введите имя автозавода в поле в верхней части окна.</span><span class="sxs-lookup"><span data-stu-id="04198-136">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="04198-137">Чтобы назначить оператора, укажите место назначения для звонков оператору.</span><span class="sxs-lookup"><span data-stu-id="04198-137">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="04198-138">Это необязательный (но рекомендуемый вариант).</span><span class="sxs-lookup"><span data-stu-id="04198-138">This designation is optional (but recommended).</span></span> <span data-ttu-id="04198-139">Установите параметр **Оператор,** чтобы разрешить вызывателям выйти из меню и поговорить с назначенным человеком.</span><span class="sxs-lookup"><span data-stu-id="04198-139">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="04198-140">Укажите часовой пояс для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="04198-140">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="04198-141">Часовой пояс используется для вычисления рабочих часов, если вы создаете отдельный поток [зовов в не часах.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="04198-141">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="04198-142">Укажите [поддерживаемый язык](create-a-phone-system-auto-attendant-languages.md) для этого автозавода.</span><span class="sxs-lookup"><span data-stu-id="04198-142">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="04198-143">Этот язык будет использоваться для системных голосовых подсказок.</span><span class="sxs-lookup"><span data-stu-id="04198-143">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="04198-144">Выберите, нужно ли включить голосовой ввод.</span><span class="sxs-lookup"><span data-stu-id="04198-144">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="04198-145">Если этот параметр включен, имя каждого параметра меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="04198-145">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="04198-146">Например, можно сказать "Один", чтобы выбрать параметр меню, который назначен клавише 1, или слово "Продажи", чтобы выбрать пункт меню "Продажи".</span><span class="sxs-lookup"><span data-stu-id="04198-146">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

   > [!NOTE]
   > <span data-ttu-id="04198-147">Если на шаге 4 выбрать язык, который не поддерживает голосовой ввод, этот параметр будет отключен.</span><span class="sxs-lookup"><span data-stu-id="04198-147">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="04198-148">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="04198-148">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="04198-149">Поток вызовов</span><span class="sxs-lookup"><span data-stu-id="04198-149">Call flow</span></span>

![Снимок экрана: параметры приветствия сообщения](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="04198-151">Выберите, хотите ли вы воспроизведения приветствия, когда автоответ отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="04198-151">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="04198-152">Если вы **выберете "Звукозапись",** с помощью Upload файла можно добавить записанное приветствие, сохраненное в качестве звукового файла.  WAV, .MP3 или . Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="04198-152">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="04198-153">Размер записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="04198-153">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="04198-154">Если выбрать **Введите приветствие,** система будет читать текст, который вы введите (до 1000 символов), когда автозавет ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="04198-154">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: параметры маршрутизов параметров перенаходящего звонка](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="04198-156">Выберите, как вы хотите перена маршрутизовыть звонок.</span><span class="sxs-lookup"><span data-stu-id="04198-156">Choose how you want to route the call.</span></span>

<span data-ttu-id="04198-157">Если вы **выберете Отключить**, автозаводщик повесит вызов.</span><span class="sxs-lookup"><span data-stu-id="04198-157">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="04198-158">Если вы выбрали **Перенаправить** звонок , вы можете выбрать одно из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="04198-158">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="04198-159">Если вы выбрали **Параметры меню**  Воспроизведения, вы  можете выбрать вариант Воспроизведения звукового файла или Ввести приветствие, а затем выбрать параметры меню и поиск по каталогу.</span><span class="sxs-lookup"><span data-stu-id="04198-159">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="04198-160">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="04198-160">Menu options</span></span>

![Снимок экрана: параметры набора номера](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="04198-162">Чтобы задать параметры набора, назначьте 0–9 клавиш на телефонной клавиатуре одному из назначений маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="04198-162">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="04198-163">(Клавиши \* (Повтор) и (Назад) зарезервированы системой и не \# могут быть перена назначены.)</span><span class="sxs-lookup"><span data-stu-id="04198-163">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="04198-164">Сопоставления ключей не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="04198-164">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="04198-165">Можно создать меню с клавишами 0, 1 и 3, относясь к параметрам, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="04198-165">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="04198-166">Если вы настроили этот оператор, рекомендуем соендировать с оператором нулевые клавиши.</span><span class="sxs-lookup"><span data-stu-id="04198-166">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="04198-167">Если оператор не назначен ни одной клавише, голосовая команда "Оператор" также отключена.</span><span class="sxs-lookup"><span data-stu-id="04198-167">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="04198-168">Для каждого параметра меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="04198-168">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="04198-169">**Клавиша набора** номера — клавиша на телефонной клавиатуре для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="04198-169">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="04198-170">Если доступны голосовые данные, вызыватели также могут сказать этот номер, чтобы получить доступ к параметру.</span><span class="sxs-lookup"><span data-stu-id="04198-170">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="04198-171">**Голосовая** команда — определяет голосовую команду, которую может предоставить вызываемая команда для доступа к этому параметру, если включены голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="04198-171">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="04198-172">Оно может содержать несколько слов, например "Обслуживание клиентов" или "Операции и причины".</span><span class="sxs-lookup"><span data-stu-id="04198-172">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="04198-173">Например, можно нажать клавишу 2, сказать "два" или "Продажи", чтобы выбрать параметр, выбранный с двумя ключами.</span><span class="sxs-lookup"><span data-stu-id="04198-173">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="04198-174">Этот текст также отрисовывания текста в речь при запросе подтверждения службы, который может выглядеть так: "Перена передаче звонка в отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="04198-174">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="04198-175">**Redirect to** (Перенаправление на) — пункт назначения маршрутиации пунктов, используемых при выборе этого параметра вызывателями.</span><span class="sxs-lookup"><span data-stu-id="04198-175">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="04198-176">Если вы перенаправляете учетную запись к автоотправлению или очереди вызовов, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="04198-176">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="04198-177">Поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="04198-177">Directory search</span></span>

<span data-ttu-id="04198-178">При назначении пунктов назначениям набираемой клавиши рекомендуется выбрать **вариант Нет** для **поиска по каталогу.**</span><span class="sxs-lookup"><span data-stu-id="04198-178">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="04198-179">Если звоняющий пытается набрать имя или расширение с помощью клавиш, которые назначены определенным пунктам назначения, он может быть неожиданно перенаправлен в определенное место, прежде чем вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="04198-179">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="04198-180">Мы рекомендуем создать отдельный автозаводщик для поиска по каталогу и связаться с ним с помощью клавиши набора номера.</span><span class="sxs-lookup"><span data-stu-id="04198-180">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="04198-181">Если вы не назначили клавиши набора номера, выберите параметр поиска по **каталогу.**</span><span class="sxs-lookup"><span data-stu-id="04198-181">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="04198-182">**Набрать номер по** имени. Если этот параметр включить, вызыватели смогут ввести имя пользователя или ввести его на телефонной клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="04198-182">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="04198-183">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с помощью набора по имени.</span><span class="sxs-lookup"><span data-stu-id="04198-183">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="04198-184">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="04198-184">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="04198-185">**Набрать номер по расширению.** Если вы встроите этот параметр, вызывающие пользователи смогут связываться с пользователями в организации, набрав их расширения для телефона.</span><span class="sxs-lookup"><span data-stu-id="04198-185">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="04198-186">Любой пользователь в Интернете или любой пользователь, использующий локальное Skype для бизнеса Server, является подходящим пользователем, и его можно найти с расширением **Dial by**..</span><span class="sxs-lookup"><span data-stu-id="04198-186">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="04198-187">(На странице "Область набора номера" можно у установить, кто является и не включен в [каталог.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="04198-187">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="04198-188">Для пользователей, которые вы хотите сделать доступными для расширения "Набор номера", необходимо добавить расширение, как часть одного [](/microsoft-365/admin/add-users/add-users) из следующих атрибутов телефонов, определенных в Active Directory или Azure Active Directory (дополнительные сведения см. в документе Добавление пользователей по одному или массово).)</span><span class="sxs-lookup"><span data-stu-id="04198-188">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="04198-189">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="04198-189">OfficePhone</span></span>
- <span data-ttu-id="04198-190">HomePhone</span><span class="sxs-lookup"><span data-stu-id="04198-190">HomePhone</span></span>
- <span data-ttu-id="04198-191">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="04198-191">Mobile/MobilePhone</span></span>
- <span data-ttu-id="04198-192">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="04198-192">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="04198-193">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="04198-193">OtherTelephone</span></span>

<span data-ttu-id="04198-194">Формат, требуемого для ввода расширения в поле номера телефона пользователя, может иметь один из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="04198-194">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="04198-195">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="04198-195">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="04198-196">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="04198-196">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="04198-197">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="04198-197">*x\<extension>*</span></span>

- <span data-ttu-id="04198-198">Пример 1. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="04198-198">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="04198-199">Пример 2. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="04198-199">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="04198-200">Пример 3. Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="04198-200">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="04198-201">Вы можете установить расширение в центре администрирования [Microsoft 365](https://admin.microsoft.com/) или Azure Active Directory [центре администрирования](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="04198-201">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="04198-202">Изменения, внесенные автоследникам и очередям вызовов, могут быть доступны в течение 12 часов.</span><span class="sxs-lookup"><span data-stu-id="04198-202">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="04198-203">Если вы хотите использовать  функции  "Набрать номер по имени" и "Набрать по расширению", назначьте клавишу набора главному автоотеке, чтобы связаться с автозаводом, включенным для функции "Набрать по **имени".**</span><span class="sxs-lookup"><span data-stu-id="04198-203">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="04198-204">В пределах этого автозавода вы можете назначить 1-й  ключ (без букв), чтобы связаться с автозаводом для набора номера по расширению.</span><span class="sxs-lookup"><span data-stu-id="04198-204">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="04198-205">Выбрав параметр поиска по **каталогу, выберите** **Далее.**</span><span class="sxs-lookup"><span data-stu-id="04198-205">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="04198-206">Поток вызовов в нечасовом времени</span><span class="sxs-lookup"><span data-stu-id="04198-206">Call flow for after hours</span></span>

![Снимок экрана: параметры дня и времени после окончания дня](media/auto-attendant-business-hours.png)

<span data-ttu-id="04198-208">Для каждого автозавода можно настроить часы работы.</span><span class="sxs-lookup"><span data-stu-id="04198-208">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="04198-209">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="04198-209">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="04198-210">В течение дня можно настроить часы работы с перерывом, а все часы, которые не считаются неавтными, считаются неавтными.</span><span class="sxs-lookup"><span data-stu-id="04198-210">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="04198-211">Вы можете настроить различные параметры обработки входящих параметров обработки звонка и приветствия в течение часа.</span><span class="sxs-lookup"><span data-stu-id="04198-211">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="04198-212">В зависимости от настройки автозаполнения и очередей звонков может потребоваться указать маршрутику звонков только для автозаполнения с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="04198-212">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="04198-213">Если вам нужна отдельная маршрутия для вызывающих телефонных вызовов в нечасовом времени, укажите часы работы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="04198-213">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="04198-214">Выберите **Добавить новое время,** чтобы указать несколько наборов часов для заданного дня, например, чтобы указать перерыв на обед.</span><span class="sxs-lookup"><span data-stu-id="04198-214">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="04198-215">После того как вы указали часы работы, выберите параметры маршрутизов параметров для неавтных часов.</span><span class="sxs-lookup"><span data-stu-id="04198-215">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="04198-216">Доступны те же параметры, что и для маршрутизов в часы работы, которые вы указали выше.</span><span class="sxs-lookup"><span data-stu-id="04198-216">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="04198-217">Когда **все будет готово,** выберите Далее.</span><span class="sxs-lookup"><span data-stu-id="04198-217">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="04198-218">Потоки вызовов во время праздников</span><span class="sxs-lookup"><span data-stu-id="04198-218">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравительных и праздничных приветствий](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="04198-220">Ваш автозаводщик может использовать поток зовов для каждого настроенного вами [праздника.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="04198-220">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="04198-221">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="04198-221">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="04198-222">На странице параметров звонка праздников выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="04198-222">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="04198-223">Введите название этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="04198-223">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="04198-224">В **dropdown Holiday** (Праздники) выберите праздник, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="04198-224">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="04198-225">Выберите нужный тип приветствия.</span><span class="sxs-lookup"><span data-stu-id="04198-225">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действий по праздничным звонкам](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="04198-227">Выберите, хотите ли вы **отключить или** **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="04198-227">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="04198-228">Если вы выбрали перенаправление, выберите пункт назначения маршрутиации для звонка.</span><span class="sxs-lookup"><span data-stu-id="04198-228">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="04198-229">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="04198-229">Select **Save**.</span></span>

![Снимок экрана: параметры праздников со списком праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="04198-231">Повторите эти процедуры для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="04198-231">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="04198-232">Когда вы добавите все праздники, выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="04198-232">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="04198-233">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="04198-233">Dial scope</span></span>

![Снимок экрана: область набора номера, включаемая и исключаемая](media/auto-attendant-dial-scope.png)

<span data-ttu-id="04198-235">Область *набора определяет,* какие пользователи доступны в каталоге, если вызываемая звонок использует по имени или по телефону по расширению.</span><span class="sxs-lookup"><span data-stu-id="04198-235">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="04198-236">По умолчанию **все пользователи в** Сети включают всех пользователей в организации, которые являются пользователями Online или которые находятся локально с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="04198-236">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="04198-237">Вы можете включить или исключить определенных  пользователей,  выбрав настраиваемую группу пользователей в группе Включить или Исключить и выбрав одну или несколько групп Microsoft 365, списков рассылки или групп безопасности. </span><span class="sxs-lookup"><span data-stu-id="04198-237">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="04198-238">Например, может потребоваться исключить руководителей организации из каталога набора номера.</span><span class="sxs-lookup"><span data-stu-id="04198-238">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="04198-239">(Если пользователь есть в обоих списках, он будет исключен из каталога.)</span><span class="sxs-lookup"><span data-stu-id="04198-239">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="04198-240">Для того чтобы имя нового пользователя было указано в каталоге, может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="04198-240">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="04198-241">После настройки области набора номера выберите **Далее.**</span><span class="sxs-lookup"><span data-stu-id="04198-241">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="04198-242">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="04198-242">Resource accounts</span></span>

<span data-ttu-id="04198-243">У всех автозаводников должна быть связанная учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="04198-243">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="04198-244">Автослужам первого уровня потребуется по крайней мере одна учетная запись ресурса с связанным номером службы.</span><span class="sxs-lookup"><span data-stu-id="04198-244">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="04198-245">При желании вы можете назначить автослужбу несколько учетных записей ресурсов с отдельным номером службы.</span><span class="sxs-lookup"><span data-stu-id="04198-245">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель добавления учетных записей для учетных записей ресурсов](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="04198-247">Чтобы добавить учетную запись ресурса, выберите **Добавить** учетную запись и найщите учетную запись, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="04198-247">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="04198-248">Выберите **Добавить**, а затем **добавить**.</span><span class="sxs-lookup"><span data-stu-id="04198-248">Select **Add**, and then select **Add**.</span></span>

![Снимок экрана: список учетных записей ресурсов с учетной записью ресурса с номером назначенной услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="04198-250">Завершив добавление учетных записей службы, выберите **Отправить,** чтобы завершить настройку автозаполнеющего.</span><span class="sxs-lookup"><span data-stu-id="04198-250">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="04198-251">Передача внешних номеров телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="04198-251">External phone number transfers - technical details</span></span>

<span data-ttu-id="04198-252">Чтобы разрешить [автоответам](plan-auto-attendant-call-queue.md#prerequisites) переводить звонки за границу, обратитесь к условиям.</span><span class="sxs-lookup"><span data-stu-id="04198-252">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="04198-253">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="04198-253">In addition:</span></span>

- <span data-ttu-id="04198-254">Для учетной записи ресурса с лицензией на план звонков [номер](calling-plans-for-office-365.md)внешнего переносного телефона должен быть введен в формате E.164 (+[код страны][код города][номер телефона]).</span><span class="sxs-lookup"><span data-stu-id="04198-254">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="04198-255">Для учетной записи ресурса с лицензией телефонная система и политикой прямой маршрутистики в Интернете формат номера внешнего переносимого телефона зависит от параметров [SBC.](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="04198-255">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="04198-256">Отображаемая исходящие телефонные номера определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="04198-256">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="04198-257">Для номеров планов звонков отображается исходный номер телефона звоня.</span><span class="sxs-lookup"><span data-stu-id="04198-257">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="04198-258">Для номеров прямой маршрутификации число, отправленное, основано на параметре P-Изучаемого удостоверения (PAI) в SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="04198-258">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="04198-259">Если за установлено отключение, отображается исходный номер телефона вызываемого звоня.</span><span class="sxs-lookup"><span data-stu-id="04198-259">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="04198-260">Этот параметр рекомендуется использовать по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="04198-260">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="04198-261">Если для этого включено, отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="04198-261">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="04198-262">Для Skype для бизнеса гибридной среды для переадстройки вызова автоотехнщика в ПСОП создайте нового локального пользователя с номером для переадстройки вызовов через ПСОП.</span><span class="sxs-lookup"><span data-stu-id="04198-262">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="04198-263">Пользователь должен быть включен для Корпоративная голосовая связь и иметь назначенную голосовую политику.</span><span class="sxs-lookup"><span data-stu-id="04198-263">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="04198-264">Дополнительные см. в теме Перенастройка [автоотвода для перенастройки звонка на ПСОП.](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="04198-264">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="04198-265">Создание автозавода с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="04198-265">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="04198-266">Вы также можете использовать PowerShell для создания и создания автоотехов.</span><span class="sxs-lookup"><span data-stu-id="04198-266">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="04198-267">Ниже статисты, необходимые для управления автозаправщиком.</span><span class="sxs-lookup"><span data-stu-id="04198-267">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="04198-268">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="04198-268">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="04198-269">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="04198-269">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="04198-270">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="04198-270">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="04198-271">Get-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="04198-271">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="04198-272">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="04198-272">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="04198-273">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="04198-273">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="04198-274">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="04198-274">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="04198-275">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="04198-275">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="04198-276">Export-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="04198-276">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="04198-277">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="04198-277">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="04198-278">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="04198-278">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="04198-279">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="04198-279">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="04198-280">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="04198-280">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="04198-281">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="04198-281">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="04198-282">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="04198-282">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="04198-283">Import-CsAutoAttendantУдаys</span><span class="sxs-lookup"><span data-stu-id="04198-283">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="04198-284">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="04198-284">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="04198-285">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="04198-285">Related topics</span></span>

[<span data-ttu-id="04198-286">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="04198-286">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="04198-287">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="04198-287">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="04198-288">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="04198-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="04198-289">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="04198-289">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
