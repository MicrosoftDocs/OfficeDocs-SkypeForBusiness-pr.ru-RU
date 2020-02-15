---
title: Запрет новых подключений к Lync Server для обслуживания сервера
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
ms.openlocfilehash: d3678414e45e556eb7092b923fab4b737bfd4842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="49e8b-102">Предотвращение новых подключений к Lync Server 2013 для обслуживания серверов</span><span class="sxs-lookup"><span data-stu-id="49e8b-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e8b-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="49e8b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="49e8b-104">Lync Server позволяет перевести сервер в автономный режим (например, для применения обновлений программного обеспечения или оборудования) без потери обслуживания пользователей.</span><span class="sxs-lookup"><span data-stu-id="49e8b-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="49e8b-p101">Как только вы выбираете параметр, блокирующий новые подключения или вызовы к серверу в пуле, сервер перестает принимать новые подключения и вызовы. Эти новые подключения и вызовы маршрутизируются через другие серверы в пуле. На сервере, блокирующем новые подключения, существующие сеансы могут продолжать выполняться. Когда все существующие сеансы будут завершены, сервер можно отключить.</span><span class="sxs-lookup"><span data-stu-id="49e8b-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="49e8b-109">При запрещении новых подключений к внешнему серверу некоторые функции и службы Lync Server используют балансировку нагрузки на DNS, чтобы убедиться, что она работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="49e8b-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="49e8b-110">Если в пуле не используется балансировка нагрузки на DNS, то подключения через эти службы могут не перенаправляться на другие серверы в течение периода, в течение которого сервер препятствует новым подключениям, и таким образом при переводе в автономный режим некоторые сеансы и вызовы могут быть прерывания.</span><span class="sxs-lookup"><span data-stu-id="49e8b-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="49e8b-111">Функции балансировки нагрузки на DNS, обеспечивающие работоспособность этого параметра, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="49e8b-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="49e8b-112">Автосекретаря</span><span class="sxs-lookup"><span data-stu-id="49e8b-112">Attendant</span></span>

  - <span data-ttu-id="49e8b-113">приложение "Объявления для конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="49e8b-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="49e8b-114">приложение группы ответа;</span><span class="sxs-lookup"><span data-stu-id="49e8b-114">Response Group application</span></span>

  - <span data-ttu-id="49e8b-115">Приложение " Оповещение"</span><span class="sxs-lookup"><span data-stu-id="49e8b-115">Announcement application</span></span>

  - <span data-ttu-id="49e8b-116">Приложение "Парковка вызовов"</span><span class="sxs-lookup"><span data-stu-id="49e8b-116">Call Park application</span></span>

<span data-ttu-id="49e8b-117">Для получения дополнительных сведений о балансировке нагрузки на DNS обратитесь к разделу [Балансировка нагрузки на DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="49e8b-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="49e8b-118">В дополнение к предотвращению новых подключений для всех служб на сервере Lync Server вы также можете запретить новые подключения для отдельных служб Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49e8b-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="49e8b-119">Например, этот метод полезен в тех случаях, когда необходимо применить обновление Lync Server, не требующее завершения работы всего сервера.</span><span class="sxs-lookup"><span data-stu-id="49e8b-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="49e8b-120">Обратите внимание на то, что при блокировании подключений для службы ее необходимо выбирать с учетом того, как она сгруппирована и отображается в списке служб Windows.</span><span class="sxs-lookup"><span data-stu-id="49e8b-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="49e8b-121">Например, служба переднего плана Lync Server и агент сбора данных для мониторинга являются отдельными службами Lync Server, но в списке служб Windows они консолидируются и отображаются как служба внешнего интерфейса Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49e8b-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="49e8b-122">Вы можете запретить новые подключения для службы внешнего интерфейса Lync Server, но не можете помешать новым подключениям для этих двух отдельных базовых служб Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49e8b-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="49e8b-p104">Если вы запретили новые подключения к серверу и затем перезагрузили его, после запуска по умолчанию сервер начнет принимать новые подключения. Во избежание этого перед перезапуском сервера настройте на нем приостановку и возобновление работы только в ручном режиме.</span><span class="sxs-lookup"><span data-stu-id="49e8b-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="49e8b-125">Чтобы запретить новые подключения к Lync Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="49e8b-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="49e8b-126">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="49e8b-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="49e8b-127">Откройте консоль оснастки "службы": нажмите кнопку **Пуск**, а затем последовательно выберите пункты **все программы**, **Администрирование**и **службы**.</span><span class="sxs-lookup"><span data-stu-id="49e8b-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="49e8b-128">В списке дважды щелкните службу Windows Lync Server, к которой вы хотите запретить новые подключения.</span><span class="sxs-lookup"><span data-stu-id="49e8b-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="49e8b-129">В диалоговом окне "Свойства" в поле **Состояние службы: запущена** щелкните **Приостановить**.</span><span class="sxs-lookup"><span data-stu-id="49e8b-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="49e8b-130">В столбце **Тип запуска** рекомендуется (но не обязательно) выбрать пункт **Вручную**.</span><span class="sxs-lookup"><span data-stu-id="49e8b-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="49e8b-p105">Если вы запретили новые подключения к серверу и затем перезагрузили его, после запуска по умолчанию сервер начнет принимать новые подключения. Во избежание этого перед перезапуском сервера настройте на нем приостановку и возобновление работы только в ручном режиме.</span><span class="sxs-lookup"><span data-stu-id="49e8b-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="49e8b-133">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49e8b-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

