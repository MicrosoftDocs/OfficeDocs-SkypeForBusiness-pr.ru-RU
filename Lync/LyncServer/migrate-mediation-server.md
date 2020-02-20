---
title: Перенос сервера-посредника
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7786ecfd72ac32de74c9947f0effa1fad0c9603
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="88e5c-102">Перенос сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="88e5c-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e5c-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="88e5c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="88e5c-104">При запуске мастера слияния сервер-посредник объединяется с пробной топологией Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e5c-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="88e5c-105">Однако сервер-посредник Lync Server 2013 настраивается после миграции всех пользователей, так как пул Office Communications Server 2007 R2 не может подключиться к серверу-посреднику Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e5c-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="88e5c-106">Во время параллельной миграции пул Lync Server 2013 обменивается данными с сервером-посредником Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="88e5c-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="88e5c-107">При настройке сервера-посредника Lync Server 2013 Вы также должны обновить или заменить шлюзы Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="88e5c-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="88e5c-108">Шлюзы Office Communications Server 2007 R2 не поддерживают сервер-посредник по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e5c-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="88e5c-109">Вам необходимо развернуть шлюзы, сертифицированные для Lync Server 2013, и связать их с сервером-посредником Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e5c-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="88e5c-110">Этот шаг необходимо выполнить, прежде чем вы сможете полностью списать развертывание Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="88e5c-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="88e5c-111">В подразделах этого раздела описываются задачи настройки, которые необходимо выполнить после миграции сервера-посредника Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e5c-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="88e5c-112">Переход с совместно размещенного сервера-посредника на отдельный сервер-посредник является необязательным.</span><span class="sxs-lookup"><span data-stu-id="88e5c-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="88e5c-113">Настройка сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="88e5c-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="88e5c-114">Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88e5c-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="88e5c-115">Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)</span><span class="sxs-lookup"><span data-stu-id="88e5c-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

