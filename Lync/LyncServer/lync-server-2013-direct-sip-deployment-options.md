---
title: 'Lync Server 2013: параметры прямого развертывания SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4bbacbbb6f1a420e989f4bed02ba2fc0db6f85f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="0d290-102">Параметры прямого развертывания SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d290-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d290-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d290-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0d290-104">В этом разделе приводятся примеры топологий для развертывания прямых подключений SIP.</span><span class="sxs-lookup"><span data-stu-id="0d290-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="0d290-105">Изолированный сервер Lync Server</span><span class="sxs-lookup"><span data-stu-id="0d290-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="0d290-106">Если в организации используется одно из развертываний, описанное в этом разделе, вы можете использовать Lync Server 2013 как одно решение для телефонной связи или для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="0d290-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="0d290-107">В этом разделе подробно описываются следующие развертывания:</span><span class="sxs-lookup"><span data-stu-id="0d290-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="0d290-108">**Добавочное развертывание:** В этом варианте предполагается, что у вас есть существующая инфраструктура обмена частной филиалом (УАТС), и вы планируете поэтапное внедрение корпоративной голосовой связи в небольшие группы или в Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="0d290-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="0d290-109">**Lync Server VoIP — развертывание только VoIP:** в этом варианте предполагается, что вы выполняете развертывание корпоративной голосовой связи на сайте, на котором не установлена традиционная инфраструктура телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="0d290-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="0d290-110">Добавочное развертывание</span><span class="sxs-lookup"><span data-stu-id="0d290-110">Incremental Deployment</span></span>

<span data-ttu-id="0d290-111">В добавочном развертывании Lync Server 2013 — это единственное решение для телефонии для отдельных отделов или отделов, а остальные пользователи в организации продолжают использовать УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="0d290-112">Эта стратегия добавочного развертывания предоставляет один способ введения IP-телефонии в корпоративный пул через контролируемые пилотные программы.</span><span class="sxs-lookup"><span data-stu-id="0d290-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="0d290-113">Рабочие группы, для которых наилучшим образом применяются Объединенные коммуникации Майкрософт, перемещаются в корпоративную голосовую связь, а другие пользователи — на имеющейся УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="0d290-114">При необходимости можно перенести дополнительные рабочие группы на корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="0d290-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="0d290-115">Добавочный вариант рекомендуется использовать, если вы четко определили группы пользователей с требованиями к обмену данными, которые используются для централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="0d290-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="0d290-116">Этот параметр также можно использовать, если у вас есть группы или отделы, распределенные по широкому географическому расположению, где экономия на междугородные звонки может быть значительной.</span><span class="sxs-lookup"><span data-stu-id="0d290-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="0d290-117">На самом деле этот параметр полезен для создания виртуальных команд, члены которых могут быть разбросаны по всему миру.</span><span class="sxs-lookup"><span data-stu-id="0d290-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="0d290-118">Вы можете создавать, изменять или дисбанд такие команды в быстром ответе на смену бизнес-требований.</span><span class="sxs-lookup"><span data-stu-id="0d290-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="0d290-119">На следующем рисунке показана общая топология для развертывания корпоративной голосовой связи за УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="0d290-120">Это рекомендуемая топология для добавочного развертывания.</span><span class="sxs-lookup"><span data-stu-id="0d290-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="0d290-121">**Параметр добавочного развертывания**</span><span class="sxs-lookup"><span data-stu-id="0d290-121">**Incremental deployment option**</span></span>

<span data-ttu-id="0d290-122">![Схема параметров переноса подразделений](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Схема параметров переноса подразделений")</span><span class="sxs-lookup"><span data-stu-id="0d290-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d290-123">Если вы подключаете развертывание Lync Server к сертифицированному прямому партнеру по протоколу SIP, шлюз для телефонной сети общего пользования (PSTN) между сервером-посредником и УАТС не требуется.</span><span class="sxs-lookup"><span data-stu-id="0d290-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="0d290-124">Список сертифицированных прямых партнеров SIP представлен на веб-сайте с открытым набором программ взаимодействия с <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>Microsoft Unified Communications.</span><span class="sxs-lookup"><span data-stu-id="0d290-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0d290-125">На пути к носителю, показанном на этом рисунке, включено обход сервера-посредника (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="0d290-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0d290-126">Если вы отказываетесь отключить обход сервера-посредника, путь к носителю направляется через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="0d290-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="0d290-127">В этой топологии для выбранных отделов или рабочих групп включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0d290-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="0d290-128">Шлюз PSTN связывает рабочую группу с включенной поддержкой протокола VoIP с УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="0d290-129">Пользователи с включенной поддержкой корпоративной голосовой связи, в том числе удаленные работники, обмениваются данными по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="0d290-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="0d290-130">Звонки пользователей корпоративной голосовой связи PSTN и сотрудникам, не включенным в корпоративную голосовую связь, перенаправляются на соответствующий шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d290-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0d290-131">Вызовы от коллег, которые по-прежнему находятся в системе УАТС или от абонентов PSTN, направляются шлюзу PSTN, который пересылает вызовы на сервер Lync Server для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0d290-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="0d290-132">Существует две Рекомендуемые конфигурации для подключения корпоративной голосовой связи к существующей инфраструктуре УАТС для взаимодействия: Корпоративная голосовая связь за УАТС и корпоративной голосовой связью перед УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="0d290-133">Корпоративная голосовая связь за УАТС</span><span class="sxs-lookup"><span data-stu-id="0d290-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="0d290-134">Когда корпоративная голосовая связь разворачивается за пределами УАТС, все звонки из сети PSTN прибывают к УАТС, которые направляют звонки на пользователей корпоративной голосовой связи шлюзу PSTN и направляются на УАТС пользователям УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="0d290-135">Корпоративная голосовая связь перед УАТС</span><span class="sxs-lookup"><span data-stu-id="0d290-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="0d290-136">Когда корпоративная голосовая связь разворачивается перед УАТС, все звонки поступают на шлюз PSTN, который направляет вызовы для пользователей корпоративной голосовой связи в Lync Server и звонки пользователям УАТС на УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="0d290-137">Звонки PSTN из пользователей корпоративной голосовой связи и УАТС направляются по IP-сети в наиболее экономичный шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d290-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="0d290-138">В следующей таблице показаны преимущества и недостатки данной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0d290-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="0d290-139">Преимущества и недостатки развертывания корпоративной голосовой связи перед УАТС</span><span class="sxs-lookup"><span data-stu-id="0d290-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d290-140">Преимущества</span><span class="sxs-lookup"><span data-stu-id="0d290-140">Advantages</span></span></th>
<th><span data-ttu-id="0d290-141">Недостатки</span><span class="sxs-lookup"><span data-stu-id="0d290-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d290-142">УАТС по-прежнему обслуживает пользователей, для которых не включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0d290-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="0d290-143">Существующие шлюзы могут не поддерживать требуемые функции или возможности.</span><span class="sxs-lookup"><span data-stu-id="0d290-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d290-144">УАТС обрабатывает все более ранние устройства.</span><span class="sxs-lookup"><span data-stu-id="0d290-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="0d290-145">Требует магистрали от шлюза к УАТС и от шлюза к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="0d290-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="0d290-146">Возможно, вам потребуются дополнительные магистрали от поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="0d290-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d290-147">Пользователи корпоративной голосовой связи хранят одни и те же номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="0d290-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="0d290-148">Развертывание Lync Server VoIP — только для VoIP</span><span class="sxs-lookup"><span data-stu-id="0d290-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="0d290-149">Корпоративная голосовая связь предоставляет новые предприятия, а также новые сайты Office для существующих предприятий с возможностью реализации полнофункционального решения VoIP без необходимости заботиться о интеграции УАТС или значительном развертывании и обслуживании. затраты инфраструктуры IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d290-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="0d290-150">Это решение поддерживает как на месте, так и на удаленных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="0d290-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="0d290-151">В этом развертывании все звонки маршрутизируются по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="0d290-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="0d290-152">Звонки PSTN направляются на соответствующий шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d290-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0d290-153">Lync 2013 или Lync Phone Edition выступает в качестве программного телефона.</span><span class="sxs-lookup"><span data-stu-id="0d290-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="0d290-154">Удаленное управление звонками недоступно и не требуется, так как у пользователей нет телефонов УАТС для управления.</span><span class="sxs-lookup"><span data-stu-id="0d290-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="0d290-155">Службы голосовой почты и автосекретаря доступны в необязательном развертывании единой системы обмена сообщениями Exchange (единой системы обмена сообщениями Exchange).</span><span class="sxs-lookup"><span data-stu-id="0d290-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d290-156">Помимо сетевой инфраструктуры, необходимой для поддержки Lync Server 2013, развертывание только VoIP может использовать небольшой квалифицированный шлюз для поддержки факсимильных аппаратов и аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="0d290-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="0d290-157">На следующем рисунке показана типичная топология для развертывания с использованием VoIP.</span><span class="sxs-lookup"><span data-stu-id="0d290-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="0d290-158">**Параметр развертывания только VoIP**</span><span class="sxs-lookup"><span data-stu-id="0d290-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="0d290-159">![Параметр развертывания гринфидле](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Параметр развертывания гринфидле")</span><span class="sxs-lookup"><span data-stu-id="0d290-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d290-160">На пути к носителю, показанном на этом рисунке, включено обход сервера-посредника (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="0d290-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0d290-161">Если вы отказываетесь отключить обход сервера-посредника, путь к носителю направляется через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="0d290-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

