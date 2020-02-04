---
title: Запрещение новых подключений к серверу Lync Server для обслуживания сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="d982f-102">Запрещение новых подключений к Lync Server 2013 для обслуживания сервера</span><span class="sxs-lookup"><span data-stu-id="d982f-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d982f-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d982f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d982f-104">Lync Server позволяет перевести сервер в автономный режим (например, для применения обновлений программного обеспечения или оборудования) без потери обслуживания пользователей.</span><span class="sxs-lookup"><span data-stu-id="d982f-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="d982f-105">Если вы укажете параметр для предотвращения новых подключений и звонков на сервер в пуле, он перестанет выполнять новые подключения и вызовы, как только вы реализуете этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d982f-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="d982f-106">Эти новые подключения и звонки перенаправляются через другие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="d982f-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="d982f-107">Сервер, который препятствует новым подключениям, допускает продолжение сеансов в существующих соединениях, пока не завершится.</span><span class="sxs-lookup"><span data-stu-id="d982f-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="d982f-108">После того как все существующие сеансы будут завершены, сервер будет готов к переходу в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="d982f-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="d982f-109">Если вы не можете помешать новым подключениям к серверу переднего плана, некоторые возможности и службы Lync Server используют балансировку нагрузки DNS для обеспечения правильной работы.</span><span class="sxs-lookup"><span data-stu-id="d982f-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="d982f-110">Если вы не используете в пуле функцию балансировки нагрузки DNS, то при подключении через эти службы может не перенаправляться к другим серверам в течение периода, в течение которого сервер препятствует новым подключениям, и, следовательно, когда сервер переводится в автономный режим некоторые сеансы и звонки могут быть рвал.</span><span class="sxs-lookup"><span data-stu-id="d982f-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="d982f-111">Возможности, которые используют балансировку нагрузки DNS для обеспечения правильного функционирования этого параметра, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="d982f-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="d982f-112">Attendant</span><span class="sxs-lookup"><span data-stu-id="d982f-112">Attendant</span></span>

  - <span data-ttu-id="d982f-113">оповещений для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d982f-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="d982f-114">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="d982f-114">Response Group application</span></span>

  - <span data-ttu-id="d982f-115">"Объявление"</span><span class="sxs-lookup"><span data-stu-id="d982f-115">Announcement application</span></span>

  - <span data-ttu-id="d982f-116">приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="d982f-116">Call Park application</span></span>

<span data-ttu-id="d982f-117">Подробные сведения о балансировке нагрузки DNS можно найти [в разделе Балансировка нагрузки DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="d982f-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="d982f-118">В дополнение к предотвращению новых подключений для всех служб на сервере Lync Server вы также можете запретить новые подключения для отдельных служб Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d982f-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="d982f-119">Например, этот метод полезен в ситуации, когда необходимо применить обновление для Lync Server, не требующее завершения работы всего сервера.</span><span class="sxs-lookup"><span data-stu-id="d982f-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="d982f-120">Обратите внимание, что при предотвращении подключений для одной службы необходимо выбрать службу, которая будет сгруппирована и отображена в списке служб Windows.</span><span class="sxs-lookup"><span data-stu-id="d982f-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="d982f-121">Например, клиентская служба Lync Server и агент сбора данных для мониторинга являются отдельными службами Lync Server, но в списке служб Windows они консолидируются и отображаются как служба переднего плана Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d982f-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="d982f-122">Вы можете запретить новые соединения для службы переднего плана Lync Server, но вы не сможете помешать новым подключениям для этих двух отдельных служб Lync Server отдельно.</span><span class="sxs-lookup"><span data-stu-id="d982f-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d982f-123">Если вы настроили сервер для предотвращения новых подключений, а затем перезагрузите сервер, по умолчанию будет сразу же приступить к приему новых подключений после его запуска.</span><span class="sxs-lookup"><span data-stu-id="d982f-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="d982f-124">Чтобы не допустить этого, настройте сервер на приостановку и возобновление вручную, прежде чем перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="d982f-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="d982f-125">Чтобы запретить создание подключений к серверу Lync Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d982f-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="d982f-126">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="d982f-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="d982f-127">Откройте консоль оснастки "службы": нажмите кнопку **Пуск**, наведите указатель на пункт **все программы**, выберите пункт **Администрирование**, а затем — пункт **службы**.</span><span class="sxs-lookup"><span data-stu-id="d982f-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="d982f-128">В списке дважды щелкните службу Windows сервера Lync Server, для которой вы хотите запретить новые подключения.</span><span class="sxs-lookup"><span data-stu-id="d982f-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="d982f-129">В диалоговом окне Свойства в разделе **состояние службы: запущено**выберите команду **приостановить**.</span><span class="sxs-lookup"><span data-stu-id="d982f-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="d982f-130">(Необязательно), но рекомендуется, рядом с полем **Тип запуска**выберите пункт **вручную**.</span><span class="sxs-lookup"><span data-stu-id="d982f-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d982f-131">Если вы настроили сервер для предотвращения новых подключений, а затем перезагрузите сервер, по умолчанию будет сразу же приступить к приему новых подключений после его запуска.</span><span class="sxs-lookup"><span data-stu-id="d982f-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="d982f-132">Чтобы не допустить этого, настройте сервер на приостановку и возобновление вручную, прежде чем перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="d982f-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="d982f-133">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d982f-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

