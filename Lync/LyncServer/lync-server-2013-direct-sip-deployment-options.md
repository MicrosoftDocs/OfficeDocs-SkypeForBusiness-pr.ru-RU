---
title: 'Lync Server 2013: варианты развертывания прямого SIP-подключения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="f7cd5-102">Варианты развертывания прямого SIP-подключения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7cd5-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7cd5-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f7cd5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f7cd5-104">В этом разделе приводятся примеры топологий для развертывания прямых подключений по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="f7cd5-105">Изолированный режим Lync Server</span><span class="sxs-lookup"><span data-stu-id="f7cd5-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="f7cd5-106">Если в вашей организации используется один из развертываний, описанных в этом разделе, вы можете использовать Lync Server 2013 в качестве единственного решения для телефонной связи для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="f7cd5-107">В этом разделе подробно описаны следующие развертывания:</span><span class="sxs-lookup"><span data-stu-id="f7cd5-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="f7cd5-108">**Инкрементное развертывание:** Этот параметр предполагает, что у вас есть существующая инфраструктура обмена частной ветвью (АТС) и вы планируете последовательное создание корпоративной голосовой связи для небольших групп или групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="f7cd5-109">**Развертывание Lync Server VoIP:** в этом случае предполагается, что вы просматриваете развертывание корпоративной голосовой связи на сайте, на котором не установлена традиционная инфраструктура телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="f7cd5-110">Инкрементное развертывание</span><span class="sxs-lookup"><span data-stu-id="f7cd5-110">Incremental Deployment</span></span>

<span data-ttu-id="f7cd5-111">В инкрементном развертывании Lync Server 2013 — это единственное решение для телефонной связи для отдельных групп или отделов, а остальные пользователи в организации продолжают использовать АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="f7cd5-112">Эта стратегия добавочного развертывания предоставляет один из способов внедрения IP-телефонии в корпоративную программу в рамках управляемых пилотных программ.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="f7cd5-113">Рабочие группы, для которых лучше подходит единая связь Майкрософт, перемещаются в корпоративную голосовую почту, а другие пользователи остаются на существующей АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="f7cd5-114">При необходимости дополнительные рабочие группы можно перенести в корпоративный голосовой счет.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="f7cd5-115">Параметр "добавочный" рекомендуется использовать в том случае, если вы четко определили группы пользователей, для которых есть требования для обмена информацией, и они могут централизованно управлять.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="f7cd5-116">Этот параметр также действует, если у вас есть команды или отделы, которые распределены по распространенным географическим областям, где экономия на междугородную связь может быть значительна.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="f7cd5-117">На самом деле этот параметр полезен для создания виртуальных рабочих групп, члены которых могут быть разбросаны по всему миру.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="f7cd5-118">Вы можете создавать, изменять и расформировать такие группы в быстром ответе на смену бизнес-требований.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="f7cd5-119">На приведенном ниже рисунке показана универсальная топология для развертывания корпоративной голосовой связи на фоне АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="f7cd5-120">Это рекомендуемая топология для инкрементного развертывания.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="f7cd5-121">**Параметр инкрементного развертывания**</span><span class="sxs-lookup"><span data-stu-id="f7cd5-121">**Incremental deployment option**</span></span>

<span data-ttu-id="f7cd5-122">![Схема параметров миграции] подразделений (images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Схема параметров миграции") подразделений</span><span class="sxs-lookup"><span data-stu-id="f7cd5-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cd5-123">Если вы подключаете развертывание Lync Server к сертифицированному прямому партнеру по протоколу SIP, коммутируемый шлюз для телефонной сети (PSTN) между сервером-посредником и УАТС не требуется.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="f7cd5-124">Список сертифицированных партнеров по протоколу SIP можно найти на веб-сайте Microsoft Unified коммуникационные программы с открытым <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>взаимодействием по адресу.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cd5-125">Путь к носителю, показанный на этом рисунке, включает функцию обхода мультимедиа (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="f7cd5-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f7cd5-126">Если вы отказываетесь отключить обход мультимедиа, путь к носителю маршрутизируется через сервер.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="f7cd5-127">В этой топологии для выбранных подразделений и рабочих групп включена Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f7cd5-128">Шлюз PSTN связывает рабочую группу с поддержкой голосовой связи с телефонным подключением по протоколу VoIP с УАТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="f7cd5-129">Пользователи, которым разрешено пользоваться корпоративной голосовой связью, в том числе с удаленными сотрудниками, общаться по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="f7cd5-130">Звонки по корпоративной голосовой связи в КТСОП и коллегам, не поддерживающим корпоративную голосовую связь, перенаправляются на соответствующий шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f7cd5-131">Звонки из коллег, которые еще не подключены к системе УАТС, или от абонентов сети PSTN, пересылаются на шлюз PSTN, который пересылает звонки на сервер Lync Server для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="f7cd5-132">Существует две рекомендованные конфигурации для подключения корпоративной голосовой связи к существующей инфраструктуре УАТС для обеспечения взаимодействия: Корпоративный голосовой интерфейс за ОФИСной АТС и корпоративной голосовой связью перед АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="f7cd5-133">Корпоративный голос за офисной АТС</span><span class="sxs-lookup"><span data-stu-id="f7cd5-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="f7cd5-134">Когда корпоративный голосовой интерфейс разворачивается за пределами УАТС, все звонки через сеть PSTN доставляются в УАТС, которые направляются пользователям корпоративной голосовой связи на шлюз PSTN и звонки в АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="f7cd5-135">Корпоративная голосовая связь на лицевой стороне УАТС</span><span class="sxs-lookup"><span data-stu-id="f7cd5-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="f7cd5-136">При развертывании корпоративной голосовой связи на лицевой стороне УАТС все звонки поступают на шлюз PSTN, который маршрутизирует звонки пользователей по корпоративной голосовой связи на Lync Server и звонки пользователям УАТС в АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="f7cd5-137">Звонки по протоколу КТСОП для пользователей корпоративной голосовой связи и АТС пересылаются по IP-сети в наиболее экономичный шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="f7cd5-138">В следующей таблице показаны преимущества и недостатки этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="f7cd5-139">Преимущества и недостатки развертывания корпоративной голосовой связи на передней панели АТС</span><span class="sxs-lookup"><span data-stu-id="f7cd5-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7cd5-140">Имеет</span><span class="sxs-lookup"><span data-stu-id="f7cd5-140">Advantages</span></span></th>
<th><span data-ttu-id="f7cd5-141">Минус</span><span class="sxs-lookup"><span data-stu-id="f7cd5-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7cd5-142">УАТС по-прежнему обслуживает пользователей, не поддерживающих корпоративную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="f7cd5-143">Существующие шлюзы могут не поддерживать нужные вам функции и возможности.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7cd5-144">УАТС обрабатывает все более ранние устройства.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="f7cd5-145">Требуется магистраль от шлюза к УАТС и от шлюза к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="f7cd5-146">Возможно, вам потребуются дополнительные магистрали от поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7cd5-147">Пользователи предприятий голосовой связи с одинаковыми номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="f7cd5-148">Развертывание Lync Server VoIP-только</span><span class="sxs-lookup"><span data-stu-id="f7cd5-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="f7cd5-149">Корпоративная голосовая связь предлагает новые компании, а также новые сайты Office для существующих предприятий с возможностью реализации полнофункционального решения для VoIP, не заботясь о том, как интегрировать АТС или не беспокоиться о том, что нужно для развертывания и обслуживания. стоимость инфраструктуры IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="f7cd5-150">Это решение поддерживает как на месте, так и на удаленных рабочих сеансах.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="f7cd5-151">В этом развертывании все звонки пересылаются по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="f7cd5-152">Звонки в КТСОП направляются на соответствующий шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f7cd5-153">Lync 2013 или Lync Phone Edition является софтфоне.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="f7cd5-154">Удаленное управление звонками недоступно и не требуется, так как для управления пользователями не существует телефонной АТС.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="f7cd5-155">Службы голосовой почты и автоматических ассистентов можно использовать в дополнительном развертывании единой системы обмена сообщениями Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="f7cd5-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cd5-156">В дополнение к сетевой инфраструктуре, необходимой для поддержки Lync Server 2013, развертывание только VoIP может использовать небольшой квалифицированный шлюз для поддержки аппаратных и аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="f7cd5-157">На приведенном ниже рисунке показана типичная топология для развертывания по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="f7cd5-158">**Параметр развертывания только по протоколу VoIP**</span><span class="sxs-lookup"><span data-stu-id="f7cd5-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="f7cd5-159">![Параметр развертывания гринфидле] (images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Параметр развертывания гринфидле")</span><span class="sxs-lookup"><span data-stu-id="f7cd5-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cd5-160">Путь к носителю, показанный на этом рисунке, включает функцию обхода мультимедиа (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="f7cd5-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f7cd5-161">Если вы отказываетесь отключить обход мультимедиа, путь к носителю маршрутизируется через сервер.</span><span class="sxs-lookup"><span data-stu-id="f7cd5-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

