---
title: Настройка автосекретаря для Microsoft Teams
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Сведения о настройке и тестировании автоматических ассистентов для Microsoft Teams.
ms.openlocfilehash: 00cf80578564db122d4eaf206456b465a21668af
ms.sourcegitcommit: 950c04ce49064209ee04880e7c7473a4f931df50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "48999221"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="b6270-103">Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b6270-103">Set up an auto attendant</span></span>

<span data-ttu-id="b6270-104">С помощью автосекретарей пользователи могут позвонить в вашу организацию и переходить в систему меню для общения с нужным Отделом, очередью звонков, лицом или оператором.</span><span class="sxs-lookup"><span data-stu-id="b6270-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="b6270-105">Вы можете создавать автоматические ассистенты в Организации с помощью центра администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6270-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="b6270-106">Перед выполнением процедур, описанных в этой статье, убедитесь, что у вас есть план прочтения [для команд автосекретаря и очереди звонков](plan-auto-attendant-call-queue.md) , а затем следуйте [инструкциям по началу работы](plan-auto-attendant-call-queue.md#getting-started) .</span><span class="sxs-lookup"><span data-stu-id="b6270-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="b6270-107">Автоматические ассистенты могут направлять звонки в соответствии с входными данными для вызывающего абонента в одном из указанных ниже мест. <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="b6270-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="b6270-108">**Сотрудник Организации** — сотрудник вашей организации, который может принимать голосовые звонки.</span><span class="sxs-lookup"><span data-stu-id="b6270-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="b6270-109">Это может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b6270-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="b6270-110">**Голосовое приложение** — другой автоматический секретарь или очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="b6270-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="b6270-111">(Выберите учетную запись ресурса, связанную с автосекретарем или очередью звонков при выборе этого пункта назначения.)</span><span class="sxs-lookup"><span data-stu-id="b6270-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="b6270-112">**Внешний номер телефона** — любой номер телефона.</span><span class="sxs-lookup"><span data-stu-id="b6270-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="b6270-113">(Дополнительные [технические сведения о внешних передачах](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="b6270-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="b6270-114">Голосовая **почта** — голосовой почтовый ящик, связанный с указанными вами группами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6270-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="b6270-115">**Operator** — оператор, определенный для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6270-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="b6270-116">Определение оператора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b6270-116">Defining an operator is optional.</span></span> <span data-ttu-id="b6270-117">Этот оператор можно задать в качестве любого из других мест в этом списке.</span><span class="sxs-lookup"><span data-stu-id="b6270-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="b6270-118">При настройке автосекретаря вам будет предложено выбрать один из этих вариантов на разных этапах.</span><span class="sxs-lookup"><span data-stu-id="b6270-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="b6270-119">Чтобы настроить автосекретарь, в центре администрирования Teams разверните элемент **Голосовая связь** , выберите **автосекретарьs** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="b6270-119">To set up an auto attendant, in the Teams admin center, expand **Voice** , click **Auto attendants** , and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="b6270-120">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="b6270-120">General info</span></span>

![Снимок экрана: параметры автосекретаря для имени, оператора, часового пояса, языка и входного голоса](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="b6270-122">Введите имя автосекретаря в поле в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="b6270-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="b6270-123">Если вы хотите назначить оператор, укажите назначение для вызова оператора.</span><span class="sxs-lookup"><span data-stu-id="b6270-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="b6270-124">Это необязательно (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="b6270-124">This is optional (but recommended).</span></span> <span data-ttu-id="b6270-125">Вы можете настроить параметр **оператора** , чтобы разрешить звонящим выйти из меню и поговорить с определенным человеком.</span><span class="sxs-lookup"><span data-stu-id="b6270-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="b6270-126">Укажите часовой пояс для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6270-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="b6270-127">Часовой пояс используется для вычисления рабочих часов, если вы [создаете отдельный поток звонков в течение часа](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="b6270-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="b6270-128">Укажите язык для этого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6270-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="b6270-129">Это язык, который будет использоваться для создаваемых системой голосовых запросов.</span><span class="sxs-lookup"><span data-stu-id="b6270-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="b6270-130">Выберите этот параметр, если вы хотите включить голосовые данные.</span><span class="sxs-lookup"><span data-stu-id="b6270-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="b6270-131">Если этот параметр включен, имя каждого пункта меню становится ключевым словом распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="b6270-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="b6270-132">Например, вызывающие объекты могут сказать "один", чтобы выбрать параметр меню, сопоставленный с клавишей 1, или указать "продажи", чтобы выбрать пункт меню "продажи".</span><span class="sxs-lookup"><span data-stu-id="b6270-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="b6270-133">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b6270-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="b6270-134">Поток звонков</span><span class="sxs-lookup"><span data-stu-id="b6270-134">Call flow</span></span>

![Снимок экрана: параметры сообщения приветствия](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="b6270-136">Укажите, нужно ли воспроизводить приветствие, когда автосекретарь отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="b6270-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="b6270-137">Если выбрать команду **Воспроизвести звуковой файл** , вы можете использовать кнопку **Добавить файл** , чтобы отправить записанное приветствие, сохраненное в виде звукового файла. WAV,. MP3 или. Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="b6270-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="b6270-138">Размер записи не может превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="b6270-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="b6270-139">Если вы выбрали команду **Введите сообщение приветствия** , система будет прочитать текст, который вы вводите (до 1000 символов), когда автосекретарь ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="b6270-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Снимок экрана: настройки маршрутизации звонков](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="b6270-141">Укажите, как вы хотите перенаправить звонок.</span><span class="sxs-lookup"><span data-stu-id="b6270-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="b6270-142">Если выбрать команду **Отключить** , автосекретарь будет зависнуть звонок.</span><span class="sxs-lookup"><span data-stu-id="b6270-142">If you select **Disconnect** , the auto attendant will hang up the call.</span></span>

<span data-ttu-id="b6270-143">Если вы выбрали команду **перенаправить звонок** , вы можете выбрать один из назначений маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="b6270-143">If you select **Redirect call** , you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="b6270-144">Если вы выбрали пункт **Параметры меню воспроизвести** , вы можете **Воспроизвести звуковой файл** или **ввести текст в сообщении приветствия** , а затем выбрать параметры меню и поиск по каталогам.</span><span class="sxs-lookup"><span data-stu-id="b6270-144">If you select **Play menu options** , you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="b6270-145">Параметры меню</span><span class="sxs-lookup"><span data-stu-id="b6270-145">Menu options</span></span>

![Снимок экрана: параметры ключа набора](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="b6270-147">Для параметров набора номера можно назначить клавиши 0-9 на клавиатуре телефона одному из адресатов маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="b6270-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="b6270-148">(Клавиши \* (Повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.)</span><span class="sxs-lookup"><span data-stu-id="b6270-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="b6270-149">Сопоставления клавиш не должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="b6270-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="b6270-150">Например, можно создать меню с клавишами 0, 1 и 3, сопоставленными с параметрами, в то время как клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="b6270-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="b6270-151">Мы рекомендуем сопоставить ключ 0 с оператором, если вы настроили его.</span><span class="sxs-lookup"><span data-stu-id="b6270-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="b6270-152">Если оператор не имеет значения ни один из клавиш, голосовая команда "оператор" также отключается.</span><span class="sxs-lookup"><span data-stu-id="b6270-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="b6270-153">Для каждого пункта меню укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b6270-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="b6270-154">**Клавиша вызова** — клавиша на клавиатуре телефона для доступа к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="b6270-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="b6270-155">Если входные данные доступны, вызывающий абонент также может сказать этот номер, чтобы получить доступ к параметру.</span><span class="sxs-lookup"><span data-stu-id="b6270-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="b6270-156">**Voice Command** — определяет голосовую команду, которую вызывающий абонент может предоставить для доступа к этому параметру, если включены голосовые входные данные.</span><span class="sxs-lookup"><span data-stu-id="b6270-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="b6270-157">Она может содержать несколько слов, таких как "услуга обслуживания клиентов" или "операции и причины".</span><span class="sxs-lookup"><span data-stu-id="b6270-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="b6270-158">Например, вызывающий абонент может нажать 2, скажите "два" или скажите "продажи", чтобы выбрать параметр, сопоставленный с клавишей 2.</span><span class="sxs-lookup"><span data-stu-id="b6270-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="b6270-159">Этот текст также отображается по тексту в речь для запроса на подтверждение службы, который может выглядеть примерно так, как "Передача звонка в продажи".</span><span class="sxs-lookup"><span data-stu-id="b6270-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="b6270-160">**Перенаправить на** — назначение маршрутизации звонков, используемое для вызывающих абонентов, если этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="b6270-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="b6270-161">Если вы перенаправлялись на автосекретарь или очередь звонков, выберите связанную с ней учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6270-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="b6270-162">Поиск в каталоге</span><span class="sxs-lookup"><span data-stu-id="b6270-162">Directory search</span></span>

<span data-ttu-id="b6270-163">Если вы назначаете ключи набора для конечных объектов, мы рекомендуем выбрать параметр **None** для **поиска в каталоге**.</span><span class="sxs-lookup"><span data-stu-id="b6270-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="b6270-164">Если вызывающий абонент пытается набрать имя или расширение с помощью ключей, которые назначены конкретным получателям, они могут неожиданно перенаправляться в место назначения, прежде чем они закончит вводить имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="b6270-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="b6270-165">Мы рекомендуем создать отдельный автосекретарь для поиска в службе каталогов и попросите основной автосекретарь на него через ключ набора.</span><span class="sxs-lookup"><span data-stu-id="b6270-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="b6270-166">Если вы не назначаете ключи набора номера, выберите параметр для **поиска по каталогу**.</span><span class="sxs-lookup"><span data-stu-id="b6270-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="b6270-167">**Набрать номер** — если вы включите этот параметр, вызывающие абоненты могут нанести имя пользователя или ввести его на клавиатуре телефона.</span><span class="sxs-lookup"><span data-stu-id="b6270-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="b6270-168">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="b6270-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="b6270-169">(Вы можете настроить пользователей, которые не включены в каталог на странице " [область набора номера](#dial-scope) ".)</span><span class="sxs-lookup"><span data-stu-id="b6270-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="b6270-170">**Набрать номер с помощью расширения** если вы включите этот параметр, абоненты могут подключаться к своим пользователям из вашей организации, набирая их добавочные номера.</span><span class="sxs-lookup"><span data-stu-id="b6270-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="b6270-171">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью **набора номера по расширению**.</span><span class="sxs-lookup"><span data-stu-id="b6270-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="b6270-172">(Вы можете настроить пользователей, которые не включены в каталог на странице " [область набора номера](#dial-scope) ".)</span><span class="sxs-lookup"><span data-stu-id="b6270-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="b6270-173">Для пользователей, которые должны быть доступны для набора номера с помощью расширения, необходимо задать расширение как часть одного из указанных ниже атрибутов, определенных в службе каталогов Active Directory или Azure Active Directory (Дополнительные сведения можно найти [в разделе Добавление пользователей по отдельности или массовое заполнение](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) ).</span><span class="sxs-lookup"><span data-stu-id="b6270-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="b6270-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="b6270-174">OfficePhone</span></span>
- <span data-ttu-id="b6270-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="b6270-175">HomePhone</span></span>
- <span data-ttu-id="b6270-176">Мобильный или MobilePhone</span><span class="sxs-lookup"><span data-stu-id="b6270-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="b6270-177">TelephoneNumber/заданный</span><span class="sxs-lookup"><span data-stu-id="b6270-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="b6270-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="b6270-178">OtherTelephone</span></span>

<span data-ttu-id="b6270-179">Формат, необходимый для ввода расширения в поле "телефонный номер пользователя", должен быть *+ \<phone number> ext \<extension> =* или *+ \<phone number> x \<extension>*.</span><span class="sxs-lookup"><span data-stu-id="b6270-179">The required format to enter the extension in the user phone number field is either *+\<phone number>ext=\<extension>* or *+\<phone number>x\<extension>*.</span></span>

<span data-ttu-id="b6270-180">Вы можете настроить расширение в [центре администрирования Microsoft 365](https://admin.microsoft.com/) или в [центре администрирования Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b6270-180">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="b6270-181">Чтобы изменения были доступны для автосекретарей и очередей звонков, может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="b6270-181">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="b6270-182">Если вы хотите использовать функции **набора номера по имени** и **набора номера** , вы можете назначить для него ключ набора номера на основном автосекретаря, чтобы получить доступ к автосекретарь **по имени**.</span><span class="sxs-lookup"><span data-stu-id="b6270-182">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="b6270-183">В рамках этого автосекретаря вы можете присвоить клавишу 1 (которая не имеет связанных с ней букв) и связаться с автосекретарем **набора номера** .</span><span class="sxs-lookup"><span data-stu-id="b6270-183">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="b6270-184">Выбрав один из вариантов **поиска в каталоге** , нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b6270-184">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="b6270-185">Поток звонков за часы</span><span class="sxs-lookup"><span data-stu-id="b6270-185">Call flow for after hours</span></span>

![Снимок экрана: Настройка дня и времени в течение часа](media/auto-attendant-business-hours.png)

<span data-ttu-id="b6270-187">Рабочие часы можно настроить для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6270-187">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="b6270-188">Если рабочие часы не настроены, по умолчанию устанавливается круглосуточный график работы без выходных дней.</span><span class="sxs-lookup"><span data-stu-id="b6270-188">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="b6270-189">Рабочие часы можно настроить с разбивкой на время в течение дня, а все часы, не заданные в качестве рабочих часов, рассматриваются после-часов.</span><span class="sxs-lookup"><span data-stu-id="b6270-189">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="b6270-190">Вы можете настроить различные параметры обработки входящих звонков и приветствия в течение не более часа.</span><span class="sxs-lookup"><span data-stu-id="b6270-190">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="b6270-191">В зависимости от того, как вы настроили автоматические ассистенты и очереди звонков, вам может потребоваться указать только после-часового звонка для автосекретарей с прямыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="b6270-191">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="b6270-192">Если вы хотите отдельно настроить маршрутизацию звонков для вызывающих абонентов после выхода из него, укажите рабочие часы для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="b6270-192">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="b6270-193">Нажмите кнопку **Добавить** , чтобы указать несколько наборов часов для определенного дня, например для выбора перерыва на обед.</span><span class="sxs-lookup"><span data-stu-id="b6270-193">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="b6270-194">После того как вы зауказали рабочее время, а затем выберете параметры маршрутизации звонков в течение часа.</span><span class="sxs-lookup"><span data-stu-id="b6270-194">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="b6270-195">Те же параметры доступны для маршрутизации вызовов рабочих часов, указанных выше.</span><span class="sxs-lookup"><span data-stu-id="b6270-195">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="b6270-196">Когда все будет готово, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="b6270-196">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="b6270-197">Потоки звонка во время праздников</span><span class="sxs-lookup"><span data-stu-id="b6270-197">Call flows during holidays</span></span>

![Снимок экрана: параметры поздравления праздников и праздников](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="b6270-199">У автосекретаря может быть поток звонков для каждого [настроенного праздника](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b6270-199">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="b6270-200">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="b6270-200">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="b6270-201">На странице Параметры звонка нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b6270-201">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="b6270-202">Введите имя для этого параметра праздников.</span><span class="sxs-lookup"><span data-stu-id="b6270-202">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="b6270-203">Из раскрывающегося списка **праздников** выберите праздничный день, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="b6270-203">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="b6270-204">Выберите тип приветствия, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="b6270-204">Choose the type of greeting that you want to use.</span></span>

    ![Снимок экрана: параметры действия звонка в праздничные дни](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="b6270-206">Выберите, хотите ли вы **Отключить** или **перенаправить** звонок.</span><span class="sxs-lookup"><span data-stu-id="b6270-206">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="b6270-207">Если вы выбрали перенаправление, выберите назначение маршрутизации звонков для звонка.</span><span class="sxs-lookup"><span data-stu-id="b6270-207">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="b6270-208">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b6270-208">Click **Save**.</span></span>

![Снимок экрана с параметрами праздников в списке праздников](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="b6270-210">Повторите процедуру, если это необходимо для каждого дополнительного праздника.</span><span class="sxs-lookup"><span data-stu-id="b6270-210">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="b6270-211">После добавления всех праздников нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b6270-211">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="b6270-212">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="b6270-212">Dial scope</span></span>

![Снимок экрана: параметры включения и исключения в области набора номера](media/auto-attendant-dial-scope.png)

<span data-ttu-id="b6270-214">*Область набора номера* определяет, какие пользователи доступны в каталоге, когда вызывающий абонент использует коммутируемое имя или коммутируемое подключение.</span><span class="sxs-lookup"><span data-stu-id="b6270-214">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="b6270-215">Значения по умолчанию для **всех пользователей** в Организации включают в себя пользователей, которые являются сетевыми и подключенными к сети с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b6270-215">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="b6270-216">Вы можете включить или исключить конкретных пользователей, выбрав **пользовательскую группу** в разделе **включить** или **исключить** и выбрать одну или несколько групп Microsoft 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6270-216">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="b6270-217">Например, вы можете исключить руководителей в организации из каталога набора.</span><span class="sxs-lookup"><span data-stu-id="b6270-217">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="b6270-218">(Если пользователь входит в оба списка, они будут исключены из каталога.)</span><span class="sxs-lookup"><span data-stu-id="b6270-218">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="b6270-219">Для нового пользователя в каталоге может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="b6270-219">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="b6270-220">Завершив настройку области набора номера, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b6270-220">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="b6270-221">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="b6270-221">Resource accounts</span></span>

<span data-ttu-id="b6270-222">У всех автосекретарей должна быть соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6270-222">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="b6270-223">Для автосекретаря первого уровня требуется по крайней мере одна учетная запись ресурса с соответствующим номером услуги.</span><span class="sxs-lookup"><span data-stu-id="b6270-223">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="b6270-224">При желании вы можете назначить несколько учетных записей ресурсов для автосекретаря, каждый из которых имеет отдельный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="b6270-224">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Снимок экрана: панель "Добавление учетных записей"](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="b6270-226">Чтобы добавить учетную запись ресурса, нажмите кнопку **Добавить учетную** запись и выполните поиск учетной записи, которую вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="b6270-226">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="b6270-227">Нажмите кнопку **Добавить** , а затем — **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b6270-227">Click **Add** , and then click **Add**.</span></span>

![Снимок экрана: список "учетные записи ресурсов" с назначенным номером услуги](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="b6270-229">Завершив добавление учетных записей служб, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="b6270-229">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="b6270-230">После этого Автоматическая Настройка автосекретаря завершается.</span><span class="sxs-lookup"><span data-stu-id="b6270-230">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="b6270-231">Внешние номера телефонов — технические сведения</span><span class="sxs-lookup"><span data-stu-id="b6270-231">External phone number transfers - technical details</span></span>

<span data-ttu-id="b6270-232">Чтобы использовать автосекретарь для внешних передач звонков, ознакомьтесь с [необходимыми условиями](plan-auto-attendant-call-queue.md#prerequisites) .</span><span class="sxs-lookup"><span data-stu-id="b6270-232">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="b6270-233">В дополнение:</span><span class="sxs-lookup"><span data-stu-id="b6270-233">In addition:</span></span>

- <span data-ttu-id="b6270-234">Для учетной записи ресурса с номером [плана звонков](calling-plans-for-office-365.md) номер внешней передачи должен быть введен в формате E. 164 (+ [код страны] [код города] [телефонный номер]).</span><span class="sxs-lookup"><span data-stu-id="b6270-234">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="b6270-235">Если для учетной записи ресурса задан прямой маршрутный номер, формат телефонной нумерации для внешнего перемещения зависит от параметров [контроллера границ сеанса (SBC)](direct-routing-connect-the-sbc.md) .</span><span class="sxs-lookup"><span data-stu-id="b6270-235">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="b6270-236">Отображаемый исходящий номер телефона определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b6270-236">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="b6270-237">Для номеров планов звонков отображается номер телефона исходного вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b6270-237">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="b6270-238">Для прямых маршрутов номер отправляется на основе параметра P-Assert-Identity (PAI) на SBC, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b6270-238">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="b6270-239">Если установлено значение "отключено", отображается номер телефона исходного вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b6270-239">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="b6270-240">Этот параметр является рекомендуемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6270-240">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="b6270-241">Если установлено значение "включено", отображается номер телефона учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="b6270-241">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="b6270-242">В гибридной среде Skype для бизнеса, чтобы передать автоматический звонок в КТСОП, создайте нового локального пользователя с переадресацией звонков, установленным на номер КТСОП.</span><span class="sxs-lookup"><span data-stu-id="b6270-242">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="b6270-243">Пользователь должен быть активирован для корпоративной голосовой связи и имеет назначенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b6270-243">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="b6270-244">Дополнительные сведения можно найти в разделе Переадресация [звонков по автосекретарем в КТСОП](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="b6270-244">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="b6270-245">Создание автосекретаря с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6270-245">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="b6270-246">Вы также можете использовать PowerShell для создания и настройки автоматических ассистентов.</span><span class="sxs-lookup"><span data-stu-id="b6270-246">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="b6270-247">Ниже приведены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="b6270-247">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="b6270-248">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b6270-248">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="b6270-249">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b6270-249">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="b6270-250">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b6270-250">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="b6270-251">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="b6270-251">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="b6270-252">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="b6270-252">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="b6270-253">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="b6270-253">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="b6270-254">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="b6270-254">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="b6270-255">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="b6270-255">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="b6270-256">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="b6270-256">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="b6270-257">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="b6270-257">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="b6270-258">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="b6270-258">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="b6270-259">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="b6270-259">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="b6270-260">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="b6270-260">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="b6270-261">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="b6270-261">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="b6270-262">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="b6270-262">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="b6270-263">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="b6270-263">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="b6270-264">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="b6270-264">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a><span data-ttu-id="b6270-265">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b6270-265">Related topics</span></span>

[<span data-ttu-id="b6270-266">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="b6270-266">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="b6270-267">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="b6270-267">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="b6270-268">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="b6270-268">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="b6270-269">Пример для малого бизнеса: Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="b6270-269">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="b6270-270">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b6270-270">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
