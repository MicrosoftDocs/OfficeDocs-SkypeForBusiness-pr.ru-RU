---
title: 'Lync Server 2013: изменение политики голосовой связи и настройка записей использования PSTN'
description: 'Lync Server 2013: изменение политики голосовой связи и настройка записей использования PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26d6c8654ebf758f8b5a185c21468443e0451a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559375"
---
# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="f5b56-103">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-103">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5b56-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f5b56-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f5b56-105">Чтобы изменить политику голосовой связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5b56-105">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="f5b56-106">Если вы хотите создать новую политику голосовой связи, ознакомьтесь со статьей [Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f5b56-106">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5b56-107">Если пользователю назначена политика голосовой связи, которая не имеет связанных записей режимов работы с ТСОП, то пользователь не сможет выполнять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="f5b56-107">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="f5b56-108">Список всех записей об использовании PSTN, доступных в развертывании корпоративной голосовой связи и просмотр их свойств, приведен <A href="lync-server-2013-view-pstn-usage-records.md">в разделе Просмотр записей использования PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5b56-108">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="f5b56-109">Изменение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f5b56-109">To modify a voice policy</span></span>

1.  <span data-ttu-id="f5b56-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f5b56-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f5b56-111">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f5b56-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5b56-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5b56-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5b56-114">В левой панели навигации последовательно выберите пункты **Voice Routing (Маршрутизация голосовой связи)** и **Voice Policy (Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-114">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="f5b56-115">На странице **Voice Policy (Политика голосовой связи)** дважды щелкните имя политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f5b56-115">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5b56-p105">Область и имя политики устанавливаются при создании политики голосовой связи. Изменить их нельзя.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="f5b56-118">В разделе **Edit Voice Policy (Изменение политики голосовой связи)** введите дополнительное описание для этой политики голосовой связи (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="f5b56-118">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="f5b56-119">Установите или снимите следующие флажки, чтобы включить или отключить соответствующие **функции вызова**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-119">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="f5b56-120">**Задержка голосовой почты** запрещает немедленное перенаправление вызова в систему голосовой почты мобильного телефона пользователя, когда настроены одновременные звонки, и мобильный телефон выключен, разряжен или вне зоны доступа.</span><span class="sxs-lookup"><span data-stu-id="f5b56-120">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f5b56-121">Эту функцию можно настроить только с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5b56-121">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="f5b56-122">**Переадресация звонков** позволяет пользователям переадресовывать звонки на другие телефоны и устройства клиента.</span><span class="sxs-lookup"><span data-stu-id="f5b56-122">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="f5b56-123">Lync Server 2013 предоставляет значительно более широкий спектр параметров конфигурации переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-123">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="f5b56-124">Например, если организация не хочет разрешать внешнюю переадресацию входящих вызовов в ТСОП, то администратор может применить специальную политику голосовой связи, чтобы развернуть это ограничение.</span><span class="sxs-lookup"><span data-stu-id="f5b56-124">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="f5b56-125">Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-125">Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-126">**Делегирование** позволяет пользователям указывать других пользователей, которые могут выполнять и принимать звонки от их имени.</span><span class="sxs-lookup"><span data-stu-id="f5b56-126">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="f5b56-127">В Lync Server 2013 делегат может настраивать Одновременный звонок, который позволяет входящим вызовам ИТ Manager звонить всем одновременным абонентам.</span><span class="sxs-lookup"><span data-stu-id="f5b56-127">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="f5b56-128">Это предоставляет делегату большую гибкость при ответе на вызовы, по умолчанию направляемые в диспетчер.</span><span class="sxs-lookup"><span data-stu-id="f5b56-128">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="f5b56-129">Значение по умолчанию: "Включено".</span><span class="sxs-lookup"><span data-stu-id="f5b56-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-p108">**Call transfer (Переключение вызова)** предоставляет пользователям возможность переключать вызовы на других пользователей. Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-p109">**Парковка вызовов** предоставляет пользователям возможность помещать вызовы на удержание, а затем принимать такой вызов с другого телефона или клиента. Эта функция по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-134">**Одновременные звонки** — благодаря этой функции входящие вызовы могут поступать на дополнительные телефоны (например, на мобильный телефон) или другие устройства в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="f5b56-134">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="f5b56-135">Lync Server 2013 предоставляет значительно более широкий спектр параметров конфигурации для одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="f5b56-135">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="f5b56-136">Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5b56-136">Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-p111">**Групповой звонок**— благодаря этой функции пользователи в заданной группе могут отвечать на вызовы для других членов группы. Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-p112">**Перенаправление в ТСОП** позволяет перенаправлять вызовы корпоративных пользователей, сделанные пользователями, которым назначена данная политика, в телефонную сеть общего пользования (ТСОП), если глобальная сеть перегружена или недоступна. Эта функция по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="f5b56-p113">**Bandwidth policy override (Переопределение политики полосы пропускания)** позволяет администраторам переопределять решения политики контроля допуска звонков (CAC) для конкретного пользователя. Эта функция по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f5b56-p114">Эта политика будет переопределяться только для входящих вызовов пользователя, но не для исходящих вызовов, размещаемых пользователем. После установки сеанса будет точно учитываться использование потребление полосы пропускания. Этот параметр следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="f5b56-p115">**Отслеживание нежелательных звонков** предоставляет пользователям возможность сообщать о нежелательных звонках (таких, как угрозы взрыва бомбы) с помощью пользовательского интерфейса клиента, что в свою очередь помечает эти звонки в сведениях о вызовах (CDR). Эта функция по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="f5b56-148">Чтобы сопоставить и настроить записи режимов работы с ТСОП для данной политики голосовой связи, выполните какие-либо из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f5b56-148">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f5b56-p116">Чтобы выбрать одну или несколько записей из списка всех записей режимов работы с ТСОП, доступных в вашем развертывании корпоративной голосовой связи, нажмите **Выбрать**. Выделите записи, которые требуется сопоставить с данной политикой голосовой связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f5b56-151">Чтобы удалить запись режима работы с ТСОП из политики голосовой связи, выделите эту запись и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-151">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="f5b56-152">Чтобы определить новую запись режима работы с ТСОП и связать ее с политикой голосовой связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5b56-152">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f5b56-153">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-153">Click **New**.</span></span>
        
        2.  <span data-ttu-id="f5b56-p117">В поле **Имя** введите уникальное описательное имя для записи. Например, для штатных сотрудников в Редмонде (Redmond) можно создать запись режима работы с ТСОП с именем **Redmond**, а для временных сотрудников — запись с именем **RedmondTemps**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="f5b56-p118">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="f5b56-158">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-158">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f5b56-159">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-159">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f5b56-160">Чтобы удалить маршрут из записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-160">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="f5b56-161">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-161">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f5b56-162">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f5b56-163">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-163">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f5b56-164">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="f5b56-165">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-165">Click **OK**.</span></span>
    
      - <span data-ttu-id="f5b56-166">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с данной политикой голосовой связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5b56-166">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="f5b56-167">Выделите запись режима работы с ТСОП, которую требуется изменить, и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-167">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="f5b56-168">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-168">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f5b56-169">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-169">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="f5b56-170">Чтобы удалить маршрут из данной записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-170">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="f5b56-171">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-171">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f5b56-172">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-172">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f5b56-173">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-173">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f5b56-174">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-174">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="f5b56-175">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-175">Click **OK**.</span></span>

8.  <span data-ttu-id="f5b56-p123">Упорядочите записи режимов работы с ТСОП, чтобы добиться максимальной производительности. Чтобы изменить положение записи в списке, выделите имя записи и нажмите стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5b56-178">Порядок, в котором записи режимов работы с ТСОП перечислены в политике голосовой связи, имеет большое значение.</span><span class="sxs-lookup"><span data-stu-id="f5b56-178">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="f5b56-179">Lync Server выполняет обход списка сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="f5b56-179">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="f5b56-180">Рекомендуется упорядочить список по частоте использования, например: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="f5b56-180">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="f5b56-181">Чтобы сопоставить и настроить записи режимов работы с ТСОП для переадресации вызовов и для одновременных звонков в политике голосовой связи, выполните какие-либо из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f5b56-181">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="f5b56-182">Чтобы использовать для переадресации вызовов и одновременных звонков те же записи режимов работы с ТСОП, что и для данной политики голосовой связи, выберите в раскрывающемся меню пункт **Route using the call PSTN usages (Перенаправлять с использованием режимов работы с ТСОП)**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-182">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="f5b56-183">Чтобы разрешить переадресацию вызовов и одновременный звонок только внутренним пользователям Lync, выберите параметр **направлять только внутренним пользователям Lync** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="f5b56-183">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="f5b56-184">Вызовы не будут переадресовываться на внешние номера в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f5b56-184">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="f5b56-p126">Чтобы указать для переадресации вызовов и одновременных звонков записи режимов работы с ТСОП, отличающиеся от используемых для данной политики голосовой связи, выберите в раскрывающемся меню пункт **Перенаправлять с помощью особых режимов работы с ТСОП**. Этот пункт отображает элемент управления для выбора существующих записей режимов работы с ТСОП или создания новых записей режимов работы с ТСОП специально для переадресации вызовов и одновременных звонков.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="f5b56-p127">Чтобы выбрать записи из списка записей режимов работы с ТСОП для переадресации вызовов и одновременных звонков, нажмите **Выбрать**. Выделите записи, которые требуется сопоставить с данной политикой переадресации вызовов и одновременных звонков, а затем нажмите кнопку **ОК**</span><span class="sxs-lookup"><span data-stu-id="f5b56-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="f5b56-189">Чтобы удалить запись режима работы с ТСОП из данной политики переадресации вызовов и одновременных звонков, выделите эту запись и нажмите **Удалить**</span><span class="sxs-lookup"><span data-stu-id="f5b56-189">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="f5b56-190">Чтобы задать новую запись режима работы с ТСОП и сопоставить ее с данной политикой переадресации вызовов и одновременных звонков, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5b56-190">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f5b56-191">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-191">Click **New**.</span></span>
            
            2.  <span data-ttu-id="f5b56-192">В поле **Имя** введите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="f5b56-192">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="f5b56-p128">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f5b56-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="f5b56-195">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-195">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f5b56-196">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-196">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f5b56-197">Чтобы удалить маршрут из записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-197">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f5b56-198">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-198">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f5b56-199">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-199">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f5b56-200">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-200">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="f5b56-201">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-201">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="f5b56-202">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-202">Click **OK**.</span></span>
        
          - <span data-ttu-id="f5b56-203">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с данной политикой голосовой связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f5b56-203">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="f5b56-204">Выделите запись режима работы с ТСОП, которую требуется изменить, и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-204">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="f5b56-205">Чтобы сопоставить и настроить маршруты для этой записи режима работы с ТСОП, воспользуйтесь любыми из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-205">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="f5b56-206">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в текущем развертывании корпоративной голосовой связи, нажмите **Выбрать**, выделите маршруты, которые требуется сопоставить с данной записью режима работы с ТСОП, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-206">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="f5b56-207">Чтобы удалить маршрут из данной записи режима работы с ТСОП, выделите его и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-207">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="f5b56-208">Чтобы определить новый маршрут и сопоставить его с записью режима работы с ТСОП, нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-208">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f5b56-209">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-209">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="f5b56-210">Чтобы изменить маршрут, уже сопоставленный с данной записью режима работы с ТСОП, выделите его и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-210">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="f5b56-211">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-211">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="f5b56-212">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-212">Click **OK**.</span></span>

10. <span data-ttu-id="f5b56-p133">Введите номер для тестирования политики голосовой связи и нажмите кнопку **Перейти**. Результаты теста отображаются под полем **Преобразованный номер для тестирования** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f5b56-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5b56-215">Можно сохранить еще не прошедшую тестирование политику голосовой связи и настроить ее позднее.</span><span class="sxs-lookup"><span data-stu-id="f5b56-215">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="f5b56-216">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5b56-216">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="f5b56-217">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-217">Click **OK**.</span></span>

12. <span data-ttu-id="f5b56-218">На странице **Политика голосовой связи** нажмите кнопку **Зафиксировать**, а затем кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="f5b56-218">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5b56-219">Команду <STRONG>Зафиксировать все</STRONG> необходимо выполнять всякий раз после создания или изменения политики голосовой связи, чтобы опубликовать изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f5b56-219">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f5b56-220">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f5b56-220">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="f5b56-221">(Необязательно) Задержка голосовой почты определяет то, что вызов был сразу же направлен в голосовую почту мобильного телефона пользователя и разъединяет вызов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-221">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="f5b56-222">Это позволяет звонить на другие конечные точки пользователя, чтобы тот мог на ответить на вызов.</span><span class="sxs-lookup"><span data-stu-id="f5b56-222">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="f5b56-223">Дополнительные сведения о настройке политики голосовой почты см в статье Настройка функции [переключения голосовой почты в Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="f5b56-223">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5b56-224">См. также</span><span class="sxs-lookup"><span data-stu-id="f5b56-224">See Also</span></span>


[<span data-ttu-id="f5b56-225">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-225">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="f5b56-226">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-226">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="f5b56-227">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-227">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="f5b56-228">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-228">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="f5b56-229">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-229">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="f5b56-230">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-230">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="f5b56-231">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b56-231">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

