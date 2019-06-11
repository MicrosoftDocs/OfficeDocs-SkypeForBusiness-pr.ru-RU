---
title: 'Lync Server 2013: настройка системных платформ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="e4c23-102">Настройка системных платформ в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4c23-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e4c23-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e4c23-104">Прежде чем приступать к развертыванию сервера сохраняемого чата, необходимо установить требуемую операционную систему на оборудовании, удовлетворяющем требованиям к системе для серверов.</span><span class="sxs-lookup"><span data-stu-id="e4c23-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="e4c23-105">Сведения о поддерживаемом оборудовании для серверов с Lync Server 2013, серверами баз данных и файловыми серверами можно найти в документации поддержка [Lync server 2013](lync-server-2013-supported-hardware.md) .</span><span class="sxs-lookup"><span data-stu-id="e4c23-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="e4c23-106">Подробнее о поддерживаемых операционных системах и программах для работы с базами данных можно найти в документации по поддержке [серверного программного обеспечения и поддержки инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) .</span><span class="sxs-lookup"><span data-stu-id="e4c23-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="e4c23-107">Подробные сведения о требованиях к обновлению для Windows можно найти в статьях [дополнительные серверные службы и требования в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e4c23-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e4c23-108">Сервер клиентского **персистентчатсервице**, на котором установлен сервер, может быть развернут на одном или нескольких отдельных компьютерах в пуле Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e4c23-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="e4c23-109">Они не могут быть выровнены на внешних серверах Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e4c23-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="e4c23-110">Сервер сохраняемого чата может развертываться загрузчиком так же, как и другие роли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4c23-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="e4c23-111">Веб **-службы сохраняемого или загружаемого файла**, а также **веб-службы сохраняемого чата для управления комнатой** — это веб-компоненты, развернутые на серверах переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4c23-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="e4c23-112">Один сервер-сервер для входа в чате может поддерживать 20 000 активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4c23-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="e4c23-113">Вы можете использовать серверный пул для постоянного чата с четырьмя активными интерфейсами, поддерживающими общее количество одновременных пользователей 80 000.</span><span class="sxs-lookup"><span data-stu-id="e4c23-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="e4c23-114">Сохраняемый сервер обратного чата, **персистентчатсторе**, сохраняет комнаты чата и категории.</span><span class="sxs-lookup"><span data-stu-id="e4c23-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="e4c23-115">Рекомендуем установить **персистентчатсторе** на выделенный сервер SQL Server в пуле выпуска Enterprise Edition; Несмотря на то что мы поддерживаем размещение сервера Lync Server 2013 на обратном стороне и **персистентчатсторе** на одном и том же экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4c23-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="e4c23-116">Если ваша организация требует поддержки соответствия требованиям, вы можете установить ее с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="e4c23-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="e4c23-117">Служба соответствия требованиям сервера, установленная на сервере постоянного чата, устанавливается на том же компьютере, что и сервер клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="e4c23-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="e4c23-118">Для обеспечения соответствия требованиям требуется отдельная база данных.</span><span class="sxs-lookup"><span data-stu-id="e4c23-118">A separate database is required for compliance.</span></span> <span data-ttu-id="e4c23-119">Подробные сведения о требованиях к соответствию требованиям для постоянного сервера чата приведены в разделе [планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e4c23-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="e4c23-120">Для каждой топологии требуется сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4c23-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="e4c23-121">В построителе топологии поддерживается несколько пулов серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e4c23-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="e4c23-122">Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и в случае с [развертыванием сервера Lync server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e4c23-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e4c23-123">Кроме того, вы можете развернуть сервер с помощью Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4c23-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="e4c23-124">В этом случае сервер переднего плана **персистентчатсервице** размещается на сервере Standard Edition, и вы можете развернуть сервер **персистентчатсторе** Back на локальном экземпляре SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="e4c23-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4c23-125">Для обеспечения высокой доступности не поддерживается постоянная версия сервера&nbsp;Chat Standard.</span><span class="sxs-lookup"><span data-stu-id="e4c23-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="e4c23-126">Производительность и масштаб будут ограничены.</span><span class="sxs-lookup"><span data-stu-id="e4c23-126">Performance and scale will be limited.</span></span> <span data-ttu-id="e4c23-127">Кроме того, мы поддерживаем только новые версии сервера&nbsp;Standard чата.</span><span class="sxs-lookup"><span data-stu-id="e4c23-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="e4c23-128">Корпорация Майкрософт не поддерживает обновление для Lync Server 2010, групповой чат с сервером в Lync Server 2013&nbsp;для сервера&nbsp;Standard Chat стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="e4c23-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4c23-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e4c23-129">See Also</span></span>


[<span data-ttu-id="e4c23-130">Поддержка дополнительных серверов и соответствующие требования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="e4c23-131">Поддерживаемое оборудование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="e4c23-132">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="e4c23-133">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="e4c23-134">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4c23-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

