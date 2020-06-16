---
title: Выполнение обратной совместимости для сервера сохраняемого чата
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5308d39e4edcfeddf494aa364f6b7ed43b9822dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="3491b-102">Выполнение обратной совместимости для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="3491b-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3491b-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3491b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3491b-104">Сервер Lync Server 2013, конечная точка сервера сохраняемого чата позволяет создать простой URL-адрес, указывающий на пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3491b-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="3491b-105">Это полезно для устаревших клиентов (Microsoft Office Communications Server 2007 R2 Group Chat Server или Lync Server 2010, группового чата), так как пользователи могут вводить простой URL-адрес в ручной настройке при попытке установить устаревший клиент на компьютер, работающий под управлением Lync 2013, сохраняемый чат.</span><span class="sxs-lookup"><span data-stu-id="3491b-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="3491b-106">Эта конечная точка не используется сохраняемым чат и является обязательной только для устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="3491b-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="3491b-107">Это полезно для временного периода, в течение которого могут переноситься комнаты, но клиенты Lync 2013 не развернуты во всей Организации.</span><span class="sxs-lookup"><span data-stu-id="3491b-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="3491b-108">Пользователи, работающие с Lync 2010 Group Chat (клиент), по-прежнему могут подключаться к внутреннему серверу сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3491b-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="3491b-109">Вам не нужно создавать несколько конечных точек сервера сохраняемого чата; для каждого пула серверов сохраняемого чата требуется только один из них.</span><span class="sxs-lookup"><span data-stu-id="3491b-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="3491b-110">Администраторы могут создавать несколько конечных точек (по одной на пул), но устаревшие клиенты могут быть настроены для подключения только к одному пулу в каждый момент времени.</span><span class="sxs-lookup"><span data-stu-id="3491b-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="3491b-111">В обычном или основном сценарии устаревшее развертывание представляет собой только один пул.</span><span class="sxs-lookup"><span data-stu-id="3491b-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="3491b-112">Новое развертывание обычно переносит этот пул на новый Lync Server 2013 и может добавить некоторые новые дополнительные пулы серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3491b-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="3491b-113">Этот основной сценарий обычно придерживается следующего шаблона.</span><span class="sxs-lookup"><span data-stu-id="3491b-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="3491b-114">Администрирование пользователей с помощью одного пула Lync Server 2010, пула групп чата и клиентов Lync 2010 Group Chat подключается к этому пулу с помощью определенного известного пользователя (SIP по умолчанию: ocschat@ \<domainName\> . com или аналогичный).</span><span class="sxs-lookup"><span data-stu-id="3491b-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="3491b-115">Пользователи входят в доменные службы Active Directory с поддержкой SIP, а служба поиска регистрирует их для получения входящих запросов.</span><span class="sxs-lookup"><span data-stu-id="3491b-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="3491b-116">Затем необходимо установить сервер сохраняемого чата Lync Server 2013 и пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3491b-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="3491b-117">В течение того времени, когда пользователи в сети отсутствуют (например, в выходные дни), выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3491b-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="3491b-118">Выключите Lync Server 2010, сгруппируйте чат.</span><span class="sxs-lookup"><span data-stu-id="3491b-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="3491b-119">Перенос данных из пула Lync Server 2010, группового чата в пул серверов сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3491b-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="3491b-120">Удаление известного пользователя из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3491b-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="3491b-121">Создается новая *конечная точка устаревшего развертывания* с тем же самым SIP URI, что и у ранее удаленного широко известного пользователя.</span><span class="sxs-lookup"><span data-stu-id="3491b-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="3491b-122">Запустите серверы сервера сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3491b-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="3491b-123">Пользователи входят в систему с помощью Lync 2010 Group Chat (клиент) и подключаются к их данным без необходимости изменять конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3491b-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="3491b-124">Позже вы можете списать Lync Server 2010 и групповой чат.</span><span class="sxs-lookup"><span data-stu-id="3491b-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="3491b-125">Затем вы можете развернуть Lync Server 2013, сервер сохраняемого чата и установить новые пулы серверов сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3491b-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="3491b-126">Для получения дополнительных сведений о переносе с Lync Server 2010, групповой чат на Lync Server 2013, сервер сохраняемого чата, ознакомьтесь со статьей [Миграция с Lync server 2010, группового чата или Office Communications Server 2007 R2 на Lync server 2013 и сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3491b-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="3491b-127">Для запуска обратной совместимости (для создания конечной точки сервера сохраняемого чата, указывающей на пул серверов сохраняемого чата, который может использоваться клиентами пула группового чата прежних версий):</span><span class="sxs-lookup"><span data-stu-id="3491b-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="3491b-128">Затем настройте клиенты сохраняемого чата, чтобы использовать этот SIP адрес в качестве объекта контакта.</span><span class="sxs-lookup"><span data-stu-id="3491b-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="3491b-129">SIP-адрес создается с помощью командлета **New-CsPersistentChatEndpoint** для определенного пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3491b-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="3491b-130">Чтобы добавить конечную точку сервера сохраняемого чата с помощью интерфейса командной строки Windows PowerShell, рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="3491b-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="3491b-131">В этом случае настраивается контактный объект с именем "persistentchat" в топологии contoso.com", где полное доменное имя пула — "pcpool.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="3491b-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="3491b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3491b-132">See Also</span></span>


[<span data-ttu-id="3491b-133">Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3491b-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

