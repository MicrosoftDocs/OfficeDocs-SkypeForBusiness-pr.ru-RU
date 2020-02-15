---
title: 'Lync Server 2013: общие концепции конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 546e350dc78883ac56623a23f9153d5bdfd4a1d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="7d9c5-102">Распространенные концепции конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d9c5-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d9c5-103">_**Последнее изменение темы:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="7d9c5-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="7d9c5-p101">Несколько концепций являются общими для всех типов конференций. Эти концепции описываются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-p101">Several concepts are common to all types of conferencing. These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="7d9c5-106">Управление политиками и пропускной способностью</span><span class="sxs-lookup"><span data-stu-id="7d9c5-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="7d9c5-107">Lync Server 2013 позволяет администраторам устанавливать политики для типов собраний, которые могут упорядочивать пользователи.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="7d9c5-108">Это помогает повысить эффективность политик, применяемых в вашей организации, а также управления использованием пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="7d9c5-109">Вы можете определять широкий спектр политик проведения собраний и назначать их отдельным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="7d9c5-110">Можно также задавать политики для управления одноранговыми беседами.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="7d9c5-111">Для получения дополнительных сведений о настройке политик конференц-связи в разделе " [политики конференц-связи в Lync Server 2013](lync-server-2013-conferencing-policies.md) " в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="7d9c5-112">Подробнее об управлении пропускной способностью можно узнать [в статье Обзор контроля допуска звонков в Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) и [настройке полосы пропускания видео в Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="7d9c5-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="7d9c5-113">Возможности архивации и обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7d9c5-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="7d9c5-114">Lync Server 2013 предоставляет функции, которые можно использовать, если ваша организация должна следовать нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="7d9c5-115">Вы можете применять возможности архивации контента, полученного на собраниях, а также контента, содержащегося в беседах и конференциях службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="7d9c5-116">Дополнительные сведения приведены в статье [Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="7d9c5-117">Возможности соответствия требованиям сервера сохраняемого чата для архивации многопользовательских, тематических бесед, поддерживаемых в течение того или иного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="7d9c5-118">Дополнительные сведения приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="7d9c5-119">Возможность мониторинга</span><span class="sxs-lookup"><span data-stu-id="7d9c5-119">Monitoring Feature</span></span>

<span data-ttu-id="7d9c5-120">Компонент сервера мониторинга может записывать записи сведений о вызовах (CDRs), которые можно использовать для отслеживания пользователей, которые говорят, к каким другим пользователям применяется Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="7d9c5-121">Подробные сведения о развертывании и настройке мониторинга можно найти [в статье Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="7d9c5-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="7d9c5-122">Включение внешнего участия в конференциях</span><span class="sxs-lookup"><span data-stu-id="7d9c5-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="7d9c5-123">Вы можете значительно увеличить преимущества инвестиций в конференц-связи Lync Server 2013, чтобы внешние пользователи также могли участвовать в конференциях в приглашении.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="7d9c5-124">К внешним пользователям относятся:</span><span class="sxs-lookup"><span data-stu-id="7d9c5-124">External users can include:</span></span>

  - <span data-ttu-id="7d9c5-125">**Удаленные пользователи**   вашей организации, когда они работают за преработкой сетевых брандмауэров и используют ноутбуки или другие устройства Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="7d9c5-126">**Федеративные пользователи**   — пользователи из компаний, которые также работают с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="7d9c5-127">Чтобы ваши пользователи могли легко общаться с такими пользователями, с этими компаниями создаются отношения федерации.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="7d9c5-128">**Анонимные пользователи**   , которые могут присоединиться к определенным конференциям, пользователями, приглашенными пользователями.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="7d9c5-129">Организатор собрания в вашей компании может отправить приглашение на конференцию по электронной почте внешнему пользователю.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="7d9c5-130">Сообщение содержит ссылку, по которой внешний пользователь может перейти, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="7d9c5-131">Чтобы включить все или все эти сценарии, необходимо развернуть пограничный сервер, чтобы обеспечить безопасное взаимодействие между развертыванием Lync Server 2013 и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="7d9c5-132">Решение Lync Server 2013 с использованием пограничных серверов обеспечивает более высококачественный носитель, чем другие решения, такие как виртуальная частная сеть (VPN).</span><span class="sxs-lookup"><span data-stu-id="7d9c5-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="7d9c5-133">Дополнительные сведения см [в разделе Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7d9c5-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="7d9c5-134">Кроме того, независимо от того, были ли развернуты пограничные серверы, можно предоставить пользователям (как внутри организации, так и за ее пределами) возможность звонить со стандартных телефонов ТСОП, чтобы присоединиться к локальным аудиоконференциям.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="7d9c5-135">Для этого выполняется развертывание конференц-связи с телефонным подключением Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="7d9c5-136">Совместимость типов собраний в разных версиях клиента</span><span class="sxs-lookup"><span data-stu-id="7d9c5-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="7d9c5-137">Если вы планируете использовать Lync Server 2013 для взаимодействия с предыдущими версиями Office Communications Server и его клиентами, необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="7d9c5-138">Пользователи, использующие Lync Server 2013, не могут планировать конференции Live Meeting или изменять перенесенные собрания этого типа.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="7d9c5-139">Пользователи, использующие Lync Server 2013, которым необходимо принять участие в конференциях Live Meeting, размещенных на серверах Office Communications Server 2007 R2, должны иметь установленный клиент Live Meeting на своем компьютере (в дополнение к Lync Server 2013) для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="7d9c5-140">При переносе конференций Live Meeting в Lync Server 2013 содержимое собраний не переносится.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="7d9c5-141">Если это содержимое необходимо, его следует отправить повторно.</span><span class="sxs-lookup"><span data-stu-id="7d9c5-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

