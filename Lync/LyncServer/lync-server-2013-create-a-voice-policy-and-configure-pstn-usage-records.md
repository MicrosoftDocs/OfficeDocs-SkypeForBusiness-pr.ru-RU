---
title: 'Lync Server 2013: Создание политики голосовой связи и настройка записей использования PSTN'
description: 'Lync Server 2013: Создание политики голосовой связи и настройка записей об использовании PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55833572b5ca79019d5037406ae530ef5591b6fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562455"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="fd7c5-103">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-103">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd7c5-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd7c5-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd7c5-105">Выполните следующие действия, если хотите создать новую политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-105">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="fd7c5-106">Если вы хотите изменить политику голосовой связи, ознакомьтесь со статьей [изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-106">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd7c5-107">У каждой политики голосовой связи должна быть по крайней мере одна связанная запись об использовании телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-107">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="fd7c5-108">Чтобы просмотреть список всех записей использования PSTN, доступных в развертывании корпоративной голосовой связи, и просмотреть их свойства, ознакомьтесь со статьей <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей использования PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-108">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="fd7c5-109">Создание политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="fd7c5-109">To create a voice policy</span></span>

1.  <span data-ttu-id="fd7c5-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fd7c5-111">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="fd7c5-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fd7c5-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fd7c5-114">В левой панели навигации щелкните элемент **Voice Routing** (Маршрутизация голосовых вызовов), а затем **Voice** (Голосовая связь).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-114">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="fd7c5-115">На странице **Voice Policy** (Политика голосовой связи) щелкните элемент **New** (Создать) и затем выберите область для новой политики:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-115">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="fd7c5-p105">**Site policy** (Политика сайта) применяется ко всему сайту, кроме тех пользователей или групп, которым назначена политика пользователей. Если вы решите использовать «Site» (Сайт) в качестве области политики, выберите этот сайт в диалоговом окне **Select a Site** (Выбор сайта). Если для сайта уже создана политика голосовой связи, он не отображается в диалоговом окне **Select a Site** (Выбор сайта).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="fd7c5-119">**User policy** (Политика пользователей) может быть применена к отдельным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-119">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="fd7c5-120">Если областью политики является «User» (Пользователь), введите описательное имя политики в поле **Name** (Имя).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-120">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd7c5-121">Если областью политики является «Site» (Сайт), поле <STRONG>Name</STRONG> (Имя) в окне <STRONG>New Voice Policy</STRONG> (Создание политики голосовой связи) предварительно заполняется именем сайта и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-121">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="fd7c5-122">(Необязательно) Введите дополнительное описание для политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-122">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="fd7c5-123">Установите или снимите следующие флажки, чтобы включить или отключить соответствующие **Calling features** (Возможности звонков) для данной политики голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-123">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="fd7c5-124">**Задержка голосовой почты** предотвращает немедленное перенаправление звонков в систему голосовой почты сотового телефона пользователя, когда настроены одновременные звонки и сотовый телефон отключен, разряжен или находится вне зоны действия сети.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-124">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fd7c5-125">Эту функцию можно настроить только с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-125">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="fd7c5-126">**Переадресация звонков** позволяет пользователям переадресовывать звонки на другие телефоны и устройства клиента.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-126">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="fd7c5-127">Lync Server 2013 предоставляет значительно более широкий спектр параметров конфигурации переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-127">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="fd7c5-128">Например, если организация не хочет разрешать внешнюю переадресацию входящих вызовов в ТСОП, то администратор может применить специальную политику голосовой связи, чтобы развернуть это ограничение.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-128">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="fd7c5-129">Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-130">**Делегирование** позволяет пользователям указывать других пользователей, которые могут выполнять и принимать звонки от их имени.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-130">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="fd7c5-131">В Lync Server 2013 делегат может настраивать Одновременный звонок, который позволяет входящим вызовам ИТ Manager звонить всем одновременным абонентам.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-131">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="fd7c5-132">Это предоставляет делегату большую гибкость при ответе на вызовы, по умолчанию направляемые в диспетчер.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-132">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="fd7c5-133">Значение по умолчанию: "Включено".</span><span class="sxs-lookup"><span data-stu-id="fd7c5-133">Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-p108">**Call transfer** (Передача звонка) позволяет пользователям передать звонок другим пользователям. По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-p109">**Call park** (Парковка вызовов) позволяет пользователям устанавливать звонки на удержание и затем принимать звонок с другого телефона или из другого клиента. По умолчанию данная возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-138">**Одновременные звонки** — благодаря этой функции входящие вызовы могут поступать на дополнительные телефоны (например, на мобильный телефон) или другие устройства в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-138">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="fd7c5-139">Lync Server 2013 предоставляет значительно более широкий спектр параметров конфигурации для одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-139">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="fd7c5-140">Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-140">Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-p111">**Групповой звонок**— благодаря этой функции пользователи в заданной группе могут отвечать на вызовы для других членов группы. Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-p112">**PSTN re-route** (Переадресация ТСОП) позволяет перенаправлять звонки, выполняемые пользователями с данной политикой другим пользователям на предприятии, в телефонную сеть общего пользования (ТСОП), если глобальная сеть перегружена или недоступна. По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="fd7c5-p113">**Bandwidth policy override** (Переопределение политики пропускной способности) позволяет администраторам переопределять политику контроля допуска звонков для отдельного пользователя. По умолчанию данная возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fd7c5-p114">Политика переопределяется только для входящих звонков данного пользователя и не распространяется на его исходящие звонки. После создания сеанса использование полосы пропускания будет тщательно учитываться. Старайтесь использовать данный параметр умеренно или не использовать совсем в случае принятия разумных мер контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="fd7c5-p115">**Отслеживание злонамеренных звонков** позволяет пользователю сообщить о злонамеренных звонках (например, угрозах о заложенной бомбе) с помощью пользовательского интерфейса клиента, что в свою очередь приводит к пометке таких звонков в записях сведений о вызовах (CDR). По умолчанию данная возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

8.  <span data-ttu-id="fd7c5-152">Чтобы сопоставить и настроить записи использования ТСОП для этой политики голосовой связи, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="fd7c5-p116">Чтобы выбрать одну или несколько записей из списка всех записей режимов работы с ТСОП, доступных в вашем развертывании корпоративной голосовой связи, нажмите **Выбрать**. Выделите записи, которые требуется сопоставить с данной политикой голосовой связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="fd7c5-155">Чтобы удалить запись режима работы с ТСОП из политики голосовой связи, выделите эту запись и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="fd7c5-156">Чтобы определить новую запись режима работы с ТСОП и связать ее с политикой голосовой связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="fd7c5-157">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-157">Click **New**.</span></span>
        
        2.  <span data-ttu-id="fd7c5-p117">В поле **Name** (Имя) введите для записи уникальное описательное имя. Например, может потребоваться создать запись использования ТСОП с именем **Redmond** для штатных сотрудников в городе Редмонд и еще одну запись с именем **RedmondTemps** для внештатных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="fd7c5-p118">Имя записи использования ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Name</STRONG> (Имя) становится недоступным для изменения.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="fd7c5-162">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-162">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="fd7c5-163">Чтобы выбрать один или несколько маршрутов в списке доступных маршрутов в вашем развертывании корпоративной голосовой связи, нажмите кнопку **Select** (Выбрать), выделите маршруты, которые хотите сопоставить с этой запись использования ТСОП, и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-163">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="fd7c5-164">Чтобы удалить маршрут из записи использования ТСОП, выделите этот маршрут и нажмите кнопку **Remove** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-164">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="fd7c5-165">Чтобы определить новый маршрут и сопоставить его с этой записью использования ТСОП, нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-165">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="fd7c5-166">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-166">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="fd7c5-167">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-167">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="fd7c5-168">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-168">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="fd7c5-169">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-169">Click **OK**.</span></span>
    
      - <span data-ttu-id="fd7c5-170">Чтобы изменить запись использования ТСОП, которая уже сопоставлена с этой политикой голосовой связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-170">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="fd7c5-171">Выделите запись использования ТСОП, которую вы хотите изменить, и щелкните элемент **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-171">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="fd7c5-172">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-172">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="fd7c5-173">Чтобы выбрать один или несколько маршрутов в списке доступных маршрутов в вашем развертывании корпоративной голосовой связи, нажмите кнопку **Select** (Выбрать), выделите маршруты, которые хотите сопоставить с этой запись использования ТСОП, и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-173">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="fd7c5-174">Чтобы удалить маршрут из записи использования ТСОП, выделите этот маршрут и нажмите кнопку **Remove** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-174">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="fd7c5-175">Чтобы определить новый маршрут и сопоставить его с этой записью использования ТСОП, нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-175">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="fd7c5-176">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-176">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="fd7c5-177">Чтобы изменить маршрут, который уже сопоставлен с этой записью использования ТСОП, выделите его и щелкните элемент **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-177">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="fd7c5-178">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-178">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="fd7c5-179">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-179">Click **OK**.</span></span>

9.  <span data-ttu-id="fd7c5-p123">Упорядочите записи режимов работы с ТСОП, чтобы добиться максимальной производительности. Чтобы изменить положение записи в списке, выделите имя записи и нажмите стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fd7c5-182">Порядок, в котором записи режимов работы с ТСОП перечислены в политике голосовой связи, имеет большое значение.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-182">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="fd7c5-183">Lync Server выполняет обход списка сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-183">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="fd7c5-184">Рекомендуется упорядочить список по частоте использования, например: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-184">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="fd7c5-185">Чтобы сопоставить и настроить записи режимов работы с ТСОП для переадресации вызовов и для одновременных звонков в политике голосовой связи, выполните какие-либо из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-185">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="fd7c5-186">Чтобы использовать для переадресации звонков и одновременных звонков такие же записи использования ТСОП, как и в этой политике голосовой связи, выберите в раскрывающемся меню параметр **Route using the call PSTN usages** (Перенаправление на основе использования звонков ТСОП).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-186">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="fd7c5-p125">Чтобы разрешить переадресацию звонков и одновременные звонки только для внутренних пользователей Lync,  выберите в раскрывающемся меню параметр **Route to internal Lync users only** (Перенаправление только внутренним пользователям Lync). В этом случае звонки не перенаправляются на внешние номера ТСОП.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p125">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu. Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="fd7c5-p126">Чтобы указать для переадресации звонков и одновременных звонков записи использования ТСОП, отличные от заданных в этой политике голосовой связи, выберите в раскрывающемся меню параметр **Route using custom PSTN usages** (Перенаправление на основе настраиваемого использования ТСОП). Данный параметр отображает элемент управления для выбора существующих или создания новых записей использования ТСОП специально для переадресации звонков и одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="fd7c5-p127">Чтобы выбрать одну или несколько записей в списке записей использования ТСОП для переадресации звонков и одновременных звонков, нажмите кнопку **Select** (Выбрать). Выделите записи, которые хотите сопоставить с этой политикой голосовой связи для переадресации звонков и одновременных звонков, и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="fd7c5-193">Чтобы удалить запись режима работы с ТСОП из данной политики переадресации вызовов и одновременных звонков, выделите эту запись и нажмите **Удалить**</span><span class="sxs-lookup"><span data-stu-id="fd7c5-193">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="fd7c5-194">Чтобы задать новую запись режима работы с ТСОП и сопоставить ее с данной политикой переадресации вызовов и одновременных звонков, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-194">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="fd7c5-195">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-195">Click **New**.</span></span>
            
            2.  <span data-ttu-id="fd7c5-196">В поле **Имя** введите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-196">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="fd7c5-p128">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="fd7c5-199">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-199">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="fd7c5-200">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-200">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="fd7c5-201">Чтобы удалить маршрут из записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-201">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="fd7c5-202">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-202">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="fd7c5-203">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-203">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="fd7c5-204">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-204">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="fd7c5-205">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-205">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="fd7c5-206">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-206">Click **OK**.</span></span>
        
          - <span data-ttu-id="fd7c5-207">Чтобы изменить запись использования ТСОП, которая уже сопоставлена с этой политикой голосовой связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-207">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="fd7c5-208">Выделите запись использования ТСОП, которую вы хотите изменить, и щелкните элемент **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-208">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="fd7c5-209">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="fd7c5-209">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="fd7c5-210">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-210">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="fd7c5-211">Чтобы удалить маршрут из данной записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-211">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="fd7c5-212">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-212">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="fd7c5-213">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-213">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="fd7c5-214">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-214">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="fd7c5-215">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-215">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="fd7c5-216">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-216">Click **OK**.</span></span>

11. <span data-ttu-id="fd7c5-p133">Введите номер для тестирования политики голосовой связи и нажмите кнопку **Перейти**. Результаты теста отображаются под полем **Преобразованный номер для тестирования** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd7c5-219">Можно сохранить еще не прошедшую тестирование политику голосовой связи и настроить ее позднее.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-219">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="fd7c5-220">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-220">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="fd7c5-221">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-221">Click **OK**.</span></span>

13. <span data-ttu-id="fd7c5-222">На странице **Политика голосовой связи** нажмите кнопку **Зафиксировать**, а затем кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-222">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd7c5-223">При каждом создании или изменении политики голосовой связи вам следует запускать команду <STRONG>Commit all</STRONG> (Исполнить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-223">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="fd7c5-224">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-224">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="fd7c5-225">(Необязательно) Задержка голосовой почты определяет то, что вызов был сразу же направлен в голосовую почту мобильного телефона пользователя и разъединяет вызов.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-225">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="fd7c5-226">Это позволяет звонить на другие конечные точки пользователя, чтобы тот мог на ответить на вызов.</span><span class="sxs-lookup"><span data-stu-id="fd7c5-226">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="fd7c5-227">Подробнее о настройке политики голосовой почты можно узнать в статье Настройка функции [экранирования голосовой почты в Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="fd7c5-227">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd7c5-228">См. также</span><span class="sxs-lookup"><span data-stu-id="fd7c5-228">See Also</span></span>


[<span data-ttu-id="fd7c5-229">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-229">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="fd7c5-230">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-230">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="fd7c5-231">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-231">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="fd7c5-232">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-232">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="fd7c5-233">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-233">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="fd7c5-234">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-234">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="fd7c5-235">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7c5-235">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

