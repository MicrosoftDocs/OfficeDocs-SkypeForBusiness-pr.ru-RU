---
title: Настройка облачного автосекретаря
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Сведения о настройке и тестировании автоматических автосекретарей в облачных целях для Microsoft Teams.
ms.openlocfilehash: 424b6cea41132bd03b9eecfbd2d387697332505f
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2019
ms.locfileid: "37402054"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="9ffd8-103">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="9ffd8-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="9ffd8-104">С помощью автосекретарей пользователи могут позвонить в вашу организацию и переходить в систему меню для общения с нужным Отделом, очередью звонков, лицом или оператором.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="9ffd8-105">Вы можете создавать автоматические ассистенты в Организации с помощью центра администрирования Microsoft Teams или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with Powershell.</span></span> <span data-ttu-id="9ffd8-106">Чтобы создать автосекретарь, на панели навигации слева выберите пункт **Голосовая связь** , а затем —**Добавить новые** **ассистенты** > .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-106">To create an auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="9ffd8-107">Если вы хотите узнать больше об автосекретарях, посмотрите, [что такое автосекретарь облака?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="9ffd8-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="9ffd8-108">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

<span data-ttu-id="9ffd8-109">Номера телефонов не назначаются автосекретаря напрямую, а также [учетной записи ресурса](manage-resource-accounts.md) , связанной с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-109">Phone numbers are not directly assigned to the auto attendant, but rather to a [resource account](manage-resource-accounts.md) that is associated to the auto attendant.</span></span>

<span data-ttu-id="9ffd8-110">В реализации автосекретаря часто задействованы несколько автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-110">Auto attendant implementations often involve several auto attendants.</span></span> <span data-ttu-id="9ffd8-111">Автоматический секретарь *первого уровня* обычно имеет учетную запись ресурса с назначенным номером телефона.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-111">A *first-level* auto attendant usually has a resource account with an assigned phone number.</span></span> <span data-ttu-id="9ffd8-112">Вложенный автосекретарь используется как меню второго уровня, которое подключается автосекретарем *первого уровня* .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-112">A nested auto attendant is used as a second-level menu that the *first-level* auto attendant connects  as call to.</span></span> <span data-ttu-id="9ffd8-113">Для учетной записи ресурса *вложенному* автосекретарь не требуется присвоение номера телефона.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-113">A *nested* auto attendant isn't required to  have a phone number assigned to its resource account.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="9ffd8-114">Этап 1 — Начало работы</span><span class="sxs-lookup"><span data-stu-id="9ffd8-114">Step 1 — Get started</span></span>

- <span data-ttu-id="9ffd8-115">Для связи с учетной записью ресурса необходимо наличие автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-115">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="9ffd8-116">Дополнительные сведения об учетных записях ресурсов и всех необходимых лицензиях смотрите [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-116">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span> 
- 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> <span data-ttu-id="9ffd8-117">Чтобы перенаправить звонки на оператора или параметр меню, который является сетевым пользователем с лицензией на телефонную систему, вам потребуется включить их для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-117">To redirect calls to an operator or a menu option that is an Online user with a Phone System license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="9ffd8-118">В разделе [Назначение лицензий на Skype для бизнеса](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) или [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="9ffd8-119">Вы также можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="9ffd8-120">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="9ffd8-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-auto-attendants"></a><span data-ttu-id="9ffd8-121">Шаг 2: создание автоматических ассистентов</span><span class="sxs-lookup"><span data-stu-id="9ffd8-121">Step 2 — Create auto attendants</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ffd8-122">Для каждого автосекретаря требуется наличие соответствующей [учетной записи ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="9ffd8-123">Сначала необходимо создать учетную запись ресурса, после чего вы сможете связать ее с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="with-the-microsoft-teams-admin-center"></a><span data-ttu-id="9ffd8-124">С центром администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ffd8-124">With the Microsoft Teams admin center</span></span>

<span data-ttu-id="9ffd8-125">В **центре администрирования Microsoft Teams** **выберите пункт** > **автосекретарь**и нажмите кнопку **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ Add**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="9ffd8-126">Страница "Общие сведения"</span><span class="sxs-lookup"><span data-stu-id="9ffd8-126">General info page</span></span>

![Снимок экрана: страница "мой секретарь"](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

<span data-ttu-id="9ffd8-128">![Значок цифры 1, выноска в предыдущем](media/teamscallout1.png)
**имени** снимка экрана введите отображаемое имя для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-128">![Icon of the number 1, a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a display name for your auto attendant.</span></span> <span data-ttu-id="9ffd8-129">Имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-129">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="9ffd8-130">Указанное здесь **имя** будет указано в столбце вкладки **автосекретарьы** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-130">The **Name** you designate here is listed in a column on the **Auto attendants** tab.</span></span>

<span data-ttu-id="9ffd8-131"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="9ffd8-131"></span></span>

* * *

<span data-ttu-id="9ffd8-132">![Значок цифры 2, выноска в предыдущем](media/teamscallout2.png)
 <a name="operator"> </a> 
 **операторе** снимка экрана это необязательный вариант (но рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-132">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png)
<a name="operator"> </a>
**Operator** This is optional (but recommended).</span></span> <span data-ttu-id="9ffd8-133">Вы можете настроить параметр **оператора** , чтобы разрешить звонящим выйти из меню и поговорить с определенным человеком.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

<span data-ttu-id="9ffd8-134">Клавиша 0 назначается оператору по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-134">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="9ffd8-135">Если вы установили оператора, сообщите пользователям, которые вызывают этот параметр в **меню "изменить** " на странице " **поток звонка** ".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-135">If you set an Operator, tell people who call about the option in **Edit menu options** on the **Call flow** page.</span></span> <span data-ttu-id="9ffd8-136">Если вы настроили оператор для автосекретаря, введите соответствующий текст подсказки в поле **вызывающий абоненты** или измените звуковой файл таким образом, чтобы он включал этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-136">If you set an operator on your auto attendant, you enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="9ffd8-137">Например, "Чтобы связаться с оператором, нажмите ноль".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-137">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="9ffd8-138">Есть несколько способов задания оператора:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-138">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="9ffd8-139">**Оператор "нет** " отключает параметр "оператор" и "нажать 0".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-139">**No operator** disables the "Operator" and "Press 0" options.</span></span> <span data-ttu-id="9ffd8-140">Это текущее значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-140">This is the current default.</span></span>
- <span data-ttu-id="9ffd8-141">**Сотрудник вашей организации** назначил сотруднику лицензии на телефонную систему, для которой разрешена Корпоративная голосовая связь или назначенные планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-141">**Person in your organization** assigns a person with a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9ffd8-142">Вы также можете настроить его таким образом, чтобы вызывающий абонент отправлялся на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-142">You can also set it up so the caller is sent to voicemail.</span></span> <span data-ttu-id="9ffd8-143">Чтобы отправить абоненту голосовой почты, выберите его **в своей организации** и настройте параметры учетной записи, чтобы отправлять звонки прямо в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-143">To send a caller to voicemail, select **Person in your organization** and set that account's settings to send calls directly to voicemail.</span></span>

     > [!Note]
     > <span data-ttu-id="9ffd8-144">Пользователь **в вашей организации** может быть пользователем в сети или локальным пользователем с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-144">**Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

- <span data-ttu-id="9ffd8-145">**Функция голосовой связи**  Выберите имя учетной записи ресурса, связанной с автоматическим ассистентом или уже созданной очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-145">**Voice Feature**  Select the name of the resource account linked to an auto attendant or call queue that has already been created.</span></span> <span data-ttu-id="9ffd8-146">Вызывающие абоненты, которые запрашивают оператора, перенаправлены там.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-146">Callers that request an operator are redirected there.</span></span>  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * * 

<span data-ttu-id="9ffd8-147">![Значок с цифрой 3, вызываемый в предыдущем часовом](media/teamscallout3.png)<a name="timezone"> </a>  
 **поясе** снимка экрана, необходимо указать часовой пояс для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-147">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png)<a name="timezone"> </a> 
**Time zone** You are required to set the time zone for your auto attendant.</span></span> <span data-ttu-id="9ffd8-148">Этот параметр может быть таким же, как часовой пояс основного адреса, указанного в вашей организации, или другой часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-148">The setting can be the same as the time zone of the main address listed for your organization, or a different time zone.</span></span> <span data-ttu-id="9ffd8-149">Каждый автоматический секретарь может иметь другой часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-149">Each auto attendant can have a different time zone.</span></span> <span data-ttu-id="9ffd8-150">Часы, заданные для автосекретаря, также используются в этом часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-150">The business hours set for the auto attendant also use this time zone.</span></span>

* * *

<span data-ttu-id="9ffd8-151">![Значок с цифрой 4, вызываемый на предыдущем](media/teamscallout4.png)
 <a name="language"> </a> 
 **языке** снимка экрана, выберите язык, который вы хотите использовать для автоматического ассистента.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-151">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)
<a name="language"> </a>
**Language** Select the language that you want to use for your auto attendant.</span></span> <span data-ttu-id="9ffd8-152">Автосекретарь использует этот язык для вызывающих абонентов, и все системные запросы воспроизводится на этом языке.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-152">The auto attendant uses that language with callers, and all system prompts are played in this language.</span></span>

 * * *

<span data-ttu-id="9ffd8-153">![Значок числа 5, вызываемый на предыдущем снимке экрана](media/teamscallout5.png)
, включает распознавание**голоса голосового ввода** , если выбран этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-153">![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png)
**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="9ffd8-154">Вызывающие абоненты могут использовать голосовые данные на выбранном [вами языке](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-154">Callers can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="9ffd8-155">Если вы хотите разрешить другим пользователям использовать клавиатуру телефона только для выбора, вы можете оставить параметр "распознавание речи" **выключенным**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-155">If you want to only let people use their phone keypad to make selections, you can leave speech recognition set to **Off**.</span></span>

* * *  

<span data-ttu-id="9ffd8-156">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-156">When you finish with your selections, click **Next**.</span></span>

#### <a name="call-flow"></a><span data-ttu-id="9ffd8-157">Поток звонков</span><span class="sxs-lookup"><span data-stu-id="9ffd8-157">Call flow</span></span>

<span data-ttu-id="9ffd8-158"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="9ffd8-158"></span></span>

> [!TIP]
> <span data-ttu-id="9ffd8-159">Вы можете настроить собственное расписание рабочих часов, используя другие режимы работы с потоком звонков в рабочее время и после него.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-159">You can choose to set up a custom business hours schedule, with different call flow behaviors during and after business hours.</span></span> <span data-ttu-id="9ffd8-160">Чтобы задать настраиваемое расписание, настройте необязательный [поток звонков в течение часа](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-160">To set a custom schedule, set the optional [Call flow for after hours](#call-flow-for-after-hours).</span></span> <span data-ttu-id="9ffd8-161">По умолчанию автосекретарь использует потоки звонков в рабочих часах.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-161">By default, an auto attendant uses business hours call flows.</span></span>

<span data-ttu-id="9ffd8-162">Вы можете настроить пользовательские приветствия, подсказки и меню, которые будут слышать пользователи, когда они попадут в свой автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-162">You can set up customized greetings, prompts, and menus that people hear when they reach your auto attendant.</span></span>

![Снимок экрана: раздел приветствия «обработка звонков»](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

<span data-ttu-id="9ffd8-164">**Начало воспроизведения сообщения приветствия** Приветствие не является обязательным, и его можно настроить на **запрет приветствий**, **Воспроизвести звуковой файл**или **ввести сообщение приветствия**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-164">**First play a greeting message** A greeting is optional and can be set to **No greeting**, **Play an audio file**, or **Type a greeting message**.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffd8-165">Приветствие является наиболее ценным для автоматического ассистента первого уровня.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-165">A greeting is most valuable for a first-level auto attendant.</span></span> <span data-ttu-id="9ffd8-166">Для вложенных автосекретарей часто не требуется приветствие.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-166">A nested auto attendant often doesn't need a greeting.</span></span>

<span data-ttu-id="9ffd8-167">![Значок с номером 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) если вы выберете **Приветствие**, вызывающий абонент не услышит сообщение или приветствие до тех пор, пока звонок не будет обработан одним из действий, выбранных позже.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-167">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) If you select **No Greeting**, the caller doesn't hear a message or greeting before the call is handled by one of the actions you select later.</span></span> 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

<span data-ttu-id="9ffd8-168">![Значок числа 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) если выбрать команду **Воспроизвести звуковой файл** , вы можете использовать кнопку **Добавить файл** , чтобы добавить записанное приветствие, сохраненное в виде звукового файла. WAV,. MP3 или. Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-168">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="9ffd8-169">Размер записи не может превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-169">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="9ffd8-170">![Значок с номером 3, выноска на предыдущем снимке экрана](media/teamscallout3.png) **Введите сообщение приветствия** , если выбрать этот вариант, введите текст, который будет отображаться в системе (до 1000 символов) в указанном поле.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-170">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="9ffd8-171">Например, введите фразу "Добро пожаловать в Contoso".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-171">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="9ffd8-172">Ваш звонок очень важен для нас."</span><span class="sxs-lookup"><span data-stu-id="9ffd8-172">Your call is important to us."</span></span> <span data-ttu-id="9ffd8-173">Выходные данные создаются программой "текст на голос".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-173">Output is created by text-to-voice software.</span></span>

* * *


<span data-ttu-id="9ffd8-174">Вы можете выбрать, что будет происходить рядом с вызовами из указанных ниже действий в разделе " **Перенаправление вызова"** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-174">You can select what happens next to calls from the following actions in the  **Then route the call** section.</span></span> <span data-ttu-id="9ffd8-175">Параметры: **Отключение**, **переадресация звонков**и **Параметры меню "воспроизведение**".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-175">Settings are **Disconnect**, **Redirect call**, or **Play menu options**.</span></span>

<span data-ttu-id="9ffd8-176">Если выбрать команду **Отключить**, вызывающий абонент отключится после воспроизведения приветствия.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-176">If you select **Disconnect**, the caller is disconnected after the greeting plays.</span></span> 

<span data-ttu-id="9ffd8-177"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="9ffd8-177"></span></span>

<span data-ttu-id="9ffd8-178">![Значок с номером 4, выноска в предыдущем](media/teamscallout4.png) **вызове переадресации** снимка экрана отправляет вызывающему объекту выбранное место назначения, не выбирая параметры.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-178">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png) **Redirect call** sends the caller to the chosen destination without choosing from options.</span></span> <span data-ttu-id="9ffd8-179">Возможны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-179">The possible settings are:</span></span>

  - <span data-ttu-id="9ffd8-180">**Пользователь в Организации** Для вашей учетной записи должна быть включена лицензия на телефонную систему для корпоративной голосовой связи или назначенный план звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-180">**Person in organization** The account you choose must have a Phone System license enabled for Enterprise Voice or have an assigned Calling Plan in Office 365.</span></span> <span data-ttu-id="9ffd8-181">Вы можете настроить его таким образом, чтобы вызывающий абонент мог отправлять голосовую почту: выберите **абонента в Организации** и настройте для этой учетной записи переадресацию звонков прямо в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-181">You can set it up so the caller can be sent to voicemail: select **Person in organization** and set that account to have calls forwarded directly to voicemail.</span></span>

  > [!Note]
  > <span data-ttu-id="9ffd8-182">**Сотрудник Организации** может быть пользователем в сети или локальным пользователем с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-182">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

  - <span data-ttu-id="9ffd8-183">**Голосовое приложение** Выберите автосекретарь или очередь звонков, которые уже настроены.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-183">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="9ffd8-184">Вы ищете автосекретарь или очередь звонков по имени учетной записи ресурса, связанной с этой службой.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-184">You search for the auto attendant or call queue by the name of the resource account associated with the service.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant.
- **Call queue** Select the name of an auto attendant that has already been created.
- **External phone number** routes the caller to a phone number outside your local system.
- **Operator** directs the call to a user you designate as an Operator. If you haven't previously set up an operator, an option to create one now shows up. The 0 key is assigned to Operator by default. Options for setting an Operator are:

  - **No operator** disables the "Operator" and "Press 0" options.
  - **Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server. They must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Search for the operator in the **Destination for your operator** field.
  - **Auto attendant** lets you choose the name of an existing auto attendant.
  - **Call queue** lets you select an existing call queue.
  - **Group Voicemail** routes the call to a voicemail box that you select. -->

 * * *

![Снимок экрана: раздел "Обработка звонков" в разделе "действия страницы"](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

<span data-ttu-id="9ffd8-186">![Значок с номером 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) при выборе **пункта меню "воспроизвести** " вы можете выбрать, нужно ли использовать звуковой файл, или ввести текст, который будет отображаться как текст в речь, чтобы придать параметрам меню панель набора номера для вызывающих клавиш.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-186">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) When you select **Play menu options** You can select whether to use an audio file or enter text that will be rendered as text to speech to give dialpad menu options to callers.</span></span> <span data-ttu-id="9ffd8-187">Выберите этот параметр вместо параметра **перенаправить** или **Отключить** вызов.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-187">Select this instead of the **Redirect call to** or **Disconnect** options.</span></span>


<span data-ttu-id="9ffd8-188">![Значок цифры 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) **Воспроизведение звуковых файлов** позволяет настроить запросы и параметры для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-188">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Play an audio file** lets you set up a prompts and options for the caller to choose.</span></span> 
- <span data-ttu-id="9ffd8-189">Если выбрать команду **Воспроизвести звуковой файл** , вы можете использовать кнопку **Добавить файл** , чтобы отправить записанное приветствие, сохраненное в виде звукового файла. WAV,. MP3 или. Формат WMA.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-189">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="9ffd8-190">Размер записи не может превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-190">The recording can be no larger than 5 MB.</span></span>

- <span data-ttu-id="9ffd8-191">**Ввод сообщения приветствия** Если выбрать этот параметр, введите текст, который система должна прочитать (до 1000 символов) в указанном поле.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-191">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="9ffd8-192">Например, введите фразу "Добро пожаловать в Contoso".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-192">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="9ffd8-193">Ваш звонок очень важен для нас."</span><span class="sxs-lookup"><span data-stu-id="9ffd8-193">Your call is important to us."</span></span> <span data-ttu-id="9ffd8-194">Выходные данные создаются программой "текст на голос".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-194">Output is created by text-to-voice software.</span></span>

<span data-ttu-id="9ffd8-195">**Настройка параметров меню** В этом диалоговом окне можно добавить или удалить клавиатуру телефона или голосовые команды.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-195">**Set menu options** Telephone keypad or voice commands can be added or removed in this dialog.</span></span> <span data-ttu-id="9ffd8-196">Чтобы удалить параметр меню, удалите запись голосовых команд и **Задайте для параметра** **Перенаправление** назад.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-196">To delete a menu option, remove the voice command entry and set **Redirect to** back to **Select**.</span></span>

> [!TIP]
> <span data-ttu-id="9ffd8-197">Обновите текст подсказки в меню или заново Запишите звуковые запросы при удалении параметров.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-197">Update menu prompt text or re-record the audio prompts when you remove options.</span></span> <span data-ttu-id="9ffd8-198">Приглашение меню, которое воспроизводится для вызывающих абонентов, не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-198">The menu prompt played for callers isn't automatically updated.</span></span>  
>
> <span data-ttu-id="9ffd8-199">Любые параметры меню можно добавлять и удалять в любом порядке, при этом сопоставления клавиш необязательно должны быть последовательными.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-199">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="9ffd8-200">Например, можно создать меню с помощью сопоставления с параметрами клавиш 0, 1 и 3, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-200">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffd8-201">Клавиши \* (повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-201">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="9ffd8-202">Если включен параметр распознавания речи, нажатие клавиши \* соответствует голосовой команде "Повтор", а нажатие клавиши # — голосовой команде "Назад".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-202">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

![Значок цифры 3, выноска на предыдущем снимке экрана](media/teamscallout3.png)

<span data-ttu-id="9ffd8-204">Чтобы настроить параметр меню, щелкните **+ Назначение клавиши вызова** и введите сведения о следующих параметрах:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-204">To set up a menu option, click on the  **+Assign a dial key** and enter information for the following options:</span></span>

![Значок цифры 4, выноска на предыдущем снимке экрана](media/teamscallout4.png) 

<span data-ttu-id="9ffd8-206">В столбце **голосовых команд** для параметра можно указать до 64 знаков и может содержать несколько слов, таких как "Обслуживание клиентов" или "операции и причины".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-206">**Voice command** column for an option can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="9ffd8-207">Если включено распознавание речи, имя автоматически распознается, и вызывающий абонент может нажать 3, скажите "три" или скажите "Обслуживание клиентов", чтобы выбрать вариант, сопоставленный с клавишей 3.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-207">If speech recognition is enabled, the name is automatically recognized, and the caller is able to press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>

<span data-ttu-id="9ffd8-208">![Значок числа 5, выноска на предыдущем снимке экрана](media/teamscallout5.png) . параметр **перенаправить на** место, на котором помещается вызов при нажатии соответствующей клавиши или выбран параметр с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-208">![Icon of the number 5, a callout in the previous screenshot](media/teamscallout5.png) The **Redirect to** option sets where the call goes if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="9ffd8-209">Кому можно направить вызов:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-209">The call can be sent to:</span></span>

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- <span data-ttu-id="9ffd8-210">**Operator (оператор** ) Если оператор уже настроен, параметр автоматически сопоставляется с ключом 0, но его также можно удалить или переназначить другим ключом.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-210">**Operator** If an operator is already set up, the option is automatically mapped to key 0, but can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="9ffd8-211">Вызывающий абонент, который выбрал этот параметр, отправляется назначенному оператору.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-211">The caller who selects this option is sent to the designated Operator.</span></span> <span data-ttu-id="9ffd8-212">Если оператор если не установлен ни в один ключ, голосовая команда "оператор" также отключается.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-212">If Operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 
- <span data-ttu-id="9ffd8-213">**Сотрудник Организации** может быть пользователем в сети или локальным пользователем с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-213">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="9ffd8-214">У пользователя должна быть лицензия на телефонную систему, для которой включена Корпоративная голосовая связь или назначенные планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-214">The user must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="9ffd8-215">Найдите пользователя в поле **Поиск по имени** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-215">Search for the person in the **Search by name** field.</span></span>

  - <span data-ttu-id="9ffd8-216">**Голосовое приложение** Выберите автосекретарь или очередь звонков, которые уже настроены.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-216">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="9ffd8-217">Вы ищете автосекретарь или очередь звонков по имени учетной записи ресурса, связанной с приложением.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-217">You search for the auto attendant or call queue by the name of the resource account associated with the application.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![Значок числа 6, выноска на предыдущем снимке экрана](media/teamscallout6.png) 

<span data-ttu-id="9ffd8-219">**Поиск в каталоге** В этом разделе вы можете включить функцию **набрать имя** и **позвонить по расширению** для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-219">**Directory search** In this section, you can enable **Dial by name** and **Dial by Extension** for the auto attendant.</span></span> <span data-ttu-id="9ffd8-220">Вы можете настроить пользователей, которые не включены в эти службы, на странице необязательной области набора номера.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-220">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="9ffd8-221">По умолчанию поиск в каталоге установлен на " **нет** ".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-221">Directory search is set to **None** by default.</span></span>

<span data-ttu-id="9ffd8-222">**Набрать номер по имени** Если вы включите этот параметр, вызывающие абоненты смогут искать пользователей в вашей организации с помощью **набора номера по имени**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-222">**Dial by name** If you enable this option, callers can search for people in your organization using **Dial by name**.</span></span> <span data-ttu-id="9ffd8-223">Говорят, что имя пользователя и распознавание голоса будут соответствовать пользователю.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-223">They say the user's name and voice recognition matches them to a user.</span></span> <span data-ttu-id="9ffd8-224">Вы можете настроить пользователей, которые не включены в эти службы, на странице необязательной области набора номера.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-224">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="9ffd8-225">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-225">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span>

<span data-ttu-id="9ffd8-226">**Позвони по расширению** Если вы включаете этот параметр, абоненты могут подключаться к пользователям в вашей организации, вводя их добавочные **номера, если вы настроили абонентскую группу, использующую расширения**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-226">**Dial by extension** If you enable this option, callers can connect with users in your organization by entering their phone extension **provided you have configured a Dial plan that uses extensions**.</span></span> <span data-ttu-id="9ffd8-227">Вы можете выбрать, какие пользователи перечислены как доступные или недоступные для **набора с помощью расширения** на странице необязательный диапазон.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-227">You can select which users are listed as available or not available for **Dial by extension** in the optional dial scope page.</span></span> <span data-ttu-id="9ffd8-228">Любой пользователь в сети с лицензией на телефонную систему или любой пользователь, размещенный в локальной среде Skype для бизнеса Server, является подходящим пользователем и может быть найден с помощью набора номера по расширению.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-228">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by extension.</span></span>

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

<span data-ttu-id="9ffd8-229">Завершив выбор, нажмите кнопку " **Далее** ", если вы хотите изменить дополнительные параметры, или кнопку " **Отправить** ", если вы хотите использовать параметры по умолчанию для таких действий, как:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-229">When you are finished with your selections, you can click **Next** if you want to change advanced settings, or click **Submit** if you want to use default settings for things like:</span></span>
- <span data-ttu-id="9ffd8-230">Поток звонков за часы</span><span class="sxs-lookup"><span data-stu-id="9ffd8-230">Call flow for after hours</span></span>
- <span data-ttu-id="9ffd8-231">Поток звонков для праздников</span><span class="sxs-lookup"><span data-stu-id="9ffd8-231">Call flow for holidays</span></span>
- <span data-ttu-id="9ffd8-232">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="9ffd8-232">Dial Scope</span></span>
- <span data-ttu-id="9ffd8-233">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="9ffd8-233">Resource accounts</span></span>

<span data-ttu-id="9ffd8-234">Так как для автосекретаря требуется наличие учетной записи ресурса, вы можете перейти на страницу **учетной записи ресурса** и связать уже настроенную учетную запись ресурса или создать учетную запись ресурса и связать ее с автоматическим для участников, описанных в разделе [Управление учетными записями ресурсов в Microsoft Teams](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-234">Since your auto attendant is required to have a resource account, you have a choice of proceeding to the **Resource account** page and associating a resource account you've already configured, or creating a resource account and associating it to the auto attendant as described in [Manage resource accounts in Microsoft Teams](manage-resource-accounts.md).</span></span> <span data-ttu-id="9ffd8-235">Вы не сможете использовать этот автосекретарь, пока не сопоставлены с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-235">You won't be able to use this auto attendant until it has been associated to a resource account.</span></span> <span data-ttu-id="9ffd8-236">для этого нажмите кнопку **Далее** в нижней части экрана, а затем выберите пункт **учетные записи ресурсов** на панели навигации слева, чтобы перейти прямо на страницу учетные записи ресурсов и связать автосекретарь с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-236">to do this, click the **Next** button at the bottom of the screen and then click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="advanced-settings-optional"></a><span data-ttu-id="9ffd8-237">Дополнительные параметры (необязательно)</span><span class="sxs-lookup"><span data-stu-id="9ffd8-237">Advanced settings (optional)</span></span>

<span data-ttu-id="9ffd8-238">Имеется четыре дополнительных экрана, которые можно настраивать или оставлять по умолчанию по мере их выбора.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-238">There are four additional screens that you can configure or leave at defaults as you choose.</span></span>

##### <a name="call-flow-for-after-hours"></a><span data-ttu-id="9ffd8-239">Поток звонков за часы</span><span class="sxs-lookup"><span data-stu-id="9ffd8-239">Call flow for after hours</span></span>

<span data-ttu-id="9ffd8-240">По умолчанию для рабочего времени автосекретаря задано значение 9am-5pm, понедельник — пятница</span><span class="sxs-lookup"><span data-stu-id="9ffd8-240">By default, an auto attendant's business hours are set to 9am-5pm, Monday to Friday</span></span>  <!--24/7--><span data-ttu-id="9ffd8-241">и параметры потока звонков для вызовов *после часа* отключаются, так как все часы рассматриваются как *Рабочие часы*.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-241">, and the call flow options for *after hours* calls are disabled because all hours are considered *business hours*.</span></span> <span data-ttu-id="9ffd8-242">После выбора параметра **Настройка настраиваемых часов рабочего времени** на странице " **поток звонков за часы** " настраиваются правила обработки звонков, используемые автосекретарем после часов.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-242">When you select the **Setup custom business hours** option, the **Call flow for after hours** page configures the call handling rules used by the auto attendant after hours.</span></span> <span data-ttu-id="9ffd8-243">Доступные параметры совпадают, разница — это возможность задания расписания для разных меню и поведения.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-243">The options available are the same, the difference is the ability to set a schedule for different menus and behaviors.</span></span>

<span data-ttu-id="9ffd8-244">Системам автосекретарей может потребоваться установить только после часов обработки звонков для автосекретаря первого уровня.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-244">A system of auto attendants may only need to set after hours call handling behavior for the first-level auto attendant.</span></span> <span data-ttu-id="9ffd8-245">Вложенные автосекретарей могут даже не вызываться автосекретарем первого уровня, но, как следствие, система может определять поведение в любое время после каждого используемого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-245">Nested auto attendants may not even be called by the first-level auto attendant, but alternately the system can define after-hours behavior for each auto attendant it uses.</span></span>

<span data-ttu-id="9ffd8-246">Изначально рабочие часы задаются для начала в 12:00 AM и заканчиваются в 12:00 PM, Воскресенье – Суббота.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-246">Initially, the business hours are defined to start at 12:00 am and end at 12:00 pm, Sunday through Saturday.</span></span> <span data-ttu-id="9ffd8-247">Все часы, недоступные в рабочее время, рассматриваются по *истечении часов*.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-247">All hours that aren't during business hours are considered *after hours*.</span></span>


![снимок экрана: параметры потока вызова после часа](media/aa-afterhour.png)
 * * *

<span data-ttu-id="9ffd8-249">![Значок с цифрой 1, выноска на предыдущем снимке](media/teamscallout1.png) экрана. Вы можете нажать кнопку **выбрать 24/7** , чтобы сделать все часы в рабочее время для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-249">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) You can click **Select 24/7** to make all hours business hours for this auto attendant.</span></span>

<span data-ttu-id="9ffd8-250">![Значок числа 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) . Выберите параметр **восстановить по умолчанию** , чтобы отменить все изменения в расписании, и вернитесь к определению по умолчанию для рабочих часов в формате 9:00 – 5:00 PM с понедельника по пятницу.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-250">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) Select the **Reset to default** option to revert all changes in the schedule and return to the default definition of business hours as 9:00 am to 5:00 pm Monday to Friday.</span></span>

<span data-ttu-id="9ffd8-251">![Значок с номером 3, выноска на предыдущем снимке экрана](media/teamscallout3.png) . для полного очистки расписания Выбери команду **Очистить все часы** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-251">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) Select **Clear all hours** to completely clear the schedule.</span></span> <span data-ttu-id="9ffd8-252">Выбор этого параметра и выход из него не рекомендуются, поэтому используйте этот параметр только в том случае, если вы хотите полностью восстановить рабочее время.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-252">Selecting this and leaving the hours unset is not recommended, so use this option only if you want to completely redo your business hours.</span></span>

<span data-ttu-id="9ffd8-253">![Значок с номером 4,](media/teamscallout4.png)![выноска на предыдущем значке снимка экрана с номером 5, выноской на предыдущем снимке](media/teamscallout5.png) экрана, чтобы настроить время начала или окончания для дня недели, выберите **начать с** или **завершить в** момент, когда вы хотите сбросить и Выберите новое время в появившемся списке.  </span><span class="sxs-lookup"><span data-stu-id="9ffd8-253">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)  ![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png) To customize start or end time for a day of the week, click on **Start at** or **End at** time you wish to reset and select the new time from the list that appears.</span></span> <span data-ttu-id="9ffd8-254">Этот список позволяет выбрать рабочие часы в 15 минутных интервалах, а также указать часы, которые вы выбираете, зависят от часового пояса, заданного на странице **Общие сведения** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-254">The list allows you to select business hours in 15-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span>

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

<span data-ttu-id="9ffd8-255">![Значок числа 6, выноска на предыдущем снимке экрана](media/teamscallout6.png) для настройки перерыва (например, перерыва на обед), выберите команду **Добавить новое время** для этого дня недели, чтобы создать строку таблицы заново, и выберите новое время начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-255">![Icon of the number 6,  a callout in the previous screenshot](media/teamscallout6.png)  To set up a break (a lunch break, for example), select **Add new time** for that day of the week to create anew table row, and select new start and end times.</span></span> <span data-ttu-id="9ffd8-256">Вы можете настроить несколько перерывов в рабочих часах.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-256">You can set multiple breaks within business hours.</span></span>

<span data-ttu-id="9ffd8-257">Параметры [потока звонков](#call-flow) , доступные после часов, совпадают с параметрами, доступными в часах в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-257">The [Call flow](#call-flow) options available after hours are the same as the options available during business hours.</span></span> <span data-ttu-id="9ffd8-258">Прокрутите страницу "информационное поле", чтобы настроить параметры потока звонка после часов.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-258">Scroll down on the information entry page to set after hours call flow options.</span></span>

* * *

<span data-ttu-id="9ffd8-259">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-259">When you are finished with your selections, click **Next**.</span></span> <span data-ttu-id="9ffd8-260">Вы также можете щелкнуть **учетные записи ресурсов** на панели навигации слева, чтобы перейти прямо на страницу учетные записи ресурсов и связать его с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-260">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

##### <a name="call-flow-during-holidays"></a><span data-ttu-id="9ffd8-261">Поток звонка во время праздников</span><span class="sxs-lookup"><span data-stu-id="9ffd8-261">Call flow during holidays</span></span>

<span data-ttu-id="9ffd8-262"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="9ffd8-262"></span></span>

<span data-ttu-id="9ffd8-263">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-263">You can add up to 20 scheduled holidays to each auto attendant.</span></span> <span data-ttu-id="9ffd8-264">Возможно, в вашей организации уже определены праздники, как описано в разделе [Настройка праздников в Microsoft Teams](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd8-264">Your organization may already have defined holidays as described in [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="9ffd8-265">Если вы видите следующий экран, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-265">If not you will see the following screen:</span></span> 

![Снимок экрана: нет настроенных праздников](media/aa-no-holidays.png)

<span data-ttu-id="9ffd8-267">![Значок с номером 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) чтобы задать настраиваемый поток звонков для праздника в автосекретаря, нажмите кнопку **+ Добавить** , чтобы открыть экран **новый поток звонка** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-267">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To set a custom call flow for a holiday on the auto attendant, click **+ Add** the see the **New holiday call flow** screen.</span></span>
> [!TIP]
> <span data-ttu-id="9ffd8-268">Для создания праздников вы можете перейти на экран в**праздничные дни** **настройки** > .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-268">To create Holidays you can  go to the screen at **Org-wide settings** > **Holidays**.</span></span>  



![Снимок экрана: Добавление обработчика вызова](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

<span data-ttu-id="9ffd8-270">![Значок цифры 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) введите **имя** для нового потока звонка.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-270">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png)  Enter a **Name** for your new call flow.</span></span>

<span data-ttu-id="9ffd8-271">![Значок цифры 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) если вы уже создали праздники, вы увидите их в раскрывающемся меню **праздников** и можете выбрать их.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-271">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you've already created holidays, you'll see them in the **Holiday** pull-down menu and can select them.</span></span> <span data-ttu-id="9ffd8-272">Возможно, вы видите неиспользуемый параметр, который можно редактировать в нужном для вас виде.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-272">You might see an unused option that you can edit into what you need.</span></span> <span data-ttu-id="9ffd8-273">В противном случае нажмите кнопку **Добавить** в нижней части раскрывающегося списка, чтобы создать новый праздник.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-273">If not, click on **Add** at the bottom of the pull-down list to create a new Holiday.</span></span>  <span data-ttu-id="9ffd8-274">Инструкции по созданию праздников можно найти [в разделе Настройка праздников в Microsoft Teams](set-up-holidays-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-274">See [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md) for the steps used to create a holiday.</span></span> 

<span data-ttu-id="9ffd8-275">Имя потока праздников может иметь длину до 64 символов и должно быть уникальным для Организации.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-275">A holiday call flow name can be up to 64 characters long and must be unique for the organization.</span></span> <span data-ttu-id="9ffd8-276">Например, в одной организации не может быть двух потоков звонков с праздниками.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-276">For example, you can't have two holiday call flows named "Thanksgiving" in the same organization.</span></span> <span data-ttu-id="9ffd8-277">У автосекретаря может быть поток звонков для каждого настроенного праздника, но вам может понадобиться создать распространенный набор поведения, отличный от настроенного приветствия.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-277">Your auto attendant can have a call flow for each Holiday you've set up, but you might want to have a common set of behaviors planned other than a customized greeting.</span></span>

<span data-ttu-id="9ffd8-278">![Значок с номером 3, выноска на предыдущем снимке экрана](media/teamscallout3.png) параметры [приветствия](#call-flow) , доступные для потока праздников, совпадают с параметрами, доступными в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-278">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) The [Greetings](#call-flow) options available for a holiday call flow are the same as the options available during business hours.</span></span> <span data-ttu-id="9ffd8-279">**Действия** , выполненные после воспроизведения приветствия, также похожи на то, за исключением того, что вы можете **отключаться** или **перенаправляться**, а также при выборе параметра **перенаправить** оператор не один из доступных вариантов. .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-279">The **Actions** performed after the greeting plays is also similar, except that the only available actions are to **Disconnect** or **Redirect to**, and when choosing the **Redirect to** option the Operator is not one of the available choices.</span></span> <span data-ttu-id="9ffd8-280">Вы не можете настроить меню для определенного потока праздников.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-280">You can't set up a menu specific to a Holiday flow.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffd8-281">По умолчанию все вызовы, полученные в течение праздничного периода, задаются как **Отключенные** после приветствия (если есть), поэтому необходимо указать переадресацию, если вы хотите настроить поведение.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-281">By default, all calls received during a holiday period are set to **Disconnect** after the greeting (if any), so you must specify a redirect if you want a custom behavior.</span></span>

![Снимок экрана: "потоки звонка на странице праздников"](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

<span data-ttu-id="9ffd8-283">Нажмите кнопку Сохранить, чтобы завершить создание потока звонка.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-283">Click on Save to finish creating the Holiday call flow.</span></span> <span data-ttu-id="9ffd8-284">После того как вы создадите поток звонка, он будет отображаться на экране " **потоки звонков во время праздников** ".</span><span class="sxs-lookup"><span data-stu-id="9ffd8-284">Once you have created a Holiday call flow, it will show up on the **Call Flows during holidays** screen.</span></span>

<span data-ttu-id="9ffd8-285">Нажмите кнопку **Далее** , чтобы настроить область набора номера, **назад** , чтобы внести изменения после почасового звонка, и **отправьте** его, если вы закончите.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-285">Click on **Next** to set Dial scope, **Back** to make changes to after hour call flows, and **Submit** if you are finished.</span></span> <span data-ttu-id="9ffd8-286">Вы также можете щелкнуть **учетные записи ресурсов** на панели навигации слева, чтобы перейти прямо на страницу учетные записи ресурсов и связать его с учетной записью ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-286">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="dial-scope"></a><span data-ttu-id="9ffd8-287">Область набора номера</span><span class="sxs-lookup"><span data-stu-id="9ffd8-287">Dial scope</span></span>

<span data-ttu-id="9ffd8-288"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="9ffd8-288"></span></span>

![Снимок экрана, на котором показана страница "область набора номера"](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

<span data-ttu-id="9ffd8-290">На этой странице вы можете указать, какие пользователи будут указаны в каталоге и будут доступны для звонков по имени, когда человек звонит в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-290">On this page, you can set who is listed in your directory and available for Dial by Name when a person calls your organization.</span></span> <span data-ttu-id="9ffd8-291">По умолчанию для набора номера по имени задано значение **Off** на более раннем экране.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-291">Dial by name is set to **Off** by default in an earlier screen.</span></span> <span data-ttu-id="9ffd8-292">Если вы создали абонентские группы, все пользователи с расширением будут доступны, если ранее было выбрано **расширение набора номера** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-292">If you have created Dial plans, all users with an extension will be available if **Dial by extension** was selected earlier.</span></span>

<span data-ttu-id="9ffd8-293">![Значок с цифрой 1, выноска на предыдущем снимке](media/teamscallout1.png) экрана **содержит** параметры, описанные в этом разделе, — либо **все пользователи в сети** , либо **пользовательские группы пользователей** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-293">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) **Include** The options in this section are either **All online users** or **Custom user groups**</span></span>

<span data-ttu-id="9ffd8-294">Если вы выберете **все пользователи в сети**, в поиск в каталоге будут включены все подходящие пользователи.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-294">If you select **All online users**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="9ffd8-295">**Пользовательские группы пользователей** Этот параметр позволяет найти и выбрать группу Office 365, список рассылки или группу безопасности, уже созданную в Организации.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-295">**Custom user groups** This option lets you search for and select an Office 365 Group, distribution list, or security group already created in your organization.</span></span> <span data-ttu-id="9ffd8-296">Пользователи добавляются в каталог, если они находятся в выбранной группе Office 365, списке рассылки или группе безопасности, и они являются **сетевыми пользователями с лицензией на телефонную систему** или размещены в локальной среде с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-296">Users are added to the directory if they are in the chosen Office 365 Group, distribution list, or security group and they are **Online users with a Phone System license** or hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="9ffd8-297">Вы можете добавить в каталог несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-297">You can add multiple Office 365 Groups, distribution lists, and security groups to the directory.</span></span>



<span data-ttu-id="9ffd8-298">![Значок цифры 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) : параметры, описанные в этом разделе, позволяют исключить определенных пользователей или группы пользователей из каталога организации. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ffd8-298">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Exclude** The options in this section let you exclude specific users or groups of users from the organization's directory.</span></span>

<span data-ttu-id="9ffd8-299">Если выбрать вариант **нет**, в поиск в каталоге будут включены все подходящие пользователи.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-299">If you select **None**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="9ffd8-300">**Настраиваемая группа пользователей** Вы можете найти группу Office 365, список рассылки или группу безопасности, созданную в Организации.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-300">**Custom user group** You can search for an Office 365 Group, distribution list, or security group that has been created in your organization.</span></span> <span data-ttu-id="9ffd8-301">Пользователи из этой группы будут исключены из поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-301">Users in that group are excluded from directory search.</span></span> <span data-ttu-id="9ffd8-302">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-302">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>


<span data-ttu-id="9ffd8-303">Если вы оставите настройки по умолчанию при включенном наборе номера по имени, все подходящие пользователи включаются в поиск в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-303">If you leave settings at their default when Dial by Name is enabled, all eligible users are included in directory search.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffd8-304">Для нового пользователя в каталоге может потребоваться до 36 часов.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-304">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span> <span data-ttu-id="9ffd8-305">Если кто-то использует набор номера по имени с распознаванием речи, новые учетные записи могут быть недоступны для этой функции.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-305">When someone uses Dial by Name with speech recognition, new accounts may not be available for this feature.</span></span>

<span data-ttu-id="9ffd8-306">После ввода всех необходимых полей и настройки меню и параметров обработки звонков нажмите кнопку **Далее** , чтобы перейти к сопоставлению учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-306">After you enter all the required fields and set up call handling menus and options, click **Next** to proceed to associating a resource account.</span></span>

#### <a name="resource-accounts"></a><span data-ttu-id="9ffd8-307">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="9ffd8-307">Resource accounts</span></span>

<span data-ttu-id="9ffd8-308">У всех автосекретарей должна быть соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-308">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="9ffd8-309">Для автосекретарей первого уровня в определенном состоянии может потребоваться хотя бы одна учетная запись ресурса, у которой есть связанный служебный номер.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-309">First level auto attendants will definitely need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="9ffd8-310">При желании вы можете назначить несколько учетных записей ресурсов для автосекретаря, каждый из которых имеет отдельный номер Услуги.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-310">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="9ffd8-311">Если вы еще не настроили учетную запись ресурса для автоматического ассистента, появится следующий экран:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-311">If you haven't already configured a resource account to your auto attendant, you would see the following screen:</span></span> 

![снимок экрана: необязательное Управление учетными записями ресурсов](media/aa-ra-optional.png) 

<span data-ttu-id="9ffd8-313">![Значок с номером 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) чтобы добавить в автосекретарь одну или несколько существующих и неназначенных учетных записей ресурсов, нажмите кнопку **Добавить учетные записи** и выполните поиск и выберите их из предоставленных диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-313">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add one or more existing and unassigned resource accounts to the auto attendant, click **Add accounts** and search and select them from the provided dialogs.</span></span>

![снимок экрана: представление сводки нового участника](media/aa-assigned.png)

<span data-ttu-id="9ffd8-315">![Значок с номером 1, выноска на предыдущем снимке экрана](media/teamscallout1.png) для добавления дополнительной учетной записи ресурса нажмите кнопку **+ Добавить учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-315">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add an additional resource account, click on **+ Add account**.</span></span>

![Значок цифры 2, выноска на предыдущем снимке экрана](media/teamscallout2.png) <span data-ttu-id="9ffd8-317">Учетная запись ресурса или учетные записи, назначенные этому автосекретарьу, отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-317">The resource account or accounts assigned to this auto attendant are shown in a list.</span></span>

## <a name="edit-auto-attendants"></a><span data-ttu-id="9ffd8-318">Изменение автоматических ассистентов</span><span class="sxs-lookup"><span data-stu-id="9ffd8-318">Edit auto attendants</span></span>

<span data-ttu-id="9ffd8-319">После сохранения нового автосекретаря оно появится на странице **автосекретарьы** .</span><span class="sxs-lookup"><span data-stu-id="9ffd8-319">After you save your new auto attendant, it is listed on the **Auto attendants** page.</span></span> <span data-ttu-id="9ffd8-320">На этой странице вы можете быстро увидеть некоторые из настроенных параметров, включая имя, соответствующую учетную запись ресурса, язык и назначенный оператор.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-320">That page allows you to quickly see some of the options that you have set up, including the name, associated resource account, language, and assigned Operator.</span></span>

![снимок экрана: список участников](media/aa-list.png)

<span data-ttu-id="9ffd8-322">Если вы хотите изменить параметры автосекретаря, выберите автосекретарь, а затем на панели действий нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-322">If you want to change auto attendant settings, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="9ffd8-323">Создание автосекретаря с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ffd8-323">Create an auto attendant with Powershell</span></span>

<span data-ttu-id="9ffd8-324">Вы также можете использовать PowerShell для создания и настройки автоматических ассистентов.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-324">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="9ffd8-325">Ниже приведены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-325">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="9ffd8-326">New-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="9ffd8-326">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="9ffd8-327">Set-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="9ffd8-327">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ffd8-328">Get-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="9ffd8-328">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ffd8-329">Get-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="9ffd8-329">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ffd8-330">Remove-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="9ffd8-330">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="9ffd8-331">New-Ксаутоаттендантмену</span><span class="sxs-lookup"><span data-stu-id="9ffd8-331">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="9ffd8-332">New-Ксонлинеаудиофиле</span><span class="sxs-lookup"><span data-stu-id="9ffd8-332">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="9ffd8-333">New-Ксаутоаттенданткаллфлов</span><span class="sxs-lookup"><span data-stu-id="9ffd8-333">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="9ffd8-334">Export-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="9ffd8-334">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ffd8-335">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="9ffd8-335">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="9ffd8-336">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="9ffd8-336">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="9ffd8-337">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="9ffd8-337">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="9ffd8-338">Get-Ксаутоаттендантсуппортедтимезоне</span><span class="sxs-lookup"><span data-stu-id="9ffd8-338">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="9ffd8-339">New-КсаутоаттенданткаллхандлингассоЦиатион</span><span class="sxs-lookup"><span data-stu-id="9ffd8-339">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="9ffd8-340">Get-Ксаутоаттендантсуппортедлангуаже</span><span class="sxs-lookup"><span data-stu-id="9ffd8-340">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="9ffd8-341">Import-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="9ffd8-341">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="9ffd8-342">New-Ксаутоаттенданткаллаблинтити</span><span class="sxs-lookup"><span data-stu-id="9ffd8-342">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="9ffd8-343">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ffd8-343">More about Windows PowerShell</span></span>

- <span data-ttu-id="9ffd8-344">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-344">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9ffd8-345">С помощью Windows PowerShell вы можете управлять набором Office 365 и Microsoft Teams с помощью одной точки администрирования, которая позволяет упростить свою повседневную работу.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-345">With Windows PowerShell, you can manage Office 365 and Microsoft Teams from a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="9ffd8-346">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-346">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9ffd8-347">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9ffd8-347">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="9ffd8-348">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9ffd8-348">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="9ffd8-349">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например внесения изменений для нескольких пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="9ffd8-349">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as making setting changes for many users at once.</span></span> <span data-ttu-id="9ffd8-350">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9ffd8-350">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9ffd8-351">Управление Office 365 с помощью Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ffd8-351">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="9ffd8-352">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9ffd8-352">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="9ffd8-353">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9ffd8-353">Related topics</span></span>

[<span data-ttu-id="9ffd8-354">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="9ffd8-354">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="9ffd8-355">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="9ffd8-355">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="9ffd8-356">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="9ffd8-356">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="9ffd8-357">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="9ffd8-357">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="9ffd8-358">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="9ffd8-358">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="9ffd8-359">Пример для малого бизнеса: Настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="9ffd8-359">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
