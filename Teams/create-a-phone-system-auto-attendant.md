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
ms.openlocfilehash: 939d1ac17007e3d823b0588f9949330e24555449
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "35807538"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="4a448-103">Настройка облачного автосекретаря</span><span class="sxs-lookup"><span data-stu-id="4a448-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="4a448-104">Автосекретарь позволяет людям, которые могут позвонить в организацию, и переходить в систему меню, чтобы получить их в нужный отдел, очередь звонков, человека или оператор.</span><span class="sxs-lookup"><span data-stu-id="4a448-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="4a448-105">Вы можете создать автосекретарь для своей организации с помощью центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4a448-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="4a448-106">Чтобы создать автосекретарь, на панели навигации слева выберите пункт **Голосовая связь** , а затем —**Добавить новые** **ассистенты** > .</span><span class="sxs-lookup"><span data-stu-id="4a448-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="4a448-107">Если вы хотите узнать больше об автосекретарях, посмотрите, [что такое автосекретарь облака?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="4a448-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="4a448-108">Эта статья относится как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4a448-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="4a448-109">Этап 1: Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="4a448-109">Step 1 - Get started</span></span>

- <span data-ttu-id="4a448-110">Для связи с учетной записью ресурса необходимо наличие автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="4a448-111">Дополнительные сведения об учетных записях ресурсов и всех необходимых лицензиях смотрите [в разделе Управление учетными записями ресурсов в Teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="4a448-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="4a448-112">Чтобы перенаправить звонки на оператора или параметр меню, который является сетевым пользователем с лицензией на **телефонную систему** , вам потребуется включить их для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4a448-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="4a448-113">В разделе [Назначение лицензий на Skype для бизнеса](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) или [Назначение лицензий Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4a448-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="4a448-114">Вы также можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a448-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="4a448-115">Например, выполните указанные ниже действия.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="4a448-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="4a448-116">Шаг 2. Создание нового автосекретаря</span><span class="sxs-lookup"><span data-stu-id="4a448-116">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a448-117">Для каждого автосекретаря требуется наличие соответствующей [учетной записи ресурса](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="4a448-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="4a448-118">Сначала необходимо создать учетную запись ресурса, после чего вы сможете связать ее с автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="4a448-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4a448-119">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a448-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4a448-120">В \*\*\*\* > \*\*\*\* **центре администрирования Microsoft Teams**щелкните "автосекретарь" и выберите пункт " **+ создать**".</span><span class="sxs-lookup"><span data-stu-id="4a448-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="4a448-121">Страница "Общие сведения"</span><span class="sxs-lookup"><span data-stu-id="4a448-121">General info page</span></span>

![Снимок экрана: страница "мой секретарь"](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="4a448-124">**Имя** Введите понятное отображаемое имя вашего автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="4a448-125">Имя является обязательным и может содержать до 64 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="4a448-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="4a448-126">Оно будет указано в столбце **Имя** на вкладке **Автосекретари**.</span><span class="sxs-lookup"><span data-stu-id="4a448-126">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="4a448-128">**Учетная запись ресурса** Нажмите эту кнопку, чтобы выбрать одну или несколько учетных записей ресурсов для подключения к новому автосекретарею.</span><span class="sxs-lookup"><span data-stu-id="4a448-128">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="4a448-129">Для всех автосекретарей требуется соответствующая учетная запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="4a448-129">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="4a448-130">У учетной записи ресурса может быть номер телефона, связанный с учетной записью, но это может быть не так.</span><span class="sxs-lookup"><span data-stu-id="4a448-130">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="4a448-131">Автосекретарь верхнего уровня обычно имеет учетную запись ресурса с назначенным номером телефона, но вложенный автосекретарь (используемый в качестве меню уровня 2, к которому подключается автосекретарь первого уровня) может не иметь номера телефона, назначенного его учетной записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="4a448-131">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="4a448-p107">**Часовой пояс**. Укажите часовой пояс для функции автосекретаря. Он не обязательно должен совпадать с часовым поясом, соответствующим указанному для вашей организации основному адресу. Для каждого автосекретаря можно указать свой часовой пояс, на основе которого в каждом конкретном случае будут установлены соответствующие рабочие часы.</span><span class="sxs-lookup"><span data-stu-id="4a448-p107">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="4a448-136">**Language (язык** ) Выберите язык, который вы хотите использовать для автосекретаря, на любом из доступных языков.</span><span class="sxs-lookup"><span data-stu-id="4a448-136">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="4a448-137">Язык, установленный в этом разделе, — это язык, который будет использоваться автосекретарем для взаимодействия с пользователями, вызывающими этот автоматический секретарь, и все системные запросы будут воспроизводиться на этом языке.</span><span class="sxs-lookup"><span data-stu-id="4a448-137">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![Значок числа 5, на котором показана ссылка на выноску на предыдущем снимке экрана](media/sfbcallout5.png)

<span data-ttu-id="4a448-139">**Оператор**Это дополнительная функция, которая является необязательной для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-139">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="4a448-140">Тем не менее, вы можете настроить параметр **оператора** для абонентов, которые должны быть в курсе, чтобы пообщаться с человеком, чтобы он мог вам помочь.</span><span class="sxs-lookup"><span data-stu-id="4a448-140">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="4a448-141">Оператору автоматически назначается клавиша 0.</span><span class="sxs-lookup"><span data-stu-id="4a448-141">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="4a448-142">Если этот параметр настроен, вам нужно будет сообщить вызывающим абонентам о том, что он доступен в разделе **"Редактировать параметры меню"** на странице **"Обработка вызовов в рабочее время"**.</span><span class="sxs-lookup"><span data-stu-id="4a448-142">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="4a448-143">Если оператор для вашего автосекретаря настроен, вам необходимо ввести соответствующий текст подсказки в поле **"Текст для вызывающих абонентов"** или изменить звуковой файл с учетом этого параметра.</span><span class="sxs-lookup"><span data-stu-id="4a448-143">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="4a448-144">Например, "Чтобы связаться с оператором, нажмите ноль".</span><span class="sxs-lookup"><span data-stu-id="4a448-144">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="4a448-145">Для выбора в качестве оператора доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="4a448-145">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="4a448-146">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a448-146">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="4a448-147">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a448-147">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="4a448-148">Настроенная вами **очередь звонков** .</span><span class="sxs-lookup"><span data-stu-id="4a448-148">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="4a448-149">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-149">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="4a448-150">Для этого выберите сотрудника **в своей компании** и настройте звонки этого пользователя прямо в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-150">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![Значок числа 6 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout6.png)

<span data-ttu-id="4a448-152">**Включение голосового ввода** Если выбран этот параметр, распознавание речи доступно.</span><span class="sxs-lookup"><span data-stu-id="4a448-152">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="4a448-153">Пользователи, которые вызывают абонентов, могут использовать голосовые данные на указанном [вами языке](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4a448-153">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="4a448-154">Вы можете отключить распознавание речи, установив значение OFF, если вы хотите, чтобы пользователи могли использовать только клавиатуру телефона.</span><span class="sxs-lookup"><span data-stu-id="4a448-154">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="4a448-155">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4a448-155">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="4a448-156">Страница "рабочие часы"</span><span class="sxs-lookup"><span data-stu-id="4a448-156">Business hours page</span></span>

<span data-ttu-id="4a448-157">По умолчанию для рабочих часов задано значение 9am для 5pm, понедельника по пятницу.</span><span class="sxs-lookup"><span data-stu-id="4a448-157">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="4a448-158">Все часы, которые не включены в часы работы, считаются нерабочим временем.</span><span class="sxs-lookup"><span data-stu-id="4a448-158">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="4a448-159">Вы можете выбрать вариант **24/7** , чтобы сделать все часы в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="4a448-159">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="4a448-160">Если вы не выбрали параметр **выбрать 24/7** , на странице **Параметры звонка после набора часов** будет использоваться для настройки обработки звонков в рабочее время для автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-160">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![Снимок экрана: страница "рабочие часы"](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="4a448-163">По умолчанию для рабочих часов задано значение понедельник — пятница, 9:00 – 5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="4a448-163">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="4a448-164">Выберите команду **Очистить все часы** , чтобы отменить выбор всех часов в расписании.</span><span class="sxs-lookup"><span data-stu-id="4a448-164">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="4a448-165">Если выбрать вариант **восстановить значения по умолчанию**, в рабочее время будет восстановлено понедельник и пятница, 9:00 – 5:00 PM.</span><span class="sxs-lookup"><span data-stu-id="4a448-165">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="4a448-167">Чтобы изменить рабочие часы, выделите часы, которые нужно установить, с помощью календаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-167">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="4a448-168">В календаре вы можете выбрать рабочие часы в течение 30 минут, а также задать рабочие часы, которые вы выбираете в соответствии с часовым поясом, установленным на странице **Общие сведения** .</span><span class="sxs-lookup"><span data-stu-id="4a448-168">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="4a448-169">Чтобы задать перерыв, например обеденное время, отмените выбор соответствующих часов в календаре.</span><span class="sxs-lookup"><span data-stu-id="4a448-169">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="4a448-170">Вы можете настроить несколько перерывов в рабочих часах.</span><span class="sxs-lookup"><span data-stu-id="4a448-170">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="4a448-171">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4a448-171">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="4a448-172">Параметры звонков в рабочее время</span><span class="sxs-lookup"><span data-stu-id="4a448-172">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="4a448-173">Если вы используете настраиваемое расписание рабочих часов, вам также потребуется настроить функцию обработки звонков после рабочего времени с помощью страницы **Обработка звонков после нескольких часов** , и вы получите те же параметры, что и **параметры звонков в бизнес-часах**.</span><span class="sxs-lookup"><span data-stu-id="4a448-173">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="4a448-174">Вы можете настроить приветствия, подсказки и меню, которые будут слышать абоненты, вызывающие Звонок на номер телефона автосекретаря вашей организации в рабочие часы.</span><span class="sxs-lookup"><span data-stu-id="4a448-174">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="4a448-175">![Снимок экрана: раздел](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![приветствия "страница обработки звонков в рабочее время" в разделе "действия страницы" обработки звонков в бизнес-часах](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="4a448-175">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="4a448-177">**Приветствие** Приветствие в рабочее время не является обязательным и может иметь значение **без приветствия**.</span><span class="sxs-lookup"><span data-stu-id="4a448-177">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="4a448-178">В этом случае вызывающий абонент не прозвучит сообщение или приветствие до тех пор, пока вызов не будет обработан одним из выбранных вами действий.</span><span class="sxs-lookup"><span data-stu-id="4a448-178">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="4a448-179">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="4a448-179">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="4a448-180">**Без приветствия** При звонках на номер телефона автосекретаря не будет воспроизводиться приветствие.</span><span class="sxs-lookup"><span data-stu-id="4a448-180">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="4a448-181">**Загрузить аудиофайл** Если выбран этот параметр, запишите приветствие и загрузите полученный звуковой файл (в формате WAV, .mp3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="4a448-181">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="4a448-182">**Ввод сообщения приветствия** Если выбрать этот параметр, введите текст, который система должна прочитать (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="4a448-182">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="4a448-183">Например, можно ввести "Вас приветствует Contoso.</span><span class="sxs-lookup"><span data-stu-id="4a448-183">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="4a448-184">Ваш звонок очень важен для нас."</span><span class="sxs-lookup"><span data-stu-id="4a448-184">Your call is important to us."</span></span> <span data-ttu-id="4a448-185">в поле **Текст для вызывающих абонентов**.</span><span class="sxs-lookup"><span data-stu-id="4a448-185">in the **Callers will hear** box.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="4a448-187">Вы можете выбрать, как будут обрабатываться звонки, поступающие в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="4a448-187">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="4a448-188">Вы можете выбрать из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4a448-188">You can chose from the following actions:</span></span>

- <span data-ttu-id="4a448-189">**Отключить** Если выбран этот параметр, вызывающий абонент будет отключен после прослушивания приветствия в рабочее время.</span><span class="sxs-lookup"><span data-stu-id="4a448-189">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="4a448-190">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4a448-190">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="4a448-191">**Сотрудник компании** с лицензией на **телефонную систему** , для которой включена Корпоративная голосовая связь или назначенные планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a448-191">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="4a448-192">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-192">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="4a448-193">Для этого выберите сотрудника **в компании** и настройте для него переадресацию звонков прямо на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-193">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="4a448-194">**Сотрудникам компании** может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a448-194">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="4a448-195">Другой **Автоматический секретарь**</span><span class="sxs-lookup"><span data-stu-id="4a448-195">Another **Auto attendant**</span></span>

   <span data-ttu-id="4a448-196">Вы можете использовать существующий автоматический секретарь для создания второго уровня параметров меню, содержащих подменю.</span><span class="sxs-lookup"><span data-stu-id="4a448-196">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="4a448-197">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="4a448-197">These are called nested auto attendants.</span></span> <span data-ttu-id="4a448-198">Чтобы отправить звонок во вложенный автоматический секретарь, выберите сотрудника **в компании** и назначьте учетную запись ресурса, в которой уже есть соответствующий автоматический секретарь, или в том случае, если вы хотите связать его с автосекретарем после того, как вы закончите создавать этот автоматический секретарь.</span><span class="sxs-lookup"><span data-stu-id="4a448-198">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="4a448-199">**Параметры меню "воспроизведение** " можно также использовать для настройки подсказок для воспроизведений.</span><span class="sxs-lookup"><span data-stu-id="4a448-199">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="4a448-201">**Запрос меню** Чтобы создать главное меню, вы можете использовать функции преобразования текста в речь или загрузить звуковой файл (WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="4a448-201">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="4a448-202">Вы можете ввести запрос в поле **Настройка навигации по меню для вызывающих абонентов** или записать звуковой файл, например: "для продажи, произнесите или нажмите или произнесите 1.</span><span class="sxs-lookup"><span data-stu-id="4a448-202">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="4a448-203">Для служб нажмите или скажите 2.</span><span class="sxs-lookup"><span data-stu-id="4a448-203">For Services, press or say 2.</span></span> <span data-ttu-id="4a448-204">Для поддержки пользователей нажмите или скажите 3.</span><span class="sxs-lookup"><span data-stu-id="4a448-204">For Customer Support, press or say 3.</span></span> <span data-ttu-id="4a448-205">Для оператора нажмите или произнесите 0.</span><span class="sxs-lookup"><span data-stu-id="4a448-205">For the operator, press or say 0.</span></span> <span data-ttu-id="4a448-206">Чтобы снова услышать это меню, нажмите звездочку или произнесите команду "повторить" ".</span><span class="sxs-lookup"><span data-stu-id="4a448-206">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="4a448-207">**Ввод сообщения приветствия** Если вы выбрали этот параметр, введите текст, который будет считаться системой (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="4a448-207">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="4a448-208">**Добавление звукового файла** Если вы выбрали этот параметр, вам нужно будет записать приветствие, а затем загрузить звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="4a448-208">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="4a448-210">**Настройка параметров меню** Вы можете добавить или удалить параметры меню с помощью клавиш на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="4a448-210">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="4a448-211">Чтобы добавить параметр меню, нажмите клавишу **+ и назначьте клавишу набора номера**.</span><span class="sxs-lookup"><span data-stu-id="4a448-211">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="4a448-212">Ниже показана соответствующая строка параметров.</span><span class="sxs-lookup"><span data-stu-id="4a448-212">A corresponding row of options will appear below.</span></span> <span data-ttu-id="4a448-213">Чтобы удалить параметр меню, щелкните слева от соответствующей клавиши на клавиатуре и щелкните значок удаления выше.</span><span class="sxs-lookup"><span data-stu-id="4a448-213">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="4a448-214">Строка сопоставления клавиш будет удалена.</span><span class="sxs-lookup"><span data-stu-id="4a448-214">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="4a448-215">Вам потребуется обновить текст подсказки в меню или заново записать звук отдельно при добавлении к параметрам удаления, так как он не будет автоматически выполняться для этого запроса меню.</span><span class="sxs-lookup"><span data-stu-id="4a448-215">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="4a448-216">Любые параметры меню можно добавлять и удалять в любом порядке, при этом сопоставления клавиш необязательно должны быть последовательными.</span><span class="sxs-lookup"><span data-stu-id="4a448-216">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="4a448-217">Например, можно создать меню с помощью сопоставления с параметрами клавиш 0, 1 и 3, при этом клавиша 2 не используется.</span><span class="sxs-lookup"><span data-stu-id="4a448-217">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="4a448-218">Клавиши \* (повтор) и \# (назад) зарезервированы системой и не могут быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="4a448-218">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="4a448-219">Если включен параметр распознавания речи, нажатие клавиши \* соответствует голосовой команде "Повтор", а нажатие клавиши # — голосовой команде "Назад".</span><span class="sxs-lookup"><span data-stu-id="4a448-219">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="4a448-220">Чтобы настроить параметры меню, после выбора ключа вызова необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a448-220">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="4a448-221">Введите **голосовую команду** для параметра.</span><span class="sxs-lookup"><span data-stu-id="4a448-221">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="4a448-222">Это может быть не более 64 символов и может содержать несколько слов, например "Обслуживание клиентов" или "операции и причины".</span><span class="sxs-lookup"><span data-stu-id="4a448-222">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="4a448-223">Если включена функция распознавания речи, имя будет распознаваться автоматически, а вызывающий абонент сможет нажать клавишу 3, сказать «три» или «обслуживание клиентов», чтобы выбрать параметр, закрепленный за клавишей 3.</span><span class="sxs-lookup"><span data-stu-id="4a448-223">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="4a448-224">Выберите, куда будет отправляться звонок при нажатии соответствующей клавиши, или параметр, выбранный с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="4a448-224">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="4a448-225">Кому можно направить вызов:</span><span class="sxs-lookup"><span data-stu-id="4a448-225">The call can be sent to:</span></span>

  - <span data-ttu-id="4a448-226">**Оператор** Если параметр "Оператор" уже настроен, он автоматически сопоставляется с клавишей 0, но его можно также удалить или закрепить за другой клавишей.</span><span class="sxs-lookup"><span data-stu-id="4a448-226">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="4a448-227">Если связь с оператором не закреплена за какой-либо клавишей, то голосовая команда "Оператор" также будет отключена.</span><span class="sxs-lookup"><span data-stu-id="4a448-227">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="4a448-228">**Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a448-228">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="4a448-229">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-229">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="4a448-230">Для этого выберите сотрудника **в компании** и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-230">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="4a448-231">**Сотрудникам вашей компании** может быть пользователь в сети или пользователь, размещенный в локальной среде, с помощью Skype для бизнеса Server или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a448-231">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="4a448-232">Другой **Автоматический секретарь**</span><span class="sxs-lookup"><span data-stu-id="4a448-232">Another **Auto attendant**</span></span>

       <span data-ttu-id="4a448-233">Вы можете использовать существующий автоматический секретарь для создания второго уровня параметров меню, содержащих подменю.</span><span class="sxs-lookup"><span data-stu-id="4a448-233">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="4a448-234">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="4a448-234">These are called nested auto attendants.</span></span> <span data-ttu-id="4a448-235">Чтобы отправить звонок во вложенный автоматический секретарь, выберите сотрудника **в компании** и назначьте учетную запись ресурса, в которой уже есть соответствующий автоматический секретарь, или в том случае, если вы хотите связать его с автосекретарем после того, как вы закончите создавать этот автоматический секретарь.</span><span class="sxs-lookup"><span data-stu-id="4a448-235">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="4a448-236">Также будет использоваться **время работы** вложенных автосекретарей (автосекретарей второго уровня), в том числе для вызовов, переадресуемых с других настроенных автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="4a448-236">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

     - <span data-ttu-id="4a448-237">**очередь звонков** С помощью команды "очередь звонков" можно передать Звонок в уже установленную очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="4a448-237">**call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up.</span></span> 

* * *

![Значок числа 5, на котором показана ссылка на выноску на предыдущем снимке экрана](media/sfbcallout5.png)

<span data-ttu-id="4a448-239">**Вызов по имени** Выбор этого параметра позволяет вызывающим абонентам выполнить поиск сотрудников организации, используя функцию поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4a448-239">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="4a448-240">Вы можете выбрать, каких пользователей можно вызвать, используя функцию "Вызов по имени", а каких — нет, настроив эти параметры на странице **Область вызова.**.</span><span class="sxs-lookup"><span data-stu-id="4a448-240">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="4a448-241">Любой пользователь в сети с лицензией на **телефонную систему** или любой пользователь, размещенный в локальной среде Skype для бизнеса Server или Lync Server 2013, может быть найден с помощью набора номера по имени.</span><span class="sxs-lookup"><span data-stu-id="4a448-241">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="4a448-242">Завершив выбор параметров, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4a448-242">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="4a448-243">Параметры звонка в праздничные дни</span><span class="sxs-lookup"><span data-stu-id="4a448-243">Holiday call settings</span></span>

<span data-ttu-id="4a448-244">Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="4a448-244">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="4a448-245">Для создания праздников можно перейти на экран \*\*\*\* > в параметрах организации "**праздники** ", а также создать новый обработчик вызова.</span><span class="sxs-lookup"><span data-stu-id="4a448-245">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![Снимок экрана со страницей параметров звонка на праздник](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="4a448-248">Если вы уже создали другие автосекретарей, возможно, вы видите параметр, который можно использовать для редактирования в этом списке.</span><span class="sxs-lookup"><span data-stu-id="4a448-248">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="4a448-249">В противном случае вам потребуется создать новый обработчик вызова.</span><span class="sxs-lookup"><span data-stu-id="4a448-249">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="4a448-250">Чтобы добавить новый обработчик вызова, щелкните значок **+ новый обработчик вызова**.</span><span class="sxs-lookup"><span data-stu-id="4a448-250">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![Снимок экрана, демонстрирующий Добавление нового обработчика вызова](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Значок числа 1 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout1.png)

<span data-ttu-id="4a448-253">В новом окне введите имя нового обработчика звонков в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="4a448-253">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="4a448-255">Если название вашего праздника уже есть в раскрывающемся списке **праздников** , вы можете использовать его.</span><span class="sxs-lookup"><span data-stu-id="4a448-255">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="4a448-256">Если нужного названия праздника еще не существует, выберите в раскрывающемся списке **создать новый праздник** и назначьте имя и дату нового праздника на появившемся новом экране.</span><span class="sxs-lookup"><span data-stu-id="4a448-256">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="4a448-257">Когда все будет готово, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="4a448-257">Click on **Save** when ready.</span></span>

<span data-ttu-id="4a448-258">Имена праздников могут содержать до 64 знаков; каждое имя праздника одного автосекретаря должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="4a448-258">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="4a448-259">Например, нельзя создать для одного автосекретаря два праздника с именем "День Благодарения".</span><span class="sxs-lookup"><span data-stu-id="4a448-259">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![Значок цифры 3, ссылающаяся на выноску на предыдущем снимке экрана](media/sfbcallout3.png)

<span data-ttu-id="4a448-261">**Приветствие** Приветствие является необязательным и может иметь значение **без приветствия**.</span><span class="sxs-lookup"><span data-stu-id="4a448-261">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="4a448-262">В этом случае вызывающий абонент не услышит никакого сообщения или приветствия, пока вызов не будет обработан с использованием одного из выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="4a448-262">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="4a448-263">Вы также можете загрузить аудиофайл (в формате WAV, mp3 или WMA) или создать настраиваемое приветствие, используя функцию преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="4a448-263">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="4a448-264">**Без приветствия** При звонках на номер телефона автосекретаря не будет воспроизводиться приветствие.</span><span class="sxs-lookup"><span data-stu-id="4a448-264">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="4a448-265">**Добавление звукового файла** Если вы выберете этот параметр, запишите поздравление праздников, а затем отправьте звуковой файл (в формате WAV, MP3 или WMA).</span><span class="sxs-lookup"><span data-stu-id="4a448-265">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="4a448-266">**Ввод сообщения приветствия** Если выбрать этот параметр, введите текст, который система должна прочитать (до 1000 символов).</span><span class="sxs-lookup"><span data-stu-id="4a448-266">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="4a448-267">Например, вы можете ввести текст "Поздравляем с новым годом!</span><span class="sxs-lookup"><span data-stu-id="4a448-267">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="4a448-268">Наш офисы сейчас закрыты."</span><span class="sxs-lookup"><span data-stu-id="4a448-268">Our offices are currently closed."</span></span> <span data-ttu-id="4a448-269">в диалоговом окне **Введите сообщение с приветствием** .</span><span class="sxs-lookup"><span data-stu-id="4a448-269">in the **Type a greeting message** box.</span></span>

![Значок числа 4 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout4.png)

<span data-ttu-id="4a448-271">**Действия** Вы можете выбрать, что произойдет с звонками, поступающими в этот праздник.</span><span class="sxs-lookup"><span data-stu-id="4a448-271">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="4a448-272">Возможен выбор одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4a448-272">You can chose from the following options:</span></span>

- <span data-ttu-id="4a448-273">**Отключить** Вызывающий абонент будет отключен после прослушивания праздничного приветствия.</span><span class="sxs-lookup"><span data-stu-id="4a448-273">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="4a448-274">**Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4a448-274">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="4a448-275">**Сотрудник компании**, имеющий лицензию на **телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a448-275">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="4a448-276">Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-276">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="4a448-277">Для этого выберите сотрудника **в своей компании**и настройте для него звонки, переадресованные непосредственно в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="4a448-277">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="4a448-278">**Сотрудник компании** может быть онлайн-пользователем или пользователем, находящимся на территории локального предприятия и использующим Skype для бизнеса Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a448-278">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

  - <span data-ttu-id="4a448-279">**Очередь звонков** для передачи звонка в уже установленную очередь звонков.</span><span class="sxs-lookup"><span data-stu-id="4a448-279">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="4a448-280">Другой **Автоматический секретарь**для создания второго уровня параметров меню, содержащих подменю.</span><span class="sxs-lookup"><span data-stu-id="4a448-280">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="4a448-281">Эти функции называются вложенными автосекретарями.</span><span class="sxs-lookup"><span data-stu-id="4a448-281">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="4a448-282">По умолчанию все вызовы, поступающие в период праздников, после приветствия (при его наличии) переводятся в режим "Отключить", поэтому если вы хотите изменить этот режим работы, необходимо указать, кому следует переадресовать вызов.</span><span class="sxs-lookup"><span data-stu-id="4a448-282">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="4a448-283">Страница "Выбор списка набора"</span><span class="sxs-lookup"><span data-stu-id="4a448-283">Select dial scope page</span></span>

<span data-ttu-id="4a448-284">На этой странице вы можете указать, какие пользователи в вашей организации будут перечислены в каталоге, и вы сможете звонить по имени, когда человек, который будет звонить в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="4a448-284">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Снимок экрана, на котором показана страница "область набора номера"](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="4a448-286">![Значок с номером 1, ссылающийся на выноску на предыдущем снимке экрана](media/sfbcallout1.png) с помощью параметра " **включить** ", у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="4a448-286">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="4a448-287">**Все пользователи в сети** С помощью этого параметра можно включать в поиск в каталоге всех сотрудников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a448-287">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="4a448-288">Все пользователи сети с лицензией на **телефонную систему** , а также пользователи, размещенные в локальной среде с помощью Skype для бизнеса Server или Lync Server 2013, у которых есть планы звонков в Office 365, будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="4a448-288">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="4a448-289">**Настраиваемая группа пользователей** Если вы используете этот параметр, вы можете выполнить поиск группы Office 365, списка рассылки или группы безопасности, созданной в Организации, а также пользователей, добавленных в эту группу Office 365, список рассылки или группу безопасности, в которую входят пользователи из **сети Лицензия на телефонную систему** или размещенная в локальной среде с помощью Skype для бизнеса server 2015 или Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a448-289">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="4a448-290">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a448-290">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![Значок числа 2 с ссылкой на выноску на предыдущем снимке экрана](media/sfbcallout2.png)

<span data-ttu-id="4a448-292">С помощью параметра **исключить** есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="4a448-292">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="4a448-293">**Нет**. Использование этой функции означает, что при поиске по справочнику никакие пользователи не исключаются из списка.   </span><span class="sxs-lookup"><span data-stu-id="4a448-293">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="4a448-294">**Настраиваемая группа пользователей** Если вы используете этот параметр, вы можете найти группу Office 365, список рассылки или группу безопасности, созданную в Организации, а все пользователи, добавленные в эту группу Office 365, список рассылки или группы безопасности, будут исключены из поиска в каталоге.</span><span class="sxs-lookup"><span data-stu-id="4a448-294">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="4a448-295">Вы можете добавить несколько групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a448-295">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="4a448-296">Для нового пользователя может потребоваться до 36 часов, когда кто-то использует подбирать по имени с помощью функции распознавания речи.</span><span class="sxs-lookup"><span data-stu-id="4a448-296">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="4a448-297">После ввода всех необходимых полей и настройки меню и параметров обработки звонков нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="4a448-297">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="4a448-298">Редактирование и тестирование автоматических ассистентов</span><span class="sxs-lookup"><span data-stu-id="4a448-298">Editing and testing auto attendants</span></span>

<span data-ttu-id="4a448-299">После сохранения автосекретаря он отображается в списке на странице **Автосекретари**.</span><span class="sxs-lookup"><span data-stu-id="4a448-299">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="4a448-300">Это позволит вам быстро увидеть некоторые из настроенных параметров, включая имя, номер телефона, язык и состояние.</span><span class="sxs-lookup"><span data-stu-id="4a448-300">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="4a448-301">Если вы хотите внести изменения в автосекретарь, выберите автосекретарь, а затем на панели действий нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="4a448-301">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="4a448-302">Вы также можете быстро выполнить тестовый вызов для автосекретаря с помощью кнопки **тест** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="4a448-302">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="4a448-303">Командлеты для работы с автосекретарями</span><span class="sxs-lookup"><span data-stu-id="4a448-303">Auto attendant cmdlets</span></span>

<span data-ttu-id="4a448-304">Можно также использовать Windows PowerShell для создания и настройки автосекретарей.</span><span class="sxs-lookup"><span data-stu-id="4a448-304">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="4a448-305">Ниже приведены командлеты, необходимые для управления автосекретарем.</span><span class="sxs-lookup"><span data-stu-id="4a448-305">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="4a448-306">New-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="4a448-306">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="4a448-307">Set-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="4a448-307">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="4a448-308">Get-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="4a448-308">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="4a448-309">Get-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="4a448-309">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="4a448-310">Remove-Ксаутоаттендант</span><span class="sxs-lookup"><span data-stu-id="4a448-310">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="4a448-311">New-Ксаутоаттендантмену</span><span class="sxs-lookup"><span data-stu-id="4a448-311">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="4a448-312">New-Ксонлинеаудиофиле</span><span class="sxs-lookup"><span data-stu-id="4a448-312">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="4a448-313">New-Ксаутоаттенданткаллфлов</span><span class="sxs-lookup"><span data-stu-id="4a448-313">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="4a448-314">Export-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="4a448-314">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="4a448-315">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="4a448-315">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="4a448-316">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="4a448-316">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="4a448-317">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="4a448-317">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="4a448-318">Get-Ксаутоаттендантсуппортедтимезоне</span><span class="sxs-lookup"><span data-stu-id="4a448-318">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="4a448-319">New-КсаутоаттенданткаллхандлингассоЦиатион</span><span class="sxs-lookup"><span data-stu-id="4a448-319">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="4a448-320">Get-Ксаутоаттендантсуппортедлангуаже</span><span class="sxs-lookup"><span data-stu-id="4a448-320">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="4a448-321">Import-Ксаутоаттендансолидайс</span><span class="sxs-lookup"><span data-stu-id="4a448-321">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="4a448-322">New-Ксаутоаттенданткаллаблинтити</span><span class="sxs-lookup"><span data-stu-id="4a448-322">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="4a448-323">Дополнительные сведения о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a448-323">More about Windows PowerShell</span></span>

- <span data-ttu-id="4a448-324">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="4a448-324">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4a448-325">С помощью Windows PowerShell вы можете управлять набором Office 365 и Microsoft Teams с помощью одной точки администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="4a448-325">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4a448-326">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="4a448-326">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4a448-327">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4a448-327">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="4a448-328">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="4a448-328">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="4a448-329">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="4a448-329">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4a448-330">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4a448-330">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4a448-331">Управление Office 365 с помощью Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a448-331">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="4a448-332">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4a448-332">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="4a448-333">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4a448-333">Related topics</span></span>

[<span data-ttu-id="4a448-334">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="4a448-334">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="4a448-335">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="4a448-335">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="4a448-336">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="4a448-336">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="4a448-337">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="4a448-337">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="4a448-338">Что представляют собой облачные автосекретари?</span><span class="sxs-lookup"><span data-stu-id="4a448-338">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="4a448-339">Пример для малого бизнеса: настройка автосекретаря</span><span class="sxs-lookup"><span data-stu-id="4a448-339">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
