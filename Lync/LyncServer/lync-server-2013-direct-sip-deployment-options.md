---
title: 'Lync Server 2013: варианты развертывания прямого SIP-подключения'
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
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="12747-102">Варианты развертывания прямого SIP-подключения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12747-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12747-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="12747-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="12747-104">В этом разделе приводятся примеры топологий для развертывания прямых подключений по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="12747-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="12747-105">Изолированный режим Lync Server</span><span class="sxs-lookup"><span data-stu-id="12747-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="12747-106">Если в вашей организации используется один из развертываний, описанных в этом разделе, вы можете использовать Lync Server 2013 в качестве единственного решения для телефонной связи для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="12747-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="12747-107">В этом разделе описываются указанные ниже варианты развертывания.</span><span class="sxs-lookup"><span data-stu-id="12747-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="12747-108">**Добавочное развертывание.** Этот вариант предполагает, что у вас уже есть инфраструктура УАТС и вы намереваетесь постепенно предоставлять службу "Корпоративная голосовая связь" небольшим группам пользователей или рабочим группам внутри организации.</span><span class="sxs-lookup"><span data-stu-id="12747-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="12747-109">**Развертывание Lync Server VoIP:** в этом случае предполагается, что вы просматриваете развертывание корпоративной голосовой связи на сайте, на котором не установлена традиционная инфраструктура телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="12747-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="12747-110">Добавочное развертывание</span><span class="sxs-lookup"><span data-stu-id="12747-110">Incremental Deployment</span></span>

<span data-ttu-id="12747-111">В инкрементном развертывании Lync Server 2013 — это единственное решение для телефонной связи для отдельных групп или отделов, а остальные пользователи в организации продолжают использовать АТС.</span><span class="sxs-lookup"><span data-stu-id="12747-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="12747-112">Эта стратегия является одним из способов развертывания IP-телефонии в организации с помощью управляемых пилотных программ.</span><span class="sxs-lookup"><span data-stu-id="12747-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="12747-113">Рабочие группы, которым требуются объединенные коммуникации (Майкрософт), перемещаются в службу "Корпоративная голосовая связь", а остальные пользователи остаются в существующей УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="12747-114">При необходимости можно перенести дополнительные рабочие группы в службу "Корпоративная голосовая связь".</span><span class="sxs-lookup"><span data-stu-id="12747-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="12747-115">Добавочное развертывание рекомендуется при наличии четко определенных групп пользователей, имеющих схожие требования к связи и поддерживающих централизованное управление.</span><span class="sxs-lookup"><span data-stu-id="12747-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="12747-116">Этот вариант также эффективен при наличии групп или отделов, находящихся в разных географических областях, для которых экономия на оплате за междугороднюю связь может быть существенной.</span><span class="sxs-lookup"><span data-stu-id="12747-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="12747-117">Кроме того, этот вариант полезен для создания виртуальных групп, участники которых могут находиться на разных континентах.</span><span class="sxs-lookup"><span data-stu-id="12747-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="12747-118">Для быстрого реагирования на изменения потребностей бизнеса можно создавать, изменять или расформировывать эти группы.</span><span class="sxs-lookup"><span data-stu-id="12747-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="12747-119">На приведенном ниже рисунке показана универсальная топология развертывания службы "Корпоративная голосовая связь" после УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="12747-120">Это рекомендуемая топология для добавочного развертывания.</span><span class="sxs-lookup"><span data-stu-id="12747-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="12747-121">**Вариант добавочного развертывания**</span><span class="sxs-lookup"><span data-stu-id="12747-121">**Incremental deployment option**</span></span>

<span data-ttu-id="12747-122">![Схема миграции отделов](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Миграция отделами (схема)")</span><span class="sxs-lookup"><span data-stu-id="12747-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12747-123">Если вы подключаете развертывание Lync Server к сертифицированному прямому партнеру по протоколу SIP, коммутируемый шлюз для телефонной сети (PSTN) между сервером-посредником и УАТС не требуется.</span><span class="sxs-lookup"><span data-stu-id="12747-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="12747-124">Список сертифицированных партнеров по протоколу SIP можно найти на веб-сайте Microsoft Unified коммуникационные программы с открытым <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>взаимодействием по адресу.</span><span class="sxs-lookup"><span data-stu-id="12747-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="12747-125">Для трафика мультимедиа, показанного на этой схеме, включен обход сервера-посредника (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="12747-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="12747-126">Если отключить обход сервера-посредника, трафик мультимедиа будет направляться через этот сервер.</span><span class="sxs-lookup"><span data-stu-id="12747-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="12747-127">В этой топологии служба "Корпоративная голосовая связь" предоставляется только определенным отделам или рабочим группам.</span><span class="sxs-lookup"><span data-stu-id="12747-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="12747-128">Шлюз ТСОП связывает рабочую группу с поддержкой протокола VoIP и УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="12747-129">Пользователи, которым предоставляется служба "Корпоративная голосовая связь", включая удаленных сотрудников, обмениваются данными по сети IP.</span><span class="sxs-lookup"><span data-stu-id="12747-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="12747-130">Звонки пользователей службы "Корпоративная голосовая связь" на номера ТСОП и коллег, которым эта служба недоступна, перенаправляются на соответствующий шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="12747-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="12747-131">Звонки из коллег, которые еще не подключены к системе УАТС, или от абонентов сети PSTN, пересылаются на шлюз PSTN, который пересылает звонки на сервер Lync Server для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="12747-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="12747-132">Существуют две рекомендуемые конфигурации для подключения службы "Корпоративная голосовая связь" к имеющейся инфраструктуре УАТС для взаимодействия: после УАТС и перед УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="12747-133">Корпоративная голосовая связь после УАТС</span><span class="sxs-lookup"><span data-stu-id="12747-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="12747-134">Если служба "Корпоративная голосовая связь" развернута после УАТС, то все звонки из ТСОП поступают на УАТС, которая перенаправляет звонки, адресованные пользователям службы "Корпоративная голосовая связь", на шлюз ТСОП, а звонки для пользователей УАТС — на УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="12747-135">Корпоративная голосовая связь перед УАТС</span><span class="sxs-lookup"><span data-stu-id="12747-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="12747-136">При развертывании корпоративной голосовой связи на лицевой стороне УАТС все звонки поступают на шлюз PSTN, который маршрутизирует звонки пользователей по корпоративной голосовой связи на Lync Server и звонки пользователям УАТС в АТС.</span><span class="sxs-lookup"><span data-stu-id="12747-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="12747-137">Звонки на ТСОП от пользователей службы "Корпоративная голосовая связь" и УАТС перенаправляются через сеть IP на шлюз ТСОП, который является наиболее экономичным.</span><span class="sxs-lookup"><span data-stu-id="12747-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="12747-138">В приведенной ниже таблице перечислены преимущества и недостатки этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12747-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="12747-139">Преимущества и недостатки развертывания службы "Корпоративная голосовая связь" перед УАТС</span><span class="sxs-lookup"><span data-stu-id="12747-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12747-140">Преимущества</span><span class="sxs-lookup"><span data-stu-id="12747-140">Advantages</span></span></th>
<th><span data-ttu-id="12747-141">Недостатки</span><span class="sxs-lookup"><span data-stu-id="12747-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12747-142">УАТС по-прежнему обслуживает пользователей, для которых служба "Корпоративная голосовая связь" не включена.</span><span class="sxs-lookup"><span data-stu-id="12747-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="12747-143">Существующие шлюзы могут не поддерживать нужные функции или возможности.</span><span class="sxs-lookup"><span data-stu-id="12747-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12747-144">УАТС обслуживает все устаревшие устройства.</span><span class="sxs-lookup"><span data-stu-id="12747-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="12747-145">Требуется магистраль от шлюза до УАТС и от шлюза до сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="12747-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="12747-146">Вам может потребоваться большее число магистралей от поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="12747-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12747-147">Номера телефонов пользователей службы "Корпоративная голосовая связь" сохраняются.</span><span class="sxs-lookup"><span data-stu-id="12747-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="12747-148">Развертывание Lync Server VoIP-только</span><span class="sxs-lookup"><span data-stu-id="12747-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="12747-149">Служба "Корпоративная голосовая связь" предоставляет новым компаниям и новым офисам существующих компаний возможность реализовать полнофункциональное решение VoIP, забыв о проблемах интеграции УАТС и дополнительных затратах на развертывание и обслуживание инфраструктуры IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="12747-150">Это решение поддерживает как локальных, так и удаленных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="12747-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="12747-151">В этом развертывании все звонки перенаправляются через сеть IP.</span><span class="sxs-lookup"><span data-stu-id="12747-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="12747-152">Звонки на ТСОП направляются на соответствующий шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="12747-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="12747-153">Lync 2013 или Lync Phone Edition является софтфоне.</span><span class="sxs-lookup"><span data-stu-id="12747-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="12747-154">Удаленное управление звонками недоступно и не требуется, так как пользователям не нужно управлять никакими телефонами УАТС.</span><span class="sxs-lookup"><span data-stu-id="12747-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="12747-155">Службы голосовой почты и автосекретаря станут доступны после необязательного развертывания единой системы обмена сообщениями (UM) Exchange.</span><span class="sxs-lookup"><span data-stu-id="12747-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12747-156">В дополнение к сетевой инфраструктуре, необходимой для поддержки Lync Server 2013, развертывание только VoIP может использовать небольшой квалифицированный шлюз для поддержки аппаратных и аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="12747-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="12747-157">На приведенном ниже рисунке показана типичная топология для развертывания VoIP.</span><span class="sxs-lookup"><span data-stu-id="12747-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="12747-158">**Вариант развертывания только протокола IP**</span><span class="sxs-lookup"><span data-stu-id="12747-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="12747-159">![Развертывание сети с нуля](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Развертывание сети с нуля")</span><span class="sxs-lookup"><span data-stu-id="12747-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12747-160">Для трафика мультимедиа, показанного на этой схеме, включен обход сервера-посредника (рекомендуемая конфигурация).</span><span class="sxs-lookup"><span data-stu-id="12747-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="12747-161">Если отключить обход сервера-посредника, трафик мультимедиа будет направляться через этот сервер.</span><span class="sxs-lookup"><span data-stu-id="12747-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

