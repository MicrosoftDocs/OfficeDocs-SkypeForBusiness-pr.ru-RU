---
title: 'Lync Server 2013: общие концепции конференции'
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
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="7974c-102">Общие принципы Конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7974c-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7974c-103">_**Тема последнего изменения:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="7974c-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="7974c-104">Некоторые понятия являются общими для всех типов конференций.</span><span class="sxs-lookup"><span data-stu-id="7974c-104">Several concepts are common to all types of conferencing.</span></span> <span data-ttu-id="7974c-105">Эти разделы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7974c-105">These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="7974c-106">Политики и управление пропускной способностью</span><span class="sxs-lookup"><span data-stu-id="7974c-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="7974c-107">Lync Server 2013 позволяет администраторам устанавливать политики для типов собраний, которые пользователи могут упорядочивать.</span><span class="sxs-lookup"><span data-stu-id="7974c-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="7974c-108">Это позволяет применять политики Организации и контролировать использование пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7974c-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="7974c-109">Вы можете определять различные политики собрания и назначать их отдельным пользователям и группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7974c-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="7974c-110">Вы также можете задать политики, которые управляют одноранговые беседы.</span><span class="sxs-lookup"><span data-stu-id="7974c-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="7974c-111">Дополнительные сведения о настройке политик конференц-связи можно найти [в разделе политики конференц-связи в Lync Server 2013](lync-server-2013-conferencing-policies.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7974c-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="7974c-112">Подробнее об управлении пропускной способностью можно узнать [в статье Обзор управления допуском звонков в Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) и [настройке пропускной способности видео в Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="7974c-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="7974c-113">Возможности архивации и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7974c-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="7974c-114">Lync Server 2013 предоставляет возможности, которые можно использовать, если в Организации должны следовать правила соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7974c-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="7974c-115">Вы можете использовать возможности архивации для архивации контента, представленного в собраниях, а также содержимого бесед и конференций с помощью мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="7974c-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="7974c-116">Подробности можно найти [в разделе Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7974c-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="7974c-117">Вы можете использовать функции соответствия требованиям сохраняемого сервера чата для архивации многофакторной многофакторной беседы, которая сохраняется с течением времени.</span><span class="sxs-lookup"><span data-stu-id="7974c-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="7974c-118">Подробности можно найти [в разделе Планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7974c-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="7974c-119">Функция мониторинга</span><span class="sxs-lookup"><span data-stu-id="7974c-119">Monitoring Feature</span></span>

<span data-ttu-id="7974c-120">Функция сервера мониторинга может собирать записи сведений о вызовах (Кдрс), которые можно использовать для отслеживания пользователей, которые будут общаться с другими пользователями, использующими Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7974c-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="7974c-121">Подробные сведения о развертывании и настройке мониторинга можно найти [в разделе Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="7974c-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="7974c-122">Включение внешнего участия в конференциях</span><span class="sxs-lookup"><span data-stu-id="7974c-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="7974c-123">Вы можете значительно повысить эффективность ваших капиталовложений в конференц-связи Lync Server 2013, включив в них участие внешних пользователей в конференциях.</span><span class="sxs-lookup"><span data-stu-id="7974c-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="7974c-124">К внешним пользователям относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="7974c-124">External users can include:</span></span>

  - <span data-ttu-id="7974c-125">**Удаленные пользователи**   вашей организации, когда они работают за пределами брандмауэров и используют ноутбуки и другие устройства Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7974c-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="7974c-126">**Пользователи федеративных пользователей**   из компаний, которые также работают с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7974c-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="7974c-127">С этими компаниями создаются отношения федерации, что упрощает взаимодействие сотрудников организации с такими пользователями.</span><span class="sxs-lookup"><span data-stu-id="7974c-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="7974c-128">**Анонимные пользователи**   , которые приглашенные пользователям для присоединения к определенным конференциям, имеют доступ к другим внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="7974c-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="7974c-129">Организатор собрания в данной компании может отправить внешнему пользователю приглашение на конференцию по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="7974c-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="7974c-130">Сообщение электронной почты содержит ссылку, по которой внешний пользователь может присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="7974c-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="7974c-131">Чтобы включить любые из этих сценариев, вам нужно развернуть пограничный сервер, чтобы обеспечить безопасную связь между развертыванием Lync Server 2013 и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="7974c-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="7974c-132">Решение Lync Server 2013, использующее пограничные серверы, обеспечивает более высокое качество мультимедиа, чем другие решения, например виртуальная частная сеть (VPN).</span><span class="sxs-lookup"><span data-stu-id="7974c-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="7974c-133">Подробности можно найти [в разделе Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7974c-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="7974c-134">Кроме того, если вы развертываете пограничные серверы, вы можете предоставить пользователям (то есть внутренним или за пределами вашей организации) возможность звонить из обычных телефонов PSTN для присоединения к локальным звуковым конференциям.</span><span class="sxs-lookup"><span data-stu-id="7974c-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="7974c-135">Для этого нужно развернуть Конференц-связь с телефонным подключением Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7974c-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="7974c-136">Совместимость между типами собраний и клиентскими версиями</span><span class="sxs-lookup"><span data-stu-id="7974c-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="7974c-137">Если вы планируете использовать Lync Server 2013 для взаимодействия с предыдущими версиями Office Communications Server и его клиентами, необходимо учитывать перечисленные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="7974c-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="7974c-138">Пользователи, использующие Lync Server 2013, не могут планировать собрания в реальном времени или изменять перенесенные собрания этого типа.</span><span class="sxs-lookup"><span data-stu-id="7974c-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="7974c-139">Пользователи, использующие Lync Server 2013, которым нужно посетить конференции на собрания в Live, размещенные на серверах с установленным пакетом Office Communications Server 2007 R2, должны установить на своем компьютере клиент Live Meeting (в дополнение к Lync Server 2013) для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="7974c-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="7974c-140">Если на Lync Server 2013 будут перенесены конференции из Live Meeting, содержимое собрания не будет перенесено.</span><span class="sxs-lookup"><span data-stu-id="7974c-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="7974c-141">Если это содержимое нужно, его необходимо отправить еще раз.</span><span class="sxs-lookup"><span data-stu-id="7974c-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

