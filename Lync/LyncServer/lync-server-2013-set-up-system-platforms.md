---
title: 'Lync Server 2013: Настройка системных платформ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59aafcda7cbe94401cdbd77479eecf38e3e9e351
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="f2ef1-102">Настройка системных платформ в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2ef1-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2ef1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f2ef1-104">Перед началом развертывания сервера сохраняемого чата необходимо установить требуемую операционную систему на оборудовании, удовлетворяющем требованиям к системе на серверах:</span><span class="sxs-lookup"><span data-stu-id="f2ef1-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="f2ef1-105">Сведения о поддерживаемом оборудовании для серверов, на которых работает Lync Server 2013, серверы баз данных и файловые серверы, приведены в статье Supported [Hardware for Lync server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="f2ef1-106">Сведения о поддерживаемых операционных системах и программном обеспечении можно найти в статье поддержка [серверного программного обеспечения и инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="f2ef1-107">Дополнительные сведения о требованиях по обновлению Windows приведены в статье дополнительные сведения о [поддержке серверов и требованиях в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f2ef1-108">Сервер переднего плана сервера сохраняемого чата, **PersistentChatService**, можно развернуть на одном или нескольких изолированных компьютерах в пуле Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="f2ef1-109">Они не могут быть размещены на серверах переднего плана Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="f2ef1-110">Сервер сохраняемого чата может быть развернут загрузчиком так же, как и другие роли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="f2ef1-111">Веб-службы **сохраняемого чата для отправки и загрузки файлов**, а также **веб-службы сохраняемого чата для управления комнатами чата** — это веб-компоненты, развернутые на серверах переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="f2ef1-112">Один сервер переднего плана сервера сохраняемого чата может поддерживать 20 000 активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="f2ef1-113">Пул серверов сохраняемого чата может иметь до 4 активных интерфейсов, поддерживающих всего 80 000 одновременно работающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="f2ef1-114">Внутренний сервер сохраняемого чата, **PersistentChatStore**, хранит комнаты и категории чата.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="f2ef1-115">Рекомендуется установить **PersistentChatStore** на выделенном внутреннем сервере SQL Server в пуле Enterprise Edition; Несмотря на то, что мы поддерживаем совместное размещение внешних серверов Lync Server 2013 и **PersistentChatStore** в одном экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="f2ef1-116">Если вашей организации требуется поддержка соответствия требованиям, ее можно установить с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="f2ef1-117">Служба соответствия сервера сохраняемого чата установлена на том же компьютере, что и сервер переднего плана сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f2ef1-118">Для совместимости требуется отдельная база данных.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-118">A separate database is required for compliance.</span></span> <span data-ttu-id="f2ef1-119">Сведения о требованиях соответствия требованиям для сервера сохраняемого чата приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="f2ef1-120">Для каждой топологии требуется как минимум сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="f2ef1-121">Построитель топологий поддерживает несколько пулов серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="f2ef1-122">Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и для любого пула развертывания [Lync server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f2ef1-123">Вы также можете развернуть сервер сохраняемого чата в Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="f2ef1-124">В этом случае сервер переднего плана **PersistentChatService** размещается на сервере Standard Edition, и вы можете развернуть внутренний сервер **PersistentChatStore** на локальном экземпляре SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2ef1-125">Мы не поддерживаем выпуск сервера&nbsp;сохраняемого чата Standard Edition для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="f2ef1-126">Производительность и масштабирование будут ограничены.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-126">Performance and scale will be limited.</span></span> <span data-ttu-id="f2ef1-127">Кроме того, поддерживаются только новые развертывания сервера&nbsp;Standard Edition для сервера persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="f2ef1-128">Мы не поддерживаем обновление Lync Server 2010, сервер группового чата до версии сервера&nbsp;&nbsp;сохраняемого чата для сервера Standard chat для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2ef1-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2ef1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ef1-129">See Also</span></span>


[<span data-ttu-id="f2ef1-130">Дополнительная поддержка и требования к серверу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="f2ef1-131">Поддерживаемое оборудование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="f2ef1-132">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="f2ef1-133">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="f2ef1-134">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2ef1-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

