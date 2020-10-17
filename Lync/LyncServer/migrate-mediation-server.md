---
title: Перенос сервера-посредника
description: Перенос сервера-посредника.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570335"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="be7be-103">Перенос сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="be7be-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be7be-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="be7be-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="be7be-105">При запуске мастера слияния сервер-посредник объединяется с пробной топологией Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7be-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="be7be-106">Однако сервер-посредник Lync Server 2013 настраивается после миграции всех пользователей, так как пул Office Communications Server 2007 R2 не может подключиться к серверу-посреднику Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7be-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="be7be-107">Во время параллельной миграции пул Lync Server 2013 обменивается данными с сервером-посредником Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="be7be-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="be7be-108">При настройке сервера-посредника Lync Server 2013 Вы также должны обновить или заменить шлюзы Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="be7be-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="be7be-109">Шлюзы Office Communications Server 2007 R2 не поддерживают сервер-посредник по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7be-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="be7be-110">Вам необходимо развернуть шлюзы, сертифицированные для Lync Server 2013, и связать их с сервером-посредником Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7be-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="be7be-111">Этот шаг необходимо выполнить, прежде чем вы сможете полностью списать развертывание Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="be7be-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="be7be-112">В подразделах этого раздела описываются задачи настройки, которые необходимо выполнить после миграции сервера-посредника Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7be-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="be7be-113">Переход с совместно размещенного сервера-посредника на отдельный сервер-посредник является необязательным.</span><span class="sxs-lookup"><span data-stu-id="be7be-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="be7be-114">Настройка сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="be7be-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="be7be-115">Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7be-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="be7be-116">Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)</span><span class="sxs-lookup"><span data-stu-id="be7be-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

