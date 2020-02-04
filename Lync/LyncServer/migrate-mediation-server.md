---
title: Миграция сервера обновлений
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
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="7a0b5-102">Миграция сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="7a0b5-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a0b5-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7a0b5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7a0b5-104">После запуска мастера слияния сервер, на котором работает ваш компьютер, будет объединен с пробной топологией Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="7a0b5-105">Однако настройка сервера обновлений Lync Server 2013 выполняется после миграции всех пользователей, так как пул Office Communications Server 2007 R2 не может взаимодействовать с сервером обновлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7a0b5-106">В ходе параллельной миграции сервер Lync Server 2013 взаимодействует с сервером Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="7a0b5-107">При настройке сервера исправлений Lync Server 2013 Вы также должны обновить или заменить шлюзы Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="7a0b5-108">Шлюзы Office Communications Server 2007 R2 не поддерживают сервер обновлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7a0b5-109">Необходимо развернуть шлюзы, сертифицированные для Lync Server 2013, и связать их с сервером обновлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7a0b5-110">Этот этап необходим для того, чтобы можно было полностью списать развертывание Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="7a0b5-111">В этом разделе описаны задачи настройки, которые необходимо выполнить после миграции сервера обновлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="7a0b5-112">Переход на размещенный сервер исправлений на отдельном сервере — это необязательная задача.</span><span class="sxs-lookup"><span data-stu-id="7a0b5-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="7a0b5-113">Настройка сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="7a0b5-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="7a0b5-114">Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a0b5-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="7a0b5-115">Переход размещенного сервера исправлений на отдельный сервер-посредник (необязательно)</span><span class="sxs-lookup"><span data-stu-id="7a0b5-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

