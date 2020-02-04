---
title: 'Lync Server 2013: создание или изменение интерактивного рабочего процесса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec10d1d9c3281485078b2d7823978c429ea1be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="e9970-102">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9970-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9970-103">_**Тема последнего изменения:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="e9970-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="e9970-104">Для создания или изменения интерактивного рабочего процесса можно воспользоваться одной из описанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="e9970-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9970-105">Вы можете использовать командную консоль Lync Server или средство настройки группы ответа для создания и изменения интерактивных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e9970-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="e9970-106">Вы можете получить доступ к средству настройки группы ответа из панели управления Lync Server или открыть ее непосредственно из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9970-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="e9970-107">Использование средства настройки группы ответа для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e9970-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="e9970-108">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="e9970-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9970-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9970-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9970-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9970-111">В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="e9970-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="e9970-112">На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="e9970-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="e9970-113">В поле поиска **Выбор службы** полностью или частично введите имя службы **ApplicationServer**, обеспечивающей размещение создаваемого или изменяемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e9970-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="e9970-114">В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9970-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-115">Откроется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="e9970-116">Вы также можете открыть средство настройки группы ответа прямо из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9970-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="e9970-117">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e9970-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="e9970-118">На странице **Создание рабочего процесса** рядом с элементом **Интерактивный** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e9970-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="e9970-119">В разделе **Управление существующим рабочим процессом** найдите рабочий процесс, который требуется изменить, затем в разделе **Действие** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e9970-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="e9970-120">Если для предоставления пользователям возможность вызывать рабочий процесс требуется дополнительная подготовка, снимите флажок **Активировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="e9970-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-p105">При создании управляемого рабочего процесса необходимо выбрать функцию <STRONG>Активировать рабочий процесс</STRONG>. После сохранения активного управляемого рабочего процесс его можно изменить или отключить.</span><span class="sxs-lookup"><span data-stu-id="e9970-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="e9970-123">To allow federated users to call the group, select the **Enable for federation** check box.</span><span class="sxs-lookup"><span data-stu-id="e9970-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="e9970-124">Кроме того, необходимо иметь политику внешнего доступа, которая применяется к приложению группы ответа, настроенному для Федерации.</span><span class="sxs-lookup"><span data-stu-id="e9970-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-125">Глобальная политика внешнего доступа применима к приложению группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="e9970-126">Глобальную политику для Федерации групп ответов можно настроить с помощью панели управления Lync Server или с помощью командлета <STRONG>Set-ксекстерналакцессполици</STRONG> , чтобы установить для параметра Енаблеаутсидеакцесс значение true.</span><span class="sxs-lookup"><span data-stu-id="e9970-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="e9970-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span><span class="sxs-lookup"><span data-stu-id="e9970-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="e9970-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span><span class="sxs-lookup"><span data-stu-id="e9970-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="e9970-129">Подробные сведения о том, как политики применяются к пользователям, можно найти <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в разделе Управление политикой внешнего доступа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="e9970-130">Дополнительные сведения о параметрах Федерации можно найти в разделе <STRONG>Set-ксекстерналакцессполици</STRONG> в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9970-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-131">Пользователи, размещенные в Lync Online, не могут размещать звонки в группы ответа, размещенные в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="e9970-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="e9970-132">Это справедливо и для гибридных развертываний, и в случаях, когда локальное развертывание является федеративным с развертыванием Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e9970-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="e9970-133">Если требуется скрыть идентификационные данные агентов во время вызовов, установите флажок **Включить анонимность агента**.</span><span class="sxs-lookup"><span data-stu-id="e9970-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-p109">Анонимные вызовы не должны начинаться с сеанса видеосвязи или обмена мгновенными сообщениями (после начала сеанса вызова можно добавить видео и мгновенные сообщения). Анонимный агент также может поставить вызов на удержание, передать вызов (скрытая передача и передача после консультации), а также выполнять парковку и извлечение вызовов. Анонимные вызовы не поддерживают конференц-связь, совместный доступ к приложениям и рабочему столу, передачу файлов, работу с доской, совместную работу с данными и запись звонков. Агенты, использующие подключаемый модуль VDI Lync, могут анонимно получать входящие вызовы, но не отправлять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="e9970-p109">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="e9970-138">В поле **Введите адрес группы, которая будет принимать звонки** введите основной адрес универсального кода ресурса (URI) SIP группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e9970-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="e9970-139">В поле **Отображаемое имя** введите отображаемое имя рабочего процесса (например, группа ответа интерактивного автоответчика отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="e9970-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-140">Не включайте символы "&lt;" или "&gt;" в отображаемом имени.</span><span class="sxs-lookup"><span data-stu-id="e9970-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="e9970-141">Не используйте следующие отображаемые имена, поскольку они зарезервированы: RGS Presence Watcher (Наблюдатель присутствия RGS) или Announcement Service (Служба оповещения).</span><span class="sxs-lookup"><span data-stu-id="e9970-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="e9970-142">В поле **Номер телефона** введите универсальный код ресурса, назначенный группе ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="e9970-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="e9970-143">В поле **Отображаемый номер** введите номер группы ответа для отображения (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="e9970-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="e9970-144">Необязательно В поле **Описание**введите описание рабочего процесса, которое должно отображаться на карточке контакта в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="e9970-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="e9970-145">В поле **Тип рабочего процесса** выберите **Управляемый**, если этот им будет управлять руководитель группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="e9970-146">Выполните указанные ниже действия, чтобы назначить диспетчерам групп ответов для рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="e9970-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="e9970-147">Введите универсальный код ресурса SIP, назначенный руководителю данного рабочего процесса, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e9970-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="e9970-148">Введите универсальный код ресурса SIP, назначенный дополнительным руководителям, которых требуется добавить к рабочему процессу, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e9970-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e9970-p112">Каждому пользователю, который назначен менеджером группы ответа, необходимо присвоить роль CsResponseGroupManager. Если пользователям не назначена эта роль, они не могут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="e9970-151">В разделе **Шаг 2. Выберите язык** щелкните язык, на котором будет выполняться распознавание речи и преобразование текста в речь.</span><span class="sxs-lookup"><span data-stu-id="e9970-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="e9970-152">Если необходимо настроить приветствие, в разделе **Шаг 3. Настройте приветствие** установите флажок **Отображать приветствие**, затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e9970-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="e9970-153">Для ввода приветствия в виде текста, который будет преобразовываться в речь для вызывающих абонентов, щелкните **Использовать текст, преобразованный в речь**, затем введите приветствие в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e9970-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-p113">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9970-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9970-p114">Для воспроизведения записи приветствия из звукового файла Wave или Windows Media щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**. Нажмите кнопку **Загрузить** для загрузки звукового файла.</span><span class="sxs-lookup"><span data-stu-id="e9970-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-160">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e9970-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="e9970-161">Подробные сведения о поддерживаемых форматах файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="e9970-162">В разделе **Шаг 4. Укажите часы работы** щелкните часовой пояс рабочего процесса в списке **Часовой пояс**.</span><span class="sxs-lookup"><span data-stu-id="e9970-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-p116">Часовой пояс – это пояс, к которому относятся вызывающие абоненты и агенты. Он используется для расчета часов открытия и закрытия. Например, если для рабочего процесса задано использование часового пояса "Североамериканское восточное стандартное время" и в качестве времени открытия указано 7:00, а в качестве времени закрытия – 11:00, предполагается, что офис открывается в 7:00 по восточному времени, а закрывается в 23:00 по восточному времени, соответственно. (Время необходимо вводить в 24-часовом формате.)</span><span class="sxs-lookup"><span data-stu-id="e9970-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="e9970-168">Выберите тип рабочего графика, который следует использовать. Для этого выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e9970-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="e9970-169">Для применения предварительно заданного графика рабочего времени щелкните **Использовать готовое расписание**, затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e9970-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-170">Чтобы можно было выбрать этот параметр, необходимо предварительно определить хотя бы одно предварительно заданное расписание.</span><span class="sxs-lookup"><span data-stu-id="e9970-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="e9970-171">Готовые расписания определяются с помощью командлета <STRONG>New-ксргшаурсофбусинесс</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e9970-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="e9970-172">Дополнительные сведения можно найти <A href="lync-server-2013-optional-define-response-group-business-hours.md">в разделе (необязательно) определение группы ответа в часах Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="e9970-173">При выборе предварительно заданного расписания дни и часы работы группы ответа автоматически водятся в полях <STRONG>День</STRONG>, <STRONG>Открыть</STRONG> и <STRONG>Закрыть</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9970-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9970-174">Для применения пользовательского графика, относящегося только к данному рабочему процессу, щелкните **Использовать расписание пользователя**.</span><span class="sxs-lookup"><span data-stu-id="e9970-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="e9970-175">Если вы создаете индивидуальное расписание для данного рабочего процесса, установите флажки, чтобы выбрать дни недели, по которым группа ответа доступна.</span><span class="sxs-lookup"><span data-stu-id="e9970-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="e9970-176">При создании пользовательского расписания введите в поля **Открыть** и **Закрыть** часы работы группы ответа для каждого дня недели..</span><span class="sxs-lookup"><span data-stu-id="e9970-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-p118">Часы вводятся в полях <STRONG>Открыть</STRONG> и <STRONG>Закрыть</STRONG> в 24-часовом формате. Например, если рабочий день продолжается с 9.00 до 17.00 с перерывом на обед в полдень, часы работы указываются следующим образом: <STRONG>Открыть</STRONG> 9:00, <STRONG>Закрыть</STRONG> 12:00, <STRONG>Открыть</STRONG> 13:00, <STRONG>Закрыть</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="e9970-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="e9970-179">Если требуется воспроизводить сообщение в нерабочее время, установите флажок **Отображать сообщение в нерабочее для группы ответа время**, затем укажите сообщение для воспроизведения, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e9970-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="e9970-180">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e9970-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-181">Не включайте в вводимый текст теги HTML.</span><span class="sxs-lookup"><span data-stu-id="e9970-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="e9970-182">В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9970-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9970-p120">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="e9970-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-187">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e9970-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="e9970-188">Подробные сведения о поддерживаемых форматах файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="e9970-189">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="e9970-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="e9970-190">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="e9970-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="e9970-191">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e9970-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="e9970-192">Адрес голосовой \<почты — имя пользователя\>@\<DomainName\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e9970-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="e9970-193">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9970-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="e9970-194">Адрес пользователя — \<\>@\<имя пользователя имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="e9970-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="e9970-195">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e9970-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="e9970-196">Формат \<номера телефона — число\>@\<DomainName\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e9970-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="e9970-197">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="e9970-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="e9970-198">В разделе **Шаг 5. Указание выходных дней** установите флажки для одной или нескольких групп выходных дней, когда группа ответа не будет работать.</span><span class="sxs-lookup"><span data-stu-id="e9970-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-199">Перед настройкой рабочего процесса вам нужно определить праздники и наборы праздников.</span><span class="sxs-lookup"><span data-stu-id="e9970-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="e9970-200">Используйте командлеты <STRONG>New-ксргшолидай</STRONG> и <STRONG>New-ксргшолидайсет</STRONG> для определения праздников и наборов праздников.</span><span class="sxs-lookup"><span data-stu-id="e9970-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="e9970-201">Дополнительные сведения можно найти <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">в разделе (необязательно) Определение наборов праздников группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="e9970-202">Если требуется воспроизводить сообщение в выходные дни, установите флажок **Отображать сообщение в выходные дни**, затем укажите воспроизводимое сообщение, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e9970-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="e9970-203">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e9970-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-204">Не включайте в вводимый текст теги HTML.</span><span class="sxs-lookup"><span data-stu-id="e9970-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="e9970-205">В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9970-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9970-p127">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="e9970-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-210">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e9970-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="e9970-211">Подробные сведения о поддерживаемых форматах звуковых файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="e9970-212">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="e9970-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="e9970-213">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="e9970-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="e9970-214">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e9970-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="e9970-215">Адрес голосовой \<почты — имя пользователя\>@\<DomainName\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e9970-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="e9970-216">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9970-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="e9970-217">Адрес пользователя — \<\>@\<имя пользователя имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="e9970-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="e9970-218">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e9970-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="e9970-219">Формат \<номера телефона — число\>@\<DomainName\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e9970-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="e9970-220">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="e9970-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="e9970-221">В разделе **Шаг 6. Настройте музыку для режима удержания** выберите музыку, которую должны будут прослушивать вызывающие абоненты в ожидании ответа агента. Для этого выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e9970-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="e9970-222">Если в режиме удержания требуется воспроизводить музыкальную запись по умолчанию, щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e9970-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="e9970-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span><span class="sxs-lookup"><span data-stu-id="e9970-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-227">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e9970-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="e9970-228">Подробные сведения о поддерживаемых форматах файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="e9970-229">В разделе **Шаг 7. Настройте интерактивный голосовой ответ** под заголовком **Пользователь услышит следующий текст или записанное сообщение** укажите вопрос, адресованный вызывающим абонентам, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9970-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="e9970-230">Для ввода вопроса в текстовом формате щелкните **Использовать текст, преобразованный в речь** (Использовать преобразование текста в речь) и введите вопрос в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="e9970-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-p134">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9970-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-233">Символ "#" интерпретируется модулем преобразования текста в речь как слово "номер".</span><span class="sxs-lookup"><span data-stu-id="e9970-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="e9970-234">Если требуется указать клавишу #, то вместо символа используйте имя клавиши.</span><span class="sxs-lookup"><span data-stu-id="e9970-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="e9970-235">Пример: Для связи с сотрудником отдела продаж нажмите кнопку с решеткой.</span><span class="sxs-lookup"><span data-stu-id="e9970-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="e9970-p136">Для воспроизведения вопроса из заранее записанного звукового файла щелкните **Выбрать запись**, затем щелкните ссылку **запись** для загрузки файла. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**. Щелкните **Загрузить** для загрузки файла, затем при необходимости введите вопрос в текстовом поле (это позволяет переадресовывать отвечающему агенту вопрос и ответ вызывающего абонента).</span><span class="sxs-lookup"><span data-stu-id="e9970-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9970-239">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e9970-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="e9970-240">Подробные сведения о поддерживаемых форматах файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9970-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="e9970-241">В поле **Ответ 1** (1 ответ) укажите первый возможный ответ на вопрос, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9970-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e9970-p138">При указании голосовых ответов не используйте двойные кавычки ("). Это может привести к сбою интерактивного автоответчика.</span><span class="sxs-lookup"><span data-stu-id="e9970-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-244">Для ответа звонящий может использовать речь или буквенно-цифровые клавиши либо и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="e9970-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="e9970-245">Если требуется разрешить вызывающему абоненту отвечать голосом, введите ответ в поле **Введите голосовой ответ**.</span><span class="sxs-lookup"><span data-stu-id="e9970-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="e9970-246">Если требуется разрешить вызывающему абоненту отвечать нажатием клавиши на клавиатуре, щелкните цифровую клавишу в поле **Цифра**.</span><span class="sxs-lookup"><span data-stu-id="e9970-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="e9970-247">Укажите, требуется ли перенаправлять звонящего в очередь или задать ему другой вопрос, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9970-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="e9970-248">Для перенаправления вызывающего абонента в очередь щелкните **Отправить в очередь** и в списке **Выбрать очередь** щелкните требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="e9970-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="e9970-p139">Если требуется задать другой вопрос, щелкните **Задать другой вопрос**, затем щелкните **Использовать текст, преобразованный в речь**, и введите вопрос либо щелкните **Выбрать запись**. Группируя ответы, укажите в этом разделе до четырех возможных ответов на дополнительный вопрос и очередь для каждого ответа. Для задания третьего или четвертого возможного ответа установите флажки **Ответ 3** или **Ответ 4**.</span><span class="sxs-lookup"><span data-stu-id="e9970-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="e9970-p140">Укажите до трех других возможных ответов на исходный вопрос и выполняемые действия для каждого ответа, повторив шаги 28 и 29. Для задания третьего или четвертого возможного ответа установите флажки **Ответ 3** или **Ответ 4**.</span><span class="sxs-lookup"><span data-stu-id="e9970-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="e9970-254">Нажмите кнопку **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="e9970-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="e9970-255">Использование Windows PowerShell для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e9970-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="e9970-256">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="e9970-257">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9970-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e9970-p141">Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9970-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="e9970-p142">Интерактивному рабочему процессу требуется как минимум две очереди и две группы агентов. Сначала создайте группы агентов. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9970-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="e9970-p143">Создайте очереди. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9970-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="e9970-p144">Создайте приглашение для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="e9970-p145">Теперь создайте действие, которое должно выполняться после приглашения, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="e9970-p146">Создайте ответ для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="e9970-p147">Теперь создайте второе приглашение, действие вызова и ответ. Сначала создайте приглашение с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="e9970-p148">Создайте второе действие вызова с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="e9970-p149">Создайте ответ для второй группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="e9970-p150">Создайте приглашение верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="e9970-p151">Создайте вопрос верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="e9970-p152">Теперь создайте рабочий процесс с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e9970-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9970-p153">Всем пользователям, назначенным менеджерами группы ответа, должна быть назначена роль CsResponseGroupManager. Если пользователям не назначить эту роль, то они не смогут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="e9970-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

