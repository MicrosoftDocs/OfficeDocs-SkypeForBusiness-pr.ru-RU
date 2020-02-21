---
title: 'Lync Server 2013: отчеты об использовании системы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f7cdbcfb8a3a25063c53d4a082f2b29d5ae0d4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="dcc6f-102">Отчеты об использовании системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcc6f-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="dcc6f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="dcc6f-104">Отчеты об использовании системы предоставляют сведения об использовании системы на основе данных регистрации вызовов (CDR), собранных сервером Lync.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dcc6f-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="dcc6f-105">In This Section</span></span>

  - [<span data-ttu-id="dcc6f-106">Отчет о регистрации пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="dcc6f-107">Предоставляет сводку по подключению пользователей к развертыванию Lync Server 2013 на основе событий регистрации, таких как вход пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="dcc6f-108">В этом отчете представлен способ просмотра внутренних и внешних входов, а также сравнения числа пользователей, выполнивших вход в Lync Server 2013 с числом пользователей, которые реально использовали эту службу во время их входа в систему.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="dcc6f-109">Сводный отчет по одноранговым действиям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="dcc6f-p102">Содержит сводку по одноранговым мгновенным сообщениям, аудио- и видеовызовам, передаче файлов и сеансам совместного использования приложений. Одноранговые сеансы — это сеансы с участием всего двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="dcc6f-112">Сводный отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="dcc6f-113">Сводка по всем действиям, связанным с конференциями.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="dcc6f-114">Конференции — это сеансы с участием трех или более пользователей.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="dcc6f-115">Сводный отчет по конференциям PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="dcc6f-p104">Сводка по всем конференциям ТСОП. Это конференции, к которым хотя бы один пользователь подключается по телефонной сети общего пользования (ТСОП) (т.н. *конференц-связь с телефонным подключением*.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="dcc6f-118">Отчет об использовании группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="dcc6f-119">Общие сведения об использовании группы ответа.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="dcc6f-120">Приложение группы ответа позволяет автоматически маршрутизировать телефонные звонки для таких объектов, как служба технической поддержки или линия поддержки клиентов.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="dcc6f-121">Отчет по инвентаризации IP-телефонов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="dcc6f-122">Предоставляет сведения об IP-телефонах, используемых в Организации в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="dcc6f-123">Отчет основан на регистрации телефонных звонков и входе в систему.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="dcc6f-124">Он не должен считаться полным запасом.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="dcc6f-125">Например, вы могли удалить телефоны, которые все еще указаны в отчете, так как они входили в систему хотя бы один раз.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="dcc6f-126">Аналогично, у вас также могут быть новые телефоны, которые не отображаются в отчете просто потому, что пользователи еще не выполнили вход в Lync Server со своими новыми телефонами.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="dcc6f-127">Отчет по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcc6f-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="dcc6f-p107">Предоставляет список действий с одноранговыми сеансами и конференциями, которые используют контроль допуска звонков. Контроль допуска звонков (CAC) позволяет определить, следует ли разрешить сеансы общения в реальном времени, например голосовые или видеовызовы, на основе ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dcc6f-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

