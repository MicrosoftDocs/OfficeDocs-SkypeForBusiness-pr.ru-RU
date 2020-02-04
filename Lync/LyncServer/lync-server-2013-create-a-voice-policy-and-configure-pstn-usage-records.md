---
title: 'Lync Server 2013: Создание политики голосовой связи и настройка записей об использовании PSTN'
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
ms.openlocfilehash: 80537aabe132f1b83714d42244409224ca53f72d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="f6114-102">Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6114-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f6114-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f6114-104">Если вы хотите создать новую политику голосовой связи, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f6114-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="f6114-105">Если вы хотите изменить политику голосовой связи, ознакомьтесь со сведениями [в разделе изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f6114-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6114-106">Каждая политика голосовой связи должна иметь по крайней мере одну связанную запись использования телефонной сети с открытым коммутируемым подключением (PSTN).</span><span class="sxs-lookup"><span data-stu-id="f6114-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="f6114-107">Чтобы просмотреть список всех записей использования PSTN, доступных в развертывании корпоративной голосовой связи, и просмотреть их свойства, ознакомьтесь с разрешениями <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей использования PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f6114-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="f6114-108">Создание политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f6114-108">To create a voice policy</span></span>

1.  <span data-ttu-id="f6114-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f6114-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f6114-110">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f6114-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6114-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6114-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6114-113">В левой области навигации щелкните **Маршрутизация голосовой связи**, затем **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="f6114-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="f6114-114">На странице **Политика голосовой связи** щелкните **Создать**, затем выберите область применения новой политики.</span><span class="sxs-lookup"><span data-stu-id="f6114-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="f6114-p105">**Политика сайта** применяется ко всему сайту, кроме тех пользователей и групп, которым назначена политика пользователей. Если в качестве области действия политики указан сайт, выберите сайт в диалоговом окне **Выбор сайта**. Если для сайта уже создана политика голосовой связи, он не отображается в диалоговом окне **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="f6114-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="f6114-118">**Политика пользователей** может применяться к отдельным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="f6114-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="f6114-119">Если в качестве области действия политики указан пользователь, введите информативное имя политики в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="f6114-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6114-120">Если в качестве области действия политики указан сайт, в поле <STRONG>Имя</STRONG> в окне <STRONG>создания политики голосовой связи</STRONG> автоматически вводится имя сайта, которое невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="f6114-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="f6114-121">(Необязательно) Введите дополнительное описание для политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f6114-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="f6114-122">Установите или снимите следующие флажки для включения или отключения соответствующих **функций вызовов** для данной политики голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="f6114-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="f6114-123">**Отключение голосовой почты** предотвращает немедленное перенаправление вызовов в систему голосовой почты на мобильном телефоне пользователя, если разрешено одновременное поступление вызовов, а телефон отключен, разряжен или находится вне зоны действия сети.</span><span class="sxs-lookup"><span data-stu-id="f6114-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f6114-124">Эту функцию можно настроить только с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f6114-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="f6114-125">**Переадресация звонков** позволяет пользователям переадресовывать звонки на другие телефоны и устройства клиента.</span><span class="sxs-lookup"><span data-stu-id="f6114-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="f6114-126">Lync Server 2013 предоставляет значительно более широкий спектр параметров настройки переадресации звонков.</span><span class="sxs-lookup"><span data-stu-id="f6114-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="f6114-127">Например, если в организации требуется запретить внешнюю переадресацию входящих вызовов в ТСОП, администратор может применить особую политику голосовой связи для реализации этого ограничения.</span><span class="sxs-lookup"><span data-stu-id="f6114-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="f6114-128">По умолчанию эта функция включена.</span><span class="sxs-lookup"><span data-stu-id="f6114-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-129">**Делегирование** позволяет пользователям указывать других пользователей, которые могут выполнять и принимать звонки от их имени.</span><span class="sxs-lookup"><span data-stu-id="f6114-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="f6114-130">В Lync Server 2013 делегат может настраивать одновременные звонки, позволяющие входящим звонкам своему начальнику звонить всем абонентам одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="f6114-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="f6114-131">Это расширяет возможность уполномоченного отвечать на вызовы, адресованные руководителю.</span><span class="sxs-lookup"><span data-stu-id="f6114-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="f6114-132">Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6114-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-p108">**Переключение звонка** позволяет пользователям передать звонок другим пользователям. По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="f6114-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-p109">**Приостановка вызовов** позволяет пользователям переводить вызовы в режим удержания, а затем принимать такой вызов с другого телефона или клиента. По умолчанию эта функция отключена.</span><span class="sxs-lookup"><span data-stu-id="f6114-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="f6114-137">**Одновременный звонок** позволяет принимать входящие звонки на другие телефоны (например, на мобильный телефон) и другие оконечные устройства.</span><span class="sxs-lookup"><span data-stu-id="f6114-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="f6114-138">Lync Server 2013 предоставляет значительно более широкий спектр вариантов настройки для одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="f6114-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="f6114-139">По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="f6114-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-140">**Групповой звонок** позволяет пользователям из заданной группы отвечать на звонки, предназначенные другим членам этой группы.</span><span class="sxs-lookup"><span data-stu-id="f6114-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="f6114-141">По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="f6114-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-142">**Переадресация через коммутируемые** линии позволяет перенаправлять звонки, сделанные пользователями, которым назначена эта политика, другим пользователям организации, если она перегружена или недоступна.</span><span class="sxs-lookup"><span data-stu-id="f6114-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="f6114-143">По умолчанию данная возможность включена.</span><span class="sxs-lookup"><span data-stu-id="f6114-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="f6114-p113">**Переопределение политики пропускной способности** позволяет администраторам переопределять политику контроля допуска звонков для отдельного пользователя. По умолчанию данная возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="f6114-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f6114-p114">Политика переопределяется только для входящих звонков данного пользователя и не распространяется на его исходящие звонки. После создания сеанса использование полосы пропускания будет тщательно учитываться. Старайтесь использовать данный параметр умеренно или не использовать совсем в случае принятия разумных мер контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="f6114-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6114-149">**Трассировка вредоносных вызовов** позволяет пользователям сообщать о вредоносных вызовах (например, угрозах бомб) с помощью пользовательского интерфейса клиента, который, в свою очередь, помечает звонки в записи сведений о вызовах (кдрс).</span><span class="sxs-lookup"><span data-stu-id="f6114-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="f6114-150">По умолчанию эта функция отключена.</span><span class="sxs-lookup"><span data-stu-id="f6114-150">Disabled by default.</span></span>

8.  <span data-ttu-id="f6114-151">Чтобы сопоставить и настроить записи использования ТСОП для этой политики голосовой связи, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f6114-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f6114-p116">Для выбора одной или нескольких записей в списке записей о режимах работы с ТСОП, доступных в данном развертывании корпоративной голосовой связи, нажмите кнопку **Выбрать** Выделите записи, которые требуется связать с данной политикой голосовой связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f6114-154">Для удаления записи о режиме работы с ТСОП из политики голосовой связи выделите эту запись и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="f6114-155">Чтобы определить новую запись использования ТСОП и сопоставить ее с политикой голосовой связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6114-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f6114-156">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="f6114-p117">В поле **Имя** введите уникальное информативное имя записи. Например, можно создать запись о режиме работы с ТСОП для штатных сотрудников в Редмонде и назвать ее **Redmond**, а также создать другую запись для внештатных сотрудников и назвать ее **RedmondTemps**.</span><span class="sxs-lookup"><span data-stu-id="f6114-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="f6114-p118">Имя записи о режиме работы с ТСОП не должно повторяться в пределах развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> не доступно для редактирования.</span><span class="sxs-lookup"><span data-stu-id="f6114-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="f6114-161">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f6114-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f6114-162">Для выбора одного или нескольких маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи нажмите кнопку **Выбрать** и выделите маршруты, которые требуется связать с данной записью о режиме работы с ТСОП, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f6114-163">Для удаления маршрута из записи о режиме работы с ТСОП выделите этот маршрут, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="f6114-164">Чтобы определить новый маршрут и связать его с этой записью использования PSTN, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f6114-165">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f6114-166">Для изменения маршрута, уже связанного с данной записью о режиме работы с ТСОП, выделите его и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f6114-167">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="f6114-168">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="f6114-169">Чтобы изменить запись использования ТСОП, которая уже сопоставлена с этой политикой голосовой связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6114-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f6114-170">Выделите запись о режиме работы с ТСОП, которую требуется изменить, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="f6114-171">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f6114-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f6114-172">Для выбора одного или нескольких маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи нажмите кнопку **Выбрать** и выделите маршруты, которые требуется связать с данной записью о режиме работы с ТСОП, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f6114-173">Для удаления маршрута из данной записи о режиме работы с ТСОП выделите маршрут и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="f6114-174">Чтобы определить новый маршрут и связать его с этой записью использования PSTN, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f6114-175">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f6114-176">Для изменения маршрута, уже связанного с данной записью о режиме работы с ТСОП, выделите его и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="f6114-177">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="f6114-178">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-178">Click **OK**.</span></span>

9.  <span data-ttu-id="f6114-p123">Упорядочите записи использования ТСОП для достижений оптимальной производительности. Чтобы изменить положение записи в списке, выделите ее имя и щелкните стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="f6114-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6114-181">Порядок записей о режиме работы с ТСОП в голосовой политике имеет значение.</span><span class="sxs-lookup"><span data-stu-id="f6114-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="f6114-182">Lync Server обходит список сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="f6114-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="f6114-183">Рекомендуется упорядочить список по частоте использования, например: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="f6114-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="f6114-184">Чтобы сопоставить и настроить записи использования ТСОП для переадресации звонков и одновременных звонков в этой политике голосовой связи, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f6114-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f6114-185">Если для переадресации вызовов и одновременного поступления вызовов требуется применять те же записи о режиме работы с ТСОП, что и в данной политике голосовой связи, выберите **Направлять с помощью применения ТСОП звонка** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="f6114-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="f6114-186">Чтобы разрешить переадресацию звонков и одновременный звонок только внутренним пользователям Lync, выберите параметр **маршрут к внутренним пользователям Lync только** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="f6114-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="f6114-187">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="f6114-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="f6114-p126">Если для переадресации вызовов и одновременного поступления вызовов требуется применять записи о режиме работы с ТСОП, отличные от применяемых в данной политике голосовой связи, выберите **Направлять с помощью пользовательского применения ТСОП** в раскрывающемся меню. Отображается элемент управления, позволяющий выбирать существующие и создавать новые записи о режимах работы с ТСОП специально для переадресации вызовов и одновременного поступления вызовов.</span><span class="sxs-lookup"><span data-stu-id="f6114-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="f6114-p127">Для выбора в списке одной или нескольких записей о режимах работы с ТСОП применительно к переадресации вызовов и одновременному поступлению вызовов нажмите кнопку **Выбрать**. Выделите записи, которые требуется связать с данной политикой переадресации вызовов и одновременного поступления вызовов, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="f6114-192">Для удаления записи о режиме работы с ТСОП из данной политики переадресации вызовов и одновременного поступления вызовов выделите эту запись и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="f6114-193">Чтобы определить новую запись использования ТСОП и сопоставить ее с этой политикой для переадресации звонков и одновременных звонков, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6114-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f6114-194">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="f6114-195">В поле **Имя** введите уникальное информативное имя записи.</span><span class="sxs-lookup"><span data-stu-id="f6114-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="f6114-p128">Имя записи о режиме работы с ТСОП не должно повторяться в пределах развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> не доступно для редактирования.</span><span class="sxs-lookup"><span data-stu-id="f6114-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="f6114-198">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f6114-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f6114-199">Для выбора одного или нескольких маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи нажмите кнопку **Выбрать** и выделите маршруты, которые требуется связать с данной записью о режиме работы с ТСОП, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f6114-200">Для удаления маршрута из записи о режиме работы с ТСОП выделите маршрут и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f6114-201">Чтобы определить новый маршрут и связать его с этой записью использования PSTN, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f6114-202">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f6114-203">Для изменения маршрута, уже связанного с данной записью о режиме работы с ТСОП, выделите его и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f6114-204">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="f6114-205">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="f6114-206">Чтобы изменить запись использования ТСОП, которая уже сопоставлена с этой политикой голосовой связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6114-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f6114-207">Выделите запись о режиме работы с ТСОП, которую требуется изменить, и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="f6114-208">Используйте любой из описанных ниже методов, чтобы сопоставить и настроить маршруты для данной записи использования ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f6114-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f6114-209">Для выбора одного или нескольких маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи нажмите кнопку **Выбрать** и выделите маршруты, которые требуется связать с данной записью о режиме работы с ТСОП, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f6114-210">Для удаления маршрута из данной записи о режиме работы с ТСОП выделите маршрут и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6114-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f6114-211">Чтобы определить новый маршрут и связать его с этой записью использования PSTN, нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="f6114-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f6114-212">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f6114-213">Для изменения маршрута, уже связанного с данной записью о режиме работы с ТСОП, выделите его и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f6114-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f6114-214">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="f6114-215">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-215">Click **OK**.</span></span>

11. <span data-ttu-id="f6114-p133">(Необязательно) Введите число для проверки политики голосовой связи и нажмите кнопку **Начать** (не обязательно). Результаты проверки отображаются в разделе **Преобразованный номер для проверки**.</span><span class="sxs-lookup"><span data-stu-id="f6114-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6114-218">Вы можете сохранить политику голосовой связи, которая еще не пройдет проверку, а затем настроить ее позже.</span><span class="sxs-lookup"><span data-stu-id="f6114-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="f6114-219">Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f6114-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="f6114-220">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6114-220">Click **OK**.</span></span>

13. <span data-ttu-id="f6114-221">На странице **Политика голосовой связи** (Политика голосовой связи) нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="f6114-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6114-222">Каждый раз, когда вы создаете или изменяете политику голосовой связи, необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f6114-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f6114-223">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="f6114-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="f6114-224">Функция отключения голосовой почты обеспечивает распознавание немедленного ответа на вызов из голосовой почты на мобильном телефоне пользователя и завершение связи с голосовой почтой (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="f6114-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="f6114-225">Благодаря этому вызов продолжает поступать на другие оконечные устройства пользователя, что позволяет ему ответить на вызов.</span><span class="sxs-lookup"><span data-stu-id="f6114-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="f6114-226">Подробнее о настройке политики голосовой почты можно узнать в разделе Настройка функции [переключения голосовой почты в Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="f6114-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6114-227">См. также</span><span class="sxs-lookup"><span data-stu-id="f6114-227">See Also</span></span>


[<span data-ttu-id="f6114-228">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="f6114-229">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="f6114-230">Создание голосового маршрута в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="f6114-231">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="f6114-232">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="f6114-233">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="f6114-234">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6114-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

