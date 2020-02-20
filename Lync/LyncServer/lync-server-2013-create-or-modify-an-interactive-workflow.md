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
ms.openlocfilehash: 7173d739c66982d0995a478e086fee2442fcbd0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="23f9c-102">Создание или изменение интерактивного рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23f9c-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f9c-103">_**Последнее изменение темы:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="23f9c-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="23f9c-104">Для создания или изменения интерактивного рабочего процесса используйте одну из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="23f9c-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23f9c-105">Для создания и изменения интерактивных рабочих процессов можно использовать командную консоль Lync Server или средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="23f9c-106">Для доступа к средству настройки группы ответа из панели управления Lync Server или открытия веб-страницы непосредственно из веб-браузера введите следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="23f9c-107">Использование средства настройки группы ответа для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="23f9c-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="23f9c-108">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="23f9c-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23f9c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23f9c-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23f9c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23f9c-111">В левой панели навигации щелкните **Response Groups** (Группы ответа), а затем **Workflow** (Рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="23f9c-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="23f9c-112">На странице **Workflow** (Рабочий процесс) щелкните **Create or edit a workflow** (Создание или изменение рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="23f9c-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="23f9c-113">В поле **выбора службы** введите полностью или частично имя службы **ApplicationServer**, размещающей рабочий процесс, который требуется создать или изменить.</span><span class="sxs-lookup"><span data-stu-id="23f9c-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="23f9c-114">В полученном списке служб щелкните нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23f9c-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-115">Откроется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="23f9c-116">Средство настройки группы ответа также можно открыть непосредственно из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="23f9c-117">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="23f9c-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-118">На странице **Create a New Workflow** (Создание нового рабочего процесса) напротив **Interactive** (Интерактивный) нажмите кнопку **Create** (Создать).</span><span class="sxs-lookup"><span data-stu-id="23f9c-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="23f9c-119">В разделе **Manage an Existing Workflow** (Управление существующим рабочим процессом) найдите рабочий процесс, который требуется изменить, а затем в меню **Action** (Действие) выберите команду **Edit** (Изменить).</span><span class="sxs-lookup"><span data-stu-id="23f9c-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="23f9c-120">Если вы не готовы обрабатывать пользовательские вызовы рабочего процесса, снимите флажок **Activate the workflow** (Активировать рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="23f9c-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-p105">При создании управляемого рабочего процесса необходимо установить флажок <STRONG>Activate the workflow</STRONG> (Активировать рабочий процесс). После сохранения активного, управляемого рабочего процесса его можно изменять и отключать.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="23f9c-123">Чтобы разрешить федеративным пользователям звонки группе, установите флажок **Enable for federation** (Включить федерацию).</span><span class="sxs-lookup"><span data-stu-id="23f9c-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="23f9c-124">Кроме того, необходимо иметь политику внешнего доступа, которая применяется к приложению группы ответа, настроенному для Федерации.</span><span class="sxs-lookup"><span data-stu-id="23f9c-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-125">Глобальная политика внешнего доступа применяется к приложению группы ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="23f9c-126">Глобальную политику для Федерации группы ответа можно настроить с помощью панели управления Lync Server или с помощью командлета <STRONG>Set – CsExternalAccessPolicy</STRONG> , чтобы установить для параметра Енаблеаутсидеакцесс значение true.</span><span class="sxs-lookup"><span data-stu-id="23f9c-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="23f9c-127">Обратите внимание, что параметры глобальной политики применяются ко всем пользователям, если им не назначена политика на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="23f9c-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="23f9c-128">Поэтому перед изменением этого параметра для групп ответа убедитесь, что параметры федерации соответствуют требованиям организации.</span><span class="sxs-lookup"><span data-stu-id="23f9c-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="23f9c-129">Сведения о том, как политики применяются к пользователям, приведены <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в статье Manage External Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="23f9c-130">Сведения о параметрах Федерации приведены в статье <STRONG>Set – CsExternalAccessPolicy</STRONG> in the Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="23f9c-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-131">Пользователи, размещенные в Lync Online, не могут помещать вызовы в группы ответа, размещенные в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="23f9c-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="23f9c-132">Это справедливо и в гибридных развертываниях, и в случаях, когда локальное развертывание участвует в развертывании Lync Online.</span><span class="sxs-lookup"><span data-stu-id="23f9c-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="23f9c-133">Чтобы скрывать удостоверения агентов в ходе звонка, установите флажок **Enable agent anonymity** (Включить анонимность агента).</span><span class="sxs-lookup"><span data-stu-id="23f9c-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-134">Для выполнения анонимных звонков нельзя использовать мгновенные сообщения или видеоконференции, однако агент или звонящий может добавить функцию обмена мгновенными сообщениями и видео после установления звонка.</span><span class="sxs-lookup"><span data-stu-id="23f9c-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="23f9c-135">Анонимный агент также может помещать звонки на удержание, переводить звонки (с консультацией и без нее), а также парковать и извлекать звонки.</span><span class="sxs-lookup"><span data-stu-id="23f9c-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="23f9c-136">Анонимные звонки не поддерживают конференции, общий доступ к приложениям, совместный доступ к рабочему столу, передачу файлов, доступ к доске и совместную работу с данными, а также запись звонков.</span><span class="sxs-lookup"><span data-stu-id="23f9c-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="23f9c-137">Агенты, использующие подключаемый модуль VDI для Lync, могут принимать входящие вызовы анонимно, но они не могут выполнять анонимные вызовы.</span><span class="sxs-lookup"><span data-stu-id="23f9c-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="23f9c-138">В поле **Enter the address of the group that will receive the calls** (Введите адрес группы, которая будет принимать звонки) введите основной URI SIP группы, которая принимать звонки для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="23f9c-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="23f9c-139">В поле **Display name** (Отображаемое имя) введите отображаемое имя для рабочего процесса (например, группа ответа интерактивного автоответчика отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="23f9c-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-140">Не включайте в отображаемое&lt;имя символы "&gt;" или "".</span><span class="sxs-lookup"><span data-stu-id="23f9c-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="23f9c-141">Не используйте имена "RGS Presence Watcher" или "Announcement Service", поскольку они зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="23f9c-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="23f9c-142">В поле **Telephone number** (Номер телефона) введите URI для группы ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="23f9c-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="23f9c-143">В поле **Display number** (Отображаемый номер) введите отображаемый номер для группы ответа (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="23f9c-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="23f9c-144">Необязательно В поле **Описание**введите описание рабочего процесса, которое будет отображаться в карточке контакта в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="23f9c-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="23f9c-145">В поле **Workflow Type** (Тип рабочего процесса) выберите **Managed** (Управляемый), если этот рабочий процесс будет управляться менеджером группы ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="23f9c-146">Чтобы назначить диспетчеров группы ответа для рабочего процесса, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="23f9c-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="23f9c-147">Введите URI SIP менеджера для этого рабочего процесса и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="23f9c-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="23f9c-148">Введите URI SIP дополнительных менеджеров для добавления к этому рабочему процессу и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="23f9c-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23f9c-p112">Каждому пользователю, назначенному менеджером группы ответа, должна быть назначена роль CsResponseGroupManager. Если пользователям не назначить эту роль, то они не смогут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="23f9c-151">В разделе **Step 2 Select a Language** (Шаг 2. Выбор языка) выберите язык, используемый для распознавания речи и преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="23f9c-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="23f9c-152">Если требуется настроить приветственное сообщение, то в разделе **Step 3 Configure a Welcome Message** (Шаг  3. Настройка приветственного сообщения) установите флажок **Play a welcome message** (Воспроизводить приветственное сообщение) и затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="23f9c-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-153">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите флажок **Use text-to-speech** (Использовать преобразование текста в речь), а затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="23f9c-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-154">Вводимый текст не должен содержать HTML-теги.</span><span class="sxs-lookup"><span data-stu-id="23f9c-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="23f9c-155">При добавлении HTML-тегов вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="23f9c-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="23f9c-p114">Чтобы использовать звуковой WAV- или WMA-файл, установите флажок **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне браузера нажмите кнопку **Browse** (Обзор), выберите нужный звуковой файл и нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-160">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="23f9c-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="23f9c-161">Подробные сведения о поддерживаемых форматах файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="23f9c-162">В разделе **Step 4 Specify Your Business Hours** (Шаг 4. Указание режима работы) выберите часовой пояс в списке **Your time zone** (Часовой пояс).</span><span class="sxs-lookup"><span data-stu-id="23f9c-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-p116">С помощью этого параметра задается часовой пояс, в котором расположены звонящие и агенты рабочего процесса. Он используется для определения времени открытия и закрытия. Например, если рабочий процесс настроен для использования североамериканского восточного часового пояса и задано время открытия и закрытия 7:00 A.M. и 11:00 P.M. соответственно, то по восточноевропейскому времени временем открытия и закрытия будет 7:00 и 11:00:00 соответственно. (Для ввода времени необходимо использовать 24-часовой формат.)</span><span class="sxs-lookup"><span data-stu-id="23f9c-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="23f9c-168">Выберите тип расписания, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="23f9c-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-169">Чтобы использовать предварительно заданное расписание, установите переключатель **Use a preset schedule** (Использовать предварительно заданное расписание) и затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="23f9c-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-170">Для выбора этого параметра необходимо создать как минимум одно предварительно заданное расписание.</span><span class="sxs-lookup"><span data-stu-id="23f9c-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="23f9c-171">Для настройки предварительно заданных расписаний используется командлет <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="23f9c-172">Дополнительные сведения см. <A href="lync-server-2013-optional-define-response-group-business-hours.md">в разделе (необязательно) определение рабочих часов для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="23f9c-173">При выборе предварительно заданного расписания поля <STRONG>Day</STRONG> (День недели), <STRONG>Open</STRONG> (Время открытия) и <STRONG>Close</STRONG> (Время закрытия) будут заполнены автоматически.</span><span class="sxs-lookup"><span data-stu-id="23f9c-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="23f9c-174">Чтобы использовать настраиваемое расписание, которое применяется только к этому рабочему процессу, установите переключатель **Use a custom schedule** (Использовать настраиваемое расписание).</span><span class="sxs-lookup"><span data-stu-id="23f9c-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="23f9c-175">Если вы создаете настраиваемое расписание для этого рабочего процесса, установите флажки для дней недели, по которым группа ответа будет доступна.</span><span class="sxs-lookup"><span data-stu-id="23f9c-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="23f9c-176">Если вы создаете настраиваемое расписание, задайте часы работы группы ответа с помощью полей **Open** (Время открытия) и **Close** (Время закрытия).</span><span class="sxs-lookup"><span data-stu-id="23f9c-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-p118">При вводе значений в поля <STRONG>Open</STRONG> (Время открытия) и <STRONG>Close</STRONG> (Время закрытия) используйте 24-часовой формат. Например, если организация работает с 09:00 до 17:00 с перерывом на обед, то в поле <STRONG>Open</STRONG> (Время открытия) укажите 09:00, в поле <STRONG>Close</STRONG> (Время закрытия) укажите 12:00, в поле <STRONG>Open</STRONG> (Время открытия) укажите 13:00 и в поле <STRONG>Close</STRONG> (Время закрытия) укажите 17:00.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="23f9c-179">Если требуется воспроизводить сообщение в нерабочие дни, установите флажок **Play a message when the response group is outside of business hours** (Воспроизводить сообщение, если группа ответа не работает в это время) и затем укажите сообщение, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="23f9c-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-180">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите переключатель **Use text-to-speech** (Использовать преобразование текста в речь) и затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="23f9c-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-p119">Не включайте в этот текст HTML-теги. Если включить HTML-теги, то будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="23f9c-p120">Чтобы использовать звуковой файл, установите переключатель **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-187">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="23f9c-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="23f9c-188">Подробные сведения о поддерживаемых форматах файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="23f9c-189">Укажите способ обработки звонков после воспроизведения приветственного сообщения (если оно задано):</span><span class="sxs-lookup"><span data-stu-id="23f9c-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="23f9c-190">Чтобы разъединять звонки, установите переключатель **Disconnect Call** (Разъединить звонок).</span><span class="sxs-lookup"><span data-stu-id="23f9c-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="23f9c-191">Чтобы переадресовывать звонки на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="23f9c-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="23f9c-192">В качестве адреса голосовой \<почты используется формат username\>@\<имя_домена\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="23f9c-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="23f9c-193">Чтобы переадресовывать звонки другому пользователю, установите переключатель **Forward to SIP URI** (Переадресация на SIP URI) и затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="23f9c-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="23f9c-194">В качестве адреса \<пользователя используется формат username\>@\<имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="23f9c-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="23f9c-195">Чтобы переадресовывать звонки на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="23f9c-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="23f9c-196">В качестве номера \<телефона используется формат номер\>@\<имя_домена\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="23f9c-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="23f9c-197">Имя домена используется для направления пользователя по нужному адресу.</span><span class="sxs-lookup"><span data-stu-id="23f9c-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="23f9c-198">В разделе **Step 5 Specify Your Holidays** (Шаг 5. Указание выходных дней) установите флажки для одного набора выходных дней или нескольких наборов.</span><span class="sxs-lookup"><span data-stu-id="23f9c-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-199">Перед настройкой рабочего процесса необходимо задать выходные дни и наборы выходных дней.</span><span class="sxs-lookup"><span data-stu-id="23f9c-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="23f9c-200">Чтобы задать выходные дни и наборы выходных дней, используйте командлеты <STRONG>New-CsRgsHoliday</STRONG> и <STRONG>New-CsRgsHolidaySet</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="23f9c-201">Дополнительные сведения см. <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">в разделе (необязательно) Определение наборов праздников группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="23f9c-202">Если требуется воспроизводить приветственное сообщение по выходным дням, установите флажок **Play a message during holidays** (Воспроизводить сообщение в выходные дни) и затем укажите сообщение, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="23f9c-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-203">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите переключатель **Use text-to-speech** (Использовать преобразование текста в речь) и затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="23f9c-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-p126">Не включайте в этот текст HTML-теги. Если включить HTML-теги, то будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="23f9c-p127">Чтобы использовать звуковой файл, установите переключатель **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-210">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="23f9c-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="23f9c-211">Подробные сведения о поддерживаемых форматах аудио файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="23f9c-212">Укажите способ обработки звонков после воспроизведения приветственного сообщения (если оно задано):</span><span class="sxs-lookup"><span data-stu-id="23f9c-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="23f9c-213">Чтобы разъединять звонки, установите переключатель **Disconnect Call** (Разъединить звонок).</span><span class="sxs-lookup"><span data-stu-id="23f9c-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="23f9c-214">Чтобы переадресовывать звонки на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="23f9c-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="23f9c-215">В качестве адреса голосовой \<почты используется формат username\>@\<имя_домена\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="23f9c-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="23f9c-216">Чтобы переадресовывать звонки другому пользователю, установите переключатель **Forward to SIP URI** (Переадресация на SIP URI) и затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="23f9c-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="23f9c-217">В качестве адреса \<пользователя используется формат username\>@\<имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="23f9c-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="23f9c-218">Чтобы переадресовывать звонки на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="23f9c-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="23f9c-219">В качестве номера \<телефона используется формат номер\>@\<имя_домена\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="23f9c-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="23f9c-220">Имя домена используется для перенаправления вызывающего в правильное конечное расположение.</span><span class="sxs-lookup"><span data-stu-id="23f9c-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="23f9c-221">В разделе **Step 6 Configure Music on Hold** (Шаг 6. Настройка музыки при удержании звонка) выберите музыку, воспроизводимую для вызывающих при ожидании агента, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="23f9c-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="23f9c-222">Чтобы использовать музыку по умолчанию, установите переключатель **Use default** (Использовать по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23f9c-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="23f9c-p132">Чтобы использовать звуковой файл, установите переключатель **Select a music file** (Выбор файла музыки). Чтобы загрузить новый звуковой файл, щелкните ссылку **a music file** (файл музыки). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-227">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="23f9c-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="23f9c-228">Подробные сведения о поддерживаемых форматах файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="23f9c-229">В разделе **Step 7 Configure Interactive Voice Response** (Шаг 7. Настройка интерактивного автоответчика) под заголовком **The user will hear the following text or recorded message** (Пользователь услышит следующий текст или записанное сообщение) укажите вопрос, который будет задан звонящему:</span><span class="sxs-lookup"><span data-stu-id="23f9c-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="23f9c-230">Чтобы ввести вопрос в текстовом формате, установите переключатель **Use text-to-speech** (Использовать преобразование текста в речь) и затем введите вопрос в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="23f9c-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-p134">Вводимый текст не должен содержать HTML-теги. При добавлении HTML-тегов вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-233">Символ "#" интерпретируется модулем преобразования текста в речь как слово "номер".</span><span class="sxs-lookup"><span data-stu-id="23f9c-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="23f9c-234">Если требуется указать клавишу #, то вместо символа используйте имя клавиши.</span><span class="sxs-lookup"><span data-stu-id="23f9c-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="23f9c-235">Пример: Для связи с сотрудником отдела продаж нажмите кнопку с решеткой.</span><span class="sxs-lookup"><span data-stu-id="23f9c-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="23f9c-p136">Чтобы использовать предварительно записанный звуковой файл, содержащий вопрос, щелкните **Select a recording** (Выбор записи) и затем щелкните ссылку **a recording** (запись), чтобы загрузить файл. В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Щелкните **Upload** (Загрузить), чтобы загрузить файл, и затем введите вопрос в текстовом поле (это позволяет перенаправлять отвечающему агенту вопрос и ответ звонящего).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23f9c-239">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="23f9c-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="23f9c-240">Подробные сведения о поддерживаемых форматах файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23f9c-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="23f9c-241">В разделе **Response 1** (1 ответ) укажите первый возможный ответ на вопрос, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="23f9c-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23f9c-p138">При указании голосовых ответов не используйте двойные кавычки ("). Это может привести к сбою интерактивного автоответчика.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-244">Для ответа звонящий может использовать речь или буквенно-цифровые клавиши либо и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="23f9c-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="23f9c-245">Чтобы выбрать речевой ответ, введите ответ в поле **Enter a voice response** (Введите голосовой ответ).</span><span class="sxs-lookup"><span data-stu-id="23f9c-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="23f9c-246">Чтобы выбрать ответ с помощью клавиш, введите требуемую цифру в поле **Digit** (Цифра).</span><span class="sxs-lookup"><span data-stu-id="23f9c-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="23f9c-247">Укажите, требуется ли перенаправлять звонящего в очередь или задать ему другой вопрос, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="23f9c-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="23f9c-248">Чтобы перенаправить звонящего в очередь, щелкните **Send to a queue** (Отправить в очередь) и затем в списке **Select a queue** (Выбор очереди) выберите требуемую очередь.</span><span class="sxs-lookup"><span data-stu-id="23f9c-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="23f9c-p139">Чтобы задать другой вопрос, щелкните **Ask another question** (Задать другой вопрос), затем щелкните **Use text-to-speech** (Использовать преобразование текста в речь) и введите вопрос либо щелкните **Select a recording** (Выбор записи). С помощью группировки ответов в этом разделе укажите до 4 возможных ответов на дополнительные вопросы и задайте очередность ответов. Чтобы указать 3 или 4 возможные ответы, установите флажки **Response 3** (3 ответ) или **Response 4** (4 ответ).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="23f9c-p140">Укажите до трех других возможных ответов на исходный вопрос, повторив шаги 28 и 29, чтобы указать возможные ответы и действия, которые необходимо предпринять для каждого ответа. Чтобы указать 3 или 4 возможные ответы, установите флажки **Response 3** (3 ответ) или **Response 4** (4 ответ).</span><span class="sxs-lookup"><span data-stu-id="23f9c-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="23f9c-254">Щелкните **Deploy** (Развернуть).</span><span class="sxs-lookup"><span data-stu-id="23f9c-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="23f9c-255">Использование Windows PowerShell для создания или изменения интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="23f9c-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="23f9c-256">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="23f9c-257">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23f9c-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23f9c-p141">Извлеките имя службы для службы группы ответа и назначьте его переменной. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="23f9c-p142">Интерактивному рабочему процессу требуется как минимум 2 очереди и как минимум 2 группы агентов. Сначала создайте группы агентов. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="23f9c-p143">Создайте очереди. Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="23f9c-p144">Создайте приглашение для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="23f9c-p145">Теперь создайте действие, которое должно выполняться после приглашения, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="23f9c-p146">Создайте ответ для первой группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="23f9c-p147">Теперь создайте второе приглашение, действие вызова и ответ. Сначала создайте приглашение с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="23f9c-p148">Создайте второе действие вызова с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="23f9c-p149">Создайте ответ для второй группы ответа с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="23f9c-p150">Создайте приглашение верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="23f9c-p151">Создайте вопрос верхнего уровня с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="23f9c-p152">Теперь создайте рабочий процесс с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="23f9c-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23f9c-p153">Всем пользователям, назначенным менеджерами группы ответа, должна быть назначена роль CsResponseGroupManager. Если пользователям не назначить эту роль, то они не смогут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="23f9c-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

