---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 953b422527e095a6fef1e34cbf8b8fde2d494f42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="7b4c9-102">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="7b4c9-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b4c9-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7b4c9-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7b4c9-104">Предыдущие версии Office Communications Server предоставили шлюз расширенных сообщений и протокол присутствия (КСМПП), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с помощью КСМППных развертываний.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="7b4c9-105">В Lync Server 2013 функциональность КСМПП может быть развернута как функция.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="7b4c9-106">Функции КСМПП устанавливаются в виде прокси-сервера КСМПП, который работает на пограничном сервере Lync Server 2013 и шлюз КСМПП, который работает на сервере переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="7b4c9-107">С точки зрения миграции учетная запись пользователя Office Communications Server 2007 R2 может быть перенесена в пул Lync Server 2013 и продолжать использовать шлюз Office Communications Server 2007 R2 КСМПП Gateway.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="7b4c9-108">Это возможно, только если для федеративного партнера КСМПП не настроена платформа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="7b4c9-109">Если вы развернули Office Communications Server с помощью шлюза Office Communications Server 2007 R2 КСМПП Gateway и КСМПП Federation для пользователей Office Communications Server 2007 R2, перенесите КСМПП Федерацию на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="7b4c9-110">Развертывание пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="7b4c9-111">Разверните сервер Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="7b4c9-112">Переместите всех пользователей в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="7b4c9-113">Создавайте политики доступа КСМПП и сертификаты для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="7b4c9-114">Включите Федерацию КСМПП в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="7b4c9-115">Обновите записи DNS, чтобы они указывали на сервер Lync Server 2013 КСМПП Gateway.</span><span class="sxs-lookup"><span data-stu-id="7b4c9-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

