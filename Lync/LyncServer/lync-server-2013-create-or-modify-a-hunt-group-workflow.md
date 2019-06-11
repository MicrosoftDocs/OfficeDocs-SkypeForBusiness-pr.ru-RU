---
title: 'Lync Server 2013: создание или изменение рабочего процесса группы слежения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="43686-102">Создание или изменение рабочего процесса группы слежения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43686-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43686-103">_**Тема последнего изменения:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="43686-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="43686-104">Для создания или изменения рабочего процесса группы слежения воспользуйтесь одной из описанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="43686-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43686-105">Вы можете использовать командную консоль Lync Server или средство настройки группы ответа для создания и изменения рабочих процессов группы слежения.</span><span class="sxs-lookup"><span data-stu-id="43686-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="43686-106">Вы можете получить доступ к средству настройки группы ответа из панели управления Lync Server или открыть ее непосредственно из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43686-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="43686-107">Использование средства настройки группы ответа для создания или изменения рабочего процесса группы слежения</span><span class="sxs-lookup"><span data-stu-id="43686-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="43686-108">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="43686-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43686-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43686-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43686-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43686-111">В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="43686-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="43686-112">На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="43686-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="43686-113">В поле поиска **Выбор службы** полностью или частично введите имя службы **ApplicationServer**, обеспечивающей размещение создаваемого или изменяемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43686-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="43686-114">В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43686-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-115">Откроется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="43686-116">Вы также можете открыть средство настройки группы ответа прямо из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43686-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="43686-117">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="43686-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="43686-118">В разделе **Создание рабочего процесса** рядом с элементом **Сервисная группа** нажмите кнопку "Создать".</span><span class="sxs-lookup"><span data-stu-id="43686-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="43686-119">В разделе **Управление существующим рабочим процессом** найдите рабочий процесс, который требуется изменить, затем в разделе **Действие** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="43686-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="43686-120">Если все готово к тому, чтобы разрешить пользователям вызывать рабочий процесс, установите флажок **Активировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="43686-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-p105">При создании управляемого рабочего процесса необходимо выбрать функцию <STRONG>Активировать рабочий процесс</STRONG>. После сохранения активного управляемого рабочего процесс его можно изменить или отключить.</span><span class="sxs-lookup"><span data-stu-id="43686-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="43686-123">To allow federated users to call the group, select the **Enable for federation** check box.</span><span class="sxs-lookup"><span data-stu-id="43686-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="43686-124">Кроме того, необходимо иметь политику внешнего доступа, которая применяется к приложению группы ответа, настроенному для Федерации.</span><span class="sxs-lookup"><span data-stu-id="43686-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-125">Глобальная политика внешнего доступа применима к приложению группы ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="43686-126">Глобальную политику для Федерации групп ответов можно настроить с помощью панели управления Lync Server или с помощью командлета <STRONG>Set-ксекстерналакцессполици</STRONG> , чтобы установить для параметра Енаблеаутсидеакцесс значение true.</span><span class="sxs-lookup"><span data-stu-id="43686-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="43686-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span><span class="sxs-lookup"><span data-stu-id="43686-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="43686-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span><span class="sxs-lookup"><span data-stu-id="43686-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="43686-129">Подробные сведения о том, как политики применяются к пользователям, можно найти <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в разделе Управление политикой внешнего доступа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="43686-130">Дополнительные сведения о параметрах Федерации можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-ксекстерналакцессполици</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-131">Пользователи, размещенные в Lync Online, не могут размещать звонки в группы ответа, размещенные в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="43686-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="43686-132">Это справедливо и для гибридных развертываний, и в случаях, когда локальное развертывание является федеративным с развертыванием Lync Online.</span><span class="sxs-lookup"><span data-stu-id="43686-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="43686-133">Если требуется скрыть идентификационные данные агентов во время вызовов, установите флажок **Включить анонимность агента**.</span><span class="sxs-lookup"><span data-stu-id="43686-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-p109">Анонимные вызовы не должны начинаться с сеанса видеосвязи или обмена мгновенными сообщениями (после начала сеанса вызова можно добавить видео и мгновенные сообщения). Анонимный агент также может поставить вызов на удержание, передать вызов (скрытая передача и передача после консультации), а также выполнять парковку и извлечение вызовов. Анонимные вызовы не поддерживают конференц-связь, совместный доступ к приложениям и рабочему столу, передачу файлов, работу с доской, совместную работу с данными и запись звонков. Агенты, использующие подключаемый модуль VDI Lync, могут анонимно получать входящие вызовы, но не отправлять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="43686-p109">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="43686-138">В поле **Введите адрес группы, которая будет принимать звонки** введите основной адрес универсального кода ресурса (URI) SIP группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43686-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-139">Основной адрес универсального кода ресурса для рабочего процесса служит для распознавания рабочего процесса и ссылок на него.</span><span class="sxs-lookup"><span data-stu-id="43686-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="43686-140">Введенный URI SIP создается как объект контакта в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43686-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="43686-141">Для создания URI объект должен быть уникальным в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43686-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="43686-142">В поле **Отображаемое имя**введите имя, которое будет отображаться для рабочего процесса (например, Группа отклика на продажу).</span><span class="sxs-lookup"><span data-stu-id="43686-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-143">Не включайте символы "&lt;" или "&gt;" в отображаемом имени.</span><span class="sxs-lookup"><span data-stu-id="43686-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="43686-144">Не допускаются отображаемые имена <STRONG>RGS Presence Watcher</STRONG> (Наблюдатель присутствия RGS) и <STRONG>Announcement Service</STRONG> (Служба оповещения), так как они зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="43686-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="43686-145">В поле **Номер телефона** введите строку универсального кода ресурса для группы ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="43686-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="43686-146">В поле **Отображаемый номер** введите номер группы ответа для отображения (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="43686-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="43686-147">Необязательно В поле **Описание**введите описание рабочего процесса в том виде, в котором оно должно отображаться на карточке контакта в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="43686-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="43686-148">В поле **Тип рабочего процесса** выберите **Управляемый**, если этот им будет управлять руководитель группы ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="43686-149">Выполните указанные ниже действия, чтобы назначить диспетчерам групп ответов для рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="43686-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="43686-150">Введите универсальный код ресурса SIP, назначенный руководителю данного рабочего процесса, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="43686-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="43686-151">Введите универсальный код ресурса SIP, назначенный дополнительным руководителям, которых требуется добавить к рабочему процессу, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="43686-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="43686-p113">Каждому пользователю, который назначен менеджером группы ответа, необходимо присвоить роль CsResponseGroupManager. Если пользователям не назначена эта роль, они не могут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="43686-154">В разделе **Шаг 2. Выберите язык** щелкните язык, на котором будет выполняться распознавание речи и преобразование текста в речь.</span><span class="sxs-lookup"><span data-stu-id="43686-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="43686-155">Если необходимо настроить приветствие, в разделе **Шаг 3. Настройте приветствие** установите флажок **Отображать приветствие**, затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="43686-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="43686-156">Для ввода приветствия в виде текста, который будет преобразовываться в речь для вызывающих абонентов, щелкните **Использовать текст, преобразованный в речь**, затем введите приветствие в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="43686-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-157">Не включайте в вводимый текст теги HTML.</span><span class="sxs-lookup"><span data-stu-id="43686-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="43686-158">В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="43686-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="43686-p115">Для воспроизведения записи приветствия из звукового файла Wave (.wav) или файла Windows Media (.wma) щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый звуковой файл, затем нажмите кнопку **Открыть**. Нажмите кнопку **Загрузить** для загрузки звукового файла.</span><span class="sxs-lookup"><span data-stu-id="43686-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-163">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="43686-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="43686-164">Подробные сведения о поддерживаемых форматах файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="43686-165">В разделе **Шаг 4. Укажите часы работы** в поле **Ваш часовой пояс** щелкните часовой пояс для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43686-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-p117">Часовой пояс – это пояс, к которому относятся вызывающие абоненты и агенты. Он используется для расчета часов открытия и закрытия. Например, если для рабочего процесса задано использование часового пояса "Североамериканское восточное стандартное время" и в качестве времени открытия указано 7:00, а в качестве времени закрытия – 23:00, предполагается, что офис открывается в 7:00 по восточному времени, а закрывается в 23:00 по восточному времени, соответственно. (Время необходимо вводить в 24-часовом формате.)</span><span class="sxs-lookup"><span data-stu-id="43686-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="43686-171">Выберите тип рабочего графика, который следует использовать. Для этого выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="43686-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="43686-172">Для применения предварительно заданного графика рабочего времени щелкните **Использовать готовое расписание**, затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="43686-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-173">Чтобы можно было выбрать этот параметр, необходимо предварительно определить хотя бы одно предварительно заданное расписание.</span><span class="sxs-lookup"><span data-stu-id="43686-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="43686-174">Готовые расписания определяются с помощью командлета <STRONG>New-ксргшаурсофбусинесс</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="43686-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="43686-175">Дополнительные сведения можно найти <A href="lync-server-2013-optional-define-response-group-business-hours.md">в разделе (необязательно) определение группы ответа в часах Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-176">При выборе предварительно заданного расписания дни и часы работы группы ответа автоматически водятся в полях <STRONG>День</STRONG>, <STRONG>Открыть</STRONG> и <STRONG>Закрыть</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43686-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="43686-177">Для применения пользовательского графика, относящегося только к данному рабочему процессу, щелкните **Использовать расписание пользователя**.</span><span class="sxs-lookup"><span data-stu-id="43686-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="43686-178">Если вы создаете индивидуальное расписание для данного рабочего процесса, установите флажки, чтобы выбрать дни недели, по которым группа ответа доступна.</span><span class="sxs-lookup"><span data-stu-id="43686-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="43686-179">При создании пользовательского расписания введите в полях **Открыть** и **Закрыть** часы работы группы ответа для каждого дня недели.</span><span class="sxs-lookup"><span data-stu-id="43686-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-p119">Часы вводятся в полях <STRONG>Открыть</STRONG> и <STRONG>Закрыть</STRONG> в 24-часовом формате. Например, если рабочий день продолжается с 9.00 до 17.00 с перерывом на обед в полдень, часы работы указываются следующим образом: <STRONG>Открыть</STRONG> 9:00, <STRONG>Закрыть</STRONG> 12:00, <STRONG>Открыть</STRONG> 13:00, <STRONG>Закрыть</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="43686-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="43686-182">Если требуется воспроизводить сообщение в нерабочее время, установите флажок **Отображать сообщение в нерабочее для группы ответа время**, затем укажите сообщение для воспроизведения, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="43686-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="43686-183">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="43686-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-p120">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="43686-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="43686-p121">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="43686-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-190">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="43686-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="43686-191">Подробные сведения о поддерживаемых форматах звуковых файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="43686-192">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="43686-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="43686-193">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="43686-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="43686-194">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="43686-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="43686-195">Адрес голосовой \<почты — имя пользователя\>@\<domainName\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43686-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="43686-196">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="43686-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="43686-197">Адрес пользователя — \<\>@\<имя пользователя имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="43686-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="43686-198">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="43686-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="43686-199">Формат \<номера телефона — число\>@\<domainName\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43686-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="43686-200">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="43686-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="43686-201">В разделе **Шаг 5. Указание выходных дней** установите флажки для одной или нескольких групп выходных дней, когда группа ответа не будет работать.</span><span class="sxs-lookup"><span data-stu-id="43686-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-202">Перед настройкой рабочего процесса вам нужно определить праздники и наборы праздников.</span><span class="sxs-lookup"><span data-stu-id="43686-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="43686-203">Используйте командлеты <STRONG>New-ксргшолидай</STRONG> и <STRONG>New-ксргшолидайсет</STRONG> для определения праздников и наборов праздников.</span><span class="sxs-lookup"><span data-stu-id="43686-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="43686-204">Дополнительные сведения можно найти <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">в разделе (необязательно) Определение наборов праздников группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="43686-205">Если требуется воспроизводить сообщение в выходные дни, установите флажок **Отображать сообщение в выходные дни**, затем укажите воспроизводимое сообщение, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="43686-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="43686-206">Для ввода сообщения в виде текста, подлежащего преобразованию в речь для вызывающего абонента, щелкните **Использовать текст, преобразованный в речь**, затем введите сообщение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="43686-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-p127">Не включайте в вводимый текст теги HTML. В случае добавления тегов HTML появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="43686-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="43686-p128">Если требуется воспроизводить записанное сообщение из звукового файла, щелкните **Выбрать запись**. Для загрузки нового звукового файла щелкните ссылку **запись**. В новом окне браузера щелкните **Обзор**, выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="43686-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-213">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="43686-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="43686-214">Подробные сведения о поддерживаемых форматах звуковых файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="43686-215">Укажите способ обработки вызовов после воспроизведения сообщения (если оно настроено):</span><span class="sxs-lookup"><span data-stu-id="43686-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="43686-216">Для разрыва связи щелкните **Разъединить звонок**.</span><span class="sxs-lookup"><span data-stu-id="43686-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="43686-217">Для переадресации вызова на голосовую почту щелкните **Переадресовывать на голосовую почту**, затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="43686-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="43686-218">Адрес голосовой \<почты — имя пользователя\>@\<domainName\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43686-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="43686-219">Для переадресации вызова другому пользователю щелкните **Переадресовывать на URI для SIP**, затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="43686-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="43686-220">Адрес пользователя — \<\>@\<имя пользователя имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="43686-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="43686-221">Для переадресации вызова на другой телефонный номер щелкните **Переадресовывать на номер телефона**, затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="43686-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="43686-222">Формат \<номера телефона — число\>@\<domainName\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43686-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="43686-223">Имя домена необходимо для правильного определения адресата, которому перенаправляется вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="43686-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="43686-224">В разделе **Шаг 6. Настройте очередь** (Шаг 6. Настройка очереди) в списке **Выберите очередь, которая будет принимать звонки** выберите очередь для удержания вызывающих абонентов до освобождения оператора.</span><span class="sxs-lookup"><span data-stu-id="43686-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="43686-225">В разделе **Шаг 7. Настройте музыку для режима удержания** выберите музыку, которую должны будут прослушивать вызывающие абоненты в ожидании ответа агента. Для этого выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="43686-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="43686-226">Если в режиме удержания требуется воспроизводить музыкальную запись по умолчанию, щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="43686-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="43686-p133">Если в режиме удержания требуется воспроизводить музыкальную запись из звукового файла, щелкните **Выбрать музыкальный файл**. Для загрузки нового звукового файла щелкните ссылку **музыкальный файл**. В новом окне браузера нажмите кнопку **Обзор** и выберите требуемый файл, затем нажмите кнопку **Открыть**. Для загрузки звукового файла нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="43686-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43686-231">Все звуковые файлы, предоставленные пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="43686-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="43686-232">Подробные сведения о поддерживаемых форматах звуковых файлов можно найти в статьях <A href="lync-server-2013-technical-requirements-for-response-group.md">технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="43686-233">Нажмите кнопку **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="43686-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="43686-234">Создание или изменение рабочего процесса группы слежения с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43686-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="43686-235">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="43686-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="43686-236">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="43686-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="43686-p135">Создайте подсказку для воспроизведения в качестве приветственного сообщения и сохраните ее в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="43686-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="43686-239">Например:</span><span class="sxs-lookup"><span data-stu-id="43686-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-240">Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43686-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="43686-241">Подробности можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-ксргсаудиофиле</A>.</span><span class="sxs-lookup"><span data-stu-id="43686-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="43686-242">Получите идентификатор очереди или вопроса при перенаправлении вызовов.</span><span class="sxs-lookup"><span data-stu-id="43686-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="43686-243">В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="43686-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="43686-244">Подробнее о создании очереди можно узнать в статьях [New-ксргскуеуе](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="43686-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="43686-p138">Определите действие по умолчанию, которое будет выполняться при открытии рабочего процесса в рабочие часы, и сохраните его в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="43686-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-p139">Для рабочих процессов сервисной группы действие по умолчанию должно перенаправлять вызов в очередь. Этот параметр требуется для активных рабочих процессов. Для неактивных рабочих процессов этот параметр указывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="43686-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="43686-250">Например:</span><span class="sxs-lookup"><span data-stu-id="43686-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="43686-251">Если вы хотите определить рабочие часы и праздники, вам нужно создать их перед созданием или изменением рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="43686-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="43686-252">Дополнительные сведения можно найти в разделе [(необязательно) определение группы ответа. часы в Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) и [(необязательно) Определите наборы праздников групп ответов в Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="43686-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="43686-253">Если вы хотите получать запросы на звонки, которые получены в рабочее время или в праздничные дни, используйте командлет **New-ксргспромпт** , чтобы определить запрос, и используйте команду **New-ксргскаллактион** , чтобы определить действие, которое будет выполняться после запроса.</span><span class="sxs-lookup"><span data-stu-id="43686-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="43686-254">Подробные сведения можно найти в разделе [New-ксргспромпт](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) и [New-ксргскаллактион](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="43686-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="43686-255">Получите имя службы для службы группы ответа Lync Server и назначьте ее переменной.</span><span class="sxs-lookup"><span data-stu-id="43686-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="43686-256">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43686-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="43686-257">Создайте или измените рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="43686-257">Create or modify the workflow.</span></span> <span data-ttu-id="43686-258">Для создания рабочего процесса выполните командлет **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="43686-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="43686-259">Для изменения рабочего процесса выполните командлет **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="43686-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="43686-260">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43686-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="43686-261">Например:</span><span class="sxs-lookup"><span data-stu-id="43686-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="43686-262">Всем пользователям, которые назначены менеджерами рабочих процессов, необходимо присвоить роль CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="43686-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43686-263">Дополнительные сведения о дополнительных параметрах можно найти в статьях <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-ксргсворкфлов</A> или <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-ксргсворкфлов</A></span><span class="sxs-lookup"><span data-stu-id="43686-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43686-264">См. также</span><span class="sxs-lookup"><span data-stu-id="43686-264">See Also</span></span>


[<span data-ttu-id="43686-265">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43686-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="43686-266">Необязательно Определение группы ответа в рабочее время в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43686-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="43686-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="43686-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="43686-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="43686-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="43686-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="43686-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="43686-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="43686-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

