---
title: 'Lync Server 2013: Планирование доступа внешних пользователей'
description: 'Lync Server 2013: Планирование доступа внешних пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562785"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="89b09-103">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-103">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89b09-104">_**Последнее изменение темы:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="89b09-104">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="89b09-p101">Коммуникации в большинстве организаций включают службы и пользователей, которые находятся за пределами внутренней сети. Эти службы и пользователи могут быть представлены сотрудниками, временно или постоянно работающими вне офиса, сотрудниками организаций клиентов или партнеров, лицами, использующими общедоступные службы мгновенных сообщений, а также потенциальными клиентами, партнерами и анонимными пользователями, которые были приглашены принять участие в собраниях и презентациях. В данной документации все эти лица называются *внешними пользователями*.</span><span class="sxs-lookup"><span data-stu-id="89b09-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="89b09-108">С помощью Microsoft Lync Server 2013 пользователи в организации могут использовать обмен мгновенными сообщениями и сведения о присутствии для связи с внешними пользователями, а также могут участвовать в конференциях аудио-и видеосвязи и конференц-связи с внешними сотрудниками и другими типами внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="89b09-108">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="89b09-109">Кроме того, можно поддерживать внешний доступ с мобильных устройств и с помощью корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="89b09-109">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="89b09-110">Внешние пользователи, которые не входят в вашу организацию, могут участвовать в собраниях Lync Server 2013, разрешая анонимным участникам.</span><span class="sxs-lookup"><span data-stu-id="89b09-110">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="89b09-111">Для поддержки обмена данными между брандмауэром организации необходимо развернуть пограничный сервер Lync Server 2013 в сети периметра (также известной как DMZ, демилитаризованная зона и экранированная подсеть).</span><span class="sxs-lookup"><span data-stu-id="89b09-111">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="89b09-112">Пограничный сервер управляет тем, как пользователи, не входящие в брандмауэр, могут подключаться к внутреннему развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89b09-112">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="89b09-113">Он также управляет взаимодействием с внешними пользователями, инициированным в границах брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="89b09-113">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="89b09-114">В зависимости от ваших потребностей, можно разворачивать один или несколько пограничных серверов в одном или нескольких расположениях.</span><span class="sxs-lookup"><span data-stu-id="89b09-114">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="89b09-115">В этом разделе описываются сценарии доступа внешних пользователей в Lync Server 2013, а также описано, как спланировать пограничный и обратную топологию прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="89b09-115">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89b09-116">Несмотря на то, что для поддержки доступа к корпоративной голосовой связи и внешним пользователям необходим пограничный сервер, этот раздел посвящен поддержке мгновенных сообщений, присутствия, аудио-и видеоконференций, Федерации, веб-конференций и Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="89b09-116">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="89b09-117">Подробные сведения о поддержке корпоративной голосовой связи можно найти <A href="lync-server-2013-planning-for-enterprise-voice.md">в статье Планирование корпоративной голосовой связи в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="89b09-117">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89b09-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="89b09-118">In This Section</span></span>

  - [<span data-ttu-id="89b09-119">Изменения в Lync Server 2013, затрагивающие планирование пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="89b09-119">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="89b09-120">Требования к системе для компонентов доступа внешних пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-120">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="89b09-121">Обзор доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-121">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="89b09-122">Общие сведения о службе автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-122">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="89b09-123">Выбор топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-123">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="89b09-124">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-124">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="89b09-125">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="89b09-126">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-126">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="89b09-127">Планирование сертификатов пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-127">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="89b09-128">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89b09-128">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

