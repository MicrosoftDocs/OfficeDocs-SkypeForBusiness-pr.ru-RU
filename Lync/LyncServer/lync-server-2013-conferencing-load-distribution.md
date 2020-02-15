---
title: Распределение загрузки для конференц-связи Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dad04b445421e27e68cf49900d4bb925918bd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="8b67a-102">Распределение нагрузки конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b67a-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b67a-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8b67a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8b67a-104">В отличие от некоторых других выделенных решений для конференц-связи, архитектура Lync Server — это модель общего оборудования.</span><span class="sxs-lookup"><span data-stu-id="8b67a-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="8b67a-105">Это означает, что одно и то же оборудование совместно используется многими компонентами программного обеспечения, каждая из которых поддерживает различные возможности связи в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="8b67a-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="8b67a-106">Каждый тип загрузок связи в режиме реального времени зависит от сервера.</span><span class="sxs-lookup"><span data-stu-id="8b67a-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="8b67a-107">Например, сервер переднего плана может запускать компоненты маршрутизации SIP, веб-приложения (например, поиск в адресной книге), службу веб-конференций, службу аудио-и видеоконференций, корпоративные голосовые приложения (например, приложение для конференц-связи и приложение группы ответа) и сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="8b67a-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="8b67a-108">Набор баз данных на сервере переднего плана также обеспечивает хранение и обработку для пользователей, контактов, сведений о присутствии, конференций и данных маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8b67a-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="8b67a-109">Благодаря этому совместному использованию оборудования компоненты, службы и процессы конкурируют за ресурсы ЦП и памяти, поэтому рабочие нагрузки, не связанные с конференц-связью, напрямую влияют на масштабирование сервера.</span><span class="sxs-lookup"><span data-stu-id="8b67a-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="8b67a-110">По сравнению с другими решениями для конференц-связи на основе аппаратного порта, архитектура конференц-связи Lync Server — это модель без резервирования.</span><span class="sxs-lookup"><span data-stu-id="8b67a-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="8b67a-111">Когда пользователь планирует собрание, Lync Server создает запись в базе данных конференций, в которой хранятся данные конференц-связи, но не резервирует аппаратные ресурсы для запланированного собрания заранее.</span><span class="sxs-lookup"><span data-stu-id="8b67a-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="8b67a-112">Вместо этого Lync Server имеет встроенную логику балансировки нагрузки для динамического выделения ресурсов конференц-связи на серверах переднего плана таким образом, что они равномерно распределяются между всеми серверами переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="8b67a-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="8b67a-113">Это эффективно обеспечивает и использует аппаратные ресурсы, но делает его несложным для поддержки очень больших собраний (особенно без надлежащего планирования).</span><span class="sxs-lookup"><span data-stu-id="8b67a-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="8b67a-114">Например, если пул Lync Server 2013 работает ближе к своей максимальной емкости, каждый сервер переднего плана может размещаться около 125 среднего числа собраний.</span><span class="sxs-lookup"><span data-stu-id="8b67a-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="8b67a-115">Добавление еще одного небольшого собрания не является проблемой, но при добавлении собрания для 1000 пользователей возникает проблема, так как сервер переднего плана может не поддерживать такое большое собрание одновременно с другими 125ми собрания.</span><span class="sxs-lookup"><span data-stu-id="8b67a-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

