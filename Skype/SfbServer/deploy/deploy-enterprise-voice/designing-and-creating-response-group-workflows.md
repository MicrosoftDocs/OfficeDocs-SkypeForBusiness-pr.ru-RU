---
title: Проектирование и создание рабочих процессов группы ответа в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Разработка и создание рабочих процессов для группы ответа, в Скайп Business Server корпоративной голосовой связи. Описаны как рабочие процессы сервисной группы, так и интерактивные процессы.
ms.openlocfilehash: 71380d7dc048663eca9543a31d67462ead0321c3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business-2015"></a><span data-ttu-id="9bccf-104">Проектирование и создание рабочих процессов группы ответа в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="9bccf-104">Designing and creating response group workflows in Skype for Business 2015</span></span>
 
<span data-ttu-id="9bccf-105">Разработка и создание рабочих процессов для группы ответа, в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9bccf-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="9bccf-106">Описаны как рабочие процессы сервисной группы, так и интерактивные процессы.</span><span class="sxs-lookup"><span data-stu-id="9bccf-106">Both hunt group workflows and interactive workflows are covered.</span></span>
  
<span data-ttu-id="9bccf-107">Рабочий процесс определяет последовательность обработки вызова с момента звукового сигнала до момента ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="9bccf-108">Рабочий процесс указывает очередь, которая будет использовать для удержания вызова и метод маршрутизации для использования для рабочих процессов для сервисной группы или вопросы и ответы для рабочих процессов для группы ответа интерактивного.</span><span class="sxs-lookup"><span data-stu-id="9bccf-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span> 
  
<span data-ttu-id="9bccf-109">Рабочий процесс также задает такие параметры, как приветственное сообщение, музыка при удержании, часы работы и выходные.</span><span class="sxs-lookup"><span data-stu-id="9bccf-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9bccf-110">Вам следует создать группы агентов и очереди до создания рабочего процесса, который их использует.</span><span class="sxs-lookup"><span data-stu-id="9bccf-110">You must create agent groups and queues before you create a workflow that uses them.</span></span> 
  
## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="9bccf-111">Создание или изменение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="9bccf-112">Использование средства настройки группы ответа для создания или изменения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="9bccf-113">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9bccf-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bccf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9bccf-115">В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>
    
4. <span data-ttu-id="9bccf-116">На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>
    
5. <span data-ttu-id="9bccf-117">В поле поиска **выберите службу** введите полностью или частично имя службы **сервера приложений** , на котором размещается рабочий процесс, чтобы создать или изменить.</span><span class="sxs-lookup"><span data-stu-id="9bccf-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="9bccf-118">В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-119">Откроется окно программы настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="9bccf-120">Можно также открыть средство настройки группы ответа непосредственно из веб-браузера, введя следующий URL-адрес: https:// _ \<Полное_доменное_имя_веб\>_/RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="9bccf-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https:// _\<webPoolFqdn\>_/RgsConfig.</span></span> 
  
6. <span data-ttu-id="9bccf-121">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-121">Do one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-122">В разделе **Создание рабочего процесса** рядом с элементом **Сервисная группа** нажмите кнопку "Создать".</span><span class="sxs-lookup"><span data-stu-id="9bccf-122">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
   - <span data-ttu-id="9bccf-123">В разделе **Управление существующим рабочим процессом** найдите рабочий процесс, который требуется изменить, затем в разделе **Действие** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>
    
7. <span data-ttu-id="9bccf-124">Если все готово к тому, чтобы разрешить пользователям вызывать рабочий процесс, установите флажок **Активировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="9bccf-p106">При создании управляемого рабочего процесса необходимо выбрать функцию **Активировать рабочий процесс**. После сохранения активного управляемого рабочего процесс его можно изменить или отключить.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p106">If you are to creating a managed workflow, you need to select **Activate the workflow**. After you save the active, managed workflow, you can then modify and deactivate it.</span></span> 
  
8. <span data-ttu-id="9bccf-127">Чтобы разрешить федеративным пользователям звонки группе, установите флажок **Включить поддержку федерации** .</span><span class="sxs-lookup"><span data-stu-id="9bccf-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="9bccf-128">Кроме того, необходимо иметь политики внешнего доступа, применяемое к приложения группы ответа, настроенные для федерации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-129">Глобальную политику внешнего доступа применяется к приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="9bccf-130">Глобальная политика для федерации группы ответа можно настроить с помощью Скайп для панели управления Business Server или с помощью командлета **Set-CsExternalAccessPolicy** задать для параметра EnableOutsideAccess значение True.</span><span class="sxs-lookup"><span data-stu-id="9bccf-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="9bccf-131">Имейте в виду, параметров глобальной политики применяются ко всем пользователям, если они назначена политика узла или пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="9bccf-132">Таким образом прежде чем изменять этот параметр для групп ответа, убедитесь в том, что параметр федерации отвечает требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="9bccf-133">Для получения дополнительных сведений о как политики применяются к пользователям видеть [Управление внешнюю политику доступа для вашей организации](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="9bccf-134">Для получения дополнительных сведений о настройке федерации видеть [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9bccf-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9bccf-135">Пользователей, которые размещаются в Скайп для бизнеса в Интернет не может размещать звонки для группы ответа, которые размещаются в локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="9bccf-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="9bccf-136">Это значение true в обоих гибридных развертываниях и в тех случаях, где федеративных локальное развертывание с помощью Скайп для бизнеса в Интернет развертывания.</span><span class="sxs-lookup"><span data-stu-id="9bccf-136">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Skype for Business Online deployment.</span></span> 
  
9. <span data-ttu-id="9bccf-137">Если требуется скрыть идентификационные данные агентов во время вызовов, установите флажок **Включить анонимность агента**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p110">Анонимные вызовы не должны начинаться с сеанса видеосвязи или обмена мгновенными сообщениями (после начала сеанса вызова можно добавить видео и мгновенные сообщения). Анонимный агент также может поставить вызов на удержание, передать вызов (скрытая передача и передача после консультации), а также выполнять парковку и извлечение вызовов. Анонимные вызовы не поддерживают конференц-связь, совместный доступ к приложениям и рабочему столу, передачу файлов, работу с доской, совместную работу с данными и запись звонков. Агенты, использующие подключаемый модуль VDI Lync, могут анонимно получать входящие вызовы, но не отправлять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p110">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span> 
  
10. <span data-ttu-id="9bccf-142">В поле **Введите адрес группы, которая будет принимать звонки** введите основной адрес универсального кода ресурса (URI) SIP группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-143">Основной адрес универсального кода ресурса для рабочего процесса служит для распознавания рабочего процесса и ссылок на него.</span><span class="sxs-lookup"><span data-stu-id="9bccf-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="9bccf-144">URI SIP, введенные создается в качестве контактного объекта в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9bccf-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="9bccf-145">Чтобы создать URI, объект должно быть уникальным в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9bccf-145">To create the URI, the object must be unique in Active Directory.</span></span> 
  
11. <span data-ttu-id="9bccf-146">В поле **отображаемое имя**введите имя, которое должно отображаться для рабочего процесса (например, группа ответа отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="9bccf-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p112">В отображаемом имени не разрешено употребление символов "<" или ">". Не допускаются отображаемые имена **RGS Presence Watcher** (Наблюдатель присутствия RGS) и **Announcement Service** (Служба оповещения), так как они зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p112">Do not include the "<" or ">" characters in the display name. Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span> 
  
12. <span data-ttu-id="9bccf-149">В поле **Номер телефона** введите строку универсального кода ресурса для группы ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="9bccf-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>
    
13. <span data-ttu-id="9bccf-150">В поле **Отображаемый номер** введите номер группы ответа для отображения (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="9bccf-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>
    
14. <span data-ttu-id="9bccf-151">(Необязательно) В поле **Описание**введите описание рабочего процесса, как он должен отображаться в карточке контакта в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>
    
15. <span data-ttu-id="9bccf-152">В поле **Тип рабочего процесса** выберите **Управляемый**, если этот им будет управлять руководитель группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="9bccf-153">Выполните следующие действия, чтобы назначить менеджеров группы ответа в рабочий процесс:</span><span class="sxs-lookup"><span data-stu-id="9bccf-153">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    <span data-ttu-id="9bccf-154">а.</span><span class="sxs-lookup"><span data-stu-id="9bccf-154">a.</span></span> <span data-ttu-id="9bccf-155">Введите универсальный код ресурса SIP, назначенный руководителю данного рабочего процесса, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    <span data-ttu-id="9bccf-156">б.</span><span class="sxs-lookup"><span data-stu-id="9bccf-156">b.</span></span> <span data-ttu-id="9bccf-157">Введите универсальный код ресурса SIP, назначенный дополнительным руководителям, которых требуется добавить к рабочему процессу, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9bccf-p116">Каждому пользователю, который назначен менеджером группы ответа, необходимо присвоить роль CsResponseGroupManager. Если пользователям не назначена эта роль, они не могут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p116">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span> 
  
16. <span data-ttu-id="9bccf-160">В разделе **Шаг 2. Выберите язык** щелкните язык, на котором будет выполняться распознавание речи и преобразование текста в речь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>
    
17. <span data-ttu-id="9bccf-161">Если необходимо настроить приветствие, в разделе **Шаг 3. Настройте приветствие** установите флажок **Отображать приветствие**, затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9bccf-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-162">Для ввода приветствия в виде текста, который будет преобразовываться в речь для вызывающих абонентов, щелкните **Использовать текст, преобразованный в речь**, затем введите приветствие в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p117">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p117">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
   - <span data-ttu-id="9bccf-p118">Для воспроизведения записи приветствия из звукового файла Wave (.wav) или файла Windows Media (.wma) щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**. Нажмите кнопку **Загрузить** для загрузки звукового файла.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p118">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-169">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-170">Для получения дополнительных сведений о форматах файлов, поддерживаемые видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-170">For details about supported file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
18. <span data-ttu-id="9bccf-171">В разделе **Шаг 4. Укажите часы работы** в поле **Ваш часовой пояс** щелкните часовой пояс для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p120">Часовой пояс – это пояс, к которому относятся вызывающие абоненты и агенты. Он используется для расчета часов открытия и закрытия. Например, если для рабочего процесса задано использование часового пояса "Североамериканское восточное стандартное время" и в качестве времени открытия указано 7:00, а в качестве времени закрытия – 23:00, предполагается, что офис открывается в 7:00 по восточному времени, а закрывается в 23:00 по восточному времени, соответственно. (Время необходимо вводить в 24-часовом формате.)</span><span class="sxs-lookup"><span data-stu-id="9bccf-p120">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span> 
  
19. <span data-ttu-id="9bccf-177">Выберите тип рабочего графика, который следует использовать. Для этого выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9bccf-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-178">Для применения предварительно заданного графика рабочего времени щелкните **Использовать готовое расписание**, затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-179">Необходимо определить по крайней мере один стандартное расписание, ранее, чтобы иметь возможность установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="9bccf-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="9bccf-180">Определение предварительно расписания с помощью командлета **New-CSRgsHoursOfBusiness** .</span><span class="sxs-lookup"><span data-stu-id="9bccf-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="9bccf-181">Дополнительные сведения см [(необязательно) группы ответа определение рабочих часов в Скайп для бизнеса 2015](optional-define-response-group-business-hours.md).</span><span class="sxs-lookup"><span data-stu-id="9bccf-181">For details, see [(Optional) Define Response Group business hours in Skype for Business 2015](optional-define-response-group-business-hours.md).</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="9bccf-182">При выборе предварительно заданного расписания дни и часы работы группы ответа автоматически водятся в полях **День**, **Открыть** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>
  
   - <span data-ttu-id="9bccf-183">Для применения пользовательского графика, относящегося только к данному рабочему процессу, щелкните **Использовать расписание пользователя**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>
    
20. <span data-ttu-id="9bccf-184">Если вы создаете индивидуальное расписание для данного рабочего процесса, установите флажки, чтобы выбрать дни недели, по которым группа ответа доступна.</span><span class="sxs-lookup"><span data-stu-id="9bccf-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>
    
21. <span data-ttu-id="9bccf-185">При создании пользовательского расписания введите в полях **Открыть** и **Закрыть** часы работы группы ответа для каждого дня недели.</span><span class="sxs-lookup"><span data-stu-id="9bccf-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p122">Часы вводятся в полях **Открыть** и **Закрыть** в 24-часовом формате. Например, если рабочий день продолжается с 9.00 до 17.00 с перерывом на обед в полдень, часы работы указываются следующим образом: **Открыть** 9:00, **Закрыть** 12:00, **Открыть** 13:00, **Закрыть** 17:00.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p122">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>
  
22. <span data-ttu-id="9bccf-188">Если требуется воспроизводить сообщение в нерабочее время, установите флажок **Отображать сообщение в нерабочее для группы ответа время**, затем укажите сообщение для воспроизведения, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-189">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-p123">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p123">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
   - <span data-ttu-id="9bccf-p124">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p124">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-196">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-196">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-197">Для получения дополнительных сведений о форматах файлов, поддерживаемые звука видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-197">For details about supported audio file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
23. <span data-ttu-id="9bccf-198">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="9bccf-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
   - <span data-ttu-id="9bccf-199">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-199">To disconnect the call, click **Disconnect Call**.</span></span>
    
   - <span data-ttu-id="9bccf-200">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bccf-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="9bccf-201">Формат адреса голосовой почты _ \<username\>_@ _\<domainName\> _ (например, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-201">The format for the voice mail address is  _\<username\>_@ _\<domainName\>_ (for example, bob@contoso.com).</span></span>
    
   - <span data-ttu-id="9bccf-202">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="9bccf-203">Имеет формат для пользователя адрес _ \<username\>_@ _\<domainName\>_.</span><span class="sxs-lookup"><span data-stu-id="9bccf-203">The format for the user address is  _\<username\>_@ _\<domainName\>_.</span></span>
    
   - <span data-ttu-id="9bccf-204">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9bccf-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="9bccf-205">— Номер телефона в формате _ \<номер\>_@ _\<domainName\> _ (например, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-205">The format for the telephone number is  _\<number\>_@ _\<domainName\>_ (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="9bccf-206">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="9bccf-206">The domain name is used to route the caller to the correct destination.</span></span>
    
24. <span data-ttu-id="9bccf-207">В разделе **Шаг 5. Указание выходных дней** установите флажки для одной или нескольких групп выходных дней, когда группа ответа не будет работать.</span><span class="sxs-lookup"><span data-stu-id="9bccf-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-208">Необходимо определить праздников и наборах праздников, прежде чем настраивать этот рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9bccf-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="9bccf-209">Используйте командлеты **New-CsRgsHoliday** и **Командлет New-CsRgsHolidaySet** для определения праздников и победы наборов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="9bccf-210">Дополнительные сведения см [(необязательно) определение наборах праздников ответа в Скайп для 2015 бизнеса](optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9bccf-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business 2015](optional-define-response-group-holiday-sets.md).</span></span> 
  
25. <span data-ttu-id="9bccf-211">Если требуется воспроизводить сообщение в выходные дни, установите флажок **Отображать сообщение в выходные дни**, затем укажите воспроизводимое сообщение, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
  - <span data-ttu-id="9bccf-212">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p130">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p130">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
   - <span data-ttu-id="9bccf-p131">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p131">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-219">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-219">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-220">Для получения дополнительных сведений о форматах файлов, поддерживаемые звука видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-220">For details about supported audio file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
26. <span data-ttu-id="9bccf-221">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="9bccf-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
   - <span data-ttu-id="9bccf-222">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-222">To disconnect the call, click **Disconnect Call**.</span></span>
    
   - <span data-ttu-id="9bccf-223">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bccf-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="9bccf-224">Формат адреса голосовой почты _ \<username\>_@ _\<domainName\> _ (например, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-224">The format for the voice mail address is  _\<username\>_@ _\<domainName\>_ (for example, bob@contoso.com).</span></span>
    
   - <span data-ttu-id="9bccf-225">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="9bccf-226">Имеет формат для пользователя адрес _ \<username\>_@ _\<domainName\>_.</span><span class="sxs-lookup"><span data-stu-id="9bccf-226">The format for the user address is  _\<username\>_@ _\<domainName\>_.</span></span>
    
   - <span data-ttu-id="9bccf-227">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9bccf-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="9bccf-228">— Номер телефона в формате _ \<номер\>_@ _\<domainName\> _ (например, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-228">The format for the telephone number is  _\<number\>_@ _\<domainName\>_ (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="9bccf-229">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="9bccf-229">The domain name is used to route the caller to the correct destination.</span></span>
    
27. <span data-ttu-id="9bccf-230">В разделе **Шаг 6. Настройте очередь** (Шаг 6. Настройка очереди) в списке **Выберите очередь, которая будет принимать звонки** выберите очередь для удержания вызывающих абонентов до освобождения оператора.</span><span class="sxs-lookup"><span data-stu-id="9bccf-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>
    
28. <span data-ttu-id="9bccf-231">В разделе **Шаг 7. Настройте музыку для режима удержания** выберите музыку, которую должны будут прослушивать вызывающие абоненты в ожидании ответа агента. Для этого выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-232">Если в режиме удержания требуется воспроизводить музыкальную запись по умолчанию, щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-232">To use the default music-on-hold recording, click **Use default**.</span></span>
    
   - <span data-ttu-id="9bccf-p136">Если в режиме удержания требуется воспроизводить музыкальную запись из звукового файла, щелкните **Выбрать музыкальный файл**. Для загрузки нового звукового файла щелкните ссылку **музыкальный файл**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p136">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-237">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-237">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-238">Для получения дополнительных сведений о форматах файлов, поддерживаемые звука видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-238">For details about supported audio file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
29. <span data-ttu-id="9bccf-239">Нажмите кнопку **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-239">Click **Deploy**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="9bccf-240">Чтобы использовать Скайп для консоли Business Server для создания или изменения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="9bccf-241">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9bccf-242">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9bccf-p138">Создайте подсказку для воспроизведения в качестве приветственного сообщения и сохраните ее в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p138">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="9bccf-245">Например:</span><span class="sxs-lookup"><span data-stu-id="9bccf-245">For example:</span></span>
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="9bccf-246">Чтобы использовать звукового файла в строке, используйте командлет **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="9bccf-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="9bccf-247">Дополнительные сведения см [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9bccf-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="9bccf-p140">Получите идентификатор очереди или вопроса при перенаправлении вызовов. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p140">Get the identity of the queue or question where the calls will be directed. At the command line, run:</span></span>
    
   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="9bccf-250">Для получения дополнительных сведений о создании очереди видеть [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9bccf-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>
    
5. <span data-ttu-id="9bccf-p141">Определите действие по умолчанию, которое будет выполняться при открытии рабочего процесса в рабочие часы, и сохраните его в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p141">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="9bccf-p142">Для рабочих процессов сервисной группы действие по умолчанию должно перенаправлять вызов в очередь. Этот параметр требуется для активных рабочих процессов. Для неактивных рабочих процессов этот параметр указывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p142">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span> 
  
    <span data-ttu-id="9bccf-256">Например:</span><span class="sxs-lookup"><span data-stu-id="9bccf-256">For example:</span></span>
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="9bccf-257">Если вы хотите определить рабочее время и выходные дни, необходимо создать их до создания или изменения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="9bccf-258">Дополнительные сведения см [(необязательно) группы ответа определение рабочих часов в Скайп для бизнеса 2015](optional-define-response-group-business-hours.md) и [(необязательно) определение наборах праздников ответа в Скайп для 2015 бизнеса](optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9bccf-258">For details, see [(Optional) Define Response Group business hours in Skype for Business 2015](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business 2015](optional-define-response-group-holiday-sets.md).</span></span>
    
7. <span data-ttu-id="9bccf-259">Если требуется предоставить запросы для вызовов, полученных из рабочих часов или в выходные дни, используйте командлет **New-CsRgsPrompt** для определения в строке и используйте **New-CsRgsCallAction** , чтобы определить действие, выполняемое после в строке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="9bccf-260">Дополнительные сведения см [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) и [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9bccf-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>
    
8. <span data-ttu-id="9bccf-261">Получить имя службы для службы группы ответа Lync Server и присвойте переменной.</span><span class="sxs-lookup"><span data-stu-id="9bccf-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="9bccf-262">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-262">At the command, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="9bccf-263">Создайте или измените рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9bccf-263">Create or modify the workflow.</span></span> <span data-ttu-id="9bccf-264">Чтобы создать рабочий процесс, используйте **Командлет New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="9bccf-265">Чтобы изменить рабочий процесс, используйте **Командлет Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="9bccf-266">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-266">At the command line, type:</span></span>
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="9bccf-267">Например:</span><span class="sxs-lookup"><span data-stu-id="9bccf-267">For example:</span></span>
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="9bccf-268">Всем пользователям, которые назначены менеджерами рабочих процессов, необходимо присвоить роль CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="9bccf-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="9bccf-269">Для получения дополнительных сведений о дополнительных параметра отображаться [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) или [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9bccf-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>
  
## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="9bccf-270">Проектирование интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-270">Designing an interactive workflow</span></span>

<span data-ttu-id="9bccf-271">Интерактивного автоответчика (IVR) можно использовать для получения сведений из абонентов и направления вызовов в соответствующую очередь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="9bccf-272">Пар вопросов и ответов определить, какие очереди для использования.</span><span class="sxs-lookup"><span data-stu-id="9bccf-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="9bccf-273">В зависимости от вызывающего абонента ответа звонящий слышит следующим вопросом либо маршрутизируются в соответствующую очередь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="9bccf-274">Вопросы IVR и ответы вызывающего абонента предоставляются отвечающему агенту, принимающему звонок, предоставляя ценные сведения для агента.</span><span class="sxs-lookup"><span data-stu-id="9bccf-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>
  
### <a name="overview-of-ivr-features"></a><span data-ttu-id="9bccf-275">Обзор возможностей интерактивного автоответчика</span><span class="sxs-lookup"><span data-stu-id="9bccf-275">Overview of IVR Features</span></span>

<span data-ttu-id="9bccf-276">Приложение группы ответа предлагает распознавания речи и преобразования текста в речь возможности на 26 языках.</span><span class="sxs-lookup"><span data-stu-id="9bccf-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="9bccf-277">Вопросы интерактивного автоответчика вводятся с помощью функции преобразования текста в речь либо из звукового файла Wave (.wav) или Windows Media (.wma).</span><span class="sxs-lookup"><span data-stu-id="9bccf-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="9bccf-278">Вызывающие абоненты могут отвечать голосом или в режиме двухтонального многочастотного набора (DTMF).</span><span class="sxs-lookup"><span data-stu-id="9bccf-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>
  
<span data-ttu-id="9bccf-279">Интерактивные рабочие процессы поддерживает до двух уровнями вопросов, каждый вопрос, создавая до четырех вариантов ответов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="9bccf-280">IVR запрашивает у вызывающего абонента вопрос и в зависимости от вызывающего абонента ответа маршрутизирует звонящего в очередь или второй вопрос.</span><span class="sxs-lookup"><span data-stu-id="9bccf-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="9bccf-281">Второй вопрос также может иметь четыре варианта ответов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="9bccf-282">В зависимости от того, ответ на вопрос второго уровня Звонящий перенаправляется в соответствующую очередь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9bccf-283">При создании потоков обработки вызовов с помощью Скайп для консоли Business Server можно назначить любое число уровней вопросы IVR и любого количества ответов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="9bccf-284">Тем не менее для удобства вызывающего абонента, рекомендуется не использовать более трех уровней вопросов, с не более пяти ответы.</span><span class="sxs-lookup"><span data-stu-id="9bccf-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="9bccf-285">Кроме того при разработке потока вызовов с более чем двумя уровнями вопросов с более четырех ответы нельзя изменить поток вызовов с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bccf-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="9bccf-286">Вопросы IVR и ответы вызывающего абонента предоставляются отвечающему агенту, принимающему звонок.</span><span class="sxs-lookup"><span data-stu-id="9bccf-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>
  
### <a name="working-with-speech-technologies"></a><span data-ttu-id="9bccf-287">Работа с речевыми технологиями</span><span class="sxs-lookup"><span data-stu-id="9bccf-287">Working with Speech Technologies</span></span>

<span data-ttu-id="9bccf-p151">Речевые технологии, такие как распознавание и синтез речи, могут улучшить работу пользователей и позволить получать доступ к информации более естественно и эффективно. Но могут быть ситуации, когда заданный текст или голосовой ответ пользователя распознается неправильно речевой системой. Например, символ "#" интерпретируется модулем преобразования текста в речь как слово "номер". Эту проблему можно устранить следующим способом.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p151">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively. However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine. For example, the "#" symbol is translated by the text-to-speech engine as the word "number." This issue can be mitigated by the following:</span></span>
  
- <span data-ttu-id="9bccf-p152">Речевой модуль предоставляет звонящему пять попыток для ответа на вопрос. Если звонящий неправильно отвечает на вопрос (т. е. ответ не входит в число допустимых ответов) или не отвечает на вопрос, то ему или ей предоставляется еще одна попытка. Звонящему предоставляется 5 попыток, после чего звонок разъединяется. Вы можете настроить IVR для воспроизведения настраиваемого сообщения после каждой ошибки. Вопрос повторяется каждый раз.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p152">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>
    
- <span data-ttu-id="9bccf-p153">Чтобы минимизировать возможность интерпретации шума окружающей среды как ответа, используйте более длительные ответы. Например, в ответах должно быть более одного слога и они должны значительно отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p153">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>
    
- <span data-ttu-id="9bccf-p154">Если ваши вопросы предполагают как речевые, так и тональные (DTMF) ответы, настройте речевые ответы со словами, представляющими концепцию, а не ответы DTMF. Например, вместо "Нажмите или скажите один" используйте "Нажмите 1 или скажите «счета»".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p154">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>
    
- <span data-ttu-id="9bccf-p155">После настройки IVR, позвоните но номеру, прослушайте голосовые подсказки, ответьте на каждую из них голосом и убедитесь, что IVR звучит и работает, как ожидается. Затем вы можете изменить IVR, чтобы определить проблемы с интерпретацией. Вспомним предыдущий пример – если требуется указать клавишу #, вы можете перезаписать подсказку IVR и использовать имя клавиши вместо символа. Пример: Для связи с сотрудником отдела продаж нажмите кнопку с решеткой.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p155">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected. You can then modify the IVR to fix any interpretation issues. Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol. For example, "To talk to sales, press the pound key."</span></span>
    
### <a name="ivr-design-examples"></a><span data-ttu-id="9bccf-305">Примеры IVR</span><span class="sxs-lookup"><span data-stu-id="9bccf-305">IVR Design Examples</span></span>

<span data-ttu-id="9bccf-306">В следующих разделах представлены примеры различных сценариев IVR и пар вопросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span> 
  
#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="9bccf-307">IVR с одним уровнем вопросов</span><span class="sxs-lookup"><span data-stu-id="9bccf-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="9bccf-308">В следующем примере показан IVR, использующий один уровень вопросов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="9bccf-309">Распознавание речи используется для обнаружения ответа вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="9bccf-309">It uses speech recognition to detect the caller's response.</span></span>
  
 <span data-ttu-id="9bccf-p157">**Вопрос:** "Благодарим за звонок в отдел кадров. Для обсуждения заработной платы скажите «зарплата». Для обсуждения других вопросов скажите «кадры»".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p157">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>
  
- <span data-ttu-id="9bccf-313">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу, отвечающую за зарплату.</span><span class="sxs-lookup"><span data-stu-id="9bccf-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>
    
- <span data-ttu-id="9bccf-314">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу отдела кадров.</span><span class="sxs-lookup"><span data-stu-id="9bccf-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>
    
<span data-ttu-id="9bccf-315">На следующем рисунке показан поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-315">The following figure shows the call flow.</span></span>
  
 <span data-ttu-id="9bccf-316">**Одноуровневый интерактивный поток вызовов**</span><span class="sxs-lookup"><span data-stu-id="9bccf-316">**One-level interactive call flow**</span></span>
  
![Создание потоков обработки вызовов с использованием систем речевого взаимодействия](../../media/Ops_OCS_RGS_IVRLevel1.jpg)
  
#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="9bccf-318">IVR с двумя уровнями вопросов</span><span class="sxs-lookup"><span data-stu-id="9bccf-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="9bccf-p158">В следующем примере показан IVR, использующий два уровня вопросов. Он позволяет звонящим отвечать с использованием речи или команд DTMF.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p158">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>
  
 <span data-ttu-id="9bccf-p159">**Вопрос:** "Благодарим за звонок в справочную службу отдела информационных технологий. Если неполадка связана с доступом к сети, нажмите 1 или скажите «сеть». Если неполадка связана с программным обеспечением, нажмите 2 или скажите «программное обеспечение». Если неполадка связана с оборудованием, нажмите 3 или скажите «оборудование»".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p159">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>
  
- <span data-ttu-id="9bccf-325">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки сети.</span><span class="sxs-lookup"><span data-stu-id="9bccf-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>
    
- <span data-ttu-id="9bccf-326">**Выбран вариант 2:** вызывающему абоненту задается следующий вопрос.</span><span class="sxs-lookup"><span data-stu-id="9bccf-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="9bccf-p160">**Вопрос:** "Если неполадка связана с операционной системой, нажмите 1 или скажите «операционная система». Если неполадка связана с внутренним приложением, нажмите 2 или скажите «внутреннее приложение». В случае иных неполадок нажмите 3 или скажите иное".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p160">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
  - <span data-ttu-id="9bccf-330">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки операционных систем.</span><span class="sxs-lookup"><span data-stu-id="9bccf-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
  - <span data-ttu-id="9bccf-331">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу поддержки внутренних приложений.</span><span class="sxs-lookup"><span data-stu-id="9bccf-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
  - <span data-ttu-id="9bccf-332">**Выбран вариант 3:** вызывающий абонент перенаправляется в группу поддержки программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9bccf-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>
    
- <span data-ttu-id="9bccf-333">**Выбран вариант 3:** вызывающему абоненту задается следующий вопрос.</span><span class="sxs-lookup"><span data-stu-id="9bccf-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="9bccf-p161">**Вопрос:** "Если неполадка связана с принтером, нажмите 1. В противном случае нажмите 2".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p161">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
  - <span data-ttu-id="9bccf-336">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки принтеров.</span><span class="sxs-lookup"><span data-stu-id="9bccf-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
  - <span data-ttu-id="9bccf-337">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу поддержки оборудования.</span><span class="sxs-lookup"><span data-stu-id="9bccf-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>
    
<span data-ttu-id="9bccf-338">На следующем рисунке показан поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-338">The following figure shows the call flow.</span></span>
  
 <span data-ttu-id="9bccf-339">**Двухуровневый интерактивный поток вызовов**</span><span class="sxs-lookup"><span data-stu-id="9bccf-339">**Two-level interactive call flow**</span></span>
  
![Создание потоков обработки вызовов с использованием систем речевого взаимодействия](../../media/Ops_OCS_RGS_IVRLevel2.jpg)
  
### <a name="best-practices"></a><span data-ttu-id="9bccf-341">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9bccf-341">Best Practices</span></span>

<span data-ttu-id="9bccf-342">В следующем списке описываются некоторые рекомендации по созданию IVR.</span><span class="sxs-lookup"><span data-stu-id="9bccf-342">The following list describes some best practices for designing your IVR:</span></span>
  
- <span data-ttu-id="9bccf-p162">Позвольте звонящему быстро перейти к нужной задаче. Избегайте слишком большого объема информации или длинных маркетинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p162">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>
    
- <span data-ttu-id="9bccf-p163">Если вы хотите включить длинное сообщение, рассмотрите возможность добавления его к первому вопросу, а не к сообщению приветствия. Звонящие смогут пропустить сообщение, если оно входит в первый вопрос, ответив на него, но они не смогут пропустить приветствие.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p163">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>
    
- <span data-ttu-id="9bccf-347">Говорите на языке вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="9bccf-347">Speak in the caller's language.</span></span> <span data-ttu-id="9bccf-348">Избегайте stilted языка.</span><span class="sxs-lookup"><span data-stu-id="9bccf-348">Avoid stilted language.</span></span> <span data-ttu-id="9bccf-349">Произнесите несколько слов естественным образом.</span><span class="sxs-lookup"><span data-stu-id="9bccf-349">Speak naturally.</span></span>
    
- <span data-ttu-id="9bccf-350">Пишите эффективные подсказки.</span><span class="sxs-lookup"><span data-stu-id="9bccf-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="9bccf-351">Удалите все ненужные варианты.</span><span class="sxs-lookup"><span data-stu-id="9bccf-351">Remove any unnecessary options.</span></span> <span data-ttu-id="9bccf-352">Структура сведения, чтобы у вызывающего абонента ожидается ответ — в конце предложения.</span><span class="sxs-lookup"><span data-stu-id="9bccf-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="9bccf-353">Например «говорить Группа продаж, нажмите 1.»</span><span class="sxs-lookup"><span data-stu-id="9bccf-353">For example, "To speak to the sales team, press 1."</span></span>
    
- <span data-ttu-id="9bccf-p166">Сделайте голосовые ответы понятными для пользователя. Например, если вы указываете и тональные, и голосовые ответы, используйте, например, следующую фразу: "Чтобы поговорить с группой продаж, нажмите 1 или скажите «продажи»".</span><span class="sxs-lookup"><span data-stu-id="9bccf-p166">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>
    
- <span data-ttu-id="9bccf-356">Проверьте IVR на группе пользователей перед развертыванием в организации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>
    
## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="9bccf-357">Создание и изменение интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="9bccf-358">Использование средства настройки группы ответа для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="9bccf-359">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9bccf-360">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bccf-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9bccf-361">В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>
    
4. <span data-ttu-id="9bccf-362">На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>
    
5. <span data-ttu-id="9bccf-363">В поле поиска **выберите службу** введите полностью или частично имя службы **сервера приложений** , на котором размещается рабочий процесс, чтобы создать или изменить.</span><span class="sxs-lookup"><span data-stu-id="9bccf-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="9bccf-364">В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-365">Откроется окно программы настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="9bccf-366">Можно также открыть средство настройки группы ответа непосредственно из веб-браузера, введя следующий URL-адрес: https:// _ \<Полное_доменное_имя_веб\>_/RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="9bccf-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https:// _\<webPoolFqdn\>_/RgsConfig.</span></span> 
  
6. <span data-ttu-id="9bccf-367">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-367">Do one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-368">На странице **Создание рабочего процесса** рядом с элементом **Интерактивный** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
   - <span data-ttu-id="9bccf-369">В разделе **Управление существующим рабочим процессом** найдите рабочий процесс, который требуется изменить, затем в разделе **Действие** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>
    
7. <span data-ttu-id="9bccf-370">Если для предоставления пользователям возможность вызывать рабочий процесс требуется дополнительная подготовка, снимите флажок **Активировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="9bccf-p169">При создании управляемого рабочего процесса необходимо выбрать функцию **Активировать рабочий процесс**. После сохранения активного управляемого рабочего процесс его можно изменить или отключить.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p169">If you are to creating a managed workflow, you need to select **Activate the workflow**. After you save the active, managed workflow, you can then modify and deactivate it.</span></span> 
  
8. <span data-ttu-id="9bccf-373">Чтобы разрешить федеративным пользователям звонки группе, установите флажок **Включить поддержку федерации** .</span><span class="sxs-lookup"><span data-stu-id="9bccf-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="9bccf-374">Кроме того, необходимо иметь политики внешнего доступа, применяемое к приложения группы ответа, настроенные для федерации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-375">Глобальную политику внешнего доступа применяется к приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="9bccf-376">Глобальная политика для федерации группы ответа можно настроить с помощью Скайп для панели управления Business Server или с помощью командлета **Set-CsExternalAccessPolicy** задать для параметра EnableOutsideAccess значение True.</span><span class="sxs-lookup"><span data-stu-id="9bccf-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="9bccf-377">Имейте в виду, параметров глобальной политики применяются ко всем пользователям, если они назначена политика узла или пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="9bccf-378">Таким образом прежде чем изменять этот параметр для групп ответа, убедитесь в том, что параметр федерации отвечает требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="9bccf-379">Для получения дополнительных сведений о как политики применяются к пользователям видеть [Управление внешнюю политику доступа для вашей организации](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="9bccf-380">Для получения дополнительных сведений о настройке федерации см **Set-CsExternalAccessPolicy** в документации.</span><span class="sxs-lookup"><span data-stu-id="9bccf-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="9bccf-381">Пользователей, которые размещаются в Скайп для бизнеса в Интернет не может размещать звонки для группы ответа, которые размещаются в локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="9bccf-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="9bccf-382">Это значение true в обоих гибридных развертываниях и в тех случаях, где федеративных локальное развертывание с помощью Скайп для бизнеса в Интернет развертывания.</span><span class="sxs-lookup"><span data-stu-id="9bccf-382">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Skype for Business Online deployment.</span></span> 
  
9. <span data-ttu-id="9bccf-383">Если требуется скрыть идентификационные данные агентов во время вызовов, установите флажок **Включить анонимность агента**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p173">Анонимные вызовы не должны начинаться с сеанса видеосвязи или обмена мгновенными сообщениями (после начала сеанса вызова можно добавить видео и мгновенные сообщения). Анонимный агент также может поставить вызов на удержание, передать вызов (скрытая передача и передача после консультации), а также выполнять парковку и извлечение вызовов. Анонимные вызовы не поддерживают конференц-связь, совместный доступ к приложениям и рабочему столу, передачу файлов, работу с доской, совместную работу с данными и запись звонков. Агенты, использующие подключаемый модуль VDI Lync, могут анонимно получать входящие вызовы, но не отправлять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p173">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span> 
  
10. <span data-ttu-id="9bccf-388">В поле **Введите адрес группы, которая будет принимать звонки** введите основной адрес универсального кода ресурса (URI) SIP группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
11. <span data-ttu-id="9bccf-389">В поле **Отображаемое имя** введите отображаемое имя рабочего процесса (например, группа ответа интерактивного автоответчика отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="9bccf-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-390">Исключение "\<«или»\>" символов в поле отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="9bccf-391">Не используйте следующие отображаемые имена, поскольку они зарезервированы: RGS Presence Watcher (Наблюдатель присутствия RGS) или Announcement Service (Служба оповещения).</span><span class="sxs-lookup"><span data-stu-id="9bccf-391">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span> 
  
12. <span data-ttu-id="9bccf-392">В поле **Номер телефона** введите универсальный код ресурса, назначенный группе ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="9bccf-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>
    
13. <span data-ttu-id="9bccf-393">В поле **Отображаемый номер** введите номер группы ответа для отображения (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="9bccf-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>
    
14. <span data-ttu-id="9bccf-394">(Необязательно) В поле **Описание**введите описание рабочего процесса, которое будет отображаться в карточке контакта в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9bccf-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span> 
    
15. <span data-ttu-id="9bccf-395">В поле **Тип рабочего процесса** выберите **Управляемый**, если этот им будет управлять руководитель группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="9bccf-396">Выполните следующие действия, чтобы назначить менеджеров группы ответа в рабочий процесс:</span><span class="sxs-lookup"><span data-stu-id="9bccf-396">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    <span data-ttu-id="9bccf-397">а.</span><span class="sxs-lookup"><span data-stu-id="9bccf-397">a.</span></span> <span data-ttu-id="9bccf-398">Введите универсальный код ресурса SIP, назначенный руководителю данного рабочего процесса, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-398">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    <span data-ttu-id="9bccf-399">б.</span><span class="sxs-lookup"><span data-stu-id="9bccf-399">b.</span></span> <span data-ttu-id="9bccf-400">Введите универсальный код ресурса SIP, назначенный дополнительным руководителям, которых требуется добавить к рабочему процессу, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9bccf-p178">Каждому пользователю, который назначен менеджером группы ответа, необходимо присвоить роль CsResponseGroupManager. Если пользователям не назначена эта роль, они не могут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p178">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span> 
  
16. <span data-ttu-id="9bccf-403">В разделе **Шаг 2. Выберите язык** щелкните язык, на котором будет выполняться распознавание речи и преобразование текста в речь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>
    
17. <span data-ttu-id="9bccf-404">Если необходимо настроить приветствие, в разделе **Шаг 3. Настройте приветствие** установите флажок **Отображать приветствие**, затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9bccf-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
    - <span data-ttu-id="9bccf-405">Для ввода приветствия в виде текста, который будет преобразовываться в речь для вызывающих абонентов, щелкните **Использовать текст, преобразованный в речь**, затем введите приветствие в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p179">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p179">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
    - <span data-ttu-id="9bccf-p180">Для воспроизведения записи приветствия из звукового файла Wave или Windows Media щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**. Нажмите кнопку **Загрузить** для загрузки звукового файла.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p180">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-412">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-413">Для получения дополнительных сведений о форматах файлов, поддерживаемые видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-413">For details about supported file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
18. <span data-ttu-id="9bccf-414">В разделе **Шаг 4. Укажите часы работы** щелкните часовой пояс рабочего процесса в списке **Часовой пояс**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p182">Часовой пояс – это пояс, к которому относятся вызывающие абоненты и агенты. Он используется для расчета часов открытия и закрытия. Например, если для рабочего процесса задано использование часового пояса "Североамериканское восточное стандартное время" и в качестве времени открытия указано 7:00, а в качестве времени закрытия – 11:00, предполагается, что офис открывается в 7:00 по восточному времени, а закрывается в 23:00 по восточному времени, соответственно. (Время необходимо вводить в 24-часовом формате.)</span><span class="sxs-lookup"><span data-stu-id="9bccf-p182">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span> 
  
19. <span data-ttu-id="9bccf-420">Выберите тип рабочего графика, который следует использовать. Для этого выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9bccf-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-421">Для применения предварительно заданного графика рабочего времени щелкните **Использовать готовое расписание**, затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-422">Необходимо определить по крайней мере один стандартное расписание, ранее, чтобы иметь возможность установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="9bccf-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="9bccf-423">Определение предварительно расписания с помощью командлета **New-CSRgsHoursOfBusiness** .</span><span class="sxs-lookup"><span data-stu-id="9bccf-423">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="9bccf-424">Дополнительные сведения см [(необязательно) группы ответа определение рабочих часов в Скайп для бизнеса 2015](optional-define-response-group-business-hours.md).</span><span class="sxs-lookup"><span data-stu-id="9bccf-424">For details, see [(Optional) Define Response Group business hours in Skype for Business 2015](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="9bccf-425">При выборе предварительно заданного расписания дни и часы работы группы ответа автоматически водятся в полях **День**, **Открыть** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>
  
   - <span data-ttu-id="9bccf-426">Для применения пользовательского графика, относящегося только к данному рабочему процессу, щелкните **Использовать расписание пользователя**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>
    
20. <span data-ttu-id="9bccf-427">Если вы создаете индивидуальное расписание для данного рабочего процесса, установите флажки, чтобы выбрать дни недели, по которым группа ответа доступна.</span><span class="sxs-lookup"><span data-stu-id="9bccf-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>
    
21. <span data-ttu-id="9bccf-428">При создании пользовательского расписания введите в поля **Открыть** и **Закрыть** часы работы группы ответа для каждого дня недели..</span><span class="sxs-lookup"><span data-stu-id="9bccf-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-p184">Часы вводятся в полях **Открыть** и **Закрыть** в 24-часовом формате. Например, если рабочий день продолжается с 9.00 до 17.00 с перерывом на обед в полдень, часы работы указываются следующим образом: **Открыть** 9:00, **Закрыть** 12:00, **Открыть** 13:00, **Закрыть** 17:00.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p184">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>
  
22. <span data-ttu-id="9bccf-431">Если требуется воспроизводить сообщение в нерабочее время, установите флажок **Отображать сообщение в нерабочее для группы ответа время**, затем укажите сообщение для воспроизведения, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
    - <span data-ttu-id="9bccf-432">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-p185">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p185">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
    - <span data-ttu-id="9bccf-p186">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p186">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-439">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-440">Для получения дополнительных сведений о форматах файлов, поддерживаемые видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-440">For details about supported file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
23. <span data-ttu-id="9bccf-441">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="9bccf-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
     - <span data-ttu-id="9bccf-442">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-442">To disconnect the call, click **Disconnect Call**.</span></span>
    
     - <span data-ttu-id="9bccf-443">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bccf-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="9bccf-444">Формат адреса голосовой почты _ \<username\>_@ _\<domainname\> _ (например, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-444">The format for the voice mail address is  _\<username\>_@ _\<domainname\>_ (for example, bob@contoso.com).</span></span>
    
     - <span data-ttu-id="9bccf-445">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="9bccf-446">Имеет формат для пользователя адрес _ \<username\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="9bccf-446">The format for the user address is  _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="9bccf-447">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9bccf-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="9bccf-448">— Номер телефона в формате _ \<номер\>_@ _\<domainname\> _ (например, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-448">The format for the telephone number is  _\<number\>_@ _\<domainname\>_ (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="9bccf-449">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="9bccf-449">The domain name is used to route the caller to the correct destination.</span></span>
    
24. <span data-ttu-id="9bccf-450">В разделе **Шаг 5. Указание выходных дней** установите флажки для одной или нескольких групп выходных дней, когда группа ответа не будет работать.</span><span class="sxs-lookup"><span data-stu-id="9bccf-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-451">Необходимо определить праздников и наборах праздников, прежде чем настраивать этот рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9bccf-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="9bccf-452">Используйте командлеты **New-CsRgsHoliday** и **Командлет New-CsRgsHolidaySet** для определения праздников и победы наборов.</span><span class="sxs-lookup"><span data-stu-id="9bccf-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="9bccf-453">Дополнительные сведения см [(необязательно) определение наборах праздников ответа в Скайп для 2015 бизнеса](optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9bccf-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business 2015](optional-define-response-group-holiday-sets.md).</span></span> 
  
25. <span data-ttu-id="9bccf-454">Если требуется воспроизводить сообщение в выходные дни, установите флажок **Отображать сообщение в выходные дни**, затем укажите воспроизводимое сообщение, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
   - <span data-ttu-id="9bccf-455">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-p192">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p192">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
   - <span data-ttu-id="9bccf-p193">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p193">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-462">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-462">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-463">Для получения дополнительных сведений о форматах файлов, поддерживаемые звука видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-463">For details about supported audio file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
26. <span data-ttu-id="9bccf-464">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="9bccf-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
    - <span data-ttu-id="9bccf-465">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-465">To disconnect the call, click **Disconnect Call**.</span></span>
    
    - <span data-ttu-id="9bccf-466">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9bccf-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="9bccf-467">Формат адреса голосовой почты _ \<username\>_@ _\<domainname\> _ (например, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-467">The format for the voice mail address is  _\<username\>_@ _\<domainname\>_ (for example, bob@contoso.com).</span></span>
    
    - <span data-ttu-id="9bccf-468">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bccf-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="9bccf-469">Имеет формат для пользователя адрес _ \<username\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="9bccf-469">The format for the user address is  _\<username\>_@ _\<domainname\>_.</span></span>
    
    - <span data-ttu-id="9bccf-470">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9bccf-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="9bccf-471">— Номер телефона в формате _ \<номер\>_@ _\<domainname\> _ (например, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9bccf-471">The format for the telephone number is  _\<number\>_@ _\<domainname\>_ (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="9bccf-472">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="9bccf-472">The domain name is used to route the caller to the correct destination.</span></span>
    
27. <span data-ttu-id="9bccf-473">В разделе **Шаг 6. Настройте музыку для режима удержания** выберите музыку, которую должны будут прослушивать вызывающие абоненты в ожидании ответа агента. Для этого выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9bccf-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
    - <span data-ttu-id="9bccf-474">Если в режиме удержания требуется воспроизводить музыкальную запись по умолчанию, щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-474">To use the default music on-hold recording, click **Use default**.</span></span>
    
    - <span data-ttu-id="9bccf-475">Чтобы использовать запись музыки при удержании звуковой файл, нажмите кнопку **выбрать файл музыки**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-475">To use an audio file recording for the on-hold music, click **Select a music file**.</span></span> <span data-ttu-id="9bccf-476">Для загрузки нового звукового файла щелкните ссылку **музыкальный файл**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-476">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="9bccf-477">В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый файл, затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-477">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="9bccf-478">Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-478">Click **Upload** to load the audio file.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-479">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-479">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-480">Для получения дополнительных сведений о форматах файлов, поддерживаемые видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-480">For details about supported file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
28. <span data-ttu-id="9bccf-481">В разделе **Шаг 7. Настройте интерактивный голосовой ответ** под заголовком **Пользователь услышит следующий текст или записанное сообщение** укажите вопрос, адресованный вызывающим абонентам, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9bccf-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
    - <span data-ttu-id="9bccf-482">Для ввода вопроса в текстовом формате щелкните **Использовать текст, преобразованный в речь** (Использовать преобразование текста в речь) и введите вопрос в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="9bccf-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bccf-p200">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p200">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9bccf-485">Символ "#" интерпретируется модулем преобразования текста в речь как слово "номер".</span><span class="sxs-lookup"><span data-stu-id="9bccf-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="9bccf-486">Если требуется указать клавишу #, то вместо символа используйте имя клавиши.</span><span class="sxs-lookup"><span data-stu-id="9bccf-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="9bccf-487">Пример: Для связи с сотрудником отдела продаж нажмите кнопку с решеткой.</span><span class="sxs-lookup"><span data-stu-id="9bccf-487">For example, "To talk to sales, press the pound key."</span></span> 
  
   - <span data-ttu-id="9bccf-488">Для воспроизведения вопроса из заранее записанного звукового файла щелкните **Выбрать запись**, затем щелкните ссылку **запись** для загрузки файла.</span><span class="sxs-lookup"><span data-stu-id="9bccf-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="9bccf-489">В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="9bccf-490">Нажмите кнопку **Отправить** загрузить файл и затем при необходимости можно ввести вопрос в текстовом поле (Это позволяет вопрос и ответ вызывающего абонента, пересылаемые отвечающему агенту).</span><span class="sxs-lookup"><span data-stu-id="9bccf-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9bccf-491">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="9bccf-491">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="9bccf-492">Для получения дополнительных сведений о форматах файлов, поддерживаемые видеть [Технические требования для групп ответа](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bccf-492">For details about supported file formats, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span> 
  
29. <span data-ttu-id="9bccf-493">В поле **Ответ 1** (1 ответ) укажите первый возможный ответ на вопрос, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9bccf-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9bccf-p204">При указании голосовых ответов не используйте двойные кавычки ("). Это может привести к сбою интерактивного автоответчика.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p204">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9bccf-496">Для ответа звонящий может использовать речь или буквенно-цифровые клавиши либо и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="9bccf-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span> 
  
    - <span data-ttu-id="9bccf-497">Если требуется разрешить вызывающему абоненту отвечать голосом, введите ответ в поле **Введите голосовой ответ**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
    - <span data-ttu-id="9bccf-498">Если требуется разрешить вызывающему абоненту отвечать нажатием клавиши на клавиатуре, щелкните цифровую клавишу в поле **Цифра**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>
    
30. <span data-ttu-id="9bccf-499">Укажите, требуется ли перенаправлять звонящего в очередь или задать ему другой вопрос, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9bccf-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
    - <span data-ttu-id="9bccf-500">Для перенаправления вызывающего абонента в очередь щелкните **Отправить в очередь** и в списке **Выбрать очередь** щелкните требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="9bccf-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
    - <span data-ttu-id="9bccf-p205">Если требуется задать другой вопрос, щелкните **Задать другой вопрос**, затем щелкните **Использовать текст, преобразованный в речь**, и введите вопрос либо щелкните **Выбрать запись**. Группируя ответы, укажите в этом разделе до четырех возможных ответов на дополнительный вопрос и очередь для каждого ответа. Для задания третьего или четвертого возможного ответа установите флажки **Ответ 3** или **Ответ 4**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p205">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>
    
31. <span data-ttu-id="9bccf-p206">Укажите до трех других возможных ответов на исходный вопрос и выполняемые действия для каждого ответа, повторив шаги 28 и 29. Для задания третьего или четвертого возможного ответа установите флажки **Ответ 3** или **Ответ 4**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p206">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>
    
32. <span data-ttu-id="9bccf-506">Нажмите кнопку **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-506">Click **Deploy**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="9bccf-507">Чтобы использовать Скайп для консоли Business Server для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bccf-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="9bccf-508">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9bccf-509">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9bccf-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9bccf-p207">Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p207">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}) .ServiceId;
   ```

4. <span data-ttu-id="9bccf-p208">Интерактивному рабочему процессу требуется как минимум две очереди и две группы агентов. Сначала создайте группы агентов. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p208">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="9bccf-p209">Создайте очереди. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p209">Create the queues. Run:</span></span>
    
   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="9bccf-p210">Создайте приглашение для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p210">Create the first response group prompt. Run:</span></span>
    
   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="9bccf-p211">Теперь создайте действие, которое должно выполняться после приглашения, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p211">Then create the action to be performed after the prompt. Run:</span></span>
    
   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="9bccf-p212">Создайте ответ для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p212">Create the first response group answer. Run:</span></span>
    
   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="9bccf-p213">Теперь создайте второе приглашение, действие вызова и ответ. Сначала создайте приглашение с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p213">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="9bccf-p214">Создайте второе действие вызова с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p214">Create the second call action. Run:</span></span>
    
    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="9bccf-p215">Создайте ответ для второй группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p215">Create the second response group answer. Run:</span></span>
    
    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="9bccf-p216">Создайте приглашение верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p216">Create the top-level prompt. Run:</span></span>
    
    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="9bccf-p217">Создайте вопрос верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p217">Create the top-level question. Run:</span></span>
    
    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="9bccf-p218">Теперь создайте рабочий процесс с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9bccf-p218">Now create the workflow. Run:</span></span>
    
    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="9bccf-p219">Всем пользователям, назначенным менеджерами группы ответа, должна быть назначена роль CsResponseGroupManager. Если пользователям не назначить эту роль, то они не смогут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="9bccf-p219">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9bccf-538">См. также</span><span class="sxs-lookup"><span data-stu-id="9bccf-538">See also</span></span>

#### 

[<span data-ttu-id="9bccf-539">(Необязательно) Определение группы ответа праздничные дни в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="9bccf-539">(Optional) Define Response Group holiday sets in Skype for Business 2015</span></span>](optional-define-response-group-holiday-sets.md)
#### 

[<span data-ttu-id="9bccf-540">(Необязательно) Группа ответа определение рабочих часов в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="9bccf-540">(Optional) Define Response Group business hours in Skype for Business 2015</span></span>](optional-define-response-group-business-hours.md)
#### 

[<span data-ttu-id="9bccf-541">Командлет New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="9bccf-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)
  
[<span data-ttu-id="9bccf-542">Командлет Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="9bccf-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)
  
[<span data-ttu-id="9bccf-543">Командлет New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="9bccf-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="9bccf-544">Командлет New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="9bccf-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

