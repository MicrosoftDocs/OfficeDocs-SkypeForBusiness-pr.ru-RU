---
title: 'Lync Server 2013: создание или изменение рабочего процесса сервисной группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03563506a739ca9eb0fcf1992899ba14167627d1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="ece34-102">Создание или изменение рабочего процесса сервисной группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece34-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ece34-103">_**Последнее изменение темы:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="ece34-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="ece34-104">Используйте одну из следующих процедур для создания или изменения рабочего процесса сервисной группы.</span><span class="sxs-lookup"><span data-stu-id="ece34-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ece34-105">Для создания и изменения рабочих процессов группы слежения можно использовать командную консоль Lync Server или средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="ece34-106">Для доступа к средству настройки группы ответа из панели управления Lync Server или открытия веб-страницы непосредственно из веб-браузера введите следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ece34-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="ece34-107">Использование средства настройки группы ответа для создания или изменения рабочего процесса сервисной группы</span><span class="sxs-lookup"><span data-stu-id="ece34-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="ece34-108">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ece34-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ece34-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ece34-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ece34-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ece34-111">В левой панели навигации щелкните **Response Groups** (Группы ответа), а затем **Workflow** (Рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="ece34-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="ece34-112">На странице **Workflow** (Рабочий процесс) щелкните **Create or edit a workflow** (Создание или изменение рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="ece34-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="ece34-113">В поле поиска **Выберите службу** введите имя службы **ApplicationServer** (полностью или частично), в которой размещается создаваемый или изменяемый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="ece34-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="ece34-114">В полученном списке служб щелкните нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ece34-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-115">Откроется средство настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="ece34-116">Средство настройки группы ответа также можно открыть непосредственно из веб-браузера, введя следующий URL-адрес: <STRONG>https://</STRONG>&lt;вебпулфкдн&gt;<STRONG>/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ece34-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="ece34-117">Выполните одно их следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="ece34-118">На странице **Create a New Workflow** (Создание нового рабочего процесса) напротив Hunt Group (Сервисная группа) нажмите кнопку **Create** (Создать).</span><span class="sxs-lookup"><span data-stu-id="ece34-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="ece34-119">В области **Управление существующим рабочим процессом** найдите рабочий процесс, который нужно изменить, а затем в разделе **Действие** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ece34-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="ece34-120">Если все готово к тому, чтобы разрешить пользователям использовать этот рабочий процесс, установите флажок **Activate the workflow** (Активировать рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="ece34-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-p105">Если вы создаете управляемый рабочий процесс, необходимо выбрать функцию <STRONG>Активировать рабочий процесс</STRONG>. После сохранения активного управляемого рабочего процесс его можно изменить или отключить.</span><span class="sxs-lookup"><span data-stu-id="ece34-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="ece34-123">Чтобы разрешить федеративным пользователям звонки группе, установите флажок **Enable for federation** (Включить федерацию).</span><span class="sxs-lookup"><span data-stu-id="ece34-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="ece34-124">Кроме того, необходимо иметь политику внешнего доступа, которая применяется к приложению группы ответа, настроенному для Федерации.</span><span class="sxs-lookup"><span data-stu-id="ece34-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-125">Глобальная политика внешнего доступа применяется к приложению группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="ece34-126">Глобальную политику для Федерации группы ответа можно настроить с помощью панели управления Lync Server или с помощью командлета <STRONG>Set – CsExternalAccessPolicy</STRONG> , чтобы установить для параметра Енаблеаутсидеакцесс значение true.</span><span class="sxs-lookup"><span data-stu-id="ece34-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="ece34-127">Обратите внимание, что параметры глобальной политики применяются ко всем пользователям, если им не назначена политика на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="ece34-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="ece34-128">Поэтому перед изменением этого параметра для групп ответа убедитесь, что параметры федерации соответствуют требованиям организации.</span><span class="sxs-lookup"><span data-stu-id="ece34-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="ece34-129">Сведения о том, как политики применяются к пользователям, приведены <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в статье Manage External Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="ece34-130">Подробнее о параметре Федерации можно узнать в статье <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set – CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-131">Пользователи, размещенные в Lync Online, не могут помещать вызовы в группы ответа, размещенные в локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="ece34-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="ece34-132">Это справедливо и в гибридных развертываниях, и в случаях, когда локальное развертывание участвует в развертывании Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ece34-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="ece34-133">Чтобы скрывать удостоверения агентов в ходе звонка, установите флажок **Enable agent anonymity** (Включить анонимность агента).</span><span class="sxs-lookup"><span data-stu-id="ece34-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-134">Для выполнения анонимных звонков нельзя использовать мгновенные сообщения или видеоконференции, однако агент или звонящий может добавить функцию обмена мгновенными сообщениями и видео после установления звонка.</span><span class="sxs-lookup"><span data-stu-id="ece34-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="ece34-135">Анонимный агент также может помещать звонки на удержание, переводить звонки (с консультацией и без нее), а также парковать и извлекать звонки.</span><span class="sxs-lookup"><span data-stu-id="ece34-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="ece34-136">Анонимные звонки не поддерживают конференции, общий доступ к приложениям, совместный доступ к рабочему столу, передачу файлов, доступ к доске и совместную работу с данными, а также запись звонков.</span><span class="sxs-lookup"><span data-stu-id="ece34-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="ece34-137">Агенты, использующие подключаемый модуль VDI для Lync, могут принимать входящие вызовы анонимно, но они не могут выполнять анонимные вызовы.</span><span class="sxs-lookup"><span data-stu-id="ece34-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="ece34-138">В поле **Enter the address of the group that will receive the calls** (Введите адрес группы, которая будет получать вызовы) введите основной адрес универсального кода ресурса (URI) SIP группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ece34-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-139">Основной URI рабочего процесса определяет порядок идентификации рабочего процесса и ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="ece34-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="ece34-140">Введенный универсальный код ресурса (URI) SIP создается как объект Contact в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece34-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="ece34-141">Для создания URI объект должен быть уникальным в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ece34-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="ece34-142">В поле **Display name** (Отображаемое имя) введите отображаемое имя для рабочего процесса (например, группа ответа отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="ece34-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-143">Не включайте в отображаемое&lt;имя символы "&gt;" или "".</span><span class="sxs-lookup"><span data-stu-id="ece34-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="ece34-144">Не используйте следующие отображаемые имена, поскольку они зарезервированы: <STRONG>RGS Presence Watcher</STRONG> (Наблюдатель присутствия RGS) или <STRONG>Announcement Service</STRONG> (Служба оповещения).</span><span class="sxs-lookup"><span data-stu-id="ece34-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="ece34-145">В области **Номер телефона** введите URI линии для группы ответа (например, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="ece34-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="ece34-146">В поле **Display number** (Отображаемый номер) введите отображаемый номер для группы ответа (например, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="ece34-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="ece34-147">Необязательно В поле **Описание**введите описание рабочего процесса, которое будет отображаться в карточке контакта в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="ece34-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="ece34-148">В поле **Workflow Type** (Тип рабочего процесса) выберите **Managed** (Управляемый), если этот рабочий процесс будет управляться менеджером группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="ece34-149">Чтобы назначить диспетчеров группы ответа для рабочего процесса, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ece34-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="ece34-150">Введите URI SIP менеджера данного рабочего процесса и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece34-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="ece34-151">Введите URI SIP дополнительных менеджеров, чтобы добавить их в рабочий процесс, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ece34-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ece34-p113">Каждому пользователю, который назначен менеджером группы ответа, необходимо присвоить роль CsResponseGroupManager. Если пользователям не назначена эта роль, они не могут управлять группами ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="ece34-154">В области **Шаг 2 — выбор языка** щелкните язык, который необходимо использовать для распознавания речи и преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="ece34-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="ece34-155">Если требуется настроить приветственное сообщение, то в разделе **Step 3 Configure a Welcome Message** (Шаг  3. Настройка приветственного сообщения) установите флажок **Play a welcome message** (Воспроизводить приветственное сообщение) и затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ece34-156">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите флажок **Use text-to-speech** (Использовать преобразование текста в речь), а затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="ece34-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-p114">Вводимый текст не должен содержать HTML-теги. При добавлении HTML-тегов вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ece34-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ece34-p115">Чтобы использовать звуковой WAV- или WMA-файл, установите переключатель **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="ece34-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-163">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="ece34-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ece34-164">Подробные сведения о поддерживаемых форматах файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="ece34-165">В разделе **Step 4 Specify Your Business Hours** (Шаг 4. Указание режима работы) выберите часовой пояс в списке **Your time zone** (Часовой пояс).</span><span class="sxs-lookup"><span data-stu-id="ece34-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-p117">С помощью этого параметра задается часовой пояс, в котором расположены звонящие и агенты рабочего процесса. Он используется для определения времени открытия и закрытия. Например, если рабочий процесс настроен для использования североамериканского восточного часового пояса и задано время открытия и закрытия 7:00 A.M. и 11:00 P.M. соответственно, то по восточноевропейскому времени временем открытия и закрытия будет 7:00 и 23:00 соответственно. (Для ввода времени необходимо использовать 24-часовой формат.)</span><span class="sxs-lookup"><span data-stu-id="ece34-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="ece34-171">Выберите тип расписания, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="ece34-172">Чтобы использовать предварительно заданное расписание, установите переключатель **Use a preset schedule** (Использовать предварительно заданное расписание) и затем выберите требуемое расписание в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="ece34-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-173">Для выбора этого параметра необходимо создать как минимум одно предварительно заданное расписание.</span><span class="sxs-lookup"><span data-stu-id="ece34-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="ece34-174">Для настройки предварительно заданных расписаний используется командлет <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ece34-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="ece34-175">Дополнительные сведения см. <A href="lync-server-2013-optional-define-response-group-business-hours.md">в разделе (необязательно) определение рабочих часов для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-176">При выборе предварительно заданного расписания поля <STRONG>Day</STRONG> (День недели), <STRONG>Open</STRONG> (Время открытия) и <STRONG>Close</STRONG> (Время закрытия) будут заполнены автоматически.</span><span class="sxs-lookup"><span data-stu-id="ece34-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="ece34-177">Чтобы использовать настраиваемое расписание, которое применяется только к этому рабочему процессу, установите переключатель **Use a custom schedule** (Использовать настраиваемое расписание).</span><span class="sxs-lookup"><span data-stu-id="ece34-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="ece34-178">Если вы создаете настраиваемое расписание для этого рабочего процесса, установите флажки для дней недели, по которым группа ответа будет доступна.</span><span class="sxs-lookup"><span data-stu-id="ece34-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="ece34-179">Кроме того, введите время открытия и закрытия в поля **Open** (Время открытия) и **Close** (Время закрытия) для каждого дня недели.</span><span class="sxs-lookup"><span data-stu-id="ece34-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-p119">При вводе значений в поля <STRONG>Open</STRONG> (Время открытия) и <STRONG>Close</STRONG> (Время закрытия) используйте 24-часовой формат. Например, если организация работает с 09:00 до 17:00 с перерывом на обед, то в поле <STRONG>Open</STRONG> (Время открытия) укажите 09:00, в поле <STRONG>Close</STRONG> (Время закрытия) укажите 12:00, в поле <STRONG>Open</STRONG> (Время открытия) укажите 13:00 и в поле <STRONG>Close</STRONG> (Время закрытия) укажите 17:00.</span><span class="sxs-lookup"><span data-stu-id="ece34-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="ece34-182">Если требуется воспроизводить сообщение в нерабочие дни, установите флажок **Play a message when the response group is outside of business hours** (Воспроизводить сообщение, если группа ответа не работает в это время) и затем укажите сообщение, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="ece34-183">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите переключатель **Use text-to-speech** (Использовать преобразование текста в речь) и затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="ece34-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-p120">Не включайте в этот текст HTML-теги. Если включить HTML-теги, то будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ece34-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ece34-p121">Чтобы использовать звуковой файл, установите переключатель **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="ece34-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-190">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="ece34-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ece34-191">Подробные сведения о поддерживаемых форматах аудио файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="ece34-192">Укажите способ обработки звонков после воспроизведения приветственного сообщения (если оно задано):</span><span class="sxs-lookup"><span data-stu-id="ece34-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="ece34-193">Чтобы разъединять звонки, установите переключатель **Disconnect Call** (Разъединить звонок).</span><span class="sxs-lookup"><span data-stu-id="ece34-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="ece34-194">Чтобы переадресовывать звонки на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ece34-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="ece34-195">В качестве адреса голосовой \<почты используется формат username\>@\<имя_домена\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ece34-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ece34-196">Чтобы переадресовывать звонки другому пользователю, установите переключатель **Forward to SIP URI** (Переадресация на SIP URI) и затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="ece34-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="ece34-197">В качестве адреса \<пользователя используется формат username\>@\<имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="ece34-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="ece34-198">Чтобы переадресовывать звонки на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="ece34-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="ece34-199">В качестве номера \<телефона используется формат номер\>@\<имя_домена\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ece34-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="ece34-200">Имя домена используется для перенаправления вызывающего в правильное конечное расположение.</span><span class="sxs-lookup"><span data-stu-id="ece34-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="ece34-201">В разделе **Step 5 Specify Your Holidays** (Шаг 5. Указание выходных дней) установите флажки для одного набора выходных дней или нескольких наборов.</span><span class="sxs-lookup"><span data-stu-id="ece34-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-202">Перед настройкой рабочего процесса необходимо задать выходные дни и наборы выходных дней.</span><span class="sxs-lookup"><span data-stu-id="ece34-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="ece34-203">Чтобы задать выходные дни и наборы выходных дней, используйте командлеты <STRONG>New-CsRgsHoliday</STRONG> и <STRONG>New-CsRgsHolidaySet</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ece34-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="ece34-204">Дополнительные сведения см. <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">в разделе (необязательно) Определение наборов праздников группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="ece34-205">Если требуется воспроизводить приветственное сообщение по выходным дням, установите флажок **Play a message during holidays** (Воспроизводить сообщение в выходные дни) и затем укажите сообщение, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="ece34-206">Чтобы ввести приветственное сообщение в виде текста, который будет преобразовываться для звонящих в речь, установите переключатель **Use text-to-speech** (Использовать преобразование текста в речь) и затем введите в поле текст приветственного сообщения.</span><span class="sxs-lookup"><span data-stu-id="ece34-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-p127">Не включайте в этот текст HTML-теги. Если включить HTML-теги, то будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ece34-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ece34-p128">Чтобы использовать звуковой файл, установите переключатель **Select a recording** (Выбор записи). Чтобы загрузить новый звуковой файл, щелкните ссылку **a recording** (запись). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="ece34-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-213">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="ece34-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ece34-214">Подробные сведения о поддерживаемых форматах аудио файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="ece34-215">Укажите способ обработки звонков после воспроизведения приветственного сообщения (если оно задано):</span><span class="sxs-lookup"><span data-stu-id="ece34-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="ece34-216">Чтобы разъединять звонки, установите переключатель **Disconnect Call** (Разъединить звонок).</span><span class="sxs-lookup"><span data-stu-id="ece34-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="ece34-217">Чтобы переадресовывать звонки на голосовую почту, установите переключатель **Forward to voice mail** (Переадресация на голосовую почту) и затем введите адрес голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ece34-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="ece34-218">В качестве адреса голосовой \<почты используется формат username\>@\<имя_домена\> (например, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ece34-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ece34-219">Чтобы переадресовывать звонки другому пользователю, установите переключатель **Forward to SIP URI** (Переадресация на SIP URI) и затем введите адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="ece34-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="ece34-220">В качестве адреса \<пользователя используется формат username\>@\<имя_домена.\></span><span class="sxs-lookup"><span data-stu-id="ece34-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="ece34-221">Чтобы переадресовывать звонки на другой номер телефона, установите переключатель **Forward to telephone number** (Переадресация на номер телефона) и затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="ece34-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="ece34-222">В качестве номера \<телефона используется формат номер\>@\<имя_домена\> (например, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ece34-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="ece34-223">Имя домена используется для перенаправления вызывающего в правильное конечное расположение.</span><span class="sxs-lookup"><span data-stu-id="ece34-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="ece34-224">В разделе **Step 6 Configure a Queue** (Шаг 6. Настройка очереди) выберите очередь, используемую для удержания вызывающих, которые ожидают агента в списке **Select the queue that will receive the calls** (Выбор очереди, используемой для приема звонков).</span><span class="sxs-lookup"><span data-stu-id="ece34-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="ece34-225">В разделе **Step 7 Configure Music on Hold** (Шаг 7. Настройка музыки при удержании звонка) выберите музыку, воспроизводимую для вызывающих при ожидании агента, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ece34-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="ece34-226">Чтобы использовать музыку по умолчанию, установите переключатель **Use default** (Использовать по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ece34-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="ece34-p133">Чтобы использовать звуковой файл, установите переключатель **Select a music file** (Выбор файла музыки). Чтобы загрузить новый звуковой файл, щелкните ссылку **a music file** (файл музыки). В открывшемся окне нажмите кнопку **Browse** (Обзор), выберите требуемый звуковой файл и затем нажмите кнопку **Open** (Открыть). Чтобы загрузить звуковой файл, щелкните **Upload** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="ece34-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ece34-231">Все звуковые файлы, предоставляемые пользователями, должны удовлетворять определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="ece34-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ece34-232">Подробные сведения о поддерживаемых форматах аудио файлов приведены <A href="lync-server-2013-technical-requirements-for-response-group.md">в статье технические требования для группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="ece34-233">Щелкните **Deploy** (Развернуть).</span><span class="sxs-lookup"><span data-stu-id="ece34-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="ece34-234">Использование Windows PowerShell для создания или изменения рабочего процесса сервисной группы</span><span class="sxs-lookup"><span data-stu-id="ece34-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="ece34-235">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ece34-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ece34-236">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ece34-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ece34-p135">Создайте подсказку для воспроизведения в качестве приветственного сообщения и сохраните ее в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ece34-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="ece34-239">Например:</span><span class="sxs-lookup"><span data-stu-id="ece34-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-240">Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ece34-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="ece34-241">Дополнительные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import – CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="ece34-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="ece34-242">Получите идентификатор очереди или вопроса при перенаправлении вызовов.</span><span class="sxs-lookup"><span data-stu-id="ece34-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="ece34-243">В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ece34-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="ece34-244">Подробнее о создании очереди можно узнать в статье [New/CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="ece34-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="ece34-p138">Определите действие по умолчанию, которое будет выполняться при открытии рабочего процесса в рабочие часы, и сохраните его в качестве переменной. В командной строке выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ece34-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-p139">Для рабочих процессов сервисной группы действие по умолчанию должно перенаправлять вызов в очередь. Этот параметр требуется для активных рабочих процессов. Для неактивных рабочих процессов этот параметр указывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="ece34-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="ece34-250">Пример:</span><span class="sxs-lookup"><span data-stu-id="ece34-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="ece34-251">Если вы хотите определить рабочие часы и праздники, их необходимо создать перед созданием или изменением рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ece34-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="ece34-252">Дополнительные сведения см. [в разделе (необязательно) определение рабочих часов для группы ответа в Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) и [(необязательно) Определите наборы праздников группы ответа в Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ece34-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="ece34-253">Если вы хотите получать приглашения на звонки, которые получены из рабочих часов или праздников, используйте командлет **New-CsRgsPrompt** , чтобы определить приглашение, и используйте командлет **New-CsRgsCallAction** , чтобы определить действие, которое должно выполняться после приглашения.</span><span class="sxs-lookup"><span data-stu-id="ece34-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="ece34-254">Дополнительные сведения см. в статье [New – CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) и [New – CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="ece34-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="ece34-255">Получение имени службы для службы группы ответа Lync Server и присвоение его переменной.</span><span class="sxs-lookup"><span data-stu-id="ece34-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="ece34-256">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ece34-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="ece34-257">Создайте или измените рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="ece34-257">Create or modify the workflow.</span></span> <span data-ttu-id="ece34-258">Чтобы создать рабочий процесс, используйте **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="ece34-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="ece34-259">Чтобы изменить рабочий процесс, используйте **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="ece34-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="ece34-260">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ece34-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="ece34-261">Например:</span><span class="sxs-lookup"><span data-stu-id="ece34-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ece34-262">Всем пользователям, которые назначены менеджерами рабочих процессов, необходимо присвоить роль CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="ece34-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ece34-263">Дополнительные сведения о дополнительных параметрах можно узнать в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New/CsRgsWorkflow</A> или <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set – CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="ece34-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ece34-264">См. также</span><span class="sxs-lookup"><span data-stu-id="ece34-264">See Also</span></span>


[<span data-ttu-id="ece34-265">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece34-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="ece34-266">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ece34-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="ece34-267">New — CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="ece34-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="ece34-268">Set — CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="ece34-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="ece34-269">New — CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="ece34-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="ece34-270">New — CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="ece34-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

