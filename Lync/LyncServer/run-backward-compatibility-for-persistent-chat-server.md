---
title: Организация обратной совместимости для сервера сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d7054e9dfb3eba8e6365710accfd3a9693bc39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="72f4f-102">Организация обратной совместимости для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="72f4f-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72f4f-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="72f4f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="72f4f-104">Сервер Lync Server 2013, постоянная конечная точка сервера чата предоставляет способ создания простого URL-адреса, указывающего на пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="72f4f-105">Это полезно для устаревших клиентов (Microsoft Office Communications Server 2007 R2 Group Chat Server или Lync Server 2010, групповой чат), так как пользователи могут вводить простой URL-адрес в ручном режиме при попытке указать старый клиент на компьютер с Lync 2013. Сохраняемый чат.</span><span class="sxs-lookup"><span data-stu-id="72f4f-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="72f4f-106">Эта конечная точка не используется сохраняемым чат и требуется только для устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="72f4f-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="72f4f-107">Это полезно для временного периода, в котором может быть перенесены помещения, но клиенты Lync 2013 не развернуты во всей Организации.</span><span class="sxs-lookup"><span data-stu-id="72f4f-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="72f4f-108">Пользователи, работающие в Lync 2010 Group Chat (клиент), смогут по-прежнему подключаться к серверу сохраняемого сервера обратного чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="72f4f-109">Вам не нужно создавать несколько конечных точек сервера для сеансов чата. для каждого пула серверов "сохраняемый чат" требуется только один из них.</span><span class="sxs-lookup"><span data-stu-id="72f4f-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="72f4f-110">Администраторы могут создать несколько конечных точек (для одного пула), но старые клиенты можно настроить так, чтобы они могли подключаться только к одному пулу за один раз.</span><span class="sxs-lookup"><span data-stu-id="72f4f-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="72f4f-111">В стандартном или обычном варианте развертывание устарело только для одного пула.</span><span class="sxs-lookup"><span data-stu-id="72f4f-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="72f4f-112">Новое развертывание обычно переносит этот пул на новый сервер Lync Server 2013 и может добавить новые дополнительные пулы серверов для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="72f4f-113">Этот наиболее распространенный сценарий, как правило, следует за следующим шаблоном:</span><span class="sxs-lookup"><span data-stu-id="72f4f-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="72f4f-114">Администрирование пользователей с помощью одного из Lync Server 2010, пула групп чата и клиентов группового чата Lync 2010 подключается к этому пулу с помощью известного пользователя (SIP: ocschat@\<ИмяДомена\>. com или аналогичного).</span><span class="sxs-lookup"><span data-stu-id="72f4f-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="72f4f-115">Пользователи входят в доменные службы Active Directory с поддержкой SIP, а служба поиска регистрирует их для получения входящих запросов.</span><span class="sxs-lookup"><span data-stu-id="72f4f-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="72f4f-116">Затем вы установите сервер для Lync Server 2013 и пул серверов для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="72f4f-117">Когда пользователи обычно не в сети (например, выходные), выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="72f4f-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="72f4f-118">Отключите Lync Server 2010, групповой чат.</span><span class="sxs-lookup"><span data-stu-id="72f4f-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="72f4f-119">Перенесите данные из пула Lync Server 2010, группового чата в пул серверов для сервера Lync Server 2013 (сохраняемый чат).</span><span class="sxs-lookup"><span data-stu-id="72f4f-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="72f4f-120">Удалите известного пользователя из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72f4f-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="72f4f-121">Создайте новую *конечную точку* с тем же URI SIP, что и у ранее известного пользователя.</span><span class="sxs-lookup"><span data-stu-id="72f4f-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="72f4f-122">Запустите сервер Lync Server 2013, сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="72f4f-123">Войдите в систему с помощью Lync 2010 Group Chat (клиент) и подключитесь к своим данным, не изменяя конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="72f4f-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="72f4f-124">Позже вы можете списать Lync Server 2010, групповой чат.</span><span class="sxs-lookup"><span data-stu-id="72f4f-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="72f4f-125">Затем вы можете развернуть Lync Server 2013, сохраняемый сервер чата и установить новый серверный пул для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72f4f-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="72f4f-126">Сведения о переходе с Lync Server 2010, групповой чат на Lync Server 2013 и сохраняемый сервер чатов можно найти в разделе [Миграция с Lync server 2010, группового чата или Office Communications Server 2007 R2 Group Chat на Lync server 2013 и сохраняемый сервер чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="72f4f-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="72f4f-127">Для выполнения обратной совместимости (чтобы создать конечную точку сервера чатов, указывающую на пул сервера сохраняемого чата, который может использоваться клиентами группового чата старого пула):</span><span class="sxs-lookup"><span data-stu-id="72f4f-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="72f4f-128">Затем настройте в клиентах сохраняемого чата использование адреса SIP в качестве объекта контакта.</span><span class="sxs-lookup"><span data-stu-id="72f4f-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="72f4f-129">Адрес SIP создается с помощью командлета **New-ксперсистентчатендпоинт** для определенного пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="72f4f-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="72f4f-130">Чтобы добавить конечную точку сервера для работы с сохраняемым чат с помощью интерфейса командной строки Windows PowerShell, рассматривайте пример ниже.</span><span class="sxs-lookup"><span data-stu-id="72f4f-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="72f4f-131">В этом случае вы настраиваете объект Contact именем "персистентчат" в топологии "contoso.com", где полное доменное имя (FQDN) пула имеет значение "pcpool.contoso.com":</span><span class="sxs-lookup"><span data-stu-id="72f4f-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="72f4f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="72f4f-132">See Also</span></span>


[<span data-ttu-id="72f4f-133">Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72f4f-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

